# imageSelect

You can configure an image selector.

## Configuration description

|Field|Description|Type|Required?|Remarks|
|:----|:----------|----|:--------|:------|
|`name`|The name of the control.|string|Yes|None.`xxx`|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|array|No|If this field is not specified, the default value is the first item in the `options` field.|
|`options`|The list of options.|array|No|The value is an object array, which consists of the `label`, `value`, and `src` fields. The `label` field specifies the text to be displayed, the `value` field specifies the value of the text, and the `src` field specifies the image URL or icon name.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`"left"`|`""`|

## Configuration examples

![Configuration example of an image selector](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1479301161/p92927.png)

```
"bubbleKey": {
    "name": "Bubble Type",
    "type": "imageSelect",
    "default": "type1",
    "options": [
      {
        "label": "Type 1",
        "value": "type1",
        "src": "https://img.alicdn.com/tfs/TB1BCgwoAT2gK0jSZFkXXcIQFXa-162-104.png"
      },
      {
        "label": "Type 2",
        "value": "type2",
        "src": "https://img.alicdn.com/tfs/TB1EmgwoAT2gK0jSZFkXXcIQFXa-162-104.png"
      },
      {
        "label": "Type 3",
        "value": "type3",
        "src": "https://img.alicdn.com/tfs/TB13x3soAP2gK0jSZPxXXacQpXa-162-104.png"
      },
      {
        "label": "Type 4",
        "value": "type4",
        "src": "https://img.alicdn.com/tfs/TB1pKUuoAL0gK0jSZFxXXXWHVXa-162-104.png"
      }
    ]
  }
```

