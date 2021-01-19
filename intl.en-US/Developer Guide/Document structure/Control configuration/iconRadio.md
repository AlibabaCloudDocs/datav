# iconRadio

You can configure an option button with icons.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|string|No|If this field is not specified, no option is selected by default.|
|`options`|The list of options.|array|Yes|The value is an object array, which consists of the `label`, `value`, and `src` fields. The `label` field specifies the text to be displayed, the `value` field specifies the value of the text, and the `src` field specifies the image URL or icon name.|
|`optionCol`|The width of options.|number|No|This field specifies the width of options.|
|`evenlySplit`|Specifies whether the options are evenly distributed.|boolean|No|If the `evenlySplit` field and the `optionCol` field are both configured, the former takes effect in priority.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|string|`"left"`|`""`|

## Configuration examples

-   Image options

    ![Configuration example - image options](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3979301161/p92922.png)

    ```
    "direction": {
        "name": "Moving Direction",
        "type": "iconRadio",
        "options": [
          {
            "value": "left",
            "label": "Left",
            "src": "https://img.alicdn.com/tfs/TB1.77AgxYaK1RjSZFnXXa80pXa-48-48.png"
          },
          {
            "value": "right",
            "label": "Right",
            "src": "https://img.alicdn.com/tfs/TB1sWoggwDqK1RjSZSyXXaxEVXa-48-48.png"
          },
          {
            "value": "top",
            "label": "Top",
            "src": "https://img.alicdn.com/tfs/TB1t0wjgCzqK1RjSZFjXXblCFXa-48-48.png"
          },
          {
            "value": "bottom",
            "label": "Bottom",
            "src": "https://img.alicdn.com/tfs/TB1UAAjgwHqK1RjSZFkXXX.WFXa-48-48.png"
          }
        ]
      }
    ```

-   Icon options

    ![Configuration example - icon options](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3979301161/p92924.png)

    ```
    "algin": {
        "name": "Alignment",
        "type": "iconRadio",
        "evenlySplit": true,
        "options": [
          {
            "value": "left",
            "label": "Left",
            "src": "align-left"
          },
          {
            "value": "right",
            "label": "Center",
            "src": "align-center"
          },
          {
            "value": "bottom",
            "label": "Bottom",
            "src": "align-right"
          }
        ]
      }
    ```


