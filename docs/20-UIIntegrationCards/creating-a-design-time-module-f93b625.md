<!-- loiof93b625f9bb14a4e832b94f2dce25b18 -->

# Creating a Design Time Module

A new design time module is used to configure and implement functionality used in the card editor. The editor is launched by the host environment for different personas and uses the design time module to create the user interface.

When the user creates a new UI Card project using the *Yeoman* generator, the design time module is already available in the generated project. \(“dt” folder and the inner “configuration.js” file are ready, and “designtime” property is specified as “dt/configuration” in the manifest.json\)

For existing projects without a design time module setup, when the user opens the property editor, the design time module is set up automatically.

**Create a design time module and register it in the cards manifest**

Advanced design time configuration and implementation should happen outside the manifest of the card. With that design time code won’t harm or influence the runtime or the card instance for the end user.

Add the following initial module setup into the `dt/configuration.js` file.

```
sap.ui.define(["sap/ui/integration/Designtime"], function (
	Designtime
) {
	"use strict";
	return function () {
		return new Designtime({
			form: {
				items: {
					//here goes the configuration
				}
			},
			preview: {
				modes: "Abstract"
			}
		});
	};
});
```

Similar to a Card Extension, the design time module is registered in the manifest. As soon as the Editor is launched.

```
"sap.card": {
	"designtime": "dt/configuration"
}
```

**Configure the editor's form**

Within the configuration, the form section contains the items that are shown in the Editor

```
sap.ui.define(["sap/ui/integration/Designtime"], function (
	Designtime
) {
	"use strict";
	return function () {
		return new Designtime({
			form: {
				items: {
 
				}
			},
			preview: {
				modes: "Abstract"
			}
		});
	};
});
```

**Form items**

**Field Type Items**


<table>
<tr>
<th valign="top">

Property



</th>
<th valign="top">

Type



</th>
<th valign="top">

Required



</th>
<th valign="top">

Default



</th>
<th valign="top">

Description



</th>
</tr>
<tr>
<td valign="top">

manifestpath



</td>
<td valign="top">

string



</td>
<td valign="top">

Yes



</td>
<td valign="top">

 



</td>
<td valign="top">

Path to the manifest value that should be edited. In case the type of the item is "group" the path can be omitted.

`manifestpath : "sap.card/configuration/parameters/title/value"`



</td>
</tr>
<tr>
<td valign="top">

type



</td>
<td valign="top">

string



</td>
<td valign="top">

Yes



</td>
<td valign="top">

string



</td>
<td valign="top">

type of the value in the manifest that is edited. Currently "string", "integer", "number", "date", "datetime", "boolean", "string\[\]" are supported.

type="group" in an item allows to set a group title within the form to cluster elements. For a group typed item the manifestpath setting can be omitted. A label should be provided.

`type : "string"`



</td>
</tr>
<tr>
<td valign="top">

label



</td>
<td valign="top">

string



</td>
<td valign="top">

No



</td>
<td valign="top">

Name of the item in the form/items collection



</td>
<td valign="top">

Defines the label string. This value can be bound to values in the i18n file used in the connected Card.

`label : "fixedString`

`label : "{i18n>translatedStringKey}"`



</td>
</tr>
<tr>
<td valign="top">

defaultValue



</td>
<td valign="top">

any



</td>
<td valign="top">

No



</td>
<td valign="top">

Depending on type property



</td>
<td valign="top">

Defines the default value that is used if the current value in the manifest for this property is empty.

```
defaultValue : "stringValue" //string type
defaultValue : true //boolean type
"
defaultValue : "{i18n>translatedDefaultKey}" //trnaslatedDefaultValue for strings
```



</td>
</tr>
<tr>
<td valign="top">

required



</td>
<td valign="top">

boolean



</td>
<td valign="top">

No



</td>
<td valign="top">

false



</td>
<td valign="top">

Defines whether the value is required or not. The editors label for the field gets a "\*" to indicate this state.

`required: true`



</td>
</tr>
<tr>
<td valign="top">

visible



</td>
<td valign="top">

boolean



</td>
<td valign="top">

 



</td>
<td valign="top">

true



</td>
<td valign="top">

Defines whether the value is visible in the editor or not. For technical parameters, it might be needed to hide them from the user. In future version an administrator is able to change the visible property for the page/content administrator. This will only apply for parameters that are visible to the administrator.

`visible: true`



</td>
</tr>
<tr>
<td valign="top">

translatable



</td>
<td valign="top">

boolean



</td>
<td valign="top">

No



</td>
<td valign="top">

false



</td>
<td valign="top">

Defines whether the value is potentially translatable and should be shown in the Card Editor in translation mode. This setting should be used for fields of type string only. to indicate this state.

`translatable: true`



</td>
</tr>
<tr>
<td valign="top">

cols



</td>
<td valign="top">

1 or 2



</td>
<td valign="top">

No



</td>
<td valign="top">

2



</td>
<td valign="top">

By default, the form in the editor spans field to its two columns. Setting cols=1 in two sibling items, will allow to align two fields next to each other

`cols: 1`



</td>
</tr>
<tr>
<td valign="top">

allowDynamicValues



</td>
<td valign="top">

boolean



</td>
<td valign="top">

No



</td>
<td valign="top">

depending



</td>
<td valign="top">

Defines whether the value can be bound to a context value of the host environment. The default value for an administrator and content admin is true. In translation mode this property is ignored. To activate the feature additionally the allowDynamicValues property of the Card Editor control needs to be enabled.

`translatable: true`



</td>
</tr>
<tr>
<td valign="top">

allowSettings



</td>
<td valign="top">

boolean



</td>
<td valign="top">

No



</td>
<td valign="top">

depending



</td>
<td valign="top">

Defines whether the administrator is allowed to change the settings of the field. For example, the administrator can hide or disable fields for the content mode. To activate the feature additionally the allowSettings property of the Card Editor control needs to be enabled.

`translatable: true`



</td>
</tr>
</table>

**Providing Lists for string**

To allow a selection of values for fields of type "string", you can add a values section. Similar to the Card data section, the list can be filled with a static json or a request. The item section in the values definition links the data. The "key" property of the item is used as the value for the setting referred by the "manifestPath".

> ### Sample Code:  
> Static Data List:
> 
> ```
> "stringWithStaticList": {
>   "manifestpath": "/sap.card/configuration/parameters/stringWithStaticList/value",
>   "type": "string",
>   "values": {
>      "data": {
>         "json": {
>            "values": [
>               { "text": "From JSON 1", "key": "key1" },
>               { "text": "From JSON 2", "key": "key2" },
>               { "text": "From JSON 3", "key": "key3" }
>            ]
>         },
>         "path": "/values"
>      },
>      "item": {
>         "text": "{text}",
>         "key": "{key}"
>      }
>   }
> }
> ```

Request Data List: There referred url delivers the data asynchronous. Also an extension could be used as a data provider.

> ### Sample Code:  
> Request Values
> 
> ```
> "stringWithStaticList": {
>   "manifestpath": "/sap.card/configuration/parameters/stringWithRequestList/value",
>   "type": "string",
>   "values": {
>      "data": {
>         "request": {
>             "url": "./dt/listdata.json"
>         },
>         "path": "/values"
>      },
>      "item": {
>         "text": "{text}",
>         "key": "{key}"
>      }
>   }
> }
> ```

> ### Sample Code:  
> Data of dt/listdata.json
> 
> ```
> "values": [
> 		{ "text": "From JSON 1", "key": "key1" },
> 		{ "text": "From JSON 2", "key": "key2" },
> 		{ "text": "From JSON 3", "key": "key3" }
> 	]
> ```

**Providing Lists for string arrays**

To allow a selection of values for fields of type "string\[\]", you can add the same values sections as above. Similar to the Card data section, the list can be filled with a static json or a request. The item section in the values definition links the data. The "key" property of the item is used as the value for the setting referred by the "manifestPath".

> ### Sample Code:  
> Static Array List:
> 
> ```
> "stringArrayWithStaticList": {
> 	"manifestpath": "/sap.card/configuration/parameters/stringArrayWithStaticList/value",
> 	"type": "string[]",
> 	"values": {
> 		"data": {
> 		"json": {
> 			"values": [
> 				{ "text": "From JSON 1", "key": "key1" },
> 				{ "text": "From JSON 2", "key": "key2" },
> 				{ "text": "From JSON 3", "key": "key3" }
> 			]
> 		},
> 		"path": "/values"
> 		},
> 		"item": {
> 		"text": "{text}",
> 		"key": "{key}"
> 		}
> 	}
> }
> 
> ```

Request Data List: There referred url delivers the data asynchronous. Also an extension could be used as a data provider.

> ### Sample Code:  
> String Array List with requests
> 
> ```
> "stringWithStaticList": {
> 	"manifestpath": "/sap.card/configuration/parameters/stringArrayWithRequestList/value",
> 	"type": "string[]",
> 	"values": {
> 		"data": {
> 		"request": {
> 			"url": "./dt/listdata.json"
> 		},
> 		"path": "/values"
> 		},
> 		"item": {
> 		"text": "{text}",
> 		"key": "{key}"
> 		}
> 	}
> }
> ```

> ### Sample Code:  
> Data of dt/listdata.json
> 
> ```
> 
> 	"values": [
> 		{ "text": "From JSON 1", "key": "key1" },
> 		{ "text": "From JSON 2", "key": "key2" },
> 		{ "text": "From JSON 3", "key": "key3" }
> 	]
> ```

