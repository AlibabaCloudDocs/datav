# Specifications of a package.json file

A package.json file contains configurations of a widget. This topic describes fields in a package.json file. You can configure these fields in the file to customize the style of a widget as needed.

## Example of a package.json file in protocol version 2

**Note:** The comments in the following example provide the details of fields in a package.json file.

```
{
  "name": "@leaf/pie-multi-radius-with-title",   //@Namespace/Widget name. The namespace is the name of a widget package. If you do not specify a namespace, the widget cannot be published.
  "version": "0.1.5",                            // The version number.
  "dependencies": {                              // The dependencies that exclude datav:/com/.
    "bcore": "0.0.9",
    "jquery": "2.1.4",                           // All dependency versions must be locked.
    "lodash": "4.6.1"
  },
  "datav": {                                     // The configurations of DataV.
    "cn_name": "Multidimensional pie chart with a title",               // The name of the widget.
    "protocol": 2,                               // The version of the protocol.
    "type": ["regular_pie"],                     // The type of the widget.
    "supportTheme": true,                      // Specifies whether the widget supports theme configurations.
    "view": {
      "width": 300,
      "height": 200,
      "minWidth": 100,
      "minHeight": 50
    },
    "icon": "",                                    // The URL of the widget icon.
    "apis": {                                      // The widget APIs. You can add one or more APIs.
      "source": {                                  // The name of the API.
        "handler": "render",                       // The method to handle the widget returned by the API.
        "description" : "The API of a multidimensional pie chart",          // The description of the API.
        "fields" : {                               // The fields required by the API. You can add one or more fields.
          "x" : {                                  // The name of the field.
            "description" : "Category",                // The description of the field.
            "type" : "string",                     // The type of the field.
            "optional": true                       // Specifies whether the field is optional.
          },
          "y" : {
            "description" : "Value",
            "type" : "int"
          }
        }
      }
    },
    "config" : {                                 // The configuration of the widget. It consists of the UI elements that are displayed in the editor.
      "paxis" : {
        "type" : "group",                        // Specifies that the element is a group. For more information, see Description of the config field.
        "name" : "Label",
        "children" : {
          "dx" : {
            "type" : "text",                    // Specifies that the element is a text. For more information, see Description of the config field.
            "name" : "Distance from the label to the center",
            "default" : 220
          }
        }
      },
      "title" : {
        "type" : "group",
        "name" : "Title",
        "children" : {
          "value" : {
            "hasVisibility" : "true",
            "visible" : "true",
            "type" : "text",
            "name" : "Title",
            "default" : "This is a title"
          },
          "font-size" : {
            "type" : "number",                 // Specifies that the element is a number. For more information, see Description of the config field.
            "name" : "Font",
            "min" : 10,
            "default" : 32,
            "max" : 100
          },
          "text-align" : {
            "name" : "Alignment",
            "type" : "select",                // Specifies that the element is a drop-down list. For more information, see Description of the config field.
            "options" : [
              {"name" : "Left", "value" : "left"},
              {"name" : "Right", "value" : "right"},
              {"name" : "Center", "value" : "center"}
            ],
            "default" : "center"
          },
          "color" : {
            "name" : "Font color",
            "type" : "color",                  // Specifies that the element is a color. For more information, see Description of the config field.
            "default" : "#fff"
          },
          "background-color" : {
            "name" : "Background",
            "type" : "color",
            "default" : "#000"
          }
         }
        }
      }
    },
  "api_data":{                               // The API data. You can add one or more pieces of data.
    "source" : [                             // The name of the API. It must be the same as the API name in the apis field. The size of data contained in this field cannot exceed 6 KB.
      {"x": "General goods", "y" : 5},
      {"x": "General goods", "y" : 22},
      {"x": "Light goods", "y" : 22},
      {"x": "Devices", "y" : 14},
      {"x": "Mineral products", "y" : 15},
      {"x": "Steel", "y" : 15},
      {"x": "Building materials", "y" : 12},
      {"x": "Food", "y" : 12},
      {"x": "Grain", "y" : 28}
    ],
  },
  "events": {                              // The global event parameters.
    "event-name": {                        // The name of the event.
      "description": "Event description",           // The description of the event.
      "fields": {                          // Specifies one or more fields.
        "value": {                         // The name of the field.
          "description": "Description"          // The description of the field.
        }
      }
    }
  },
  "publicHandler": {
    "show": {
      "name": "Display",
      "description": "Description",
      "type": "object",                  // Valid values: object, array, null, and any. The value any indicates any type.
      "fields": {
        "data": {
          "name": "Data",
          "type": "array",
          "children": {
                    ...
          }
        }
      }
    }
  },
}
```

## Configuration items in the config field

The `config` field contains the configuration items of a widget. These configuration items control the display of a widget and are used to present UI elements in the editor.

When you configure the `config` field, take note of the following requirements:

-   Specify the default configuration items of the widget.
-   Specify the input requirements so that the editor can identify the input information.

`type` in the `config` field allows you to configure the type and style of a widget. The type field determines the UI elements that are displayed in the editor. You can configure the type field as needed to significantly improve the quality and user experience of a widget. For more information, see [Control configuration]().

## apis and api\_data fields

-   `apis` field

    The apis field defines the names of APIs in a widget and the fields required by the APIs. You can specify multiple APIs and fields.

    ```
    "apis": {                                    
      "source": {                                
      "handler": "render",                     
        "description" : "The API of a multidimensional pie chart",          
        "fields" : {                              
          "x" : {                                 
            "description" : "Category",                
            "type" : "string",                     
            "optional": true                       
          },
          "y" : {
            "description" : "Value",
            "type" : "int"
          }
        }
      },
      "source2":{
          ...                                     
      }
    }
    ```

    |Field|Description|Required|Remarks|
    |-----|-----------|--------|-------|
    |`apis`|The APIs of a widget.|Yes|A widget can provide multiple APIs.|
    |`source`|The name of an API.|No|A custom value is allowed.|
    |`handler`|The name of the method to process data returned by an API.|Yes|The method must be specified in the source code of the [index.js](/intl.en-US/Developer Guide/Document structure/index.js specifications.md) file.|
    |`description`|The description of an API.|No|None.|
    |`fields`|The fields required for an API.|Yes|An API can contain multiple fields.|
    |`fields.x`|The name of a field.|Yes|A custom value is allowed.|
    |`fields.x.description`|The description of a field.|No|None.|
    |`fields.x.type`|The type of a field.|No|Valid values: number, string, boolean, object, and array.|
    |`fields.x.optional`|Specifies whether a field is optional.|No|A value of the BOOLEAN type is supported. `true` indicates that the field is optional, and `false` indicates that the field is required.|

-   `api_data` field

    The api\_data field defines data of one or more APIs. API names in this field must be the same as those in the `apis` field. The size of data contained in the api\_data field cannot exceed 6 KB. For more information, see the comments.

    ```
    "api_data":{                          
      "source" : [                       
        {"x": "General goods", "y" : 5},
        {"x": "General goods", "y" : 22},
        {"x": "Light goods", "y" : 22},
        {"x": "Devices", "y" : 14},
        {"x": "Mineral products", "y" : 15},
        {"x": "Steel", "y" : 15},
        {"x": "Building materials", "y" : 12},
        {"x": "Food", "y" : 12},
        {"x": "Grain", "y" : 28}
      ],
    }
    ```

    |Field|Description|Required|Remarks|
    |-----|-----------|--------|-------|
    |`api_data`|The data of APIs.|Yes|A widget can contain data of one or more APIs.|
    |`source`|The name of an API.|No|The API name in this field must be the same as that in the `apis` field. The size of data contained in the field cannot exceed 6 KB.|


## Specifications of interaction events

Interaction events of DataV are controlled by the `emit` method \(triggered in the widget code\) and the `events` field in the package.json file.``

-   `events` field

    The `events` field is under the `datav` field and is at the same level as the `config` field. The events field defines the name, description, and variable name of an interaction event.

    ```
    {
      "events": {                 
        "click-me": {      "description": "Click-triggered event",           
          "fields": {                            
            "value": {                        
              "description": "Click value" 
            }
          }
        }
      }
    }
    ```

    |Field|Description|Required|Remarks|
    |-----|-----------|--------|-------|
    |`click-me`|The name of an event.|Yes|A custom value is allowed.|
    |`description`|The description of an event.|No|This field is used to describe the usage of an event.|
    |`fields`|The fields.|Yes|This field can contain the names and descriptions of multiple fields.|
    |`fields.value`|The name of a field.|Yes|A custom value is allowed.|
    |`fields.value.description`|The description of a field.|No|None.|

-   `emit` method

    `emit` is a basic method that passes event names and data in a widget as parameters. After this method is triggered, other widgets can obtain the parameter values of the widget based on the variable name. This method is implemented in the source code of the [index.js](/intl.en-US/Developer Guide/Document structure/index.js specifications.md) file. For more information, see the comments.

    ```
    render: function () {
      this.container.on('click', () => {
        this.emit('click-me', data)            // data must be an object, instead of a value. The attribute name is the variable name.
      })
    }
    ```


## type field

The type field defines the type of a widget. For more information, see the comments.``

```
type: ["regular_bar", ...]  // One widget can belong to multiple groups. Multiple widget types are separated by underscores (_), for example, "type1_type2".
  {                      // The common widget types.
    regular: "Regular chart",
    map: "Map", 
    media : "Media", 
    network: "Network", 
    text: "Text", 
    interact: "Interaction",
    material: "Material"
  }
```

## publicHandler field

The `publicHandler` field defines a behavior event of DataV. Example:

```
"publicHandler": {
  "select": {
    "name": "select",
    "description": "Select an option",
    "type": "object",    
    "fields": {
      "data": {
        "name": "Data",
        "type": "array",
        "children": {
               ...
        }
      }
    }
  }
}
```

In the preceding example, a `select` behavior event is registered. The `index.js` file must implement the `select` method. Otherwise, an error is returned if the select method is executed.

**Note:**

-   If you do not implement the `show`, `hide`, and `updateOptions` methods, DataV automatically registers and implements these methods.
-   You can manually implement the `updateOptions` method. If the manual operation is not performed, DataV calls the `render` method to implement the updateOptions method.

|Field|Description|Required|Remarks|
|-----|-----------|--------|-------|
|`name`|The name of an event.|Yes|The event name is used in node-based programming configurations.|
|`description`|The description of an event.|No|There is no limit on the number of characters in a description.|
|`type`|The type of the first input parameter of an event.|No|Optional. The value is fixed to object.|
|`fields`|The field.|No|None.|
|`fields.data.name`|The name of a field.|Yes|None.|
|`fields.data.description`|The description of a field.|No|None.|
|`fields.data.type`|The type of a field.|Yes|Optional. Valid values: number, string, boolean, object, and array.|
|`fields.data.children`|The subnode.|No|This field must be specified if `fields.data.type` is set to object or array.|
|`fields.data.default`|The default value.|No|This field must be specified if `fields.data.type` is set to number, string, or boolean.|
|`fields.data.optional`|Specifies whether a field is optional.|No|Optional. This field takes effect when fields.data.type is set to boolean. `true` indicates that the field is optional, and `false` indicates that the field is required.|

