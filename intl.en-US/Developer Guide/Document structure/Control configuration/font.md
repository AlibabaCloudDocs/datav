# font

You can configure a font control suite that consists of a font selector, font weight selector, font size stepper, and solid color padding box.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|array|No|If this field is not specified, the default value is empty.|
|`components`|The controls in the suite.|array|No|Default value: `["fontFamily","fontWeight","fontSize","color"]`. You can configure `"fontFamily"`, `"fontWeight"`, `"fontSize"`, and `"color"`.|
|`enableHide`|Specifies whether controls in the suite can be hidden.|boolean|No|Default value: `false`. If this field is set to `true`, a show or hide icon appears, and the `show` field is added.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|The `enableHide` field is not configured or is set to `false`.|object|```
{
 "fontFamily": "simSun",
 "fontWeight": 400,
 "color": "#333",
 "fontSize": 12
}
```

|```
{
 "fontFamily": "Microsoft Yahei",
 "fontWeight": "normal",
 "color": "#fff",
 "fontSize": 12
}
``` |
|The `enableHide` field is set to `true`.|object|```
{
 "fontFamily": "simSun",
 "fontWeight": 400,
 "color": "#333",
 "fontSize": 12,
 "show": true
}
```

|```
{
 "fontFamily": "Microsoft Yahei",
 "fontWeight": "normal",
 "color": "#fff",
 "fontSize": 12,
 "show": true
}
``` |

## Configuration examples

-   The `enableHide` field not configured

    ![Configuration example 1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7289301161/p93007.png)

    ```
    {
      "font": {
        "name": "Font",
        "type": "font",
        "default": {
          "fontFamily": "simSun",
          "fontWeight": 400,
          "color": "#333",
          "fontSize": 12
        }
      }
    }
    ```

-   The `enableHide` field set to `true`

    ![Configuration example 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7289301161/p93008.png)

    ```
    {
      "font": {
        "name": "Font",
        "type": "font",
        "enableHide": true,
        "default": {
          "fontFamily": "simSun",
          "fontWeight": 400,
          "color": "#333",
          "fontSize": 12
        }
      }
    }
    ```

-   Customized settings of the `components` field

    ![Configuration example 3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7289301161/p93009.png)

    ```
    {
      "fontComponents": {
        "name": "Font",
        "type": "font",
        "enableHide": true,
        "components": ["fontSize", "color"]
      }
    }
    ```


