# tabs

You can configure a group of tabs that can be switched and dynamically added or deleted.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|object|No|If this field is not specified, the default value is empty.|
|`addable`|Specifies whether the tabs can be dynamically added or deleted.|boolean|No|Default value: `true`.|
|`template`|The template used to dynamically add or delete tabs.|object|No|Default value: `{}`.|
|`children`|The settings of each tab.|array|No|Default value: `[]`. The key of the tab cannot be `_icon`, `ID`, or `_label`. **Note:** You can add the `_label` field to customize the tab name and add the `_icon` field to specify an icon. For example, change the tab name from `Series 1` to `Template`. |
|`fold`|Specifies whether to show the tab by default.|boolean|No|Default value: `true`.|

## Value description

|Condition|Data type|Example|Default value|Remarks|
|---------|---------|-------|-------------|-------|
|None|array|```
[
 {
   "name": "Series 1",
 },
 {
   "name": "Series 2",
 }
]
```

|```
[]
```

|You can add the `_label` field to customize a tab name and add the `_icon` field to specify an icon.|

## Configuration examples

-   The `template` field configured \(Tabs can be dynamically added or deleted.\)

    ![Configuration example 1](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6389301161/p93021.png)

    ```
    {
      "tabs": {
        "name": "User Info",
        "type": "tabs",
        "maxTabs": 4,
        "fold": false,
        "default": [{ "user": "Alice" }, { "user": "Bob" }],
        "template": {
          "name": "User <%= i + 1%>",
          "children": {
            "user": {
              "type": "text",
              "name": "UserName"
            }
          }
        }
      }
    }
    ```

-   The `template` field not configured \(fixed content\)

    ![Configuration example 2](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6389301161/p93025.png)

    ```
    {
      "tabs": {
        "name": "Components",
        "type": "tabs",
        "addable": false,
        "fold": false,
        "default": [{ "comType": "chart" }, { "show": false }],
        "children": [
          {
            "name": "Com A",
            "children": {
              "comType": {
                "name": "Com Type",
                "type": "text"
              }
            }
          },
          {
            "name": "Com B",
            "children": {
              "show": {
                "name": "Show",
                "type": "switch"
              }
            }
          }
        ]
      }
    }
    ```

-   Custom label and icon

    ![Configuration example 3](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6389301161/p93024.png)

    You must specify the URL of the icon.

    -   Configuration

        ```
         "tabs": {
            "name": "Tab",
            "type": "tabs",
            "template": {
              "name": "Industry <%= i + 1%>",
              "children": {
                "link": {
                  "type": "switch",
                  "name": "Link"
                }
              }
            }
        }
        ```

    -   Value

        ```
         "tabs": [
            {
              "apply": true,
              "_label": "Food Industry",
              "_icon": "https://img.alicdn.com/tfs/TB1fck7voH1gK0jSZSyXXXtlpXa-201-200.png"
            },
            {
              "apply": false
            }
        ]
        ```


