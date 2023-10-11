# IN YOUR TERMINAL: Start in YOUR main NODEJS folder on your drive.
# CLONE: https://github.com/su-w3-bootcamp/software-4.5-sequelize-models.git
# This creates a project folder for you.
# CD to this new folder in your terminal

# Go to YOUR github and create a new repository: 
  # software-4.5-sequelize-models
  # Select Public with NO README FILE
  
# AGAIN, make sure you are in the correct folder in your terminal
# git remote -v // SHOWS YOU THE ORIGINAL w3Schools github repository
   # This next one gives error - you already have the ORIGIN connected to su-w3-bootcamp
   # git remote add origin https://github.com/Jault1/software-4.5-sequelize-models.git
   # So we need to swap the ORIGIN LINK
   # Do this to CHANGE the ORIGIN LINK
   # $ git remote set-url origin https://github.com/Jault1/software-4.5-sequelize-models.git

# Their site is using PostGre, I'm going to try to use mySQL

# $ npm i mysql2
# $ npm i sequelize

# mysql -u root -p  -- I think this is the format here

# Try running this script: line by line, after line one (creating the db), 
# After creating db, 
# $ use ecommerce;

# Run this sql for setup
# Look at this but run the two create tables below; not from this link
# # https://github.com/su-w3-bootcamp/software-4.4-relational-postgresql/blob/main/src/lesson.sql
# Changes I made: 
#   Change SERIAL to AUTO_INCREMENT
#   id MEDIUMINT NOT NULL AUTO_INCREMENT,
# After running these two below; run the rest from the url above.

# CREATE TABLE categories (
#    id MEDIUMINT NOT NULL AUTO_INCREMENT,
#     name VARCHAR(255) UNIQUE NOT NULL,
#     PRIMARY KEY (id)
# );

# CREATE TABLE items (
#     id MEDIUMINT NOT NULL AUTO_INCREMENT,
#     name VARCHAR(255) NOT NULL,
#     price NUMERIC(10, 2) NOT NULL,
#     description TEXT,
#     category_id MEDIUMINT,
#     PRIMARY KEY (id),
#     FOREIGN KEY (category_id) 
#         REFERENCES categories(id)
#         ON DELETE CASCADE 
#         ON UPDATE CASCADE
# );

# Assignment
# Recreate the "meats" category. (Note what the id number will be)
# INSERT INTO categories (name) VALUES ('meats');

# Create 2 items called "pork" and "chicken". (Provide the other details as needed.)
# INSERT INTO items (name, price, description) VALUES ('Pork', 9.75, 'A bunch of other white meat');
# INSERT INTO items (name, price, description) VALUES ('Chicken', 4.75, 'A bunch of white meat');

# Search for all fruits and display the name and description of each.
# SELECT c.name, i.name, i.description 
# FROM categories c 
# JOIN items i
# ON i.category_id = c.id; 

# Update all the meat prices to 120.99
# UPDATE items SET category_id = 3 WHERE name = 'Pork';
# UPDATE items SET category_id = 3 WHERE name = 'Chicken';
# UPDATE items SET price = 120.99 
# WHERE category_id = 3; 

# Select all items with prices greater than 20
# SELECT * FROM items WHERE price > 20;

# categories
# +----+------------+
# | id | name       |
# +----+------------+
# # |  1 | fruits     |
# |  3 | meats      |
# |  2 | vegetables |
# +----+------------+

# # items
# +----+---------+-------+-----------------------------+-------------+
# | id | name    | price | description                 | category_id |
# +----+---------+-------+-----------------------------+-------------+
# |  1 | Banana  | 18.75 | A bunch of yellow bananas   |           1 |
# |  3 | Celery  |  5.00 | A sprig of celery           |           2 |
# |  4 | Pork    |  9.75 | A bunch of other white meat |           3 |
# |  5 | Chicken |  4.75 | A bunch of white meat       |           3 |
# +----+---------+-------+-----------------------------+-------------+


# Sequelize and Models

## Dependencies

Refer to the following markdown file for the respective sections of the class:
- [Self Studies](./studies.md)
- [Lesson](./lesson.md)
- [Assignment](./assignment.md)

## Lesson Objectives

Learners will understand:
- How database tables would translate into models
- How Sequelize can be used to create models

Learners will be able to:
- Use Sequelize to create models


## Lesson Plan

|Duration|What|How or Why|
|--------|-----|-------|
|- 5mins |Start zoom session|So that students can join early and start class on time|
|10 mins|Self studies check-in|Prepare 3 questions for students to answer as a form of warm up and engaging students with the lesson topic.|
|30 mins|Conceptual Knowledge| Instructors brief students on the subject matter conceptually before diving into hands on. This section can be shorter but not longer. Use video clips for explanation if necessary.|
|20 mins|Code Along| Practical hands on|
||**1 HR MARK**|
|5 mins|Break|Break|
|40 mins|Code Along| Practical hands on|
|5 mins|Buffer|In case of overrun|
|5 mins|Break||
|5 mins|Assignment Briefing|Help students to understand the expectation and direction of the assignment to prevent mis-interpretations.|
||**END OF CLASS 2 HR MARK**|

