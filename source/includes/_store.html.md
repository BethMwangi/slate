
# stores

## Create a store type

### HTTP Request

`POST https://api.mymookh.com/stores/store_type/`

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
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/store_type/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
  "store_name": " ",
  "store_label":" ",
  "icon":" ",
  "description": " ",
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/stores/store_type/"
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
        "store_name": " ",
        "store_label":" ",
        "icon":" ",
        "description": " ",
    }
  },
    function (error, response, body) {
      // TODO: Use the body object to extract the response
      console.log(body)
    }
  )
```

## Get All stores types

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/api/stores/store_type/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url, headers=headers)
print(response.text)

```

```shell
curl "https://api.mymookh.com/stores/store_type/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/store_type/"

```

```javascript
let api_url = "https://api.mymookh.com/users/store_type/"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     return xmlHttp.responseText;
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

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/stores/store/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
   "manager_fk": "be67ea3a-774c-4cce-9887-a8fdcc3fd54c",
    "manager_name": "beth wanjiku",
    "created_by": null,
    "store_name": "story",
    "balances": 0,
    "store_description": null,
    "store_type_fk": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "store_type_name": "mymookh",
    "store_type_description": "selling tickets"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/stores/store/"
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
    "manager_fk": "be67ea3a-774c-4cce-9887-a8fdcc3fd54c",
    "manager_name": "beth wanjiku",
    "created_by": null,
    "store_name": "story",
    "balances": 0,
    "store_description": null,
    "store_type_fk": "daf67422-0e40-4a6e-969e-7a58406e229a",
    "store_type_name": "mymookh",
    "store_type_description": "selling tickets"
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



```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/api/stores/store/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url({:d}), headers=headers)
print(response.text)
```

```shell
curl "https://api.mymookh.com/stores/store/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/stores/store/<pk>/"

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
