# keyBoard

You can configure a keyboard control to define a shortcut key.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|array|No|If this field is not specified, the default value is `[16, 38]`.|

## Value description

|Condition|Data type|Example|Default value|Remarks|
|---------|---------|-------|-------------|-------|
|None|array|`[16,38]`|`[16,38]`|ASCII codes of the shortcut key.|

## Configuration examples

![Configuration example of a keyboard control](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1089301161/p92935.png)

```
"keyboard": {
   "name": "Shortcut Key",
   "type": "keyboard",  
   "default": [16,38]
}
```

