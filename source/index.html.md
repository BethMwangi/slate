---
title: Mookh API Reference

language_tabs: # must be one of https://git.io/vQNgJ
  - shell
  - python
  - javascript

toc_footers:
  - <a href='#'>Sign Up for a Developer Key</a>
#   - <a href='https://github.com/lord/slate'>Documentation Powered by</a>

includes:
  - store
  - products
  - digital
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


```shell
# With shell, you can just pass the correct header with each request
curl "api_endpoint_here"
  -H "Authorization: auth"
``` -->

```javascript
let api_url = "https://api.mymookh.com/"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

HTTP requests to the REST API are protected with HTTP Basic authentication


# Users

## Get All Users

+ Response 200 (application/json)

```shell
curl "https://api.mymookh.com/api/users/user/"
  -H "Authorization: auth"
curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/users/user/"
```

```python
import json
import requests
api_token = 'api_token'
api_url = "https://api.mymookh.com/users/user/"
data = {}
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url, data=data)
print(response)

```

```javascript
let api_url = "https://api.mymookh.com/users/user/"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

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


```python
import json
import requests
api_token = 'api_token'
api_url = "https://api.mymookh.com/api/users/user/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url{:id}, headers=headers)
print(response)
```

```shell
curl "https://api.mymookh.com/users/user/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/users/user/<pk>"
```

```javascript
// const mookh = require('mookh');

// let api = mookh.authorize('mookh');
// let max = api.users.get(<pk>);
```

```javascript
let api_url = "https://api.mymookh.com/users/user/<pk>"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
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
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/users/user/user_roles/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url, headers=headers)
print(response)
```

```shell
curl "https://api.mymookh.com/users/user_roles/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/users/user_roles/"
```


```javascript
let api_url = "https://api.mymookh.com/users/user_roles/"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     return xmlHttp.responseText;
```

### GET Parameters
The above command returns JSON structured like this:

```json
[
    "store_owner",
    "store_agent",
    "super_admin"
]
```

+ Response Status  200 (application/json)


# events

## Create an event

### HTTP Request

`POST https://api.mymookh.com/stores/event_category/`

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/event_category/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
 "category_name": "cat",
    "event_label": "conference",
    "category_metadata": null
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)

```

```javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/stores/event_category/"
  auth = "Bearer " + oauth_token;

  request(
    {
      method: 'POST'
      url : url,
      headers : {
        'Accept': 'application/json',
        'Content-Type': 'application/json',
        "Authorization" : auth
      },
    json : {
     "category_name": "cat",
    "event_label": "conference",
    "category_metadata": null
    }
  },
    function (error, response, body) {
      // TODO: Use the body object to extract the response
      console.log(body)
    }
  )
```

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


```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/event/public/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
  "event_name": "Color run",
    "event_venue": null,
    "event_description": "the color run event",
    "event_category_fk": "711ab531-511a-4ee3-8b7e-676ecc8f753d",
    "parent_event_id": null,
    "category_name": "cat",
    "event_poster": null,
    "store_fk": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "store_type_id": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "store_name": "story"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)

```

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

```shell

curl -d '{  "ticket_name": "Color run", "event_fk": "bd0e90a0-1f81-4d9a-90f7-d63e088335a3", "schedule_name": null, "ticket_description": null,"schedule_fk": null,
    "ticket_value": "0.00"}' s
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/stores/tickets/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/tickets/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
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
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)

```


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

```shell

curl -d '{
"customer": "mwangi","card": "2332111","store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
"agent": "Dee",
"agent_name": "phyl",
"event_name": "skiza",
"event": "null",
"order_items_summary": "null",
"order_detail": "null",
"order_status": "",
"order_number": "92873",
"currency": "Ksh",
"order_amount": "90"}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/stores/order/"
```


```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/order/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
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
"payment_method": "MPESA"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)

```


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

```shell

curl -d '{ "customer": "bf3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
    "card": "78387",
    "agent_name": "pikado",
    "event_name": "color run",
    "event": "event",
    "order_items_summary": "lorm ipsum dolar sit"

}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/stores/order/validate_order"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/order/validate_order/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
    "customer": "bf3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
    "card": "78387",
    "agent_name": "pikado",
    "event_name": "color run",
    "event": "event",
    "order_items_summary": "lorm ipsum dolar sit",
    "order_detail": "",
    "order_status": "",
    "order_number": "39393",
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)

```


### verify an order
### HTTP Request

`POST https://api.mymookh.com/stores/order/verify_order`
```shell

curl -d '{ "customer": "bf3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
    "card": "78387",
    "agent_name": "pikado",
    "event_name": "color run",
    "event": "event",
    "order_items_summary": "lorm ipsum dolar sit"

}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/stores/order/verify_order"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/order/verify_order/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
    "customer": "bf3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "store_fk": "63546dc4-f314-418a-9ccc-8eba97267499",
    "card": "78387",
    "agent_name": "pikado",
    "event_name": "color run",
    "event": "event",
    "order_items_summary": "lorm ipsum dolar sit",
    "order_detail": "lorem ipsum",
    "order_status": "",
    "order_number": "39393",
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)

```


## Retrieve a particular order

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/api/stores/orders/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url({:id}), headers=headers)
print(response.text)
```

```shell
curl "https://api.mymookh.com/stores/orders/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/orders/<pk>/"

```
```javascript
let api_url = "https://api.mymookh.com/stores/orders/<pk>"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
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

```shell

curl -d '{ "store": "63546dc4-f314-418a-9ccc-8eba97267499","event": "null", "promo_name": "stylez", "value": "3500"}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/stores/promo_codes/<pk>/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/promo_codes/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
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

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

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
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/api/stores/promo_codes/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url({:id}), headers=headers)
print(response.text)

```

```shell
curl "https://api.mymookh.com/stores/promo_codes/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/promo_codes/<pk>/"

```


```javascript
let api_url = "https://api.mymookh.com/stores/promo_codes/<pk>"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

### HTTP Request

`GET https://api.mymookh.com/stores/promo_codes/<pk>/"`

HTTP/1.1 200 OK

### URL Parameters

Parameter | Description
--------- | -----------
ID        | The ID of the promo_code to retrieve. The ID is in UUID format





