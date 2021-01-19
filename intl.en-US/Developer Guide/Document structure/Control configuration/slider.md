# slider

You can configure a single or double slider as well as the step, maximum and minimum values, prefix, suffix, precision, and range of the slider.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|number or array|No|If this field is not specified, the default value is empty.|
|`step`|The step.|number|No|None.|
|`min`|The minimum value.|number|No|None.|
|`max`|The maximum value.|number|No|None.|
|`prefix`|The prefix.|string|No|None.|
|`suffix`|The suffix.|string|No|None.|
|`precision`|The precision of the value in the slider. It is indicated by the number of decimal places.|number|No|This field takes effect only for decimal values.|
|`mode`|The type of the slider.|string|No|Valid values: -   `single` \(This is the default value.\)
-   `double` |
|`showRange`|Specifies whether to show the value range.|boolean|No|This field takes effect only when the `mode` field is set to `double`. Default value: `false`.|
|`showCurrentRange`|Specifies whether to show the current value range.|boolean|No|This field takes effect only when the `mode` field is set to `single`. Default value: `true`.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|The `mode` field is set to `single`.|number|`22`|`0`|
|The `mode` field is set to `double`.|array|`[10,30]`|`[0,0]`|

## Configuration examples

-   The `mode` field set to `single`

    ![Configuration example of a single slider](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1779301161/p92933.png)

    ```
    "slider": {
        "name": "Alpha",
        "type": "slider",
        "step": 0.1,
        "min": 0,
        "max": 1,
        "suffix": "α",
        "showRange": true
      }
    ```

-   The `mode` field set to `double`

    ![Configuration example of a double slider](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1779301161/p92934.png)

    ```
    "slider": {
        "name": "Filter Range",
        "type": "slider",
        "mode": "double",
        "step": 1,
        "min": 10,
        "max": 30,
        "showCurrentRange": true
      }
    ```


