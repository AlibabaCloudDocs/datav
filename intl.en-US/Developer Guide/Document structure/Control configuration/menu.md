# menu

You can configure a menu to show the hierarchical structure of controls. Level-1 and level-2 menus are supported.

## Menu styles

-   Level-1 menu

    ![Level-1 menu](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4489301161/p93032.png)

-   Level-2 menu

    ![Level-2 menu](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5489301161/p93033.png)


## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|object|No|If this field is not specified, the default value is empty.|
|`children`|The menu content.|object|No|Default value: `{}`. The `mode` and `name` fields must be configured. -   `mode`: whether a level-2 menu is configured. If you set this field to `single`, a level-1 menu is configured. If you set this field to `multiple`, a level-2 menu is configured.
-   `name`: the name of the menu. |

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|object|```
"options": {
   "menuA": {
     "switch": true
   },
   "menuB": {
     "menuB1": {
       "text": "Hello"
     },
     "menuB2": {
       "stepper": 2
     }
   }
 }
```

|```
{}
``` |

## Configuration examples

![Configuration example of a menu](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5489301161/p93034.png)

```
{
  "menu": {
    "name": "Menu",
    "type": "menu",
    "children": {
      "menuA": {
        "name": "Menu A",
        "mode": "single",
        "children": {
          "switch": {
            "name": "Open ",
            "type": "switch",
            "default": true
          }
        }
      },
      "menuB": {
        "name": "Menu B",
        "mode": "multiple",
        "children": {
          "menuB1": {
            "name": "Menu B1",
            "children": {
              "text": {
                "name": "Name",
                "type": "text",
                "default": "Alice"
              }
            }
          },
          "menuB2": {
            "name": "Menu B2",
            "children": {
              "stepper": {
                "name": "Age",
                "type": "stepper",
                "default": 22
              }
            }
          }
        }
      }
    }
  }
}
```

