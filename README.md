[![Build Status](https://travis-ci.com/rafaelsfaria/recipe-drf-api.svg?branch=master)](https://travis-ci.com/rafaelsfaria/recipe-drf-api)
# recipe-drf-api
Recipe app api

## About
RESTful API with Django Rest Framework and integrated with TravisCI.

Create, Read, Update and Delete Ingredients and Recipes.

## Dependencies
- Docker (python, postgres)

## Start
```sh
docker-compose up -d
docker-compose run app sh -c "python manage.py makemigrations"
docker-compose run app sh -c "python manage.py test && flake8"
```
Go to 'localhost:8000/api/user/create' and create a new user. Get the token from the json response.
Modify the header of your requests with the header 'Authorization':

Request Header: Authorization, Value: Token 'your-token-here'.

I recommend using ModHeader Chrome extension. You **need** to be authenticated to access other routes.

## Endpoints

### User - localhost:8000/api/user/
1. create - create new user
2. token - login user, get a token
3. me - profile info

### User - localhost:8000/api/recipe/
1. ingredients - CRUD ingredients
2. recipes - CRUD recipes
3. tags - CRUD tags

### Admin - localhost:8000/admin
Django admin.

## Tests
### 1 - Core (core/tests)
[x] Commands

[x] Admin

[x] Models

### 2 - Recipe (recipe/tests)
[x] Recepi

[x] Tags

[x] Ingredients

### 3 - User (user/tests)
[x] User

## Models (core/models)
1. User - email, password
2. Tag - user (fk), name
3. Ingredients - user (fk), name
4. Recipe - user (fk), title, time in minutes, price, link, ingredients (fk), tags (fk), image

## Superuser
If you want to create a super user and access '/admin', run the script:

```sh
docker-compose run app sh -c "python manage.py createsuperuser"
```
