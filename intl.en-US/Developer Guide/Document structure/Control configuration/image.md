# image

You can configure an image box.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default image.|string|No|If this field is not specified, the default image is empty.|

**Note:** If you want to specify a static image file in your computer, save the image file to the resources directory of the widget, for example, ./resources/xxxx.png.

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`"https://img.alicdn.com/tfs/TB1cjY3ANTpK1RjSZFMXXbG_VXa-180-180.png"`|`""`|

## Configuration examples

![Configuration example of an image box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9969301161/p92926.png)

```
{
  "name" : "Background",
  "type" : "image",
  "default": "http://datav.oss-cn-hangzhou.aliyuncs.com/uploads/images/c4ba3c6518c1997f4baa612a600c3fbe.png"
}
```

