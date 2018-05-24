---
title: API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
#   - ruby
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/lord/slate'>Documentation Powered by</a>

# includes:
#   - errors

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

<!-- ```ruby
require 'mookh'

api = Mookh::APIClient.authorize!('auth')
``` -->
<!--
```python
import mookh

api = mookh.authorize('auth')
```

```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: auth"
``` -->

<!-- ```javascript
const mookh = require('mookh');

let api = mookh.authorize('auth');
``` -->

HTTP requests to the REST API are protected with HTTP Basic authentication


# Users

## Get All Users

+ Response 200 (application/json)

```python
import requests

api = mookh.authorize('auth')
api.users.get()
```

```shell
curl "https://api.mymookh.com/api/users/user/"
  -H "Authorization: auth"
curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/users/user/"
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

`GET https://api.mymookh.com/users/user/`

<!-- ### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
is_active | true | If set to false, the result will also include users
 -->

## Get a Specific User

+ Response 200 (application/json)

<!-- ```ruby
require 'mookh'

api = Mookh::APIClient.authorize!('auth')
api.users.get({<pk>})
``` -->

```python
import requests

api = mookh.authorize('auth')
api.users.get({<pk>})
```

```shell
curl "https://api.mymookh.com/users/user/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/users/user/<pk>"
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

`GET https://api.mymookh.com/users/b0d0cb74-0833-4af2-ab1f-51be03c1f64a`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the user to retrieve. The ID is in UUID format


## Create a user

### HTTP Request

`POST https://api.mymookh.com/users/user/`

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

`POST https://api.mymookh.com/users/verification/`

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

`GET https://api.mymookh.com/users/user/user_roles`

```python
import requests

api = mookh.authorize('auth')
api.users.get({})
```

```shell
curl "https://api.mymookh.com/users/user_roles/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/users/user_roles/"
```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.users.get();
```

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

`POST https://api.mymookh.com/stores/user/request`

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
api_url ="https://api.mymookh/request"
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
import requests

api = mookh.authorize('auth')
api.stores.get()
```

```shell
curl "https://api.mymookh.com/stores/store_type/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/store_type/"

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

`GET https://api.mmookh.com/stores/store_type/`

### Query Parameters

Parameter | Default | Description
--------- | ------- | -----------
store id  | true    | The store id is passed



## Create a store

### HTTP Request

`POST https://api.mymookh.com/stores/store/`

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

<!-- ```ruby
require 'mookh'

api = Mookh::APIClient.authorize!('auth')
api.stores.get({<pk>})
``` -->

```python
import requests

api = mookh.authorize('auth')
api.stores.get({<pk>})
```

```shell
curl "https://api.mymookh.com/stores/store/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/store/<pk>/"

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

`GET https://api.mymookh.com/stores/store/<pk>`

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the store is passed in UUID format



# events

## Create an event

### HTTP Request

`POST https://api.mymookh.com/stores/event_category/`

### POST Parameters
##### Required Parameters

Parameter     | Default   | Description
---------     | -------   | -----------
id            | Required  | created upon event creation. The ID is in UUID format
category_name |           | The event category
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

`POST https://api.mymookh.com/stores/event/public/`

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

`POST https://api.mymookh.com/stores/tickets/`

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

`POST https://api.mymookh.com/stores/order/`

### POST Parameters
The above command returns JSON structured like this:

```json
{
 "id":"af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
"customer": "mwangi",
"card": "2332111",
"store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
"agent": "Dee",
"agent_name": "phyl",
"event_name": "skiza",
"event": "null",
"order_items_summary": "null",
"order_detail": "null",
"order_status": "",
"order_number": "92873",
"currency": "Ksh",
"order_amount": "90",
"order_balance": "90",
"promo_code": "7662728",
"promo_code_value": "900",
"payment_method": "MPESA",
"order_type": "",
"payment_reference": "",
"order_udf": "",
"flag_email_sent": "false",
"flag_sms_sent":"false"
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

`POST https://api.mymookh.com/stores/order/validate_order`


### verify an order
### HTTP Request

`POST https://api.mymookh.com/stores/order/verify_order`


## Retrieve a particular order

```python
import requests

api = mookh.authorize('auth')
api.stores.get({<pk>})
```

```shell
curl "https://api.mymookh.com/stores/orders/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/orders/<pk>/"

```


```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.users.get(<pk>);
```


### HTTP Request

`GET https://api.mymookh.com/stores/orders/<pk>/"`

HTTP/1.1 200 OK

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the order to retrieve. The ID is in UUID format

> The above command returns JSON structured like this:

```json
{
    "id": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "customer": "bf3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
    "agent": "null",
    "agent_name": "pikado",
    "event_name": "color run",
    "event": "event",
    "order_items_summary": "lorm ipsum dolar sit",
    "order_detail": "",
    "order_status": "",
    "order_number": "39393",
    "currency": "Ksh",
    "order_amount": "20",
    "order_balance": "10",
    "promo_code": "FHK09",
    "promo_code_value": "",
    "payment_method": "",
    "order_type": "",
    "payment_reference": "",
    "order_udf": "",
    "flag_email_sent": "true",
    "flag_sms_sent": "true"

}
```

# promo

### create a promo_code

### HTTP Request

`POST https://api.mymookh.com/stores/promo_codes/`

### POST Parameters
The above command returns JSON structured like this:

```json
{
 "id":"af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
"is_active": "true",
"store": "63546dc4-f314-418a-9ccc-8eba97267499",
"event": "null",
"promo_name": "stylez",
"value": "3500",
"quantity": "20",
"promo_value": "900",
"is_percentage": "false",
"is_fixed": "false",
"is_custom": "true",
"start_date": "",
"end_date":"",
"code":"MY7s8s"
}

```
##### Required Parameters

Parameter     | Default    | Description
---------     | -------    | -----------
promo_name    |  Required  | Name associated with the promo
quantuty      |  Requierd  | number of promo codes available
start_date    | Required   | The start date promo is running
end_date      | Required   | The end of promo


## Retrieve a particular promo code

```python
import requests

api = mookh.authorize('auth')
api.stores.get({<pk>})
```

```shell
curl "https://api.mymookh.com/stores/promo_codes/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/promo_codes/<pk>/"

```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.users.get(<pk>);
```

### HTTP Request

`GET https://api.mymookh.com/stores/promo_codes/<pk>/"`

HTTP/1.1 200 OK

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the promo_code to retrieve. The ID is in UUID format


# products

The Mookh API lets you do the following with the Product resource.

### create a product category
### HTTP Request

`POST https://api.mymookh.com/products/category/`

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
sku           |  Required   | A unique code associated with a product
delivery_days  |  Required  | The number of delivery days


## Retrieve a particular product

```python
import requests

api = mookh.authorize('auth')
api.stores.get({<pk>})
```

```shell
curl "https://api.mymookh.com/products/product/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/products/product/<pk>"

```


```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.users.get(<pk>);
```


### HTTP Request

`GET https://api.mymookh.com/products/product/<pk>/`

HTTP/1.1 200 OK

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the product to retrieve. The ID is in UUID format

The above command returns JSON structured like this:

```json

{
    "id": "3635dc2c-8513-42dc-a81a-3ed1eff68d46",
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "category": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "category_name": "clothing",
    "name": "dress",
    "brand": "",
    "description": "maxi dress",
    "prices": [],
    "sku": "1237",
    "is_published": true,
    "is_featured": true,
    "slug": null,
    "is_returnable": false,
    "delivery_days": "11",
    "return_policy": null
}
```

This endpoint retrieves a specific product.


## Retrieve all products


```python
import requests

api = mookh.authorize('auth')
api.stores.get({<pk>})
```

```shell
  curl -X GET "https://api.mymookh.com/products/product/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/products/product/"
```


```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.users.get(<pk>);
```

### HTTP Request

`GET https://api.mymookh.com/products/`

HTTP/1.1 200 OK

The above command returns JSON structured like this:

```json

{
    "id": "619a45b8-84ba-4948-98f0-336476b18b19",
    "product": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
    "products_metadata":

        {
          "title": "Pink",
          "price": "199.00",
          "sku": "IPOD2008PINK",
          "position": 1,
          "option1": "Pink"
        }

 } ,
    "shipping_metadata": {},
    "promotion_metadata": {},
    "thumbnail": null,
    "quantity": null,
    "discount": "0.00",
    "is_published": false,
    "is_featured": false,
    "slug": null
},
{
    "id": "819a45b8-84ba-4948-98f0-336476b18b19",
    "product": "a36b8f6f-a86a-4446-bb2f-62d028904c67",
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
This endpoint retrieves a list of products in a particular store.



## product variants
### HTTP Request

`POST https://api.mymookh.com/products/variant/`

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

## create digital media file
### HTTP Request

`POST https://api.mymookh.com/digital_content/media/`

### POST Parameters
The above command returns JSON structured like this:


```json
{
    "id": "d075a0ef-2b63-4e61-8b3f-58e0fe35c0b3",
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "album": [],
    "artist": [],
    "genre": null,
    "name": "music",
    "description": "",
    "thumbnail": "",
    "country": "AO",
    "author": "coldplay",
    "metadata": {
        "1": "wwwwe",
        "2": "dddd"
    }
}  "slug": null
}

```

##### Required Parameters

Parameter     | Default     | Description
---------     | -------     | -----------
store       |  Required   | The store ID associated with the media type
genre       |  Required   |  the genre of the media type
metadata    |  Required   |  JSON field
author      |  Required   | name of the artist



## create digital album
### HTTP Request

`POST https://api.mymookh.com/digital_content/album/`

### POST Parameters
The above command returns JSON structured like this:

```json
{
    "id": "9e1390c1-5160-4fbe-ac04-9d104e2b0f75",
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "genre": null,
    "name": "",
    "description": "coldplay we are young",
    "thumbnail": "",
    "publish_date": "2018-05-22T21:54:00.861162Z",
    "country": "AO",
    "author": "",
    "prices": [],
    "is_published": false
}

```

##### Required Parameters

Parameter     | Default     | Description
---------     | -------     | -----------
store       |  Required   | The store ID associated with the media type
genre       |             |  the genre of the media type
description |  Required |  album description
author      |  Required   | name of the artist
country     |  Required   | country of origin, i.e KE

## create genre
### HTTP Request

`POST https://api.mymookh.com/digital_content/genre/`

### POST Parameters
The above command returns JSON structured like this:

##### Required Parameters

Parameter   | Default     | Description
---------   | -------     | -----------
name        |  Required   | genre of media files


```json
{
    "id": "04a88c8e-b370-4ce5-9c22-a1700618deb4",
    "name": "hiphop"
}

```

## create a media_file
### HTTP Request

`POST https://api.mymookh.com/digital_content/media_files/`

### POST Parameters
The above command returns JSON structured like this:

##### Required Parameters

Parameter   | Default     | Description
---------   | -------     | -----------
name        |  Required   | name asociated with the media files
digital_media |  Required   | i.e music
media_type |    Required     | i.e MP3, MP4
publish__date |    Required  | Date file is posted
metadata |    Required  | A JSON field that captures the media file data


```json
{
    "id": "5dbf07b1-0922-47d2-9314-3aac87b8ec2b",
    "name": "God's plan",
    "digital_media": "c25ba93c-fe98-46e3-b027-922820246f99",
    "media_type": "AUDIO",
    "media_format": "mp3",
    "description": "",
    "file": "",
    "media_player_url": "",
    "thumbnail": "",
    "publish_date": "2018-05-22T22:12:22.643277Z",
    "is_published": true,
    "metadata": {
        "price": "9.20",
        "size": "20mb"
    },
    "prices": []
}

```

## Artist

### HTTP Request

`POST https://api.mymookh.com/digital_content/artist/`

### POST Parameters
The above command returns JSON structured like this:


##### Required Parameters

Parameter   | Default     | Description
---------   | -------     | -----------
ID        |  Required   | Generated when creating an artist
User      |  Required   | PimaryKeyRelated Field, this fields takes the default authenticated user/ store manager
stage_name |    Required   | The name of the artist

```json
{
    "id": "e3855c1a-c4e7-4641-975e-6857df14881e",
    "user": "a9cfe48c-84fe-4d57-932d-db17d071d937",
    "stage_name": "Drake"
}

```


## Get a list of digital content

```python
import requests

api = mookh.authorize('auth')
api.stores.get()
```

```shell
curl "https://api.mymookh.com/digital_content"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/digital_content/"

```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.stores.get();
```

The above command returns JSON structured like this:

```json


```

This endpoint retrieves a list of all digital content.

### HTTP Request

`GET https://api.mymookh.com/digital_content/`


## Get a particular album


```python
import requests

api = mookh.authorize('auth')
api.stores.get()
```

```shell
curl "https://api.mymookh.com/album/<pk>"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/album/<pk>"

```

```javascript
const mookh = require('mookh');

let api = mookh.authorize('mookh');
let max = api.stores.get({<pk>});
```

>The above command returns JSON structured like this:

```json
{
    "id": "9e1390c1-5160-4fbe-ac04-9d104e2b0f75",
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "genre": null,
    "name": "",
    "description": "coldplay we are young",
    "thumbnail": "",
    "publish_date": "2018-05-22T21:54:00.861162Z",
    "country": "AO",
    "author": "",
    "prices": [],
    "is_published": false
}

```

This endpoint retrieves an album

### HTTP Request

`GET https://api.mymookh.com/digital_content/album/<pk>`

##### Required Parameters

Parameter   | Default     | Description
---------   | -------     | -----------
ID          |  Required      | The ID of the album in UUID format





