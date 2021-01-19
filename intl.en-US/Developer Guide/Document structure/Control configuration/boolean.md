# boolean

You can configure a boolean control. However, we recommend that you use a switch control instead.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|boolean|No|If this field is not specified, the default value is `true`.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|boolean|`true`|`true`|

## Configuration examples

![Configuration example of a boolean control](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9179301161/p93721.png)

```
"boolean": {
   "type": "boolean",
   "name": "Show",
}
```

