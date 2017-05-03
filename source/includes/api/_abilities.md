# Abilities/Permissions

## What is an Ability?

Abilities restricts what resources a given user is allowed to access.

The permissions are defined for each user role.

## Available user permissions

User abilities:

| User role       | Permissions
| -------------   | -------------
| admin           | Can manage and read all entities
|                 | Can not activate, deactivate, delete it self
| publisher       | Can read all
|                 | Can activate - deactivate: Comment, Project, User, Photo, Document, ExternalSource, Country, Impact
|                 | Can publish - unpublish Project
|                 | Can manage owned projects and create a new one
|                 | Can read all entities
|                 | Can create projects
|                 | Can write comments
|                 | Can not activate, deactivate it self
| editor          | Can read all except comments and not owned projects
|                 | Can manage it self
|                 | Can create business models and comments
|                 | Can update owned business models and study cases
|                 | Can read owned business models
| user            | Can read all except comments and not owned projects
|                 | Can manage it self
|                 | Can create comments
|                 | Can update owned business models and study cases
|                 | Can read owned business models
| guest           | Can read all except comments and business models
