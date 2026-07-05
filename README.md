# Recipe API Project

A Django REST Framework example - Recipe App API.

[![Python](https://img.shields.io/badge/python-3.9-blue.svg)](https://www.python.org/downloads/release/python-390/)
[![License](https://img.shields.io/github/license/partORG/Django_Rest_Framework_Recipe_App_API)](LICENSE)
[![Tests](https://github.com/partORG/Django_Rest_Framework_Recipe_App_API/actions/workflows/checks.yml/badge.svg?branch=main)](https://github.com/partORG/Django_Rest_Framework_Recipe_App_API/actions/workflows/checks.yml)

## Introduction

The Recipe API project is a Django REST Framework application designed to manage recipes. It provides a robust backend for storing, retrieving, updating, and deleting recipe data. The API includes endpoints for ingredients, recipes, and tags, making it easy to integrate into any frontend application.

This project aims to be a comprehensive example of how to build a scalable and maintainable API using Django REST Framework. It includes features such as automatic documentation generation, image uploads, and robust testing.

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

### Automatic Documentation
The API includes automatic documentation using `drf-spectacular`, which generates interactive Swagger UI and ReDoc interfaces.

### Image Uploads
Support for uploading recipe images using the `Pillow` library, ensuring high-quality image handling.

### Robust Testing
Comprehensive testing with Django's built-in test framework and additional tests for API endpoints.

## How It Works

The project follows a typical Django REST Framework architecture:

1. **Models**: Define the data structure using Django models.
2. **Serializers**: Convert model instances to JSON and vice versa.
3. **Views**: Handle HTTP requests and responses.
4. **URLs**: Map URLs to views.

## Technology Stack

| Technology | Purpose |
|------------|---------|
| Django     | The web framework used for building the API. |
| djangorestframework | Provides powerful and flexible tools for building Web APIs. |
| psycopg2   | PostgreSQL adapter for Python, used for database operations. |
| drf-spectacular | Generates interactive API documentation using Swagger UI and ReDoc. |
| Pillow     | Python Imaging Library (PIL) fork with additional features, used for image processing. |

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

- `DEBUG`: Enable or disable debug mode.
- `SECRET_KEY`: Secret key for cryptographic signing.
- `DATABASE_URL`: Database connection URL.

These variables can be set in a `.env` file or directly in the environment where the application is running.

## Quick Start

To quickly start using the API, follow these steps:

1. Run the development server:
   ```sh
   python manage.py runserver
   ```

2. Access the API documentation at `http://localhost:8000/swagger/` or `http://localhost:8000/redoc/`.

## Usage

Here are some example commands and usage scenarios:

1. **Creating a Recipe**:
   ```sh
   curl -X POST http://localhost:8000/api/recipes/ \
       -H "Content-Type: application/json" \
       -d '{"title": "Chocolate Cake", "description": "A delicious chocolate cake"}'
   ```

2. **Listing Recipes**:
   ```sh
   curl -X GET http://localhost:8000/api/recipes/
   ```

3. **Updating a Recipe**:
   ```sh
   curl -X PUT http://localhost:8000/api/recipes/1/ \
       -H "Content-Type: application/json" \
       -d '{"title": "Chocolate Cake", "description": "A delicious chocolate cake with extra chocolate"}'
   ```

4. **Deleting a Recipe**:
   ```sh
   curl -X DELETE http://localhost:8000/api/recipes/1/
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
│   ├── wsgi.py
│   ├── core/
│   │   ├── __init__.py
│   │   ├── admin.py
│   │   ├── apps.py
│   │   ├── management/
│   │   │   ├── __init__.py
│   │   │   └── commands/
│   │   │       ├── __init__.py
│   │   │       └── wait_for_db.py
│   │   ├── migrations/
│   │   │   ├── 0001_initial.py
│   │   │   ├── 0002_recipe.py
│   │   │   ├── 0003_auto_20230601_1149.py
│   │   │   ├── 0004_auto_20230603_1546.py
│   │   │   ├── 0005_recipe_image.py
│   │   │   └── __init__.py
│   │   ├── models.py
│   │   ├── tests/
│   │   │   ├── __init__.py
│   │   │   ├── test_admin.py
│   │   │   ├── test_commands.py
│   │   │   └── test_models.py
│   │   └── views.py
│   ├── manage.py
│   ├── recipe/
│   │   ├── __init__.py
│   │   ├── apps.py
│   │   ├── serializers.py
│   │   ├── tests/
│   │   │   ├── __init__.py
│   │   │   ├── test_ingredients_api.py
│   │   │   ├── test_recipe_api.py
│   │   │   └── test_tags_api.py
│   │   ├── urls.py
│   │   └── views.py
│   └── user/
│       ├── __init__.py
│       ├── apps.py
│       ├── serializers.py
│       ├── tests/
│       │   ├── __init__.py
│       │   └── test_user_api.py
│       ├── urls.py
│       └── views.py
├── docker-compose.yml
└── requirements.dev.txt
```

## Development

The project follows a standard Django development workflow:

1. **Code Changes**: Make changes to the codebase.
2. **Testing**: Run tests using `python manage.py test`.
3. **Migrations**: Generate and apply migrations using `python manage.py makemigrations` and `python manage.py migrate`.

## Testing

The project includes comprehensive testing with Django's built-in test framework:

```sh
python manage.py test
```

## Limitations

- The project assumes a PostgreSQL database.
- Image uploads are limited to JPEG format.

## License

This project is licensed under the [MIT License](LICENSE).