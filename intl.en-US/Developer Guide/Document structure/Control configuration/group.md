# group

You can configure a group that consists of multiple controls. We recommend that you add controls of the same type to the same group. A group can be used to organize controls. You can show or hide controls in the group.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|object|No|If this field is not specified, the default value is empty.|
|`children`|The controls in a group.|object|No|If this field is not specified, the group is empty.|
|`enableHide`|Specifies whether controls in the group can be hidden.|boolean|No|Default value: `false`. If this field is set to `true`, a show or hide icon appears in the control group, and the `show` field is added.|
|`fold`|Specifies whether to show the controls by default.|boolean|No|None.|

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

    ![Configuration example 1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9479301161/p93013.png)

    ```
    {
      "group": {
        "name": "Group",
        "type": "group",
        "default": { "open": true, "size": 6 },
        "fold": false,
        "children": {
          "open": {
            "name": "Open",
            "type": "switch",
            "col": 12
          },
          "size": {
            "type": "stepper",
            "name": "Size",
            "min": 0,
            "max": 10,
            "step": 1,
            "col": 12
          }
        }
      }
    }
    ```

-   The `enableHide` field set to `true`

    ![Configuration example 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9479301161/p93014.png)

    ```
    {
      "group": {
        "name": "Group",
        "type": "group",
        "default": { "open": true, "size": 6 },
        "enableHide": true,
        "fold": false,
        "children": {
          "open": {
            "name": "Open",
            "type": "switch",
            "col": 12
          },
          "size": {
            "type": "stepper",
            "name": "Size",
            "min": 0,
            "max": 10,
            "step": 1,
            "col": 12
          }
        }
      }
    }
    ```


