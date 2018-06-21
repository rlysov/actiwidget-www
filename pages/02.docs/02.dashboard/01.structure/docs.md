---
title: 'Dashboard structure'
taxonomy:
    category:
        - docs
---

Every dashboard in **ACTIWIDGET** describes in JSON-format and has three basic sections:

* Basic dashboard properties and attributes
* User parameters definition
* Pages collection

### Basic dashboard structure


![Dashboard structure](structure.png?lightbox=800,600&resize=400,400)

**Dashboard JSON-format:**
```json
{
	"title": "My Dashboard Title",
	"bgcolor": "#AAAAAA", 	//optional
	"darktheme": true,		//optional
	"params": {...},		//optional
	"plugins": [...],		//optional
	"pages": [
		{...},
		{...}
	]
}
```


### Dashboard top level properties

| Property | Type | Description |
| ------ | ----------- |
| title   | string | Dashboard title. Displaying on top of screen  |
| bgcolor | string (_optional_) | Set dashboard background color. Default: null. Ex: #AAAAAA, rgb(10,20,30) |
| darktheme  | bool (_optional_)| If true display dashboard in dark theme. Default: false |
| [params](../user-params)  | object (_optional_) | Describes set of [user specific parameters](../user-params). Use to specify login\password, api-key and etc.  |
| [plugins](../../plugins) | array of strings (_optional_) | Array of absolute URLs to plugins used with this dashboard |
| [pages](../pages)  | array of objects | Array of [Pages](../pages) objects. Every page is a container for widgets |

