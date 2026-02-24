🗄️ Population Records Management System
Police Department Database Design
Overview

This project consists of the design and implementation of a relational database meant to simulate the population records system used within a police department.

The database manages both civil and operational data related to individuals, such as personal information, identity documents, criminal records, address history, driving licenses, registered vehicles, and name changes. It also includes a role-based user system to simulate different access levels inside the institution.

Although the documentation is written in English, the database schema (table and column names) is implemented in Romanian.

Project Goal

The main objective was to design a structured and normalized database that allows efficient storage, retrieval, and management of citizen data.

The system supports:

Searching individuals by national identification number (CNP), name, or other attributes

Tracking current and past addresses

Validating identity documents

Viewing criminal record information

Checking driving license status

Managing vehicles registered to a specific person

The focus of the project is on database structure, data integrity, and correctly modeling real-world relationships between entities.

User Roles

To simulate a real institutional environment, the system defines three types of users:

Administrator

Has full control over the database.
Can insert, update, and delete records, as well as manage relationships and system users.

Internal User (Police Officer)

Has access to all stored information.
Can update existing records but cannot delete data or manage user accounts.

Citizen

Has restricted access to their own data only.
Authentication can be done using identifiers such as CNP or VIN.
Citizens can view:

Their registered vehicles

Their identity documents

Driving license status

Their own criminal record (if available)

They are not allowed to modify any information.

Database Structure

The database is organized around the following main entities:

Persoane – stores personal data

Adrese – stores address information

PersoaneAdresa – associative table for many-to-many relationship with address history

DocumenteIdentitate – identity documents

Cazier – criminal record data

SchimbareNume – name change history

ContactePersoana – contact details

Permise – driving licenses

VehiculeInmatriculate – registered vehicles

Utilizatori – system users and roles

Relationships

The database models several types of relationships:

Many-to-many between Persons and Addresses (with historical tracking)

One-to-one between Person and Criminal Record

One-to-many between Person and:

Name changes

Contact details

Driving licenses

Registered vehicles

One-to-one between Person and active Identity Document

All relationships are enforced using foreign keys and integrity constraints.

Technical Details

The project was implemented using SQL and includes:

Primary and foreign keys

Unique constraints

Check constraints

Default values

Not-null constraints

The database design follows normalization principles to reduce redundancy and ensure consistency.

Entity–Relationship Diagram

The ER diagram is included in the repository as:

diagram.png
or
ERD.pdf

Possible Extensions

Future improvements could include:

A web-based interface

Secure password hashing

Stored procedures and triggers

Audit logging

More advanced access control mechanisms
