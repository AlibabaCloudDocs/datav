# radio

You can configure a common option button.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|string|No|If this field is not specified, no option is selected by default.|
|`options`|The list of options.|array|No|The value is an object array, which consists of the `label` and `value` fields. The `label` field specifies the text to be displayed, and the `value` field specifies the value of the text.|
|`optionCol`|The width of options.|number|No|This field specifies the width of options.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`"left"`|`""`|

## Configuration examples

![Configuration example of an option button](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7279301161/p92896.png)

```
"align": {
    "name": "Alignment",
    "type": "radio",
    "optionCol": 12,
    "options": [
      {
        "label": "Left",
        "value": "left"
      },
      {
        "label": "Center",
        "value": "center"
      },
      {
        "label": "Right",
        "value": "right"
      }
    ]
}
```

