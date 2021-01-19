# color

You can configure a color picker. However, we recommend that you use a color padding box instead \(set the type field to fill\).

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`type`|The type of the control.|string|Yes|None.|
|`name`|The name of the control.|string|Yes|None.|
|`default`|The default value.|string|No|If this field is not specified, the default value is `#000`.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`12`|`"#000"`|

## Configuration examples

![Configuration example of a color picker](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5869301161/p93715.png)

```
"color": {
    "name": "Color",
    "type": "color",
    "default": "#fff"
}
```

