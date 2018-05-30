# Digital content

## create digital media file

### HTTP Request

`POST https://api.mymookh.com/digital_content/media/`

```shell
curl -d '{
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "album": [],
    "artist": [],
    "genre": null,
    "name": "music",
    "description": "",
    "thumbnail": "",
    "country": "AO",
    "author": "coldplay"
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/digital_content/media/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/digital_content/media/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
     "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "album": [],
    "artist": [],
    "genre": null,
    "name": "music",
    "description": "",
    "thumbnail": "",
    "country": "AO",
    "author": "coldplay"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/digital_content/media/"
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
            "album": [],
            "artist": [],
            "genre": null,
            "name": "music",
            "description": "",
            "thumbnail": "",
            "country": "AO",
            "author": "coldplay"
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
$url = 'https://api.mymookh.com/digital_content/media/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'store' => ' ',
  'album' => ' ',
  'artist' => ' '
  "icon": " ",
  "description": " ",
  "country":""

);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string); //post data

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

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

| Parameter | Default  | Description                                 |
| --------- | -------- | ------------------------------------------- |
| store     | Required | The store ID associated with the media type |
| genre     | Required | the genre of the media type                 |
| metadata  | Required | JSON field                                  |
| author    | Required | name of the artist                          |

## create digital album

### HTTP Request

`POST https://api.mymookh.com/digital_content/album/`

```shell
curl -d '{
     "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "genre": null,
    "name": "",
    "description": "coldplay we are young",
    "thumbnail": "",
    "publish_date": "2018-05-22T21:54:00.861162Z",
    "country": "AO"
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/digital_content/album/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/digital_content/album/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
    "store": "7b0e39bf-44c8-44da-8409-a0a2b8fe9263",
    "genre": null,
    "name": "",
    "description": "coldplay we are young",
    "thumbnail": "",
    "publish_date": "2018-05-22T21:54:00.861162Z",
    "country": "AO"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/digital_content/album/"
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
        "genre": null,
        "name": "",
        "description": "coldplay we are young",
        "thumbnail": "",
        "publish_date": "2018-05-22T21:54:00.861162Z",
        "country": "AO"
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
$url = 'https://api.mymookh.com/digital_content/album/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'store' => ' ',
  'album' => ' ',
  'artist' => ' '
  "icon": " ",
  "description": " ",
  "country":""

);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string); //post data

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

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

| Parameter   | Default  | Description                                 |
| ----------- | -------- | ------------------------------------------- |
| store       | Required | The store ID associated with the media type |
| genre       |          | the genre of the media type                 |
| description | Required | album description                           |
| author      | Required | name of the artist                          |
| country     | Required | country of origin, i.e KE                   |

## create genre

### HTTP Request

`POST https://api.mymookh.com/digital_content/genre/`

```shell
curl -d '{
     "name": "hiphop"
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/digital_content/genre/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/digital_content/genre/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
    "name": "hiphop"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/digital_content/genre/"
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
         "name": "hiphop"
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
$url = 'https://api.mymookh.com/digital_content/genre/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'name' => ' ',

);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string); //post data

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

### POST Parameters

The above command returns JSON structured like this:

##### Required Parameters

| Parameter | Default  | Description          |
| --------- | -------- | -------------------- |
| name      | Required | genre of media files |

```json
{
  "id": "04a88c8e-b370-4ce5-9c22-a1700618deb4",
  "name": "hiphop"
}
```

## create a media_file

### HTTP Request

`POST https://api.mymookh.com/digital_content/media_files/`

```shell
curl -d '{
    "name": "Gods plan",
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
    }
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/digital_content/media_files/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/digital_content/media_files/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
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
    }
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/digital_content/media_files/"
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
    }
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
$url = 'https://api.mymookh.com/digital_content/media_files/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'name' => ' ',
  'digital_media' => ' ',
  'media_type' => ' '
  "description": " ",
  "media_format": " ",
  "publish_date":" "

);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string); //post data

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

### POST Parameters

The above command returns JSON structured like this:

##### Required Parameters

| Parameter       | Default  | Description                                    |
| --------------- | -------- | ---------------------------------------------- |
| name            | Required | name asociated with the media files            |
| digital_media   | Required | i.e music                                      |
| media_type      | Required | i.e MP3, MP4                                   |
| publish\_\_date | Required | Date file is posted                            |
| metadata        | Required | A JSON field that captures the media file data |

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

```shell
curl -d '{
    "user": "a9cfe48c-84fe-4d57-932d-db17d071d937",
    "stage_name": "Drake"
}'
 -H "Content-Type: application/json"
 -X POST "https://api.mymookh.com/digital_content/artist/"
```

```python
import requests
import json

access_token = "Access_Token"
api_url = "https://api.mymookh.com/digital_content/artist/"
header =  { "Authorization": "Bearer %s" % access_token }
data = {
   "user": "a9cfe48c-84fe-4d57-932d-db17d071d937",
    "stage_name": "Drake"
}

response = requests.post(api_url, json = data, headers=headers)
print (response.text)
```

```Javascript
var request = require('request'),
  oauth_token = "Access_Token"
  url = "https://api.mymookh.com/digital_content/artist/"
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
            "user": "a9cfe48c-84fe-4d57-932d-db17d071d937",
            "stage_name": "Drake"
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
$url = 'https://api.mymookh.com/digital_content/artist/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);  //The url of the service
curl_setopt($curl, CURLOPT_HTTPHEADER, array('Content-Type:application/json','Authorization:Bearer ACCESS_TOKEN'));

$curl_post_data = array(
  //Fill in the request parameters with valid values
  'user' => ' ',
  'stage_name' => ' ',

);

$data_string = json_encode($curl_post_data);

curl_setopt($curl, CURLOPT_RETURNTRANSFER, true);
curl_setopt($curl, CURLOPT_POST, true);
curl_setopt($curl, CURLOPT_POSTFIELDS, $data_string); //post data

$result = curl_exec($curl);
print_r($result);

echo $result;
?>
```

### POST Parameters

The above command returns JSON structured like this:

##### Required Parameters

| Parameter  | Default  | Description                                                                             |
| ---------- | -------- | --------------------------------------------------------------------------------------- |
| ID         | Required | Generated when creating an artist                                                       |
| User       | Required | PimaryKeyRelated Field, this fields takes the default authenticated user/ store manager |
| stage_name | Required | The name of the artist                                                                  |

```json
{
  "id": "e3855c1a-c4e7-4641-975e-6857df14881e",
  "user": "a9cfe48c-84fe-4d57-932d-db17d071d937",
  "stage_name": "Drake"
}
```

## Get a list of digital content

```shell
curl "https://api.mymookh.com/digital_content"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/digital_content/"
```

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/digital_content/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url, headers=headers)
print(response.text)
```

```Javascript
let api_url = "https://api.mymookh.com/digital_content/"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

```php
<?php
$url = 'https://api.mymookh.com/digital_content/';

$curl = curl_init();
curl_setopt($curl, CURLOPT_URL, $url);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERAGENT , "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)");
curl_setopt($curl, CURLOPT_HEADER, 0);

$result = curl_exec($curl);
curl_close($curl);

?>
```

The above command returns JSON structured like this:

```json

```

This endpoint retrieves a list of all digital content.

### HTTP Request

`GET https://api.mymookh.com/digital_content/`

## Get a particular album

```shell
curl "https://api.mymookh.com/album/<pk>"
  -H "Authorization: auth"

curl -X GET -H "Content-Type: application/json" -H  "Accept: application/json"  "https://api.mymookh.com/album/<pk>"
```

```python
import requests
import json

api_token = 'api_token'
api_url = "https://api.mymookh.com/album/"
headers = {'Content-Type': 'application/json',
            'Accept': 'application/json'
           'Authorization': 'Bearer {0}'.format(api_token)}
response = requests.get(api_url({:id}), data=data)
print(response)
```

```Javascript
let api_url = "https://api.mymookh.com/album/<pk>"

 var xmlHttp = new XMLHttpRequest();
     xmlHttp.open( "GET", api_url, false );
     xmlHttp.send();
     var response = xmlHttp.responseText;
     return JSON.parse(response);
```

```php
<?php
$url = 'https://api.mymookh.com/album/';

$curl = curl_init();
$params = array("id" => "");
curl_setopt($curl, CURLOPT_URL, $url.'?'. $params);
curl_setopt($curl, CURLOPT_RETURNTRANSFER, 1);
curl_setopt($curl, CURLOPT_USERAGENT , "Mozilla/4.0 (compatible; MSIE 8.0; Windows NT 6.1)");
curl_setopt($curl, CURLOPT_HEADER, 0);

$result = curl_exec($curl);
curl_close($curl);

?>
```

> The above command returns JSON structured like this:

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

| Parameter | Default  | Description                        |
| --------- | -------- | ---------------------------------- |
| ID        | Required | The ID of the album in UUID format |
