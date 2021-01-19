# Configuration of the showInPanel field

You can configure the rules to show or hide a control by using the showInPanel field.

## Scenarios

If a control is not required in some conditions, you can use the `showInPanel` field to specify whether the control appears in the config panel. This reduces unnecessary information. The conditions in the `showInPanel` field are the settings of other controls. For example, if Data Type is changed from Numeric to Time, the Data Format control appears.

![Usage scenario of the showInPanel field](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3589301161/p93121.png)

## Configuration rules

```
{
  "conditions": [
    [ "path", "operator", "value" ],
    ...
  ],
  "logicalType": "logicalType"
}
```

|Parameter|Description|
|---------|-----------|
|`conditions`|The configuration conditions in the array format. Each condition contains an array of three fields: `path`, `operator`, and `value`.|
|`path`|The path of the control on which the conditions depend. Both absolute and relative paths are supported. -   Absolute path: starts from the root node. Periods \(`.`\) are used to connect the path elements, for example, `chart.legend`.
-   Relative path: starts from the current configuration. Periods \(`.`\) are used to locate the path, for example, `.type ..legend.show`. |
|`operator`|The operator. Valid values: -   `eq`: equal to
-   `$ne`: not equal to
-   `$gt`: greater than
-   `$lt`: less than
-   `$gte`: greater than or equal to
-   `$lte`: less than or equal to
-   `$in`: in an array
-   `$nin`: not in an array |
|`value`|The value of the control. In [Scenarios](#section_9fz_qsx_0nl), if `dataType` is at the same level as `type` and the value of `type` equals `time`, the Data Format control appears. The following examples show the configuration of the `conditions` field:

-   Relative path

    ```
[".type", "$eq", "time"]
    ```

-   Absolute path

    ```
["options.axis.xaxis.type", "$eq", "time"]
    ``` |
|`logicalType`|The `conditions` field defines conditions, and the `logicalType` field defines the logical relationship between the conditions. Valid values: `$and` and `$or`. Default value: `$and`. If the logical relationship is `$and`, you do not need to configure the `logicalType` field and configure only the `conditions` array. For example, if `b.switch` equals `true` and `a.switch` does not equal `false`, the required control appears. The following example shows the configuration of the `showInPanel` field:

```
[["b.switch", "$eq", true], ["a.switch", "$ne", false]]
``` |

## Example 1

Example configuration format:

```
{
  chart: {
   font: {},
   margin: {}
  },
  legend: {
   switch: {},
   color: {}
  }
}
```

If switch equals true or font does not equal pingfang, the margin control appears in the config panel. Otherwise, the margin control does not appear.

The following examples show the configuration of the `showInPanel` field:

-   Absolute path

    ```
    {
      conditions:  [[ 'legend.switch', '$eq', true ], [ 'chart.font', '$ne', 'pingfang' ]],
      logicalType: '$or'
    }
    ```

-   Relative path

    ```
    {
      conditions: [[ '..legend.switch', '$eq', true ], [ '.font', '$ne', 'pingfang' ]],
      logicalType: '$or'
    }
    ```


## Example 2

In this example, the textA control appears only when switchA or switchB equals true.

![Configuration example of the showInPanel field](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3589301161/p93125.png)

```
{
  "a": {
    "type": "suite",
    "name": "suiteA",
    "children": {
      "switchA": {
        "type": "switch",
        "name": "switchA",
        "default": true,
        "col": 8
      },
      "textA": {
        "type": "text",
        "name": "textA",
        "default": "A",
        "col": 16,
        "showInPanel": {
          "conditions": [
            [
              "b.switchB",
              "$eq",
              true
            ],
            [
              "a.switchA",
              "$ne",
              false
            ]
          ],
          "logicalType": "$or"
        }
      }
    }
  },
  "b": {
    "type": "suite",
    "name": "suiteB",
    "children": {
      "switchB": {
        "type": "switch",
        "name": "switchB",
        "default": false,
        "col": 8
      },
      "textB": {
        "type": "text",
        "name": "textB",
        "default": "B",
        "col": 16
      }
    }
  }
}
```

