# Laravel Sanctum REST API

A RESTful API built with Laravel and MySQL, demonstrating token-based authentication with Laravel Sanctum and protected API endpoints.

## Overview

This project demonstrates a backend API architecture using Laravel, MySQL and Laravel Sanctum.

The API provides user authentication and authenticated endpoints, with access to protected resources controlled through Sanctum tokens.

## Technologies

* PHP
* Laravel
* Laravel Sanctum
* MySQL
* REST API
* Postman

## Features

* User registration
* User login
* Token-based authentication
* Authenticated user endpoint
* Logout and token revocation
* Protected API routes
* Request validation
* MySQL database integration
* RESTful API structure
* API testing with Postman

## API Endpoints

### Authentication

| Method | Endpoint        | Description                     | Authentication |
| ------ | --------------- | ------------------------------- | -------------- |
| POST   | `/api/register` | Register a new user             | No             |
| POST   | `/api/login`    | Authenticate a user             | No             |
| POST   | `/api/logout`   | Revoke the current token        | Yes            |
| GET    | `/api/me`       | Retrieve the authenticated user | Yes            |

## Authentication

After successful login, the API returns an authentication token.

Protected endpoints require the token using the Bearer authentication scheme:

```text
Authorization: Bearer YOUR_TOKEN
```

## Testing

The API was tested using Postman.

The Postman collection can be included in this repository to demonstrate the available endpoints and authentication flow.

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

Configure the MySQL database in `.env`, then run:

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

## Project Structure

The project follows Laravel's standard application structure, with authentication logic handled through controllers, middleware and Sanctum token authentication.

## Purpose

This project is part of my backend development portfolio and demonstrates practical experience building authenticated REST APIs with Laravel.

## Author

**Somar Hassan**

Information Technology Engineering — Cybersecurity

GitHub: https://github.com/somarhassan322
