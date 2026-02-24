Population Records Management System
Police Department Database Design
Overview

This project represents the design and implementation of a relational database that simulates a population records management system used within a police department.

The database manages both civil and operational data related to individuals, including personal details, identity documents, criminal records, address history, driving licenses, registered vehicles, and name changes. It also includes a role-based access structure meant to simulate different institutional access levels.

Although this documentation is written in English, the database schema (table and column names) is implemented in Romanian.

Project Goal

The objective of this project was to design a structured and normalized relational database capable of storing and managing citizen data efficiently while maintaining data integrity.

The system supports searching individuals by national identification number (CNP), name, or other attributes, tracking both current and historical addresses, validating identity documents, viewing criminal record information, checking driving license status, and managing vehicles registered to a specific individual.

The main focus of the project is correct relational modeling, integrity constraints, and a realistic representation of institutional data.

User Roles

To simulate a real institutional environment, the system defines three user roles.

The Administrator has full access to the database. This role can insert, update, and delete records, and can manage relationships and user accounts.

The Internal User (Police Officer) has full read access to all stored data and can update existing information, but cannot delete records or manage user accounts.

The Citizen has access strictly limited to their own records. Authentication can be done using identifiers such as CNP or VIN. Citizens can view their registered vehicles, identity documents, driving license status, and their own criminal record (if applicable), but they are not allowed to modify any data.

Database Structure

The database is organized around the following main entities: Persoane (personal data), Adrese (address information), PersoaneAdresa (associative table for the many-to-many relationship between persons and addresses, including address history), DocumenteIdentitate (identity documents), Cazier (criminal record data), SchimbareNume (name change history), ContactePersoana (contact details), Permise (driving licenses), VehiculeInmatriculate (registered vehicles), and Utilizatori (system users and roles).

Relationships

The database includes a many-to-many relationship between Persons and Addresses with historical tracking, a one-to-one relationship between Person and Criminal Record, a one-to-one relationship between Person and active Identity Document, and one-to-many relationships between Person and name changes, contact information, driving licenses, and registered vehicles. All relationships are enforced using foreign keys and integrity constraints.

Technical Details

The implementation includes primary keys, foreign keys, unique constraints, check constraints, default values, and NOT NULL constraints. The schema follows normalization principles in order to minimize redundancy and ensure consistency.

Possible Extensions

Possible future improvements include a web-based interface, secure password hashing, stored procedures, triggers for auditing, activity logging, and more advanced role-based access control mechanisms.
