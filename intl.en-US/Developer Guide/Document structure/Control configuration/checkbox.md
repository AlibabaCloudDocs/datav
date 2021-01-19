# checkbox

You can configure a check box and the width of options.

## Configuration description

|Field|Description|Type|Required?|Remarks|
|:----|:----------|----|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|array|No|If this field is not specified, no option is selected by default.|
|`options`|The list of options.|array|No|The value is an object array, which consists of the `label` and `value` fields. The `label` field specifies the text to be displayed, and the `value` field specifies the value of the text.|
|`optionCol`|The width of options.|number|No|This field specifies the width of options.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|array|`["left", "right"]`|`[]`|

## Configuration examples

![Configuration example of a check box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8779301161/p92914.png)

```
"checkbox": {
    "name": "Map Content",
    "type": "checkbox",
    "optionCol": 8,
    "options": [
      {
        "value": "bg",
        "label": "Background"
      },
      {
        "value": "building",
        "label": "Building"
      },
      {
        "value": "road",
        "label": "Road"
      },
      {
        "value": "label",
        "label": "Label"
      }
    ]
}
```

