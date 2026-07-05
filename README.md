# Recipe API Project

A Django REST Framework example - Recipe App API

[![Python](https://img.shields.io/badge/python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![License](https://img.shields.io/github/license/partORG/Django_Rest_Framework_Recipe_App_API)](LICENSE)
[![Tests](https://github.com/partORG/Django_Rest_Framework_Recipe_App_API/actions/workflows/checks.yml/badge.svg?branch=main)](https://github.com/partORG/Django_Rest_Framework_Recipe_App_API/actions/workflows/checks.yml)

## Introduction

The Recipe API project is a Django application that uses the Django REST framework to create an API for managing recipes. It includes models, serializers, views, and tests for handling recipe data, ingredients, tags, and users. The project also includes support for database migrations and user authentication.

This project aims to provide a solid foundation for building a scalable and maintainable recipe management system using modern web technologies.

## Table of Contents

- [Features](#features)
- [How It Works](#how-it-works)
- [Technology Stack](#technology-stack)
- [Requirements](#requirements)
- [Installation](#installation)
- [Configuration](#configuration)
- [Quick Start](#quick-start)
- [Usage](#usage)
- [Project Structure](#project-structure)
- [Development](#development)
- [Testing](#testing)
- [Limitations](#limitations)
- [License](#license)

## Features

### Recipe Management
- **Models**: Define the data structure for recipes, ingredients, tags, and users.
- **Serializers**: Convert complex data types, such as querysets and model instances, to native Python datatypes that can then be easily rendered into JSON, XML, or other content types.
- **Views**: Handle HTTP requests and return responses.

### User Authentication
- **User Model**: Extend Django's built-in user model for additional fields.
- **Authentication Views**: Provide endpoints for user registration, login, and logout.

### API Documentation
- **drf-spectacular**: Generate interactive API documentation using OpenAPI 3.0.

## How It Works

The project follows a typical Django application structure with the following components:

1. **Models**: Define the data schema using Django's ORM.
2. **Serializers**: Convert model instances to JSON and vice versa.
3. **Views**: Handle HTTP requests and return responses.
4. **URLs**: Map URLs to views.

## Technology Stack

| Technology | Purpose |
|------------|---------|
| Django | The web framework used for building the application. |
| djangorestframework | A powerful and flexible toolkit for building Web APIs. |
| psycopg2 | PostgreSQL adapter for Python. |
| drf-spectacular | OpenAPI 3.0 documentation generator for Django REST Framework. |
| Pillow | Python Imaging Library (PIL) fork with an emphasis on easy usage. |

## Requirements

- Python 3.9
- PostgreSQL

## Installation

To install the project, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/partORG/Django_Rest_Framework_Recipe_App_API.git
   cd Django_Rest_Framework_Recipe_App_API
   ```

2. Create a virtual environment and activate it:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   ```

3. Install dependencies:
   ```sh
   pip install -r requirements.txt
   ```

4. Set up the database:
   ```sh
   python manage.py migrate
   ```

5. Create a superuser (optional):
   ```sh
   python manage.py createsuperuser
   ```

6. Run the development server:
   ```sh
   python manage.py runserver
   ```

## Configuration

The project uses environment variables for configuration. The following variables are observed:

- `DJANGO_SECRET_KEY`: Secret key for cryptographic signing.
- `DATABASE_URL`: Database connection string.

## Quick Start

To quickly start using the API, follow these steps:

1. Create a new recipe:
   ```sh
   curl -X POST http://localhost:8000/recipes/ \
        -H "Content-Type: application/json" \
        -d '{"title": "Chocolate Cake", "description": "A delicious chocolate cake."}'
   ```

2. List all recipes:
   ```sh
   curl -X GET http://localhost:8000/recipes/
   ```

## Usage

To interact with the API, use the following commands:

- **List Recipes**:
  ```sh
  python manage.py runscript list_recipes
  ```

- **Create Recipe**:
  ```sh
  python manage.py runscript create_recipe --args "Chocolate Cake A delicious chocolate cake."
  ```

## Project Structure

```
recipe-app-api/
├── .dockerignore
├── .github/workflows/checks.yml
├── .gitignore
├── Dockerfile
├── README.md
├── app/
│   ├── .flake8
│   ├── __init__.py
│   ├── asgi.py
│   ├── calc.py
│   ├── settings.py
│   ├── test.py
│   ├── urls.py
│   └── wsgi.py
├── core/
│   ├── __init__.py
│   ├── admin.py
│   ├── apps.py
│   ├── management/
│   │   ├── __init__.py
│   │   └── commands/
│   │       ├── __init__.py
│   │       └── wait_for_db.py
│   ├── migrations/
│   │   ├── 0001_initial.py
│   │   ├── 0002_recipe.py
│   │   ├── 0003_auto_20230601_1149.py
│   │   ├── 0004_auto_20230603_1546.py
│   │   ├── 0005_recipe_image.py
│   │   └── __init__.py
│   ├── models.py
│   ├── tests/
│   │   ├── __init__.py
│   │   ├── test_admin.py
│   │   ├── test_commands.py
│   │   └── test_models.py
│   └── urls.py
├── manage.py
├── recipe/
│   ├── __init__.py
│   ├── apps.py
│   ├── serializers.py
│   ├── tests/
│   │   ├── __init__.py
│   │   ├── test_ingredients_api.py
│   │   ├── test_recipe_api.py
│   │   └── test_tags_api.py
│   ├── urls.py
│   └── views.py
├── user/
│   ├── __init__.py
│   ├── apps.py
│   ├── serializers.py
│   ├── tests/
│   │   ├── __init__.py
│   │   └── test_user_api.py
│   ├── urls.py
│   └── views.py
├── docker-compose.yml
└── requirements.dev.txt
```

## Development

The project follows a standard Django development workflow:

1. **Create Models**: Define the data schema in `app/core/models.py`.
2. **Create Serializers**: Convert model instances to JSON in `app/recipe/serializers.py`.
3. **Create Views**: Handle HTTP requests and return responses in `app/recipe/views.py`.
4. **Run Migrations**: Apply database migrations using `python manage.py migrate`.
5. **Test**: Run tests using `python manage.py test`.

## Testing

The project includes unit tests for models, views, and serializers:

```sh
python manage.py test
```

## Limitations

- The project assumes a PostgreSQL database.
- User authentication is basic and can be extended.

## License

This project is licensed under the [MIT License](LICENSE).