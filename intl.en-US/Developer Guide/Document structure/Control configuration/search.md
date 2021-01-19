# search

You can configure a drop-down search box. However, we recommend that you use a selector instead \(set the type field to select\).

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|No|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|string|No|If this field is not specified, the default value is the first item in the `range` field.|
|`range`|The value range.|array|No|The value range format can be `[{name: "" ,value: ""}]`, `[{key: value}]`, or `[value]`. If this field is not specified, the control type changes to text.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`"Microsoft Yahei"`|`""`|

## Configuration examples

![Configuration example of a drop-down search box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8769301161/p93714.png)

```
"search": {
    "name": "Font",
    "type": "search",
    "default": "Microsoft Yahei",
    "range": [
      {
        "Microsoft Yahei": "Microsoft Yahei"
      },
      {
        "SimSun": "SimSun"
      },
      "tahoma",
      "arial",
      "sans-serif"
    ]
}
```

