# Laravel Sanctum REST API

A RESTful API built with Laravel and MySQL, demonstrating token-based authentication with Laravel Sanctum, authenticated CRUD operations, request validation, and resource authorization.

## Overview

This project demonstrates a backend API architecture using Laravel, MySQL, and Laravel Sanctum.

The API provides user authentication and protected task management endpoints. Each task belongs to an authenticated user, and authorization policies ensure that users can only access and modify their own tasks.

The project also includes a Postman collection and automated feature tests covering authentication, CRUD operations, and authorization.

## Technologies

* PHP
* Laravel
* Laravel Sanctum
* MySQL
* REST API
* Eloquent ORM
* Postman
* PHPUnit

## Features

### Authentication

* User registration
* User login
* Token-based authentication with Laravel Sanctum
* Retrieve authenticated user
* Logout and token revocation
* Protected API routes
* Request validation

### Task Management

* Create tasks
* List authenticated user's tasks
* Retrieve a task
* Update tasks
* Delete tasks
* Task ownership through user relationships
* Task completion status

### Authorization

* Laravel Policy-based authorization
* Users can access only their own tasks
* Unauthorized access returns HTTP `403 Forbidden`
* Protected endpoints require Sanctum authentication

### Testing

* Automated Laravel feature tests
* Authentication tests
* Protected route tests
* Task CRUD tests
* Task ownership and authorization tests
* Postman API testing

## API Endpoints

### Health Check

| Method | Endpoint      | Description      | Authentication |
| ------ | ------------- | ---------------- | -------------- |
| GET    | `/api/health` | Check API status | No             |

### Authentication

| Method | Endpoint        | Description                     | Authentication |
| ------ | --------------- | ------------------------------- | -------------- |
| POST   | `/api/register` | Register a new user             | No             |
| POST   | `/api/login`    | Authenticate a user             | No             |
| GET    | `/api/me`       | Retrieve the authenticated user | Yes            |
| POST   | `/api/logout`   | Revoke the current token        | Yes            |

### Tasks

| Method | Endpoint            | Description                         | Authentication |
| ------ | ------------------- | ----------------------------------- | -------------- |
| GET    | `/api/tasks`        | List the authenticated user's tasks | Yes            |
| POST   | `/api/tasks`        | Create a new task                   | Yes            |
| GET    | `/api/tasks/{task}` | Retrieve a task                     | Yes            |
| PUT    | `/api/tasks/{task}` | Update a task                       | Yes            |
| DELETE | `/api/tasks/{task}` | Delete a task                       | Yes            |

## Authentication

After successful registration or login, the API returns a Sanctum authentication token.

Protected endpoints require the token using the Bearer authentication scheme:

```text
Authorization: Bearer YOUR_TOKEN
```

For example:

```text
Authorization: Bearer 1|example-token
```

Do not commit real authentication tokens, passwords, API keys, or other secrets to the repository.

## Authorization

Tasks are associated with the authenticated user through a `user_id` foreign key.

Authorization is handled using a Laravel Policy. Users can only:

* View their own tasks
* Update their own tasks
* Delete their own tasks

Attempting to access another user's task results in:

```text
403 Forbidden
```

This demonstrates resource ownership and authorization at the application level.

## Example Task Request

### Create Task

```http
POST /api/tasks
Authorization: Bearer YOUR_TOKEN
Content-Type: application/json
```

Request body:

```json
{
    "title": "Build Laravel API",
    "description": "Complete the REST API project",
    "completed": false
}
```

### Update Task

```http
PUT /api/tasks/1
Authorization: Bearer YOUR_TOKEN
Content-Type: application/json
```

Request body:

```json
{
    "title": "Build Laravel REST API",
    "completed": true
}
```

## Postman Collection

A Postman collection is included in the repository for testing the API endpoints.

The collection covers:

* Health check
* Registration
* Login
* Authenticated user
* Logout
* Create task
* List tasks
* Get task
* Update task
* Delete task
* Authorization testing

Import the collection into Postman and configure the required authentication token when testing protected endpoints.

## Installation

Clone the repository:

```bash
git clone https://github.com/YOUR-USERNAME/laravel-sanctum-rest-api.git

cd laravel-sanctum-rest-api
```

Install PHP dependencies:

```bash
composer install
```

Create the environment file:

```bash
cp .env.example .env
```

Generate the Laravel application key:

```bash
php artisan key:generate
```

Configure the MySQL database in `.env`.

Run the database migrations:

```bash
php artisan migrate
```

Start the development server:

```bash
php artisan serve
```

The API will be available at:

```text
http://127.0.0.1:8000
```

## Running Tests

Run the automated test suite with:

```bash
php artisan test
```

The tests cover authentication, protected routes, task CRUD operations, and task ownership authorization.

## Project Structure

The project follows Laravel's standard application structure.

Important application components include:

```text
app/
├── Http/
│   ├── Controllers/
│   │   └── Api/
│   └── Requests/
├── Models/
│   ├── Task.php
│   └── User.php
└── Policies/
    └── TaskPolicy.php

database/
└── migrations/

postman/
└── Laravel-Sanctum-REST-API.postman_collection.json

routes/
└── api.php

tests/
└── Feature/
```

## What This Project Demonstrates

This project demonstrates practical backend development concepts including:

* REST API design
* Laravel application structure
* Authentication with Laravel Sanctum
* Token-based API authentication
* Request validation
* Eloquent relationships
* CRUD operations
* Resource authorization with Laravel Policies
* MySQL database integration
* API testing with Postman
* Automated feature testing
* Git and GitHub workflow

## Purpose

This project is part of my backend development portfolio and demonstrates practical experience building authenticated REST APIs with Laravel.

## Author

**Somar Hassan**

Information Technology Engineering — Cybersecurity
