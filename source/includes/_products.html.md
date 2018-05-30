# products

The Mookh API lets you do the following with the Product resource.

### create a product category

### HTTP Request

`POST https://api.mymookh.com/products/category/`

```shell
curl -d '{  "name": "phone",
    "description": null,
    "parent": "63546dc4-f314-418a-9ccc-8eba97267499",
    "category_metadata": {}
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/products/category/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/products/category/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
    "name": "phone",
    "description": null,
    "parent": "63546dc4-f314-418a-9ccc-8eba97267499",
    "category_metadata": {}
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/products/category/"
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
            "name": "phone",
            "description": null,
            "parent": "63546dc4-f314-418a-9ccc-8eba97267499",
            "category_metadata": {}
    }
  },
    function (error, response, body) {
      // TODO: Use the body object to extract the response
      console.log(body)
    }
  )
```

```PHP
<?php
$url = 'https://api.mymookh.com/products/category/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'name' => ' ',
  'description' => ' ',
  'parent' => ' ',
  'category_metadata' => ' '
);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string);

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

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

| Parameter | Default  | Description                 |
| --------- | -------- | --------------------------- |
| name      | Required | The category of the product |

### create a specific product

### HTTP Request

`POST http://mookh.com/api/products/product/`

```shell
curl -d '{
     "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "category": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "category_name": "phone",
    "name": "speaker",
    "brand": "",
    "description": "bluetooth speakers"
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/products/product/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/products/product/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "category": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
    "category_name": "phone",
    "name": "speaker",
    "brand": "",
    "description": "bluetooth speakers"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/products/product/"
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
        "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
        "category": "af3903ca-5d5c-4afd-9c1f-3f896fc0d5d8",
        "category_name": "phone",
        "name": "speaker",
        "brand": "",
        "description": "bluetooth speakers"
    }
  },
    function (error, response, body) {
      // TODO: Use the body object to extract the response
      console.log(body)
    }
  )
```

```php
<?php
$url = 'https://api.mymookh.com/products/product/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'store' => ' ',
  'category' => ' ',
  'category_name' => ' ',
  'name' => ' ',
  'brand' => ' ',
  'description' => ' '
);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string);

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

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

| Parameter     | Default  | Description                                         |
| ------------- | -------- | --------------------------------------------------- |
| store         | Required | The store ID associated with the product created    |
| category      | Required | The product category ID associated with the product |
| sku           | Required | A unique code associated with a product             |
| delivery_days | Required | The number of delivery days                         |

## Retrieve a particular product

```shell
curl "https://api.mymookh.com/products/product/<pk>/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/products/product/<pk>"
```

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/products/product/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url({:id}), headers=headers)
print(response.text)
```

```Javascript
let api_url = "https://api.mymookh.com/products/product/<pk>"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

```php
<?php
$url = 'https://api.mymookh.com/products/product/';

$curl = curl_init();
$params = array("id" => "");
curl_setopt($curl, CURLOPT_URL, $url.'?'. $params);  //The url of the service
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERAGENT , "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)");
curl_setopt($curl, CURLOPT_HEADER, 0);

$result = curl_exec($curl);
curl_close($curl);

?>
```

### HTTP Request

`GET https://api.mymookh.com/products/product/<pk>/`

HTTP/1.1 200 OK

### URL Parameters

| Parameter | Description                                                 |
| --------- | ----------------------------------------------------------- |
| ID        | The ID of the product to retrieve. The ID is in UUID format |

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

```shell
  curl -X GET "https://api.mymookh.com/products/"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/products/"
```

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/api/products/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url, headers=headers)
print(response.text)
```

```Javascript
let api_url = "https://api.mymookh.com/products/"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

```php
<?php
$url = 'https://api.mymookh.com/products/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERAGENT , "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)");
curl_setopt($curl, CURLOPT_HEADER, 0);

$result = curl_exec($curl);
curl_close($curl);

?>
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

```shell
curl -d '{
    "product": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
    "products_metadata": "",
    "shipping_metadata": "",
    "promotion_metadata": ""
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/products/variant/"
```

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/api/products/variant/"
data = {
    "product": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
    "products_metadata": "",
     "shipping_metadata": "",
    "promotion_metadata": ""
    }
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.post(api_url, json=data,  headers=headers)
print(response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/products/variant/"
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
        "product": "a56b8f6f-a86a-4446-bb2f-62d028904c67",
        "products_metadata": "",
        "shipping_metadata": "",
        "promotion_metadata": ""
    }
  },
    function (error, response, body) {
      // TODO: Use the body object to extract the response
      console.log(body)
    }
  )
```

```php
<?php
$url = 'https://api.mymookh.com/products/variant/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'product' => ' ',
  'products_metadata' => ' ',
  'shipping_metadata' => ' ',
  'promotion_metadata' => ' '
);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string);

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

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

| Parameter          | Default  | Description                                                     |
| ------------------ | -------- | --------------------------------------------------------------- |
| product            | Required | The product ID associated with the product                      |
| products_metadata  | Required | metadata refers to the variations of the product in JSON format |
| shipping_metadata  |          |
| promotion_metadata |          | types of promotions to choose from                              |

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
