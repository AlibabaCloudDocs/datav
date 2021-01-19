# Guide to ECharts widget encapsulation

This topic explains how to encapsulate ECharts widgets using the example [Bar Animation Delay](http://echarts.baidu.com/demo.html?spm=a2c4g.11186623.2.4.wQf3kR#bar-animation-delay) on the ECharts website. ECharts like this echarts.datatool type used as an example here are not directly compatible with DataV. Therefore, to encapsulate this chart type into a widget, you need to first extract the configurations and data of this EChart and then convert them into a supported format.

## Extract configurations and data

According to the configurations in the left-side code bar for this example, you can extract configurations and data from the option variable. The complete code is shown as follows.

```
var xAxisData = [];
var data1 = [];
var data2 = [];
for (var i = 0; i < 100; i++) {
    xAxisData.push('Catagory' + i);
    Data1.push (math. sin (I/5) * (I/5-10) + I/6) * 5 );
    data2.push((Math.cos(i / 5) * (i / 5 -10) + i / 6) * 5);
}
option = {
    title: {
        text: 'Bar Animation Delay'
    },
    legend: {
        data: ['bar', 'bar2'],
        align: 'left'
    },
    toolbox: {
        // y: 'bottom',
        feature: {
            magicType: {
                type: ['stack', 'tiled']
            },
            dataView: {},
            saveAsImage: {
                pixelRatio: 2
            }
        }
    },
    tooltip: {},
    xAxis: {
        data: xAxisData,
        silent: false,
        splitLine: {
            show: false
        }
    },
    yAxis: {
    },
    series: [{
        name: 'bar',
        type: 'bar',
        data: data1,
        animationDelay: function (idx) {
            return idx * 10;
        }
    }, {
        name: 'bar2',
        type: 'bar',
        data: data2,
        animationDelay: function (idx) {
            return idx * 10 + 100;
        }
    }],
    animationEasing: 'elasticOut',
    animationDelayUpdate: function (idx) {
        return idx * 5;
    }
};
```

In the preceding code, you can find the following data item configurations:

-   option.xAxis.data
-   option.series\[x\].data

To convert these configurations into data elements that are recognized by DataV, you must perform the following operations.

```
[
  {
    x: 'An item value of option, xAxis, and data', 
    y: 'An item value of option, series[x], and data', 
    s: 'An item value of option, series[x], and name'
  }
]
```

Except for the preceding three data items, the rest are configurations.

## Write package.json

Write the preceding configurations and data into package.json based on [package.json specifications](/intl.en-US/Developer Guide/Document structure/Specifications of a package.json file.md) . You need to note that:

-   You can delete configurations that are not required by your widgets.
-   If the configuration that you need is not in the example code, you can obtain it from [ECharts Chart Configuration](http://echarts.baidu.com/option.html?spm=a2c4g.11186623.2.5.wQf3kR).
-   Several ECharts configuration items are supported by DataV, except for the following items:
    -   Configuration items that are functions.
    -   Configuration items of some ECharts chart type, such as, echarts.datatool.xxx.
    -   Configuration items that contain more than one item type, such as both text and number types.
-   The configuration schema must match that of ECharts. If they cannot be matched due to incompatibility with DataV, you need to convert them in index.js so that they can match. Through this process, even ECharts like echarts.datatool, which are not directly supported by DataV, can be made compatible with DataV once converted.

The following is part of the ECharts-chart converted package.json from the preceding example.

```
{
  "datav": {
    "cn_name": "Bar chart",
    "icon": "",
    "protocol": 2,
    "type": [
      "regular_bar"
    ],
    "View ":{
      "width": "600",
      "height": "200",
      "minWidth": "40",
      "minHeight": "20"
    },
    "apis": {
      "source": {
        "handler": "render",
        "description": "Interface description of echarts animation delay chart",
        "fields": {
          "x": {
            "description": "Value of the x axis"
          },
          "y": {
            "description": "Value of the y axis"
          },
          "s": {
            "description": "Value of the y axis",
            "optional": true
          }
        }
      }
    },
    "config": {
      "legend": {
        //...
      },
      "grid": {
        //...
      },
      "xAxis": {
        "name": "x axis",
        "type": "group",
        "children": {
          "show": {
            "name": "Display",
            "type": "boolean",
            "default": false
          },
          "offset": {
            "name": "Offset",
            "type": "number",
            "default": 0
          },
          "type": {
            "name": "type",
            "type": "text",
            "default": "category"
          },
          "name": {
            "name": "name",
            "type": "text",
            "default": ""
          },
          "nameLocation": {
            "name": "Name location",
            "type": "text",
            "default": "end"
          },
          "nameTextStyle": {
            "name": "Name stype",
            "type": "group",
            "children": {
              "color": {
                "name": "Color",
                "type": "color",
                "default": "rgba(0,0,0,0)"
              },
              "fontStyle": {
                "name": "Font style",
                "type": "text",
                "default": "normal"
              },
              "fontWeight": {
                "name": "Font weight",
                "type": "text",
                "default": "normal"
              },
              "fontFamily": {
                "name": "Font family",
                "type": "text",
                "default": "sans-serif"
              },
              "fontSize": {
                "name": "Font size",
                "type": "number",
                "default": 10
              }
            },
            "fold": true
          },
          "nameGap": {
            "name": "Gap between names",
            "type": "number",
            "default": 15
          },
          "nameRotate": {
            "name": "Name rotation",
            "type": "number",
            "default": null
          },
          "inverse": {
            "name": "Inverse",
            "type": "boolean",
            "default": false
          },
          "boundaryGap": {
            "Name": "Boundary gap ",
            "type": "boolean",
            "default": true
          },
          "min": {
            "name": "Min",
            "type": "text",
            "default": "dataMin"
          },
          "max": {
            "name": "Max",
            "type": "text",
            "default": "dataMax"
          },
          "scale": {
            "name": "Auto scaling",
            "type": "boolean",
            "default": false
          },
          "splitNumber": {
            "name": "Split number",
            "type": "number",
            "default": 5
          },
          "minInterval": {
            "Name": "Min interval",
            "type": "number",
            "default": 0
          },
          "logBase": {
            "name": "Log base",
            "type": "number",
            "default": 10
          },
          "silent": {
            "name": "Silent",
            "type": "boolean",
            "default": false
          },
          "triggerEvent": {
            "name": "Trigger event",
            "type": "boolean",
            "default": false
          },
          "axisLine": {
            "name": "Axis line",
            "type": "group",
            "children": {
              "show": {
                "name": "Display",
                "type": "boolean",
                "default": false
              },
              "onZero": {
                "name": "On zero",
                "type": "boolean",
                "default": true
              },
              "lineStyle": {
                "name": "Line style",
                "type": "group",
                "children": {
                  "color": {
                    "name": "Color",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(255,255,255,. 8)"
                    }
                  },
                  "width": {
                    "name": "Width",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "Type",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "Opacity",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              }
            },
            "fold": true
          },
          "axisTick": {
            "name": "Axis tick",
            "type": "group",
            "children": {
              "show": {
                "name": "Display",
                "type": "boolean",
                "default": false
              },
              "alignWithLabel": {
                "name": "Align with label",
                "type": "boolean",
                "default": false
              },
              "interval": {
                "name": "Interval",
                "type": "number",
                "default": 0
              },
              "inside": {
                "name": "Inside",
                "type": "boolean",
                "default": false
              },
              "length": {
                "name": "Length",
                "type": "number",
                "default": 5
              },
              "lineStyle": {
                "name": "Line style",
                "type": "group",
                "children": {
                  "color": {
                    "name": "Color",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(255,255,255,. 8)"
                    }
                  },
                  "width": {
                    "name": "Width",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "Type",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "Opacity",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              }
            },
            "fold": true
          },
          "axisLabel": {
            "name": "Axis label",
            "type": "group",
            "children": {
              "show": {
                "name": "Show",
                "type": "boolean",
                "default": true
              },
              "interval": {
                "name": "Interval",
                "type": "number",
                "default": 13
              },
              "inside": {
                "name": "Inside",
                "type": "boolean",
                "default": false
              },
              "rotate": {
                "name": "Rotation",
                "type": "number",
                "default": 0
              },
              "margin": {
                "name": "Margin",
                "type": "number",
                "default": 8
              },
              "showMinLabel": {
                "name": "Show minimum label",
                "type": "boolean",
                "default": true
              },
              "showMaxLabel": {
                "name": "Show maximum label",
                "type": "boolean",
                "default": true
              },
              "textStyle": {
                "name": "Text style",
                "type": "group",
                "children": {
                  "color": {
                    "name": "Color",
                    "type": "color",
                    "default": "rgba(255,255,255,. 8)"
                  },
                  "fontStyle": {
                    "name": "Font style",
                    "type": "text",
                    "default": "normal"
                  },
                  "fontWeight": {
                    "name": "Font weight",
                    "type": "text",
                    "default": "normal"
                  },
                  "fontFamily": {
                    "name": "Font family",
                    "type": "text",
                    "default": "sans-serif"
                  },
                  "fontSize": {
                    "name": "Font size",
                    "type": "number",
                    "default": 10
                  },
                  "align": {
                    "name": "Alignment",
                    "type": "select",
                    "range": [
                      {
                        "name": "Auto",
                        "value": "auto"
                      },
                      {
                        "name": "Left",
                        "value": "left"
                      },
                      {
                        "name": "Center",
                        "Value": "center"
                      },
                      {
                        "name": "Right",
                        "value": "right"
                      }
                    ],
                    "default": ""
                  },
                  "baseline": {
                    "name": "Baseline",
                    "type": "text",
                    "default": ""
                  }
                },
                "fold": true
              }
            },
            "fold": true
          },
          "splitLine": {
            "name": "split line",
            "type": "group",
            "children": {
              "show": {
                "name": "show",
                "type": "boolean",
                "default": false
              },
              "interval": {
                "name": "interval",
                "type": "number",
                "Default": 0
              },
              "lineStyle": {
                "name": "Line style",
                "type": "group",
                "children": {
                  "width": {
                    "name": "Width",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "Type",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "Opacity",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              }
            },
            "fold": true
          },
          "splitArea": {
            "name": "split area",
            "type": "group",
            "children": {
              "interval": {
                "name": "interval",
                "type": "number",
                "default": 0
              },
              "show": {
                "name": "show",
                "type": "boolean",
                "default": false
              },
              "areaStyle": {
                "name": "Area style",
                "type": "group",
                "children": {
                  "opacity": {
                    "name": "Opacity",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              }
            },
            "fold": true
          },
          "axisPointer": {
            "name": "Axis pointer",
            "type": "group",
            "children": {
              "show": {
                "name": "Show",
                "type": "boolean",
                "default": true
              },
              "type": {
                "name": "Type",
                "type": "select",
                "default": "line",
                "range": [
                  {
                    "name": "Line pointer",
                    "value": "line"
                  },
                  {
                    "name": "Shadow pointer",
                    "value": "shadow"
                  }
                ]
              },
              "snap": {
                "name": "Snap",
                "type": "boolean",
                "default": false
              },
              "value": {
                "name": "Initial value",
                "type": "number",
                "default": null
              },
              "status": {
                "name": "Status",
                "type": "boolean",
                "default": false
              },
              "label": {
                "name": "Label",
                "type": "group",
                "children": {
                  "show": {
                    "name": "Show",
                    "type": "boolean",
                    "default": false
                  },
                  "precision": {
                    "name": "precision",
                    "type": "number",
                    "default": "'auto'"
                  },
                  "margin": {
                    "name": "Margin",
                    "type": "boolean",
                    "default": 3
                  },
                  "textStyle": {
                    "name": "Text style",
                    "Type": "group ",
                    "children": {
                      "color": {
                        "name": "Color",
                        "type": "color",
                        "default": "#ffffff"
                      },
                      "fontStyle": {
                        "name": "Font style",
                        "type": "text",
                        "default": "normal"
                      },
                      "fontWeight": {
                        "name": "Font weight",
                        "type": "text",
                        "default": "normal"
                      },
                      "fontFamily": {
                        "name": "Font family",
                        "type": "text",
                        "default": "sans-serif"
                      },
                      "fontSize": {
                        "name": "Font size",
                        "type": "number",
                        "default": 10
                      }
                    },
                    "fold": true
                  },
                  "backgroundColor": {
                    "name": "Background color",
                    "type": "text",
                    "default": "auto"
                  },
                  "borderColor": {
                    "name": "Border color",
                    "type": "text",
                    "default": ""
                  },
                  "borderWidth": {
                    "name": "Border width",
                    "type": "text",
                    "default": ""
                  }
                },
                "fold": true
              },
              "lineStyle": {
                "name": "Line style",
                "type": "group",
                "show": [
                  [
                    "type",
                    "$eq",
                    "line"
                  ]
                ],
                "children": {
                  "color": {
                    "name": "Color",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(0,0,0,0)"
                    }
                  },
                  "width": {
                    "name": "Width",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "Type",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "Opacity",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              },
              "shadowStyle": {
                "name": "Shadow style",
                "type": "group",
                "show": [
                  [
                    "type",
                    "$eq",
                    "shadow"
                  ]
                ],
                "children": {
                  "color": {
                    "name": "Color",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(150,150,150,0.3)"
                    }
                  },
                  "opacity": {
                    "name": "Opacity",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              },
              "handle": {
                "name": "Handle",
                "type": "group",
                "children": {
                  "show": {
                    "name": "Show",
                    "type": "boolean",
                    "default": false
                  },
                  "size": {
                    "name": "Size",
                    "type": "number",
                    "default": 45
                  },
                  "margin": {
                    "name": "Margin",
                    "type": "number",
                    "default": 50
                  },
                  "color": {
                    "name": "Color",
                    "type": "text",
                    "default": "#333"
                  },
                  "throttle": {
                    "name": "Throttle",
                    "type": "number",
                    "default": 40
                  }
                },
                "fold": true
              }
            },
            "fold": true
          }
        },
        "fold": true
      },
      "yAxis": {
        //...
      },
      "tooltip": {
        //...
      },
      "series": {
        "name": "Series",
        "type": "array",
        "fold": true,
        "default": [
          {
            "name": "bar",
            "type": "bar",
            "legendHoverLink": true,
            "coordinateSystem": "cartesian2d",
            "label": {
              "normal": {
                "show": false,
                "textStyle": {
                  "color": "#000",
                  "fontStyle": "normal",
                  "fontWeight": "normal",
                  "fontFamily": "sans-serif",
                  "fontSize": 10
                }
              },
              "emphasis": {
                "show": false,
                "textStyle": {
                  "color": "#000",
                  "fontStyle": "normal",
                  "fontWeight": "normal",
                  "fontFamily": "sans-serif",
                  "fontSize": 10
                }
              }
            },
            "itemStyle": {
              "normal": {
                "color": {
                  "style": "single",
                  "value": "#00c2ff"
                },
                "borderColor": {
                  "style": "single",
                  "value": "#000"
                },
                "borderWidth": 0,
                "borderType": "solid",
                "barBorderRadius": 0,
                "opacity": 1
              },
              "emphasis": {
                "color": {
                  "style": "single",
                  "value": "#00c2ff"
                },
                "borderColor": {
                  "style": "single",
                  "value": "#000"
                },
                "borderWidth": 0,
                "borderType": "solid",
                "opacity": 1
              }
            },
            "stack": "",
            "barWidth": "50%",
            "barMinHeight": 0,
            "barGap": "30%",
            "barCategoryGap": "20%",
            "silent": false
          },
          {
            "name": "bar2",
            "type": "bar",
            "legendHoverLink": true,
            "coordinateSystem": "cartesian2d",
            "label": {
              "normal": {
                "show": false,
                "textStyle": {
                  "color": "#000",
                  "fontStyle": "normal",
                  "fontWeight": "normal",
                  "fontFamily": "sans-serif",
                  "fontSize": 10
                }
              },
              "emphasis": {
                "show": false,
                "textStyle": {
                  "color": "#000",
                  "fontStyle": "normal",
                  "fontWeight": "normal",
                  "fontFamily": "sans-serif",
                  "fontSize": 10
                }
              }
            },
            "itemStyle": {
              "normal": {
                "color": {
                  "style": "single",
                  "value": "#5bffb0"
                },
                "borderColor": {
                  "style": "single",
                  "value": "#000"
                },
                "borderWidth": 0,
                "borderType": "solid",
                "barBorderRadius": 0,
                "opacity": 1
              },
              "emphasis": {
                "color": {
                  "style": "single",
                  "value": "#5bffb0"
                },
                "borderColor": {
                  "style": "single",
                  "value": "#000"
                },
                "borderWidth": 0,
                "borderType": "solid",
                "opacity": 1
              }
            },
            "stack": "",
            "barWidth": "50%",
            "barMinHeight": 0,
            "barGap": "30%",
            "barCategoryGap": "20%",
            "silent": false
          }
        ],
        "child": {
          "type": "object",
          "name": "Series <%= i+1 %>",
          "child": {
            "name": {
              "name": "Name",
              "type": "text",
              "default": ""
            },
            "legendHoverLink": {
              "name": "Legend hover link highlight",
              "type": "boolean",
              "default": true
            },
            "coordinateSystem": {
              "name": Coordinate system",
              "type": "text",
              "default": "cartesian2d"
            },
            "label": {
              "name": "Label",
              "type": "group",
              "children": {
                "normal": {
                  "name": "Normal",
                  "type": "group",
                  "children": {
                    "show": {
                      "name": "Show",
                      "type": "boolean",
                      "default": false
                    },
                    "textStyle": {
                      "name": "Text style",
                      "type": "group",
                      "children": {
                        "color": {
                          "name": "Color",
                          "type": "color",
                          "default": "#000"
                        },
                        "fontStyle": {
                          "name": "Font style",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontWeight": {
                          "name": "Font weight",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontFamily": {
                          "name": "Font family",
                          "type": "text",
                          "default": "sans-serif"
                        },
                        "fontSize": {
                          "name": "Font size",
                          "type": "number",
                          "default": 10
                        }
                      },
                      "fold": true
                    }
                  },
                  "fold": true
                },
                "emphasis": {
                  "name": "Emphasis",
                  "type": "group",
                  "children": {
                    "show": {
                      "name": "Show",
                      "type": "boolean",
                      "default": false
                    },
                    "textStyle": {
                      "name": "Text style",
                      "type": "group",
                      "children": {
                        "color": {
                          "name": "Color",
                          "type": "color",
                          "default": "#000"
                        },
                        "fontStyle": {
                          "name": "Font style",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontWeight": {
                          "name": "Font weight",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontFamily": {
                          "name": "Font family",
                          "type": "text",
                          "default": "sans-serif"
                        },
                        "fontSize": {
                          "name": "Font size",
                          "type": "number",
                          "default": 10
                        }
                      },
                      "fold": true
                    }
                  },
                  "fold": true
                }
              },
              "fold": true
            },
            "itemStyle": {
              "name": "Item style",
              "type": "group",
              "children": {
                "normal": {
                  "name": "Normal",
                  "type": "group",
                  "children": {
                    "color": {
                      "name": "Color",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "rgba(0,0,0,0)"
                      }
                    },
                    "borderColor": {
                      "name": "Border color",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "#000"
                      }
                    },
                    "borderWidth": {
                      "name": "Border width",
                      "type": "number",
                      "default": 0
                    },
                    "borderType": {
                      "name": "Border type",
                      "type": "text",
                      "default": "solid"
                    },
                    "barBorderRadius": {
                      "name": "Bar border radius",
                      "type": "number",
                      "default": 0
                    },
                    "opacity": {
                      "name": "Opacity",
                      "type": "number",
                      "default": 1
                    }
                  },
                  "fold": true
                },
                "emphasis": {
                  "name": "Emphasis",
                  "type": "group",
                  "children": {
                    "color": {
                      "name": "Color",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "rgba(0,0,0,0)"
                      }
                    },
                    "borderColor": {
                      "name": "Border color",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "#000"
                      }
                    },
                    "borderWidth": {
                      "name": "Border width",
                      "type": "number",
                      "default": 0
                    },
                    "borderType": {
                      "name": "Border type",
                      "type": "text",
                      "default": "solid"
                    },
                    "opacity": {
                      "name": "Opacity",
                      "type": "number",
                      "default": 1
                    }
                  },
                  "fold": true
                }
              },
              "fold": true
            },
            "stack": {
              "name": "Stack",
              "type": "text",
              "default": ""
            },
            "barWidth": {
              "name": "Bar width",
              "type": "text",
              "default": "50%"
            },
            "barMinHeight": {
              "name": "Minimum bar height",
              "type": "number",
              "default": 0
            },
            "barGap": {
              "name": "Bar gap",
              "type": "text",
              "default": "30%"
            },
            "barCategoryGap": {
              "name": "Bar Category Gap",
              "type": "text",
              "default": "20%"
            },
            "silent": {
              "name": "Silent",
              "type": "boolean",
              "Default": false
            }
          }
        }
      },
      "animation": {
        "name": "Animation",
        "type": "boolean",
        "default": true
      },
      "animationThreshold": {
        "name": "Animation threshold",
        "type": "number",
        "default": 2000
      },
      "animationDuration": {
        "name": "Animation duration",
        "type": "number",
        "default": 1000
      },
      "animationEasing": {
        "name": "Animation easing",
        "type": "text",
        "default": "elasticOut"
      }
    },
    "api_data": {
      "source": [
        {
          "x": "Source 0",
          "y": 0,
          "s": "bar"
        },
        {
          "x": "Source 0",
          "y": -50,
          "s": "bar2"
        },
        {
          "x": "Source 1",
          "y": -8.901463875624668,
          "s": "bar"
        },
        {
          "x": "Source 1",
          "y": -47.18992898088751,
          "s": "bar2"
        },
        {
          "x": "Source 2",
          "y": -17.025413764148556,
          "s": "bar"
        },
        {
          "x": "Source 2",
          "y": -42.54426104547181,
          "s": "bar2"
        },
        {
          "x": "Source 3",
          "y": -24.038196249566663,
          "s": "bar"
        },
        {
          "x": "Source 3",
          "y": -36.290773900754886,
          "s": "bar2"
        },
        {
          "x": "Source 4",
          "y": -29.66504684804471,
          "s": "bar"
        },
        {
          "x": "Source 4",
          "Y":-28.71517529663627,
          "s": "bar2"
        },
        {
          "x": "Source 5",
          "y": -33.699527649688676,
          "s": "bar"
        },
        {
          "x": "Source 5",
          "y": -20.146937097399626,
          "s": "bar2"
        },
        {
          "x": "Source 6",
          "y": -36.00971978255796,
          "s": "bar"
        },
        {
          "x": "Source 6",
          "y": -10.94374119697364,
          "s": "bar2"
        },
        {
          "x": "Source 7",
          "y": -36.541005056170455,
          "s": "bar"
        },
        {
          "x": "Source 7",
          "y": -1.4752538113770308,
          "s": "bar2"
        },
        {
          "x": "Source 8",
          "y": -35.31542466107655,
          "s": "bar"
        },
        {
          "x": "Source 8",
          "y": 7.893046603320797,
          "s": "bar2"
        },
        {
          "x": "Source 9",
          "y": -32.427752866005996,
          "s": "bar"
        },
        {
          "x": "Source 9",
          "y": 16.81528588241657,
          "s": "bar2"
        },
        {
          "x": "Source 10",
          "y": -28.038563739693934,
          "s": "bar"
        },
        {
          "x": "Source 10",
          "y": 24.979206795219028,
          "s": "bar2"
        },
        {
          "x": "Source 11",
          "y": -22.364693082297347,
          "s": "bar"
        },
        {
          "x": "Source 11",
          "y": 32.11821023962515,
          "s": "bar2"
        },
        {
          "x": "Source 12",
          "y": -15.667600860943732,
          "s": "bar"
        },
        {
          "x": "Source 12",
          "y": 38.02096119056733,
          "s": "bar2"
        },
        {
          "x": "Source 13",
          "y": -8.240217424060843,
          "s": "bar"
        },
        {
          "x": "Source 13",
          "y": 42.53821720798438,
          "s": "bar2"
        },
        {
          "x": "Source 14",
          "y": -0.3929067389459173,
          "s": "bar"
        },
        {
          "x": "Source 14",
          "y": 45.58667093073836,
          "s": "bar2"
        },
        {
          "x": "Source 15",
          "y": 7.560799717904647,
          "s": "bar"
        },
        {
          "x": "Source 15",
          "y": 47.14973738101559,
          "s": "bar2"
        },
        {
          "x": "Source 16",
          "y": 15.318054209871054,
          "s": "bar"
        },
        {
          "x": "Source 16",
          "y": 47.275355710354944,
          "s": "bar2"
        },
        ...
      ]
    }
  }
}
```

## Write index.js

To write the index.js file, complete the following steps. For more information, see [index.js specifications](/intl.en-US/Developer Guide/Document structure/Specifications of an index.js file.md).

1.  In the initaization function, run EChart.init.
2.  In the rendering function, run chart.setOption.
3.  In the scaling function, run chart.resize.
4.  In the clearing function, run chart.clear.
5.  In the destruction function, run chart.dispose.

