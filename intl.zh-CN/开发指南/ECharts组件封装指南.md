# ECharts组件封装指南

您可在ECharts官网找到适合自己需求的图表，例如本教程的案例[柱状图动画延迟](https://www.echartsjs.com/examples/zh/editor.html?c=bar-animation-delay)。

## 抽离配置与数据

根据案例左侧代码栏中的配置，可以将一整个option抽离出配置与数据。案例的完整代码如下所示。

```
var xAxisData = [];
var data1 = [];
var data2 = [];
for (var i = 0; i < 100; i++) {
    xAxisData.push('类目' + i);
    data1.push((Math.sin(i / 5) * (i / 5 -10) + i / 6) * 5);
    data2.push((Math.cos(i / 5) * (i / 5 -10) + i / 6) * 5);
}
option = {
    title: {
        text: '柱状图动画延迟'
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

其中含有数据项的配置，如下所示。

-   option.xAxis.data
-   option.series\[x\].data

为了转换为DataV能识别的细化到数据元的数据，您可进行如下操作。

```
[
  {
    x: 'option.xAxis.data的某一项值', 
    y: 'option.series[x].data的某一项值', 
    s: 'option.series[x].name'
  }
]
```

除上述三项配置属于数据外，其他都属于配置。

## 填写package.json

将梳理的配置和数据按照 [package.json 规范](/intl.zh-CN/开发指南/文档结构/package.json规范.md) 写入package.json，需要注意以下几点。

-   可以删除自己组件不需要的配置。
-   若需要案例代码中没有的配置，可从[ECharts配置项手册](http://echarts.baidu.com/option.html?spm=a2c4g.11186623.2.5.wQf3kR)中获取。
-   ECharts配置项种类繁多，大部分都已支持，但是不支持：
    -   配置项是函数。
    -   ECharts自己的类型，例如echarts.datatool.xxx。
    -   目前也暂不支持一个配置项有多种类型，例如既可以是text类型，也可以是number类型。
-   配置结构与ECharts一致，若确实不能一致，需要在index.js中自己实现转换（所以也可以支持echarts.datatool等echarts类型）。

可单击[此处](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/64800/cn_zh/1553830969679/package.json)下载package.json完整示例文件。

示例文件中的ECharts转换后的部分package.json，如下所示：

```
{
  "datav": {
    "cn_name": "柱状图",
    "icon": "",
    "protocol": 2,
    "type": [
      "regular_bar"
    ],
    "view": {
      "width": "600",
      "height": "200",
      "minWidth": "40",
      "minHeight": "20"
    },
    "apis": {
      "source": {
        "handler": "render",
        "description": "echarts动画延迟柱状图接口描述",
        "fields": {
          "x": {
            "description": "x坐标轴值"
          },
          "y": {
            "description": "y坐标轴值"
          },
          "s": {
            "description": "系列值",
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
        "name": "x轴",
        "type": "group",
        "children": {
          "show": {
            "name": "显示",
            "type": "boolean",
            "default": false
          },
          "offset": {
            "name": "位移",
            "type": "number",
            "default": 0
          },
          "type": {
            "name": "类型",
            "type": "text",
            "default": "category"
          },
          "name": {
            "name": "名称",
            "type": "text",
            "default": ""
          },
          "nameLocation": {
            "name": "名称位置",
            "type": "text",
            "default": "end"
          },
          "nameTextStyle": {
            "name": "名称样式",
            "type": "group",
            "children": {
              "color": {
                "name": "颜色",
                "type": "color",
                "default": "rgba(0,0,0,0)"
              },
              "fontStyle": {
                "name": "字体样式",
                "type": "text",
                "default": "normal"
              },
              "fontWeight": {
                "name": "字体粗细",
                "type": "text",
                "default": "normal"
              },
              "fontFamily": {
                "name": "字体",
                "type": "text",
                "default": "sans-serif"
              },
              "fontSize": {
                "name": "字号",
                "type": "number",
                "default": 10
              }
            },
            "fold": true
          },
          "nameGap": {
            "name": "名称间隔",
            "type": "number",
            "default": 15
          },
          "nameRotate": {
            "name": "名称旋转",
            "type": "number",
            "default": null
          },
          "inverse": {
            "name": "反向",
            "type": "boolean",
            "default": false
          },
          "boundaryGap": {
            "name": "留白",
            "type": "boolean",
            "default": true
          },
          "min": {
            "name": "最小值",
            "type": "text",
            "default": "dataMin"
          },
          "max": {
            "name": "最大值",
            "type": "text",
            "default": "dataMax"
          },
          "scale": {
            "name": "自动伸缩",
            "type": "boolean",
            "default": false
          },
          "splitNumber": {
            "name": "分割段数",
            "type": "number",
            "default": 5
          },
          "minInterval": {
            "name": "最小间隔大小",
            "type": "number",
            "default": 0
          },
          "logBase": {
            "name": "对数轴底数",
            "type": "number",
            "default": 10
          },
          "silent": {
            "name": "静态",
            "type": "boolean",
            "default": false
          },
          "triggerEvent": {
            "name": "触发事件",
            "type": "boolean",
            "default": false
          },
          "axisLine": {
            "name": "轴线",
            "type": "group",
            "children": {
              "show": {
                "name": "显示",
                "type": "boolean",
                "default": false
              },
              "onZero": {
                "name": "在零上",
                "type": "boolean",
                "default": true
              },
              "lineStyle": {
                "name": "轴线样式",
                "type": "group",
                "children": {
                  "color": {
                    "name": "颜色",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(255,255,255,.8)"
                    }
                  },
                  "width": {
                    "name": "宽度",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "类型",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "透明度",
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
            "name": "刻度",
            "type": "group",
            "children": {
              "show": {
                "name": "显示",
                "type": "boolean",
                "default": false
              },
              "alignWithLabel": {
                "name": "和标签对齐",
                "type": "boolean",
                "default": false
              },
              "interval": {
                "name": "分割间隔",
                "type": "number",
                "default": 0
              },
              "inside": {
                "name": "内部",
                "type": "boolean",
                "default": false
              },
              "length": {
                "name": "长度",
                "type": "number",
                "default": 5
              },
              "lineStyle": {
                "name": "轴线样式",
                "type": "group",
                "children": {
                  "color": {
                    "name": "颜色",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(255,255,255,.8)"
                    }
                  },
                  "width": {
                    "name": "宽度",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "类型",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "透明度",
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
            "name": "刻度标签",
            "type": "group",
            "children": {
              "show": {
                "name": "显示",
                "type": "boolean",
                "default": true
              },
              "interval": {
                "name": "分割间隔",
                "type": "number",
                "default": 13
              },
              "inside": {
                "name": "内部",
                "type": "boolean",
                "default": false
              },
              "rotate": {
                "name": "旋转",
                "type": "number",
                "default": 0
              },
              "margin": {
                "name": "外间距",
                "type": "number",
                "default": 8
              },
              "showMinLabel": {
                "name": "显示最小标签",
                "type": "boolean",
                "default": true
              },
              "showMaxLabel": {
                "name": "显示最大标签",
                "type": "boolean",
                "default": true
              },
              "textStyle": {
                "name": "文本样式",
                "type": "group",
                "children": {
                  "color": {
                    "name": "颜色",
                    "type": "color",
                    "default": "rgba(255,255,255,.8)"
                  },
                  "fontStyle": {
                    "name": "字体样式",
                    "type": "text",
                    "default": "normal"
                  },
                  "fontWeight": {
                    "name": "字体粗细",
                    "type": "text",
                    "default": "normal"
                  },
                  "fontFamily": {
                    "name": "字体",
                    "type": "text",
                    "default": "sans-serif"
                  },
                  "fontSize": {
                    "name": "字号",
                    "type": "number",
                    "default": 10
                  },
                  "align": {
                    "name": "对齐",
                    "type": "select",
                    "range": [
                      {
                        "name": "自动",
                        "value": "auto"
                      },
                      {
                        "name": "左对齐",
                        "value": "left"
                      },
                      {
                        "name": "居中对齐",
                        "value": "center"
                      },
                      {
                        "name": "右对齐",
                        "value": "right"
                      }
                    ],
                    "default": ""
                  },
                  "baseline": {
                    "name": "基线",
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
            "name": "分割线",
            "type": "group",
            "children": {
              "show": {
                "name": "显示",
                "type": "boolean",
                "default": false
              },
              "interval": {
                "name": "分割间隔",
                "type": "number",
                "default": 0
              },
              "lineStyle": {
                "name": "轴线样式",
                "type": "group",
                "children": {
                  "width": {
                    "name": "宽度",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "类型",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "透明度",
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
            "name": "分割区域",
            "type": "group",
            "children": {
              "interval": {
                "name": "分割间隔",
                "type": "number",
                "default": 0
              },
              "show": {
                "name": "显示",
                "type": "boolean",
                "default": false
              },
              "areaStyle": {
                "name": "区域样式",
                "type": "group",
                "children": {
                  "opacity": {
                    "name": "透明度",
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
            "name": "坐标轴指示器",
            "type": "group",
            "children": {
              "show": {
                "name": "显示",
                "type": "boolean",
                "default": true
              },
              "type": {
                "name": "类型",
                "type": "select",
                "default": "line",
                "range": [
                  {
                    "name": "直线指示器",
                    "value": "line"
                  },
                  {
                    "name": "阴影指示器",
                    "value": "shadow"
                  }
                ]
              },
              "snap": {
                "name": "自动吸附",
                "type": "boolean",
                "default": false
              },
              "value": {
                "name": "初始值",
                "type": "number",
                "default": null
              },
              "status": {
                "name": "状态",
                "type": "boolean",
                "default": false
              },
              "label": {
                "name": "标签",
                "type": "group",
                "children": {
                  "show": {
                    "name": "显示",
                    "type": "boolean",
                    "default": false
                  },
                  "precision": {
                    "name": "小数精度",
                    "type": "number",
                    "default": "'auto'"
                  },
                  "margin": {
                    "name": "外间距",
                    "type": "boolean",
                    "default": 3
                  },
                  "textStyle": {
                    "name": "文本样式",
                    "type": "group",
                    "children": {
                      "color": {
                        "name": "颜色",
                        "type": "color",
                        "default": "#ffffff"
                      },
                      "fontStyle": {
                        "name": "字体样式",
                        "type": "text",
                        "default": "normal"
                      },
                      "fontWeight": {
                        "name": "字体粗细",
                        "type": "text",
                        "default": "normal"
                      },
                      "fontFamily": {
                        "name": "字体",
                        "type": "text",
                        "default": "sans-serif"
                      },
                      "fontSize": {
                        "name": "字号",
                        "type": "number",
                        "default": 10
                      }
                    },
                    "fold": true
                  },
                  "backgroundColor": {
                    "name": "背景色",
                    "type": "text",
                    "default": "auto"
                  },
                  "borderColor": {
                    "name": "边框色",
                    "type": "text",
                    "default": ""
                  },
                  "borderWidth": {
                    "name": "边框粗细",
                    "type": "text",
                    "default": ""
                  }
                },
                "fold": true
              },
              "lineStyle": {
                "name": "轴线样式",
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
                    "name": "颜色",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(0,0,0,0)"
                    }
                  },
                  "width": {
                    "name": "宽度",
                    "type": "number",
                    "default": 1
                  },
                  "type": {
                    "name": "类型",
                    "type": "text",
                    "default": "solid"
                  },
                  "opacity": {
                    "name": "透明度",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              },
              "shadowStyle": {
                "name": "阴影样式",
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
                    "name": "颜色",
                    "type": "multicolor",
                    "default": {
                      "style": "single",
                      "value": "rgba(150,150,150,0.3)"
                    }
                  },
                  "opacity": {
                    "name": "透明度",
                    "type": "number",
                    "default": 1
                  }
                },
                "fold": true
              },
              "handle": {
                "name": "拖拽手柄",
                "type": "group",
                "children": {
                  "show": {
                    "name": "显示",
                    "type": "boolean",
                    "default": false
                  },
                  "size": {
                    "name": "大小",
                    "type": "number",
                    "default": 45
                  },
                  "margin": {
                    "name": "外间距",
                    "type": "number",
                    "default": 50
                  },
                  "color": {
                    "name": "颜色",
                    "type": "text",
                    "default": "#333"
                  },
                  "throttle": {
                    "name": "刷新频率",
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
        "name": "系列",
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
          "name": "系列<%= i+1 %>",
          "child": {
            "name": {
              "name": "名称",
              "type": "text",
              "default": ""
            },
            "legendHoverLink": {
              "name": "图例联动高亮",
              "type": "boolean",
              "default": true
            },
            "coordinateSystem": {
              "name": "坐标系",
              "type": "text",
              "default": "cartesian2d"
            },
            "label": {
              "name": "标签",
              "type": "group",
              "children": {
                "normal": {
                  "name": "普通项",
                  "type": "group",
                  "children": {
                    "show": {
                      "name": "显示",
                      "type": "boolean",
                      "default": false
                    },
                    "textStyle": {
                      "name": "文本样式",
                      "type": "group",
                      "children": {
                        "color": {
                          "name": "颜色",
                          "type": "color",
                          "default": "#000"
                        },
                        "fontStyle": {
                          "name": "字体样式",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontWeight": {
                          "name": "字体粗细",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontFamily": {
                          "name": "字体",
                          "type": "text",
                          "default": "sans-serif"
                        },
                        "fontSize": {
                          "name": "字号",
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
                  "name": "重点项",
                  "type": "group",
                  "children": {
                    "show": {
                      "name": "显示",
                      "type": "boolean",
                      "default": false
                    },
                    "textStyle": {
                      "name": "文本样式",
                      "type": "group",
                      "children": {
                        "color": {
                          "name": "颜色",
                          "type": "color",
                          "default": "#000"
                        },
                        "fontStyle": {
                          "name": "字体样式",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontWeight": {
                          "name": "字体粗细",
                          "type": "text",
                          "default": "normal"
                        },
                        "fontFamily": {
                          "name": "字体",
                          "type": "text",
                          "default": "sans-serif"
                        },
                        "fontSize": {
                          "name": "字号",
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
              "name": "元素样式",
              "type": "group",
              "children": {
                "normal": {
                  "name": "普通项",
                  "type": "group",
                  "children": {
                    "color": {
                      "name": "颜色",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "rgba(0,0,0,0)"
                      }
                    },
                    "borderColor": {
                      "name": "边框色",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "#000"
                      }
                    },
                    "borderWidth": {
                      "name": "边框粗细",
                      "type": "number",
                      "default": 0
                    },
                    "borderType": {
                      "name": "边框样式",
                      "type": "text",
                      "default": "solid"
                    },
                    "barBorderRadius": {
                      "name": "柱状图圆角",
                      "type": "number",
                      "default": 0
                    },
                    "opacity": {
                      "name": "透明度",
                      "type": "number",
                      "default": 1
                    }
                  },
                  "fold": true
                },
                "emphasis": {
                  "name": "重点项",
                  "type": "group",
                  "children": {
                    "color": {
                      "name": "颜色",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "rgba(0,0,0,0)"
                      }
                    },
                    "borderColor": {
                      "name": "边框色",
                      "type": "multicolor",
                      "default": {
                        "style": "single",
                        "value": "#000"
                      }
                    },
                    "borderWidth": {
                      "name": "边框粗细",
                      "type": "number",
                      "default": 0
                    },
                    "borderType": {
                      "name": "边框样式",
                      "type": "text",
                      "default": "solid"
                    },
                    "opacity": {
                      "name": "透明度",
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
              "name": "堆叠图",
              "type": "text",
              "default": ""
            },
            "barWidth": {
              "name": "柱子宽度",
              "type": "text",
              "default": "50%"
            },
            "barMinHeight": {
              "name": "柱状图最小高度",
              "type": "number",
              "default": 0
            },
            "barGap": {
              "name": "柱状图间隔",
              "type": "text",
              "default": "30%"
            },
            "barCategoryGap": {
              "name": "类目间柱子间距",
              "type": "text",
              "default": "20%"
            },
            "silent": {
              "name": "静态",
              "type": "boolean",
              "default": false
            }
          }
        }
      },
      "animation": {
        "name": "动画",
        "type": "boolean",
        "default": true
      },
      "animationThreshold": {
        "name": "动画阈值",
        "type": "number",
        "default": 2000
      },
      "animationDuration": {
        "name": "动画时长",
        "type": "number",
        "default": 1000
      },
      "animationEasing": {
        "name": "缓动效果",
        "type": "text",
        "default": "elasticOut"
      }
    },
    "api_data": {
      "source": [
        {
          "x": "类目0",
          "y": 0,
          "s": "bar"
        },
        {
          "x": "类目0",
          "y": -50,
          "s": "bar2"
        },
        {
          "x": "类目1",
          "y": -8.901463875624668,
          "s": "bar"
        },
        {
          "x": "类目1",
          "y": -47.18992898088751,
          "s": "bar2"
        },
        {
          "x": "类目2",
          "y": -17.025413764148556,
          "s": "bar"
        },
        {
          "x": "类目2",
          "y": -42.54426104547181,
          "s": "bar2"
        },
        {
          "x": "类目3",
          "y": -24.038196249566663,
          "s": "bar"
        },
        {
          "x": "类目3",
          "y": -36.290773900754886,
          "s": "bar2"
        },
        {
          "x": "类目4",
          "y": -29.66504684804471,
          "s": "bar"
        },
        {
          "x": "类目4",
          "y": -28.71517529663627,
          "s": "bar2"
        },
        {
          "x": "类目5",
          "y": -33.699527649688676,
          "s": "bar"
        },
        {
          "x": "类目5",
          "y": -20.146937097399626,
          "s": "bar2"
        },
        {
          "x": "类目6",
          "y": -36.00971978255796,
          "s": "bar"
        },
        {
          "x": "类目6",
          "y": -10.94374119697364,
          "s": "bar2"
        },
        {
          "x": "类目7",
          "y": -36.541005056170455,
          "s": "bar"
        },
        {
          "x": "类目7",
          "y": -1.4752538113770308,
          "s": "bar2"
        },
        {
          "x": "类目8",
          "y": -35.31542466107655,
          "s": "bar"
        },
        {
          "x": "类目8",
          "y": 7.893046603320797,
          "s": "bar2"
        },
        {
          "x": "类目9",
          "y": -32.427752866005996,
          "s": "bar"
        },
        {
          "x": "类目9",
          "y": 16.81528588241657,
          "s": "bar2"
        },
        {
          "x": "类目10",
          "y": -28.038563739693934,
          "s": "bar"
        },
        {
          "x": "类目10",
          "y": 24.979206795219028,
          "s": "bar2"
        },
        {
          "x": "类目11",
          "y": -22.364693082297347,
          "s": "bar"
        },
        {
          "x": "类目11",
          "y": 32.11821023962515,
          "s": "bar2"
        },
        {
          "x": "类目12",
          "y": -15.667600860943732,
          "s": "bar"
        },
        {
          "x": "类目12",
          "y": 38.02096119056733,
          "s": "bar2"
        },
        {
          "x": "类目13",
          "y": -8.240217424060843,
          "s": "bar"
        },
        {
          "x": "类目13",
          "y": 42.53821720798438,
          "s": "bar2"
        },
        {
          "x": "类目14",
          "y": -0.3929067389459173,
          "s": "bar"
        },
        {
          "x": "类目14",
          "y": 45.58667093073836,
          "s": "bar2"
        },
        {
          "x": "类目15",
          "y": 7.560799717904647,
          "s": "bar"
        },
        {
          "x": "类目15",
          "y": 47.14973738101559,
          "s": "bar2"
        },
        {
          "x": "类目16",
          "y": 15.318054209871054,
          "s": "bar"
        },
        {
          "x": "类目16",
          "y": 47.275355710354944,
          "s": "bar2"
        },
        ...
      ]
    }
  }
}
```

## 编写index.js

参考[index.js规范](/intl.zh-CN/开发指南/文档结构/index.js规范.md)文档，按照以下方法编写index.js文件：

1.  在初始化方法中，执行 EChart.init。
2.  在渲染方法中，执行 chart.setOption。
3.  在缩放方法中，执行 chart.resize。
4.  在清空方法中，执行 chart.clear。
5.  在销毁方法中，执行 chart.dispose。

可单击[此处](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/64800/cn_zh/1553838110521/index.js)下载 index.js 完整示例文件。

