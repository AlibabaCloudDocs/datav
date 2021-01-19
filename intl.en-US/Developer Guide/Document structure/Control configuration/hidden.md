# hidden

You can configure a control with hidden configuration items. DataV does not render this control.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|string, number, array, or object|No|The default value is not displayed but is passed to a method as a parameter in the config field.|

## Configuration examples

```
"hiddenconfig": {
  "name": "Value",
  "type" : "hidden",
  "default": 22
}
```

