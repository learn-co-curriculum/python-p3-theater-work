# Phase 3 Mock Code Challenge: Theater Work

## Learning Goals

- Write SQLAlchemy migrations.
- Connect between tables using SQLAlchemy relationships.
- Use SQLAlchemy to run CRUD statements in the database.

***

## Key Vocab

- **Schema**: the blueprint of a database. Describes how data relates to other
  data in tables, columns, and relationships between them.
- **Persist**: save a schema in a database.
- **Engine**: a Python object that translates SQL to Python and vice-versa.
- **Session**: a Python object that uses an engine to allow us to
  programmatically interact with a database.
- **Transaction**: a strategy for executing database statements such that
  the group succeeds or fails as a unit.
- **Migration**: the process of moving data from one or more databases to one
  or more target databases.
  
***

## Introduction

The Flatiron Theater Company is holding auditions!

An actor may only `Audition` for one `Role`, while a `Role` may have many
`Auditions` for it!

![one to many](https://curriculum-content.s3.amazonaws.com/phase-3/active-record-theater-work/one_to_many.png)

## Getting started

Run `pipenv install && pipenv shell`

## Migrations

Create your migrations.

- `Auditions` should have an actor (string), location (string) and belong_to a
  role (integer).
- `Roles` should only have a character_name.

### `auditions` Table

| Column | Type |
| --- | --- |
| actor | string |
| location | string |
| phone | integer |
| hired | boolean |
| role_id | integer |

### `roles` Table

| Column | Type |
| --- | --- |
| character_name | string |
  
## Relationship

- What relationships will this need (i.e. one-to-one, one-to-many, and
  many-to-many)?

## Audition

- `Audition.role` returns an instance of role associated with this audition.
- `Audition.call_back()` will change the the hired attribute to `True`.

## Roles

- `Role.auditions` returns all of the auditions associated with this role.
- `Role.actors` returns a list of names from the actors associated with this
  role.
- `Role.locations` returns a list of locations from the auditions associated
  with this role.
- `Role.lead()` returns the first instance of the audition that was hired for
  this role or returns a string 'no actor has been hired for this role'.
- `Role.understudy()` returns the second instance of the audition that was hired
  for this role or returns a string 'no actor has been hired for understudy for
  this role'.
