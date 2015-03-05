# Setting up authentication in Laravel
This readme will describe how to setup authentication in a new laravel5 installation. Including:
- database setup
- user table creation
- authentication configuration
- default auth controllers and views

## Initial Setup
- setup .env file to point to database

## User table creation
Since laravel authentication uses Eloquent ORM by default, there are two columns that must be included in the database table that is used for user authentication. These fields are:
- remember_token varchar(255) ;; must be >= 100 chars
- created_date datetime
- updated_date datetime
 
The default configuration for authentication uses these fields:
- name
- password
- email

Additionally, the default table name is "users".

I don't like all these defaults and am going to call my table "user" and use these fields:
- first_name
- last_name
- username
- password
- email

The (my)sql for the table is:

```sql
create table user (
    id int auto_increment primary key,
    username varchar(255),
    password varchar(255),
    first_name varchar(255),
    last_name varchar(255),
    email varchar(255),
    remember_token varchar(255),
    created_at datetime,
    updated_at datetime
);
```
