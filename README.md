# A Django Rest Framework (DRF) demo project

## Description

This project consumes data from the `restcountries.eu` site. Then exposes the
data with slightly modified endpoints for modified local use.

## Project structure

The name of the project is `drf_demo` and the main app is called `restcountries`.

## Instructions

1. Initialize a virtual environment

```sh
$ python -m venv venv
$ source venv/bin/activate
```

2. Install the requirements: `pip install -r requirements`
3. Run the server: `python manage.py runserver`

## Admin user

I created the admin user `admin` with password `1` that can be used to test
project initially. New users can be made by browsing the root url of the
project and click "Register" on the left side of the page.

## Some indications

The `restcountries.utils.get_countries()` can be used to fetch data from
`restcountries.eu`. This function uses the `requests` module to send the GET
request.

The `restcountries.utils.populate_database(data)` method has been used to
populate the local database.

The `restcountries.utils.print_countries_db()` prints all the data from the
local database to the stdout. This can be used to verify that the database has
been populated succesfully after running the populate_database(data) method.

## Endpoints

To verify the tasks, this table can be used.

| No.   |  Function  |  API request and URL |
| :---: | :-------------------------- | :--------------------------------------- |
| 1.    | List all countries | GET `/api/countries` \* |
| 2.    | Specific country | GET `/api/countries/<pk>` \* |
| 3.    | Add a new country | Make POST request with data to `/api/countries` \* |
| 4.    | Update a country's details | PUT request with data to `/api/countries/<pk>` \* |
| 5.    | Delete a country instance | DELETE request to `/api/countries/<pk>` \* |
| 6.    | List a country's neighbours | GET request to `/api/countries/<pk>/neighbours/` |
| 7.    | List country's who speak a specified language | GET request to `/api/language/<str:language_name>` \*\* |
| 8.    | Search and list countries by partial country name | GET `api/countries/search=<str:name>&fields=name` |


+ __\*__: Also browsable by the browser
+ __\*\*__: GET `/api/countries/search=<str:language_name>&fields=languages`

## Using the web interface

Search countries ny name: use the search bar on the left hand side.

To browse a country in detail view, click on Details beside the country in the
table from the root directory.

## Authentication Details

To browse the APIs, a user needs to be logged in. You can use (user,pass)
(`admin`,`1`) to log in from the root directory of the website, or register a
user using the 'Register' link on the website.
