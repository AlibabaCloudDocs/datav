# switch

You can configure a switch control and specify whether to display the status text.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|boolean|No|None.|
|`statusText`|Specifies whether to display the status text.|boolean|No|Default value: `false`.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|boolean|`true`|`false`|

## Configuration examples

![Configuration example of a switch control](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6579301161/p92930.png)

```
"open": {
    "name": "Switch",
    "type": "switch",
    "default": true,
    "statusText": true
  }
```

