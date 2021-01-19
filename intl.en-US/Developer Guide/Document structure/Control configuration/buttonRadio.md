# buttonRadio

You can configure an option button in the box style.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|object|No|If this field is not specified, no option is selected by default.|
|`options`|The list of options.|array|No|The value is an object array, which consists of the `label` and `value` fields. The `label` field specifies the text to be displayed, and the `value` field specifies the value of the text.|
|`evenlySplit`|Specifies whether the options are evenly distributed.|boolean|No|None.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|object|`"left"`|`""`|

## Configuration examples

![Configuration example of the option button](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5879301161/p92918.png)

```
"algin": {
    "name": "Alignment",
    "type": "buttonRadio",
    "evenlySplit": true,
    "options": [
      {
        "value": "left",
        "label": "Left"
      },
      {
        "value": "right",
        "label": "Center"
      },
      {
        "value": "bottom",
        "label": "Right"
      }
    ]
  }
```

