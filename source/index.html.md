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


## Create a user

### HTTP Request

`POST http://mookh.com/api/users/user/`

### POST Parameters
The above command returns JSON structured like this:

```json
{
    "id": "be67ea3a-774c-4cce-9887-a8fdcc3fd54c",
    "first_name": "beth",
    "last_name": "wanjiku",
    "phone_number": "0729929972",
    "email": "wanjikumwangi@gmail.com",
    "profile_photo": null,
    "groups": [
        1
    ]
}
```
##### Required Parameters

Parameter     | Default    | Description
---------     | -------    | -----------
email         |  Required  | The store name is required
password      |  Required  | password to use during registration
confirm_password| Required | The confirm password should match the password
first_name    |            | The  first name of the user
last_name     |            | The  last name of the registering user

A verification code is sent to the email upon registration

## Verify a user

### HTTP Request

`POST http://mookh.com/api/users/verification/`

##### Required Parameters

Parameter     | Default    | Description
---------     | -------    | -----------
code          |  Required  | A 5 digit number sent to the email for verification
The above command returns JSON structured like this:

```json
{
    "message": [
        "Account verified successfully"
    ]
}
```
+ Response Status  200 (application/json)

## Get user roles

### HTTP Request

`GET http://mookh.com/api/users/user/user_roles`

### POST Parameters
The above command returns JSON structured like this:

```json
[
    "store_owner",
    "store_agent",
    "super_admin"
]
```

+ Response Status  200 (application/json)


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



## Create a store

### HTTP Request

`POST http://mookh.com/api/stores/store/`

### POST Parameters
##### Required Parameters

Parameter  | Default  | Description
---------  | -------  | -----------
store_name | Required | The store name is required
description|          | A short description of the store,i.e ticketing
store_type_fk|  Required | The store type ID in UUID format that links to th estore
store_type_fk  | Required | The store_type_fk maps the store to its type
country        | Required | The country of operation , i.e KE, UG



The above command returns JSON structured like this:

```json
{
    "id": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "manager_fk": "be67ea3a-774c-4cce-9887-a8fdcc3fd54c",
    "manager_name": "beth wanjiku",
    "created_by": null,
    "store_name": "story",
    "balances": 0,
    "store_description": null,
    "store_type_fk": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "store_type_name": "mymookh",
    "store_type_description": "selling tickets",
    "poster": null,
    "country": "KE",
    "email": null,
    "published": false,
    "store_url": null
}
```

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
    "id": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "manager_fk": "be67ea3a-774c-4cce-9887-a8fdcc3fd54c",
    "manager_name": "beth wanjiku",
    "created_by": null,
    "store_name": "sautisol",
    "balances": 0,
    "store_description": null,
    "store_type_fk": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "store_type_name": "mymookh",
    "store_type_description": "selling tickets",
    "poster": null,
    "country": "KE",
    "email": null,
    "published": false,
    "store_url": null
}
```

This endpoint retrieves a specific store.
STATUS 200 OK

### HTTP Request

`GET http://mookh.com/stores/store/<pk>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the store is passed in UUID format



# events

## Create an event

### HTTP Request

`POST http://mookh.com/api/stores/event_category/`

### POST Parameters
##### Required Parameters

Parameter     | Default   | Description
---------     | -------   | -----------
id            | Required  | created upon event creation. The ID is in UUID format
category_name |           | The eveny category
event_label   |           |
category_metadata |       | A JSONField category data to choose from


```json
{
    "id": "711ab531-511a-4ee3-8b7e-676ecc8f753d",
    "category_name": "cat",
    "event_label": "conference",
    "category_metadata": null
}


```




## Make an event public

### HTTP Request

`POST http://mookh.com/api/stores/event/public/`

### POST Parameters
##### Required Parameters

Parameter     | Default   | Description
---------     | -------   | -----------
event_name |           | The eveny name, i.e COLOR RUN
event_category_fk  | Required      | The ID of event_category associated with the event in UUID format
event_description | Required       | A short description of the public event
start_date | Required       | The date set for the public event


```json
{
    "id": "bd0e90a0-1f81-4d9a-90f7-d63e088335a3",
    "event_name": "Color run",
    "event_venue": null,
    "event_description": "the color run event",
    "event_category_fk": "711ab531-511a-4ee3-8b7e-676ecc8f753d",
    "parent_event_id": null,
    "category_name": "cat",
    "event_poster": null,
    "store_fk": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "store_type_id": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "store_name": "story",
    "store_contacts": {
        "emails": [],
        "phone_numbers": []
    },
    "start_date": "2018-01-05T22:08:37.838000Z",
    "end_date": null,
    "is_free": false,
    "is_private": false,
    "is_published": false,
    "has_complimentary": false,
    "event_metadata": {},
    "tickets": [],
    "tickets_count_by_category": [],
    "tickets_total_sales": 0,
    "tickets_sales_by_platform": 0,
    "tickets_by_status": 0,
    "total_event_tickets": null,
    "schedule": [],
    "sub_events": [],
    "created": "2018-05-22T20:36:22.899728Z"
}

```
+ Response 201 Created (application/json)


# tickets
## Create store tickets

### HTTP Request

`POST http://mookh.com/api/stores/tickets/`

### POST Parameters
##### Required Parameters

Parameter     | Default   | Description
---------     | -------   | -----------
ticket_name |   Required   | The eveny name, i.e COLOR RUN TICKET
event_fk    | Required     | The event ID of associated with the ticket in UUID format
quantity    | Required     | The number of tickets available for sale at the store

```json
{
    "id": "54b7aee8-5a65-4a20-888c-8c26676b763c",
    "ticket_name": "Color run",
    "event_fk": "bd0e90a0-1f81-4d9a-90f7-d63e088335a3",
    "schedule_name": null,
    "ticket_description": null,
    "schedule_fk": null,
    "ticket_value": "0.00",
    "is_published": false,
    "ticket_metadata": {},
    "quantity": 20,
    "tickets_bought": 0,
    "tickets_available": 20,
    "is_available": true
}

```
+ Response 201 Created (application/json)


## Create store schedule


```json
{
    "id": "25f7a01b-e088-4fc8-a5fe-e79086faa097",
    "event_name": null,
    "event_fk": null,
    "title": null,
    "allDay": false,
    "repeats": false,
    "dow": [],
    "start": null,
    "end": null
}

```
+ Response 201 Created (application/json)


# orders

### create an order

### HTTP Request

`POST http://mookh.com/api/stores/order/`

### POST Parameters
The above command returns JSON structured like this:

```json

]
}
```
##### Required Parameters

Parameter     | Default    | Description
---------     | -------    | -----------
customer      |  Required  | A customerSerializer associated with the customer order
card          |             | card serializer
store_fk      | Required     | The stores ID associated with the order
order_detail  | Required  | The details of the order

### validate an order
### HTTP Request

`POST http://mookh.com/api/stores/order/validate_order`


### verify an order
### HTTP Request

`POST http://mookh.com/api/stores/order/verify_order`


# products

### create a product category
### HTTP Request

`POST http://mookh.com/api/products/category/`

### POST Parameters
The above command returns JSON structured like this:

```json


{
    "id": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "name": "phone",
    "description": null,
    "parent": "63546dc4-f314-418a-9ccc-8eba97267499",
    "category_metadata": {}
}
```

##### Required Parameters

Parameter     | Default    | Description
---------     | -------    | -----------
name          |  Required  | The category of the product


### create a specific product
### HTTP Request

`POST http://mookh.com/api/products/product/`

### POST Parameters
The above command returns JSON structured like this:

```json

{
    "id": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "category": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "category_name": "phone",
    "name": "speaker",
    "brand": "",
    "description": "bluetooth speakers",
    "prices": [],
    "sku": "1234",
    "is_published": false,
    "is_featured": false,
    "slug": null,
    "is_returnable": false,
    "delivery_days": "12",
    "return_policy": null
}
```

##### Required Parameters

Parameter     | Default     | Description
---------     | -------     | -----------
store         |  Required   | The store ID associated with the product created
category      |  Required   | The product category ID associated with the product
sku           |  Required   | A unique code associted with a product
delivery_days  |  Required  | The number of delivery days


### product variants
### HTTP Request

`POST http://mookh.com/api/products/variant/`

### POST Parameters
The above command returns JSON structured like this:

```json

{
    "id": "619a45b8-84ba-4948-98f0-336476b18b19",
    "product": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
    "products_metadata": {},
    "shipping_metadata": {},
    "promotion_metadata": {},
    "thumbnail": null,
    "quantity": null,
    "discount": "0.00",
    "is_published": false,
    "is_featured": false,
    "slug": null
}

```

##### Required Parameters

Parameter     | Default     | Description
---------     | -------     | -----------
product       |  Required   | The product ID associated with the product
products_metadata |  Required   | metadata refers to the variations of the product in JSON format
shipping_metadata|         |
promotion_metadata |       | types of promotions to choose from


### POST Parameters
The above command returns JSON structured like this:

```json
{
    "id": "619a45b8-84ba-4948-98f0-336476b18b19",
    "product": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
    "products_metadata": {},
    "shipping_metadata": {},
    "promotion_metadata": {},
    "thumbnail": null,
    "quantity": null,
    "discount": "0.00",
    "is_published": false,
    "is_featured": false,
    "slug": null
}

```


# Digital content

