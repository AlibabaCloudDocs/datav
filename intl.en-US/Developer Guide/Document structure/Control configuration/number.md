# number

You can configure a number input box. However, we recommend that you configure a stepper or slider instead.

## Configuration description

|Field|Description|Type|Required?|Remarks|
|:----|:----------|----|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|number|No|If this field is not specified, the default value is `16`.|
|`min`|The minimum value.|number|No|You can configure a minimum value in the `min`, `range[0]`, or `range.min` field. If you do not configure any of the three fields, the control type changes to text, and the program execution may encounter errors.|
|`max`|The maximum value.|number|No|You can configure a maximum value in the `max`, `range[1]`, or `range.max` field. If you do not configure any of the three fields, the control type changes to text, and the program execution may encounter errors.|
|`range`|The value range.|array or object|No|You can configure the `range` field to display a slider bar. The value of the `range` field can be an array or object, such as `[10, 55]` or `{min: 10, max: 55}`. If none of the range, `min`, and `max` fields are specified, the control type changes to text, and the program execution may encounter errors.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|number|`12`|`0`|

## Configuration examples

-   The `range` field not configured

    ![Configuration example 1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1469301161/p93709.png)

    ```
    "number": {
        "type": "number",
        "name": "Font Size",
        "default": 22,
        "min": 10,
        "max": 55
    }
    ```

-   The `range` field configured

    ![Configuration example 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1469301161/p93710.png)

    ```
    "number": {
        "type": "number",
        "name" : "Font Size",
        "default": 22,
        "range": [
          10,
          55
        ]
    }
    ```


