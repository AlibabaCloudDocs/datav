# text

You can configure a text input box, as well as its prefix and suffix.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|string|No|If this field is not specified, the default value is empty.|
|`prefix`|The prefix.|string|No|None.|
|`suffix`|The suffix.|string|No|None.|
|`prefixIcon`|The icon name of the prefix.|string|No|Enter a name in the icon library, such as `link`.|
|`suffixIcon`|The icon name of the suffix.|string|No|Enter a name in the icon library, such as `link`.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`"Series 1"`|`""`|

## Configuration examples

![Configuration example of a text box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3369301161/p92877.png)

```
"link": {
    "name": "Link",
    "type": "text",
    "default": "http://datav.aliyun.com",
    "prefixIcon": "link"
  }
```

