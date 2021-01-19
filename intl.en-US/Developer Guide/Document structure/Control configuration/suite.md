# suite

You can configure a suite of controls.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|object|No|If this field is not specified, the default value is empty. For more information, see [Value description](#section_gh3_w1b_nx8).|
|`children`|The controls in the suite.|object|No|Default value: `{}`. For more information, see [Value description](#section_gh3_w1b_nx8).|
|`enableHide`|Specifies whether controls in the suite can be hidden.|boolean|No|Default value: `false`. If this field is set to `true`, a show or hide icon appears, and the `show` field is added.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|The `enableHide` field is not configured or is set to `false`.`xxx`|object|```
{
 "number": 12,
 "open": true
}
```

|```
{}
``` |
|The `enableHide` field is set to `true`.|object|```
{
 "number": 12,
 "open": true,
 "show": true
}
```

|```
{
 "show": true
}
``` |

## Configuration examples

-   The `enableHide` field not configured

    ![Configuration example 1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8089301161/p92967.png)

    ```
    "style": {
        "name": "Suite",
        "type": "suite",
        "children": {
          "open": {
            "name": "Switch",
            "type": "switch",
            "col": 12
          },
          "size": {
            "type": "stepper",
            "caption": "Size",
            "min": 0,
            "max": 10,
            "step": 1,
            "col": 12
          }
        }
    }
    ```

-   The `enableHide` field set to `true`

    ![Configuration example 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8089301161/p92968.png)

    ```
    "style": {
        "name": "Suite",
        "type": "suite",
        "enableHide": true,
        "children": {
          "open": {
            "name": "Switch",
            "type": "switch",
            "col": 12
          },
          "size": {
            "type": "stepper",
            "caption": "Size",
            "min": 0,
            "max": 10,
            "step": 1,
            "col": 12
          }
        }
    }
    ```


