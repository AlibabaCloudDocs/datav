# Configuration of the valuePath field

When the GUI rendering configuration is not at the same level as the data to be rendered, you can use the valuePath field to associate the configuration with the data.

## Scenario

In the following example, the GUI rendering configuration is at the same level as the data:

-   GUI rendering configuration

    ```
    {
      "apply": {
        "type": "switch",
        "defalut": true
      },
      "snapTrd": {
        "type": "stepper",
        "default": 20
      }
    }
    ```

-   Data

    ```
    {
      "apply": true,
      "snapTrd": 20
    }
    ```


In the preceding example, `snapTrd` and `apply` are at the same level. However, in actual configuration, `snapTrd` is in the `space` object, and the `space` object is at the same level as `apply`. You can use the `valuePath` field to associate the configuration with the data. Example:

-   Configuration

    ```
    {
      "apply": {
        "type": "switch",
        "defalut": true
      },
      "snapTrd": {
        "type": "stepper",
        "default": 20,
        "valuePath": "space.snapTrd"
      }
    }
    ```

-   Data \(The `valuePath` field associates the values of apply and snapTrd.\)

    ```
    {
      "apply": true,
      "space": {
        "snapTrd": 20
      }
    }
    ```


## Configuration rules

-   If you use the `valuePath` field in a basic control, you can directly add the field. For more information, see [Example 1](#section_zue_pkh_jbg).
-   If you use the `valuePath` field in a frequently used control suite, control group, or menu, a child control inherits the settings of the `valuePath` field from the parent control. For more information, see [Example 2](#section_e2q_u29_wqv).
-   If you use the `valuePath` field in a group of tabs, a child control in a tab can only inherit the settings of the `valuePath` field from the tab. You cannot configure the `valuePath` field for the child control. For more information, see [Example 3](#section_eiv_we1_jmb).

## Example 1

-   Configuration

    ```
    {
      "paddingTop": {
        "type": "stepper",
        "name": "top",
        "default": 3,
        "valuePath": "chart.padding.top"
      },
      "paddingLeft": {
        "type": "hidden",
        "name": "left",
        "default": 10
      }
    }
    ```

-   Data

    ```
    {
      "chart": {
        "padding": {
          "top": 3
        }
      },
      "paddingLeft": 10
    }
    ```


## Example 2

-   Configuration

    ```
    {
      "padding": {
        "type": "group",
        "name": "Group",
        "default": {
          "top": 3,
          "left": 10
        },
        "valuePath": "chart.padding",
        "children": {
          "top": {
            "type": "stepper",
            "valuePath": "abc.top"
          },
          "left": {
            "type": "stepper"
          }
        }
      }
    }
    ```

-   Data

    ```
    {
      "abc": {
        "top": 3.5
      },
      "chart": {
        "padding": {
          "left": 10
        }
      }
    }
    ```


## Example 3

-   Configuration

    ```
    {
      "padding": {
        "type": "tabs",
        "name": "Group",
        "default": [
          {
            "top": 3,
            "left": 10
          }
        ],
        "valuePath": "chart.padding",
        "template": {
          "name": "Series <%= i + 1%>",
          "description": "This is series <%= i + 1%>",
          "children": {
            "top": {
              "type": "stepper"
            },
            "left": {
              "type": "stepper"
            }
          }
        }
      }
    }
    ```

-   Data

    ```
    {
      "chart": {
        "padding": [
          {
            "top": 3,
            "left": 10
          }
        ]
      }
    }
    ```


