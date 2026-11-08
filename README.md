# Library Management System - Database Design

## 1. Database Purpose / Mission Statement
The purpose of the Library Management System database is to efficiently store,
organise and track library resources, members and borrowing activities.
It ensures books are easy to find, members are uniquely identified, and
borrowings are recorded accurately to avoid data loss, duplication and
overdue books going unnoticed.

## 2. Table Separation
To avoid data redundancy, data is separated by subject into distinct tables:

1.  **Books** - Stores information about each book (title, year, author).
2.  **Members** - Stores information about each library member.
3.  **Borrowings** - Stores which member borrowed which book and when.
4.  **Authors** - Stores information about authors to avoid repeating
    author details in every book record.

Separating tables prevents repeating the same member or author details
in every borrowing record.

## 3. Fields & Primary Keys - Members Table

| Field | Data Type | Description |
| :--- | :--- | :--- |
| member_id | SERIAL | **Primary Key** - Uniquely identifies each member |
| first_name | VARCHAR(50) | Member's first name |
| last_name | VARCHAR(50) | Member's last name |
| email | VARCHAR(100) | Member's email, unique |
| phone | VARCHAR(20) | Member's phone number |
| join_date | DATE | Date member joined the library |

**Primary Key:** `member_id` - because it is unique for every member and
never changes, unlike name or email which could be duplicated.


## 4. PostgreSQL Practical

postgres=# CREATE DATABASE library_db;
CREATE DATABASE
postgres=# \c library_db
You are now connected to database "library_db" as user "postgres".
library_db=# CREATE TABLE authors (
library_db(#     author_id SERIAL PRIMARY KEY,
library_db(#     author_name VARCHAR(100)
library_db(# );
CREATE TABLE
library_db=# CREATE TABLE books (
library_db(#     book_id SERIAL PRIMARY KEY,
library_db(#     title VARCHAR(150),
library_db(#     published_year INT,
library_db(#     author_id INT REFERENCES authors(author_id)
library_db(# );
CREATE TABLE
library_db=# INSERT INTO authors (author_name) VALUES
library_db-# ('Chinua Achebe'),
library_db-# ('Buchi Emecheta'),
library_db-# ('Wole Soyinka');
INSERT 0 3
library_db=#
library_db=# INSERT INTO books (title, published_year, author_id) VALUES
library_db-# ('Things Fall Apart', 1958, 1),
library_db-# ('The Joys of Motherhood', 1979, 2),
library_db-# ('Death and the King''s Horseman', 1975, 3);
INSERT 0 3
library_db=# SELECT books.title, books.published_year, authors.author_name
library_db-# FROM books
library_db-# JOIN authors ON books.author_id = authors.author_id;
             title             | published_year |  author_name
-------------------------------+----------------+----------------
 Things Fall Apart             |           1958 | Chinua Achebe
 The Joys of Motherhood        |           1979 | Buchi Emecheta
 Death and the King's Horseman |           1975 | Wole Soyinka
(3 rows)


library_db=# \q

