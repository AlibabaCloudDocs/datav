# Control configurations

This topic describes control configurations, including the configuration rule and common fields.

## Configuration rule

Configurations of a control consist of common and [custom fields](/intl.en-US/Developer Guide/Document structure/Control configuration/text.md). For more information, see [Common fields](#section_p8y_1yv_24d).

In the following example, `name`, `type`, and `default` are common fields, and `prefix` is a custom field.

```
{
  "name": "Text Box", 
  "type": "text",
  "default": "",
  "description": "Description and Label",
  "prefix": "Progress Today:"
}
```

## Common fields

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|Example value: `Text Box`.|
|`type`|The type of the control.|string|Yes|Example value: `text`. If this field is set to `hidden`, DataV does not render the control.|
|`default`|The default value of the control.|string, number, object, or array|No|None.|
|`showInPanel`|The rule to display the control on the panel.|string|No|If you do not specify this field, the control is displayed on the panel. If you specify this field, the control is displayed based on the rule. For more information, see [Configuration of the showInPanel field](/intl.en-US/Developer Guide/Document structure/Control configuration/Configuration of the showInPanel field.md).|
|`caption`|The label of the control.|string|No|If this field is not configured, the label is not displayed.|
|`description`|The description of the control.|string|No|None.|
|`handler`|The processing function name.|string|No|None.|
|`col`|The number of grids for the control.|number|No|The 24-grid system is used.|
|`valuePath`|The value path of the control.|string|No|For more information, see [Configuration of the valuePath field](/intl.en-US/Developer Guide/Document structure/Control configuration/Configuration of the valuePath field.md).|
|show|Specifies whether to display or hide the control.|object|No|Example: ```
{
  "xAxis": {
    "type": "group",
    "name": "X-axis",
    "children": {
      "show": { 
        "type": "boolean",
        "name": "Show",
        "default": true
      },
      "color": {
        "type": "color",
        "name": "Color",
        "default": "#ccc",
        "show": [                
          ["show", "$eq", true] 
        ]
      }
    }
  }
}
```

 -   `children.show`: displays a Show option on the right of the X-axis. This option does not determine whether a sibling control is shown.
-   `color.show`: determines whether a single control is shown.
-   `["show", "$eq", true]`: The `color` picker control is shown only when the `children.show` field in the sibling control is set to `true`. |

## Custom fields

The custom fields for different controls vary. For more information, see [Control configurations](/intl.en-US/Developer Guide/Document structure/Control configuration/text.md).

