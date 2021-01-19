# Control overview

This topic provides an overview of controls used to configure DataV widgets. You can define the type and configuration of a control by using the `type` field in the package.json file.

## Control types

You can configure the following types of controls in the `type` field.

|Category|Control type|Description|
|--------|:-----------|:----------|
|Basic controls|[text](/intl.en-US/Developer Guide/Document structure/Control configuration/text.md)|Text input box. You can customize the prefix and suffix of the text input box.|
|[number](/intl.en-US/Developer Guide/Document structure/Control configuration/number.md)|Number input box.|
|[select]()|Selector. It supports option filtering and custom input. If you need to configure font options in the selector, you can enable the font rendering function to preview the fonts.|
|[search]()|Drop-down search box.|
|[color]()|Color picker.|
|[multicolor]()|Gradient color picker. You can configure one or more colors.|
|[array]()|Data series. You can configure a series of configuration items or colors.|
|[hidden]()|Hidden control. DataV does not render this control.|
|[boolean]()|Boolean control.|
|[radio]()|Common option button.|
|[checkbox]()|Check box. You can configure the width of options.|
|[buttonRadio]()|Option button in the box style.|
|[iconRadio]()|Option button with icons.|
|[percent]()|Percentage control.|
|[image]()|Image box.|
|[imageSelect]()|Decorative element.|
|[switch]()|Switch. You can specify whether to display the status text.|
|[stepper]()|Stepper. You can configure the step, maximum and minimum values, prefix, and suffix in a stepper.|
|[slider]()|Slider. You can configure a single or double slider and the step, maximum and minimum values, prefix, suffix, precision, and range of the slider.|
|[keyBoard]()|Keyboard control.|
|[fill]()|Padding box. Three types of padding boxes and their combinations are supported.|
|Frequently used control suites|[margin]()|Margin control suite. This suite consists of four steppers. You can customize the top, bottom, left, and right margins.|
|[line]()|Line control suite. This suite consists of a line weight stepper, curve option button, style selector, and solid color padding box.|
|[font]()|Font control suite. This suite consists of a font selector, font weight selector, font size stepper, and solid color padding box.|
|Combined controls|[suite]()|Control suite. The suite consists of multiple controls.|
|[tabs]()|Tab group. A tab group consists of multiple tabs. The tabs can be dynamically added or deleted.|
|[menu]()|Menu. A menu shows the hierarchical structure of controls. Level-1 and level-2 menus are supported.|
|[group]()|Control group. You can configure a group that consists of multiple controls and show or hide the controls. We recommend that you add controls of the same type to a group.|

**Note:** The keys in the configurations can not be reserved keywords, such as `default`, `show`, and `range`.

## Configuration example

The following example shows configurations to add controls for DataV widgets. DataV renders the controls on the config panel of the DataV console.

![Configuration example](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0669301161/p93131.png)

```
{
  "options": {
    "type": "menu",
    "children": {
      "chart": {
        "name": "Graph",
        "children": {
          "margin": {
            "type": "margin",
            "name": "Margin",
            "default": {
              "top": 20,
              "bottom": 30,
              "left": 35,
              "right": 15
            }
          },
          "loadAmount": {
            "name": "Maximum Data Records",
            "description": "To ensure the display effect of a project, you can specify the maximum number of data records to be loaded for calculation, layout, and rendering.",
            "type": "stepper",
            "default": 2000,
            "step": 1
          },
          "bar": {
            "name": "Bar Chart Style",
            "type": "group",
            "children": {
              "bgColor": {
                "name": "Background Color",
                "type": "fill",
                "default": "RGBA(255,255,255,0.1)"
              }
            }
          },
          "numericalLabel": {
            "name": "Value Label",
            "type": "group",
            "children": {
              "show": {
                "name": "Show/Hide",
                "type": "boolean",
                "default": false
              },
              "textStyle": {
                "type": "font",
                "name": "Text",
                "default": {
                  "fontFamily": "Microsoft Yahei",
                  "fontWeight": "normal",
                  "fontSize": 10,
                  "color": "#000"
                }
              },
              "pos": {
                "name": "Position",
                "type": "iconRadio",
                "default": "center",
                "options": [
                  {
                    "label": "Top",
                    "value": "top",
                    "src": "top-center-pos"
                  },
                  {
                    "label": "Center",
                    "value": "center",
                    "src": "middle-center-pos"
                  },
                  {
                    "label": "Bottom",
                    "value": "bottom",
                    "src": "bottom-center-pos"
                  }
                ]
              },
              "emptyData": {
                "name": "Empty Value",
                "type": "switch",
                "default": false
              }
            },
            "enableHide": true
          }
        },
        "type": "menuChild",
        "mode": "single"
      },
      "axis": {
        "name": "Axis",
        "children": {
          "xaxis": {
            "name": "X-axis",
            "children": {
              "isShow": {
                "type": "switch",
                "name": "X-axis Visible",
                "default": true
              },
              "boundaryGap": {
                "type": "slider",
                "name": "Border Spacing",
                "default": 0.6,
                "step": 0.01,
                "min": 0,
                "max": 1,
                "precision": 2,
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ],
                  "logicalType": "$and"
                }
              },
              "interval": {
                "type": "slider",
                "name": "Interval",
                "default": 0.6,
                "step": 0.01,
                "min": 0,
                "max": 0.95,
                "precision": 2,
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ],
                  "logicalType": "$and"
                }
              },
              "label": {
                "name": "Axis Label",
                "type": "group",
                "enableHide": true,
                "children": {
                  "show": {
                    "default": true
                  },
                  "format": {
                    "name": "Format",
                    "type": "select",
                    "default": "%m (Month)",
                    "description": "The time format is %m/%d/%Y %H:%M:%S. d indicates an integer, and .1f indicates a floating-point number.",
                    "options": [
                      {
                        "value": "d",
                        "label": "11 (Integer)"
                      },
                      {
                        "value": ".1f",
                        "label": "11.1 (Floating-point Number)"
                      },
                      {
                        "value": ".2f",
                        "label": "11.11 (Floating-point Number)"
                      },
                      {
                        "value": "%Y (Year)",
                        "label": "2016"
                      },
                      {
                        "value": "%Y",
                        "label": "2016 (Year)"
                      },
                      {
                        "value": "%m (Month) %d (Day)",
                        "label": "01 (Month) 01 (Day)"
                      },
                      {
                        "value": "%m/%d",
                        "label": "01/01 (Month/Day)"
                      },
                      {
                        "value": "%H:%M:%S",
                        "label": "02:30:00"
                      },
                      {
                        "value": "%H:%M",
                        "label": "02:30 (Hour:Minute)"
                      },
                      {
                        "value": "%Y/%m/%d %H:%M",
                        "label": "2016/01/01 02:30"
                      },
                      {
                        "value": "%Y/%m/%d",
                        "label": "2016/01/01"
                      },
                      {
                        "value": "%m/%d %H:%M",
                        "label": "01/01 02:30"
                      },
                      {
                        "value": "%m (Month)",
                        "label": "1 (Month)"
                      },
                      {
                        "value": "%d (Day)",
                        "label": "2 (Day)"
                      },
                      {
                        "value": "%Hh",
                        "label": "02h"
                      },
                      {
                        "value": "%H",
                        "label": "02 (Hour)"
                      },
                      {
                        "value": "%m-%d",
                        "label": "01-01"
                      },
                      {
                        "value": "%m.%d",
                        "label": "01.01"
                      }
                    ],
                    "filterable": true,
                    "allowCustom": true,
                    "showInPanel": {
                      "conditions": [
                        [
                          "..type",
                          "$ne",
                          "category"
                        ]
                      ]
                    }
                  },
                  "textarea": {
                    "type": "font",
                    "name": "Text",
                    "default": {
                      "fontFamily": "Microsoft Yahei",
                      "fontWeight": "normal",
                      "fontSize": 12,
                      "color": "rgb(144, 160, 174)"
                    }
                  },
                  "display": {
                    "type": "suite",
                    "name": "Axis Label Style",
                    "children": {
                      "angle": {
                        "name": "Angle",
                        "type": "iconRadio",
                        "default": "0",
                        "options": [
                          {
                            "value": "0",
                            "label": "Horizontal",
                            "src": "horizontal"
                          },
                          {
                            "value": "45",
                            "label": "Incline",
                            "src": "incline"
                          },
                          {
                            "value": "90",
                            "label": "Vertical",
                            "src": "vertical"
                          }
                        ],
                        "col": 12
                      },
                      "amount": {
                        "name": "Quantity",
                        "type": "stepper",
                        "default": 0,
                        "min": 0,
                        "step": 1,
                        "description": "The maximum number of axis scale labels that can be displayed",
                        "col": 12
                      },
                      "unit": {
                        "type": "text",
                        "default": "",
                        "name": "Unit",
                        "col": 12
                      }
                    }
                  }
                },
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              },
              "axisLine": {
                "name": "Axis Line",
                "type": "group",
                "children": {
                  "show": {
                    "default": true
                  },
                  "color": {
                    "type": "fill",
                    "name": "Color",
                    "default": "rgba(255, 255, 255, 0.1)"
                  }
                },
                "enableHide": true,
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              },
              "grid": {
                "name": "Grid Line",
                "type": "group",
                "children": {
                  "show": {
                    "default": false
                  },
                  "color": {
                    "type": "fill",
                    "name": "Color",
                    "default": "#fff"
                  }
                },
                "enableHide": true,
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              }
            },
            "enableHide": true
          },
          "yaxis": {
            "name": "Y-axis",
            "children": {
              "isShow": {
                "name": "Y-axis Visible",
                "type": "switch",
                "default": true
              },
              "extent": {
                "type": "suite",
                "name": "Range",
                "children": {
                  "min": {
                    "type": "select",
                    "name": "Minimum",
                    "default": "0",
                    "description": "You can specify a minimum value for the label.",
                    "options": [
                      {
                        "value": "auto",
                        "label": "Automatic Rounding"
                      },
                      {
                        "value": "dataMin",
                        "label": "Minimum Value"
                      }
                    ],
                    "filterable": true,
                    "allowCustom": true,
                    "col": 12
                  },
                  "max": {
                    "type": "select",
                    "name": "Maximum",
                    "default": "dataMax",
                    "description": "You can specify a maximum value for the label.",
                    "options": [
                      {
                        "value": "auto",
                        "label": "Automatic Rounding"
                      },
                      {
                        "value": "dataMax",
                        "label": "Maximum Value"
                      }
                    ],
                    "filterable": true,
                    "allowCustom": true,
                    "col": 12
                  }
                },
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              },
              "label": {
                "name": "Axis Label",
                "type": "group",
                "enableHide": true,
                "children": {
                  "format": {
                    "name": "Format",
                    "type": "select",
                    "default": ".0f",
                    "description": "d indicates an integer, and .1f indicates a floating-point number",
                    "options": [
                      {
                        "value": null,
                        "label": "Default"
                      },
                      {
                        "value": ".0f",
                        "label": "11 (Integer)"
                      },
                      {
                        "value": ".1f",
                        "label": "11.1 (Floating-point Number)"
                      },
                      {
                        "value": ".2f",
                        "label": "11.11 (Floating-point Number)"
                      },
                      {
                        "value": "%",
                        "label": "11%"
                      },
                      {
                        "value": ".1%",
                        "label": "11.1%"
                      },
                      {
                        "value": ".2%",
                        "label": "11.11%"
                      }
                    ],
                    "filterable": true,
                    "allowCustom": true
                  },
                  "textarea": {
                    "type": "font",
                    "name": "Text",
                    "default": {
                      "fontFamily": "Microsoft Yahei",
                      "fontWeight": "normal",
                      "fontSize": 12,
                      "color": "rgb(144, 160, 174)"
                    }
                  },
                  "display": {
                    "type": "suite",
                    "name": "Axis Label Style",
                    "children": {
                      "amount": {
                        "name": "Quantity",
                        "type": "stepper",
                        "default": 6,
                        "min": 0,
                        "step": 1,
                        "description": "The maximum number of axis scale labels that can be displayed",
                        "col": 12
                      },
                      "unit": {
                        "type": "text",
                        "name": "Unit",
                        "default": "",
                        "col": 12,
                        "enableHide": true
                      }
                    }
                  }
                },
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              },
              "axisLine": {
                "name": "Axis Line",
                "type": "group",
                "children": {
                  "show": {
                    "default": true
                  },
                  "color": {
                    "type": "fill",
                    "name": "Color",
                    "default": "rgba(255, 255, 255, 0.1)"
                  }
                },
                "enableHide": true,
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              },
              "grid": {
                "name": "Grid Line",
                "type": "group",
                "children": {
                  "show": {
                    "default": false
                  },
                  "color": {
                    "type": "fill",
                    "name": "Color",
                    "default": "#434343"
                  }
                },
                "enableHide": true,
                "showInPanel": {
                  "conditions": [
                    [
                      ".isShow",
                      "$eq",
                      true
                    ]
                  ]
                }
              }
            },
            "enableHide": true
          }
        },
        "type": "menuChild",
        "mode": "multiple"
      },
      "series": {
        "type": "menuChild",
        "name": "Series",
        "children": {
          "series2type": {
            "type": "switch",
            "name": "Change Series Type",
            "default": false
          },
          "series": {
            "type": "tabs",
            "name": "Data Series",
            "default": [
              {
                "color": {
                  "type": "flat",
                  "value": "rgb(10, 115, 255)"
                }
              }
            ],
            "template": {
              "type": "object",
              "name": "Series <%= i + 1%>",
              "children": {
                "color": {
                  "name": "Color",
                  "type": "fill",
                  "default": {
                    "type": "flat",
                    "value": "rgba(131,32,220,0.5)"
                  },
                  "components": [
                    "flat",
                    "linearGradient"
                  ]
                }
              }
            }
          }
        }
      },
      "others": {
        "name": "Others",
        "children": {
          "animation": {
            "name": "Animation Ease",
            "type": "group",
            "fold": true,
            "children": {
              "show": {
                "default": true
              },
              "setting": {
                "type": "suite",
                "name": "Animation Settings",
                "children": {
                  "animationEasing": {
                    "name": "Ease Effect",
                    "type": "select",
                    "options": [
                      {
                        "value": "linear",
                        "label": "linear"
                      },
                      {
                        "value": "quadraticIn",
                        "label": "quadraticIn"
                      },
                      {
                        "value": "quadraticOut",
                        "label": "quadraticOut"
                      },
                      {
                        "value": "quadraticInOut",
                        "label": "quadraticInOut"
                      },
                      {
                        "value": "cubicIn",
                        "label": "cubicIn"
                      },
                      {
                        "value": "cubicOut",
                        "label": "cubicOut"
                      },
                      {
                        "value": "cubicInOut",
                        "label": "cubicInOut"
                      },
                      {
                        "value": "quarticIn",
                        "label": "quarticIn"
                      },
                      {
                        "value": "quarticOut",
                        "label": "quarticOut"
                      },
                      {
                        "value": "quarticInOut",
                        "label": "quarticInOut"
                      },
                      {
                        "value": "quinticIn",
                        "label": "quinticIn"
                      },
                      {
                        "value": "quinticOut",
                        "label": "quinticOut"
                      },
                      {
                        "value": "quinticInOut",
                        "label": "quinticInOut"
                      },
                      {
                        "value": "sinusoidalIn",
                        "label": "sinusoidalIn"
                      },
                      {
                        "value": "sinusoidalOut",
                        "label": "sinusoidalOut"
                      },
                      {
                        "value": "sinusoidalInOut",
                        "label": "sinusoidalInOut"
                      },
                      {
                        "value": "exponentialIn",
                        "label": "exponentialIn"
                      },
                      {
                        "value": "exponentialOut",
                        "label": "exponentialOut"
                      },
                      {
                        "value": "exponentialInOut",
                        "label": "exponentialInOut"
                      },
                      {
                        "value": "circularIn",
                        "label": "circularIn"
                      },
                      {
                        "value": "circularOut",
                        "label": "circularOut"
                      },
                      {
                        "value": "circularInOut",
                        "label": "circularInOut"
                      },
                      {
                        "value": "elasticIn",
                        "label": "elasticIn"
                      },
                      {
                        "value": "elasticOut",
                        "label": "elasticOut"
                      },
                      {
                        "value": "elasticInOut",
                        "label": "elasticInOut"
                      },
                      {
                        "value": "backIn",
                        "label": "backIn"
                      },
                      {
                        "value": "backOut",
                        "label": "backOut"
                      },
                      {
                        "value": "backInOut",
                        "label": "backInOut"
                      },
                      {
                        "value": "bounceIn",
                        "label": "bounceIn"
                      },
                      {
                        "value": "bounceOut",
                        "label": "bounceOut"
                      },
                      {
                        "value": "bounceInOut",
                        "label": "bounceInOut"
                      }
                    ],
                    "default": "cubicInOut",
                    "filterable": true,
                    "allowCustom": true,
                    "col": 12
                  },
                  "animationAfterPreviousSeries": {
                    "name": "Animation for Each Series in Sequence",
                    "type": "switch",
                    "default": false,
                    "col": 12
                  }
                }
              },
              "enter": {
                "type": "suite",
                "name": "Ease-in",
                "children": {
                  "animationDuration": {
                    "name": "Initial Animation Duration",
                    "type": "stepper",
                    "step": 1,
                    "default": 1000,
                    "col": 12,
                    "suffix": "ms"
                  }
                }
              },
              "update": {
                "type": "suite",
                "name": "Update",
                "children": {
                  "animationDurationUpdate": {
                    "name": "Update Animation Duration",
                    "type": "stepper",
                    "default": 300,
                    "step": 1,
                    "col": 12,
                    "suffix": "ms"
                  },
                  "animationUpdateFromPrevious": {
                    "name": "Start from Previous Position",
                    "type": "switch",
                    "default": true,
                    "col": 12
                  }
                }
              }
            },
            "enableHide": true
          },
          "tooltip": {
            "name": "Tips",
            "type": "group",
            "fold": true,
            "children": {
              "show": {
                "default": true
              },
              "hideDelay": {
                "name": "Ease-out Delay",
                "type": "stepper",
                "default": 100,
                "step": 1,
                "suffix": "ms"
              },
              "trigger": {
                "type": "suite",
                "name": "Trigger",
                "children": {
                  "type": {
                    "name": "Trigger Type",
                    "type": "iconRadio",
                    "options": [
                      {
                        "value": "item",
                        "label": "Data Item",
                        "src": "item"
                      },
                      {
                        "value": "axis",
                        "label": "Axis",
                        "src": "axis"
                      }
                    ],
                    "default": "item",
                    "col": 12
                  },
                  "action": {
                    "name": "Trigger Action",
                    "type": "iconRadio",
                    "options": [
                      {
                        "value": "hover",
                        "label": "Hover",
                        "src": "hover"
                      },
                      {
                        "value": "click",
                        "label": "Click",
                        "src": "click"
                      }
                    ],
                    "default": "hover",
                    "col": 12
                  }
                }
              },
              "textStyle": {
                "name": "Text Style",
                "type": "font",
                "default": {
                  "fontFamily": "Microsoft Yahei",
                  "fontWeight": "normal",
                  "fontSize": 14,
                  "color": "#fff"
                }
              },
              "axisPointer": {
                "name": "Axis Indicator",
                "type": "group",
                "fold": true,
                "children": {
                  "show": {
                    "name": "Show/Hide",
                    "type": "boolean",
                    "default": true
                  },
                  "_type": {
                    "name": "Type",
                    "type": "select",
                    "options": [
                      {
                        "name": "Line Indicator",
                        "value": "line"
                      }
                    ],
                    "default": "line",
                    "showInPanel": {
                      "conditions": [
                        [
                          ".show",
                          "$eq",
                          true
                        ]
                      ]
                    }
                  },
                  "lineStyle": {
                    "name": "Line Style",
                    "type": "suite",
                    "fold": true,
                    "showInPanel": {
                      "conditions": [
                        [
                          ".show",
                          "$eq",
                          true
                        ],
                        [
                          "._type",
                          "$eq",
                          "line"
                        ]
                      ]
                    },
                    "children": {
                      "width": {
                        "name": "Width",
                        "type": "stepper",
                        "step": 1,
                        "default": 1,
                        "col": 12,
                        "suffix": "px"
                      },
                      "_type": {
                        "name": "Type",
                        "type": "iconRadio",
                        "options": [
                          {
                            "name": "Solid Line",
                            "value": "solid",
                            "src": "solid"
                          },
                          {
                            "name": "Dashed Line",
                            "value": "dashed",
                            "src": "dashed-line"
                          },
                          {
                            "name": "Dotted Line",
                            "value": "dotted",
                            "src": "dot-line"
                          }
                        ],
                        "default": "solid",
                        "col": 12
                      },
                      "color": {
                        "name": "Color",
                        "type": "fill",
                        "default": "#f00",
                        "col": 24
                      }
                    }
                  }
                },
                "enableHide": true,
                "showInPanel": {
                  "conditions": [
                    [
                      ".trigger.type",
                      "$eq",
                      "axis"
                    ]
                  ]
                }
              },
              "bgBox": {
                "name" : "Background Box Style",
                "type": "group",
                "children": {
                  "backgroundColor": {
                    "name": "Background Color",
                    "type": "fill",
                    "default": "rgba(0, 0, 0, 0.65)"
                  },
                  "customSize": {
                    "name": "Custom",
                    "type": "suite",
                    "children": {
                      "show": {
                        "default": false
                      },
                      "width": {
                        "name": "Width",
                        "type": "stepper",
                        "default": 150,
                        "step": 1,
                        "col": 12,
                        "suffix": "px"
                      },
                      "height": {
                        "name": "Height",
                        "type": "stepper",
                        "default": 50,
                        "step": 1,
                        "col": 12,
                        "suffix": "px"
                      }
                    },
                    "enableHide": true
                  },
                  "padding": {
                    "name": "Inner Margin",
                    "type": "stepper",
                    "default": 10,
                    "step": 1,
                    "suffix": "px"
                  },
                  "offset": {
                    "type": "suite",
                    "name": "Offset",
                    "children": {
                      "xOffset": {
                        "name": "Horizontal Offset",
                        "type": "stepper",
                        "default": 6,
                        "step": 1,
                        "col": 12,
                        "suffix": "px"
                      },
                      "yOffset": {
                        "name": "Vertical Offset",
                        "type": "stepper",
                        "default": 10,
                        "step": 1,
                        "col": 12,
                        "suffix": "px"
                      }
                    }
                  },
                  "border": {
                    "type": "suite",
                    "name": "Border",
                    "children": {
                      "borderWidth": {
                        "name": "Border Width",
                        "type": "stepper",
                        "step": 1,
                        "default": 0,
                        "col": 12,
                        "suffix": "px"
                      },
                      "borderColor": {
                        "name": "Border Color",
                        "type": "fill",
                        "default": "#333",
                        "col": 12
                      }
                    }
                  }
                }
              }
            },
            "enableHide": true
          }
        },
        "type": "menuChild",
        "mode": "single"
      }
    }
  }
}
```

