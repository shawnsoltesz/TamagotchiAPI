# TamagotchiAPI

P

We are creating a CRUD Application that is powered by a Postgres database and Entity framework, and accessed through an API and Insomnia. The application will contain multiple models with foreign keys for joining. The application will be set up to function per the provided requirements through an API with the endpoints outlined in the Examples.

**E**

GET /pets should return all pets in your database.
GET /pets/{id} should return the pet with the corresponding id.
POST /pets should create a new pet. The controller should ensure the following: Birthday defaults to the current DateTime, HungerLevel defaults to 0 and HappinessLevel defaults to 0.
DELETE /pets/{id}, should delete a pet from the database by Id
POST /pets/{id}/playtimes should find the pet by id and add five to its happiness level and add three to its hunger level. It should also create a new Playtime for this pet and the current time.
POST /pets/{id}/feedings should find the pet by id and subtract five from its hungry level and add three to its happiness level. It should also create a new Feeding for this pet and the current time.
POST /pets/{id}/scoldings should find the pet by id and subtract five from its happiness level. It should also create a new Scolding for this pet and the current time.

**D**

Database Controller
Database Context
Add in DateTime
JOIN tables between Pets and Playtime, Feeding and Scolding with PetId
Default values in Controller for POST: Date (Now), HungerLevel (0) and HappinessLevel (0)
Defined values for Pet table Happiness and Hunger to enter for each Playtime, Feeding and Scolding actions related with the foreign key (PetId) in 1:M Tables
API with the nested endpoints

Syntax Notes:
Models/Class (Pet) - singular as a single template.
Pets - plural as a collection of the Pet objects
pet - lower case and singular because it's one of the objects of the collection

Tables:

Many to Many (M:M) Table

Pet -

Id (int - automatic primary key)
Name (string)
Birthday (DateTime)
HungerLevel (int)
HappinessLevel (int)

One to Many (1:M) Tables

Playtime-
Id (int - automatic primary key)
When (DateTime)
PetId (int - foreign key to Pet)

Feeding -
Id (int - automatic primary key)
When (DateTime)
PetId (int - foreign key to Pet)

Scolding -
Id (int - automatic primary key)
When (DateTime)
PetId (int - foreign key to Pet)

**A** -

- Create ERD (https://lucid.app/lucidchart/invitations/accept/inv_60afd9cd-82a7-41ab-b33b-707263b7867c?viewport_loc=-53%2C1%2C1579%2C911%2C0_0)
- Create Models with linking 1:M tables to Pet for PetId Foreign Key
- Modify Database Context
- Create, Update and Add Migrations
- Modify Database Controller
- Update Database Controller with default for POST: Date (Now), HungerLevel (0) and HappinessLevel (0)
- Add in DateTime as Validation on all POST endpoints

- Review Swagger to verify API endpoints
- Enter test POST pet entries to assist with updating and building code based on the following specifications:

**GET /pets should return all pets in your database.**

Verify in Swagger that api/pets endpoint returns all pets in the database

**GET /pets/{id} should return the pet with the corresponding id.**

GET api/pets/{id} endpoint returns the pet with the corresponding {id} number from the database

**POST /pets should create a new pet. The controller should ensure the following: Birthday defaults to the current DateTime, HungerLevel defaults to 0 and HappinessLevel defaults to 0.**

POST endpoint, api/pets

Update Controller for HttpPost with these updates.

- **TODO** Add validation for name to ALL queries to keep data consistent **|** **|** **|**

            pet.Birthday = DateTime.Now;
            pet.HappinessLevel = 0;
            pet.HungerLevel = 0;

**DELETE /pets/{id}, should delete a pet from the database by Id**

DELETE api/pets/{id} deletes the pet with the corresponding {id} number from the database

**POST /pets/{id}/playtimes should find the pet by id and add five to its happiness level and add three to its hunger level. It should also create a new Playtime for this pet and the current time.**

Receive pet {Id} through Playtimes API
Verify, and if != valid -> return error
If == valid ->

Add 5 to the HappinessLevel field on the Pet Model

- We need to get the current value of the HappinessLevel field for the pet {Id}
- Add 5 to HappinessLevel field on the Pets.pet table

Add 3 to the HungerLevel field on the Pet Model

- We need to get the current value of the HappinessLevel field for the pet {Id}
- Add 5 to HungerLevel field on the Pets.pet table

Return the new values to the HappinessLevel and HungerLevel fields on the Pets table

Record the date of the playtime on the Playtime.When table/field

- **POST /pets/{id}/feedings should find the pet by id and subtract five from its hungry level and add three to its happiness level. It should also create a new Feeding for this pet and the current time.**

  **POST /pets/{id}/scoldings should find the pet by id and subtract five from its happiness level. It should also create a new Scolding for this pet and the current time.**
