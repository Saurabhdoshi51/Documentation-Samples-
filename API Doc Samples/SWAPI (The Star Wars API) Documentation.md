# SWAPI (The Star Wars API) Documentation  
https://swapi.dev/
## Introduction
Welcome to SWAPI, the Star Wars API! This documentation will help you understand the available resources and how to access them using standard HTTP requests.  
This documentation will guide you through the API's structure, endpoints, and features, helping you get started with retrieving and using Star Wars data in your applications.
## Base URL
All API requests should be directed to the following base URL:  
https://swapi.py4e.com/api/   
Make sure to add this base URL to all endpoints. If you receive a 404 NOT FOUND error, double-check the endpoint URL and ensure the base URL is correctly used.  
## Getting Started
Let’s make your first request to the Star Wars API!  
You can use tools like httpie, postman, or cURL to make HTTP requests from the command line. In this example, we’ll request details about the first planet, Tatooine.
### Example Request URL
Using the httpie tool:  
http https://swapi.py4e.com/api/planets/1/
### Example Response Body
{   
        "climate": "Arid",   
        "diameter": "10465",   
        "gravity": "1 standard",   
        "name": "Tatooine",   
        "orbital_period": "304",   
        "population": "200000",   
        "residents": [   
            "https://swapi.py4e.com/api/people/1/",   
            "https://swapi.py4e.com/api/people/2/"   
        ],   
        "rotation_period": "23",   
        "surface_water": "1",   
        "terrain": "Desert",   
        "url": https://swapi.py4e.com/api/planets/1/   
     }   


**NOTE**: If your response looks slightly different, don't worry — new data may have been added since this documentation was last updated.
## Authentication
SWAPI is an open API that requires no authentication to access data. You can begin making requests immediately without an API key or token. As a result, only GET requests are supported; creating, updating, or deleting resources is not possible.   
If you notice incorrect data, please contact the maintainer via Twitter.
## Rate Limiting
To ensure fair usage and maintain service availability, SWAPI enforces rate limiting based on IP address. The current limit is 10,000 requests per day, sufficient to retrieve the entire dataset multiple times. Exceeding this limit results in too many requests. To handle this, wait until the next day to reset the rate limit for your IP address.
## JSON Schema
Access a resource’s JSON schema by appending ***/api/{resource}/schema*** to its endpoint:   
### Example Request URL   
GET https://swapi.py4e.com/api/people/schema/   
This returns a schema detailing fields, data types, and constraints, useful for validation or code generation.
## Searching
All resources support a search parameter that allows you to filter results. All searches will use case-insensitive partial matches on the set of search fields. To see the set of search fields for each resource, check out the individual resource documentation.   
For example, to find characters with "r2" in their name:   
### Example Request URL   
GET https://swapi.py4e.com/api/people/?search=r2
 

### Example Response Body:
{   
    "count": 1,   
    "next": null,   
    "previous": null,   
    "results": [   
        {   
            "name": "R2-D2",   
            "height": "96",   
            "mass": "32",    
            "hair_color": "n/a",     
            "skin_color": "white, blue",   
            "eye_color": "red",    
            "birth_year": "33BBY",    
            "gender": "n/a",    
            "homeworld": "https://swapi.py4e.com/api/planets/8/",    
            "films": [   
                "https://swapi.py4e.com/api/films/1/",    
                "https://swapi.py4e.com/api/films/2/",    
                "https://swapi.py4e.com/api/films/3/",     
                "https://swapi.py4e.com/api/films/4/",    
                "https://swapi.py4e.com/api/films/5/",    
                "https://swapi.py4e.com/api/films/6/",    
                "https://swapi.py4e.com/api/films/7/"    
            ],   
            "species": [    
                "https://swapi.py4e.com/api/species/2/"    
            ],    
            "vehicles": [],   
            "starships": [],    
            "created": "2014-12-10T15:11:50.376000Z",    
            "edited": "2014-12-20T21:17:50.311000Z",    
            "url": "https://swapi.py4e.com/api/people/3/"    
        }   
    ]   
}   
  