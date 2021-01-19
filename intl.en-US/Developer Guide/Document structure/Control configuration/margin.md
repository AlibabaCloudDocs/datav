# margin

You can configure a margin control suite that consists of four steppers to specify the top, bottom, left, and right margins.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|string|No|If this field is not specified, the default value is empty.|
|`components`|The controls in the suite.|array|No|Default value: `["top","bottom","left","right"]`. You can configure `"top"`, `"bottom"`, `"left"`, and `"right"`.|
|`enableHide`|Specifies whether controls in the suite can be hidden.|boolean|No|Default value: `false`. If this field is set to `true`, a show or hide icon appears, and the `show` field is added.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|The `enableHide` field is not configured or is set to `false`.|object|```
{
 "top": 12,
 "right": 24,
 "bottom": 8,
 "left": 24
}
```

|```
{
 "top": 10,
 "right": 10,
 "bottom": 10,
 "left": 10
}
``` |
|The `enableHide` field is set to `true`.|object|```
{
 "top": 12,
 "right": 24,
 "bottom": 8,
 "left": 24,
 "show": true
}
```

|```
{
 "top": 10,
 "right": 10,
 "bottom": 10,
 "left": 10,
 "show": true
}
``` |

## Configuration examples

-   The `enableHide` field not configured

    ![Configuration example 1](../images/p92987.png)

    ```
    "margin": {
        "name": "Margin Suite",
        "type": "margin"
      }
    ```

-   The `enableHide` field set to `true`

    ![Configuration example 2](../images/p92988.png)

    ```
    "margin": {
        "name": "Margin Suite",
        "type": "margin",
        "enableHide": true
    }
    ```

-   Customized settings of the `components` field

    ![Configuration example 3](../images/p92990.png)

    ```
    "margin": {
        "name": "Margin Suite",
        "type": "margin",
        "enableHide": true,
        "components": [
          "top",
          "bottom"
        ]
    }
    ```


