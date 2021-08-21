# TamagotchiAPI

P - ERD: https://lucid.app/lucidchart/invitations/accept/inv_60afd9cd-82a7-41ab-b33b-707263b7867c?viewport_loc=-53%2C1%2C1579%2C911%2C0_0

Create an API with the following endpoints:

GET /pets should return all pets in your database.
GET /pets/{id} should return the pet with the corresponding id.
POST /pets should create a new pet. The controller should ensure the following: Birthday defaults to the current DateTime, HungerLevel defaults to 0 and HappinessLevel defaults to 0.
DELETE /pets/{id}, should delete a pet from the database by Id
POST /pets/{id}/playtimes should find the pet by id and add five to its happiness level and add three to its hunger level. It should also create a new Playtime for this pet and the current time.
POST /pets/{id}/feedings should find the pet by id and subtract five from its hungry level and add three to its happiness level. It should also create a new Feeding for this pet and the current time.
POST /pets/{id}/scoldings should find the pet by id and subtract five from its happiness level. It should also create a new Scolding for this pet and the current time.

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
Default values in Controller for Date (Now), HungerLevel (0) and HappinessLevel (0)
Defined values for Pet table Happiness and Hunger to enter for each Playtime, Feeding and Scolding actions related with the foreign key (PetId) in 1:M Tables
API with the nested endpoints

Syntax Notes:
Models singular as a single template.
Pets is the plural for a collection of Pet
pet is lower case and singular because it's one of the objects of the collection

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

**A**

- Setup project
- Modify Database Controller
- Update Database Controller with default for Date (Now), HungerLevel (0) and HappinessLevel (0)
- Modify Database Context
- Create Models
- Create, Update and Add Migrations
- Review Swagger to verify API endpoints
- Update Code based on the following specifications:

GET /pets should return all pets in your database.

GET /pets/{id} should return the pet with the corresponding id.
POST /pets should create a new pet. The controller should ensure the following: Birthday defaults to the current DateTime, HungerLevel defaults to 0 and HappinessLevel defaults to 0.
DELETE /pets/{id}, should delete a pet from the database by Id
POST /pets/{id}/playtimes should find the pet by id and add five to its happiness level and add three to its hunger level. It should also create a new Playtime for this pet and the current time.
POST /pets/{id}/feedings should find the pet by id and subtract five from its hungry level and add three to its happiness level. It should also create a new Feeding for this pet and the current time.
POST /pets/{id}/scoldings should find the pet by id and subtract five from its happiness level. It should also create a new Scolding for this pet and the current time.
