# percent

You can configure a percentage control. However, we recommend that you use a slider instead.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|number|No|If this field is not specified, the default value is `0`. The maximum value is `100`, and the minimum value is `0`. The step is `1`.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|number|`20`|`0`|

## Configuration examples

![Configuration example of a percentage control](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4379301161/p93722.png)

```
"percent": {
  "name": "Percentage",
  "type": "percent",
  "default": 20
}
```

