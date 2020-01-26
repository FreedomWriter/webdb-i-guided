# DQL example

## Read

SELECT < column names > FROM < table name > = < some value >;

    SELECT email FROM users WHERE name = 'Jason Maurer';

SQL keynames are not case sensitive, however convention is uppercase
SQL commands always end with a semi-colon, which allows you to split commands up into multiple lines:

    SELECT email
    FROM users
    WHERE name = 'Jason Maurer';

# DML example - Don't forget the WHERE!!

## Create

INSERT INTO < table name > (< column nmaes >)
VALUES (< some values >)

    INSERT INTO Category(CategoryName, Description)
    Values('Frozen', 'Ready-to-eat meals');

## Update

UPDATE < table name>
SET <column name> = < some value >
WHERE < column name > = < some value > // This is the line that keeps us from udating EVERY row

    UPDATE Category
    SET Description = 'Desserts and ready-to-eat meals'
    WHERE Id = 9;

## Destroy

DELETE FROM < table name >
WHERE < column name > = < some value >

    DELETE FROM Category
    WHERE Id = 9;

# ORM - Object Relational Data Base Mapping Library

instead of "INSERT INTO users":

    const user = new User()
    user.save()

ORM's don't provide a lot of flexibility

# Query Builder

Allow us to write JS code that will translate into ORM

Using a Query Builder instead of "INSERT INTO users"

    table("users").insert()

We will use a Query Builder called [knexjs]("http://knexjs.org/#Builder-del%20/%20delete")

# Dependencies

    npm i knex sqlite3

Notes based on lecture by Jason Maurer.
