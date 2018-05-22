---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
  - <a href='https://github.com/lord/slate'>Documentation Powered by</a>

includes:
  - errors

search: true
---

# Introduction

Welcome to the Mookh API! You can use our API to access Mookh API endpoints, which can get information on various stores, products.... in our database.

Our APIS are built on REST and API request parameters are encoded in JSON. We have language bindings in Shell and Python!
To get staryted we have provided the code samples in Python, Java. API requests  have been provided. You can view code examples in the dark area to the right, and you can switch the programming language of the examples with the tabs in the top right.

# Getting Started

### Authentication

#### HTTP Header Parameters
With an OAuth 2.0 Access Token, an application can now invoke our APIs by including the access token in the HTTP header. Our APIs currently only supports application/json content type.

Parameter | Description
--------- | -----------
Authorization | OAuth 2.0 Access Token. Bearer keyword followed by a space and the OAuth 2.0 Access Token. Bearer <Access-Token>
Content-Type  |  Only application/json content type is supported.

> To authorize, use this code:

```ruby
require 'mookh'

api = Mookh::APIClient.authorize!('auth')
```

```python
import mookh

api = mookh.authorize('auth')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: auth"
```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('auth');
```

HTTP requests to the REST API are protected with HTTP Basic authentication


# Users

## Get All Users

```python
import mookh

api = mookh.authorize('auth')
api.users.get()
```

```shell
curl "http://example.com/api/users/user/"
  -H "Authorization: auth"
```

<!-- ```javascript
const mookh = require('mookh');

let api = users.authorize('mookh');
let kittens = api.users.get();
``` -->

> The above command returns JSON structured like this:

```json
[
   {
            "id": "b0d0cb74-0833-4af2-ab1f-51be03c1f64a",
            "first_name": "betty",
            "last_name": "wanjiku",
            "phone_number": "0756444333444",
            "email": "wanjikngib@gmail.com",
            "profile_photo": null,
            "groups": [
                1
            ]
        },
         {
            "id": "b0d0cb74-0833-4af2-ab1f-51be03c1f64a",
            "first_name": "betty",
            "last_name": "wanjiku",
            "phone_number": "0756444333444",
            "email": "wanjikumib@gmail.com",
            "profile_photo": null,
            "groups": [
                1
            ]
        }
]
```

This endpoint retrieves all users.

### HTTP Request

`GET http://mookh.com/api/users/user/`

<!-- ### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
is_active | true | If set to false, the result will also include users
 -->

## Get a Specific User

+ Response 200 (application/json)

```ruby
require 'mookh'

api = Mookh::APIClient.authorize!('auth')
api.users.get({<pk>})
```

```python
import mookh

api = mookh.authorize('auth')
api.users.get({<pk>})
```

```shell
curl "http://mookh.com/api/users/user/<pk>/"
  -H "Authorization: auth"
```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.users.get(<pk>);
```

> The above command returns JSON structured like this:

```json
{
    "id": "b0d0cb74-0833-4af2-ab1f-51be03c1f64a",
    "first_name": "betty",
    "last_name": "wanjiku",
    "phone_number": "0756444333444",
    "email": "wanjikumwangib@gmail.com",
    "profile_photo": null,
    "groups": [
        1
    ]
}
```

This endpoint retrieves a specific user.



### HTTP Request

`GET http://mookh.com/users/b0d0cb74-0833-4af2-ab1f-51be03c1f64a`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the user to retrieve. The ID is in UUID format


# stores

## Create a store type

### HTTP Request

`POST http://mookh.com/api/stores/user/request`

### POST Parameters
##### Required Parameters

Parameter  | Default  | Description
---------  | -------  | -----------
store_name | Required | The store name is required
description|          | A short description of the store
store_label|          | The store label is required
icon       |          | An icon of the store



```python

import requests
access_token = "Access_Token"
api_url ="htttps://mookh.api/request"
header =  { "Authorization": "Bearer %s" % access_token }
request = {
  "store_name": " ",
  "store_label":" ",
  "icon":" ",
  "description": " ",
}


response = requests.post(api_url, json = request, headers=headers)

print (response.text)
```

## Get All stores types

```python
import mookh

api = mookh.authorize('auth')
api.stores.get()
```

```shell
curl "http://mookh.com/api/stores/store_type/"
  -H "Authorization: auth"
```


The above command returns JSON structured like this:

```json
[
    {
            "id": "71965c7f-cc49-4815-a5f9-1b454478ac93",
            "store_name": "Sauti sol",
            "store_label": "ticketing",
            "icon": null,
            "description": "selling music albums"
        },
        {
            "id": "daf67422-0e40-4a6e-969e-7a58406e229a",
            "store_name": "mymookh",
            "store_label": "ticketing",
            "icon": null,
            "description": "selling tickets"
        }
]
```

This endpoint retrieves all store types.

### HTTP Request

`GET http://mookh.com/api/stores/store_type/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
store id  | true    | The store id is passed


## Get a Specific store

```ruby
require 'mookh'

api = Mookh::APIClient.authorize!('auth')
api.stores.get({<pk>})
```

```python
import mookh

api = mookh.authorize('auth')
api.stores.get({<pk>})
```

```shell
curl "http://mookh.com/api/stores/store/<pk>/"
  -H "Authorization: auth"
```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.stores.get(<pk>);
```

> The above command returns JSON structured like this:

```json
{
    "id": "b0d0cb74-0833-4af2-ab1f-51be03c1f64a",
    "manager_fk": "b0d0cb74-0833-4af2-ab1f-51be03c1f64a",
    "manager_name": "wanjiku",
    "store_name": "sauti sol",
    "store_type-fk": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "country": "KE",
}
```

This endpoint retrieves a specific store.


### HTTP Request

`GET http://mookh.com/stores/store/<pk>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the store to retrieve passed in UUID format


## Create a Specific store

### HTTP Request

`POST http://mookh.com/api/stores/store/request`

### POST Parameters
##### Required Parameters

Parameter     | Default   | Description
---------     | -------   | -----------
manager_fk    | Required  | This is the users/managers foreign key in UUID format
manager_name  |           | The store name is required
store_nama    |           | The name of the store
store_description|        | A short description of the store
store_type_fk  | Required | The store_type_fk maps the store to its type
country        | Required | The origin of country , i.e KE, UG


> The above POST request returns JSON structured like this:

```json


```




# products


# Digital content

