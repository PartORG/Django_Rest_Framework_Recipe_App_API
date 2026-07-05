# Recipe API Project

A Django REST Framework example - Recipe App API.

## Overview

This project is a sample application built using Django and Django REST Framework to create a recipe management API. It allows users to manage recipes, ingredients, and tags through a RESTful interface.

## Requirements

To run this project, you will need the following dependencies:

- Python 3.9
- Django>=4.0.1,<4.1
- djangorestframework>=3.13.1,<3.14
- psycopg2>=2.9.3,<2.10
- drf-spectacular>=0.22.1,<0.23
- Pillow>=9.1.0,<9.2

## Installation

To set up the project, follow these steps:

1. Clone the repository:
   ```sh
   git clone https://github.com/PartORG/Django_Rest_Framework_Recipe_App_API.git
   cd Django_Rest_Framework_Recipe_App_API
   ```

2. Create a virtual environment and install dependencies:
   ```sh
   python -m venv venv
   source venv/bin/activate  # On Windows use `venv\Scripts\activate`
   pip install -r requirements.txt
   ```

3. Apply migrations:
   ```sh
   python manage.py migrate
   ```

4. Create a superuser (optional):
   ```sh
   python manage.py createsuperuser
   ```

5. Run the development server:
   ```sh
   python manage.py runserver
   ```

## Usage

To interact with the API, you can use the following entry points:

- **Development Server**: Access the API at `http://127.0.0.1:8000/`
- **Admin Interface**: Access the Django admin interface at `http://127.0.0.1:8000/admin/` (if you created a superuser)

For more detailed usage instructions, refer to the project's documentation or source code.