---
title: 'User parameters'
taxonomy:
    category:
        - docs
---

Dashboard have a a list of parameters specified by end-user. Use it for get from user 
login\password, API-key or other specific user data.

Paramereter values will be added automatically to every widget data request. API-backend can process 
param value and send appropriate responce.

To add user param to dashboard use "params" section in JSON.

```json
{
	"title": "Dashboard with params",
	"params": {		//<-- Add parameters here
		"param1": {...},
		"param2": {...}
	}, 	
	"pages": [...]
}
```

Screenshot below shows dashboard with two user parameters **Location** and **Units**:

![Dashboard user parameters](userparams.png?lightbox=800,600&resize=400,400)


### Parameter object properties


All types has following properties:

| Property | Type | Description |
| ------ | ------- | ---- |
| [type](#param-type) | string | Type of UI HTML-element to display\set value. Can be `text`, `password` or `select`. Default: text |
| [sendMethod](#param-sendMethod) | string | How the parameter value will be passed to server. `GET`, `POST`, `HEADER`, `URL` allowed. Default: GET |
| editable | bool | If false - user cannot change parameter value in mobile app. Use with **value** property to create read-only parameters. Default: true |
| label | string | The user friendly parameter name  |
| value | string | Default value  |
| values | array of strings\object of {key: value} pairs| Define list of values for parameter with type=**select**. Pass values as array of strings ```["val1", "val2", "val3"]``` or as array of key-value pairs ```[{"fname": "John", "lname": "Smith"}]```  |


#### [**type**] property <a id="param-type"></a>

There are three types of user parameters:

* **text** - just simple `<input type="text">` element
* **password** - `<input type="password">` element
* **select** - choose one from list (`<select></select>` element). Use additional property **values** to set list of possible options


#### [**sendMethod**] property <a id="param-sendMethod"></a>

Paramereter values will be added automatically for all widgets to every widget data request and **sendMethod** propery allow to
specify exactly рщц parameter will be send.

There are several options to pass parameter value:
* **GET** - param will be added to widget `dataUrl` in URL query path `?name=value`
* **POST** - param value will be passed in POST part of HTTP request
* **HEADER** - param value will be passed as HTTP header
* **URL** - value will be inserted right in dataUrl. It is nessesary use template syntax in widget `dataUrl`. Use param name with braces in URL to specify the place to insert the value. Widget dataUrl example: `"dataUrl": "http://api.example.com/{param1}/{param2}"`


#### Examples

Sample dashboard with API-key in HTTP-header authorization:

```json
{
	"title": "...",
	"params": {
		"APIKEY": {
			"sendMethod": "HEADER"
		}
	},
	"pages": [...]
}
```

Sample dashboard with login\password authorization (use with HTTPS only for security reasons ):
```json
{
	"title": "...",
	"params": {
		"login": {
			"type": "text"
		},
		"password": {
			"type": "password",
			"sendMethod": "POST"
		}
	},
	"pages": [...]
}
```

Yahoo Weather dashboard with two parameters:

```json
{
	"title": "...",
	"params": {
		"location": {
			"sendMethod": "URL",
			"value": "London, GB"
		},
		"units": {
			"type": "select",
			"sendMethod": "URL",
			"values": {
				"f": "Fahrenheit",
				"c": "Celsius"
			},
			"value": "f"
		}
	},
	"pages": [...]
}
```
