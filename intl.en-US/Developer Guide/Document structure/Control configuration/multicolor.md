# multicolor

You can configure a gradient color picker with one or more colors.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|object|Yes|You must configure the following fields: -   `style`: the style of the color picker. Valid values: `single` and `double`.
-   `value`: the color value when the `style` field is set to `single`.
-   `from`: the start color value of the gradient when the `style` field is set to `double`.
-   `to`: the end color value of the gradient when the `style` field is set to `double`.
-   `angle`: the angle of the gradient when the `style` field is set to `double`. |

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|The `style` field is set to `single`.|object|```
{
 "style": "single",
 "value": "#ccc"
}
```

|```
{
 "style": "single",
 "value": "#000"
}
``` |
|The `style` field is set to `double`.|object|```
{
 "style": "double",
 "from": "#fff",
 "to": "#ccc",
 "angle": 0
}
```

|```
{
 "style": "double",
 "from": "#000",
 "to": "rbga(0,0,0,.5)",
 "angle": 0
}
``` |

## Configuration examples

![Configuration example of a color picker](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3969301161/p93717.png)

```
"color": {
    "name": "Gradient Color",
    "type": "multicolor",
    "default": {
      "style": "double",
      "from": "#000",
      "to": "#fff",
      "angle": 0
    }
}
```

