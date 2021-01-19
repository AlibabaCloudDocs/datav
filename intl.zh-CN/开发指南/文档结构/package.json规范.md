# package.json规范

package.json文件是组件的配置文件。本文档介绍package.json文件的字段详情，您可以参考本文档的字段说明，根据自身需求，灵活修改package.json文件，自定义组件样式。

## 协议版本2规范示例

**说明：** 请着重查看下述案例中的备注信息。

```
{
  "name": "@leaf/pie-multi-radius-with-title",   //@命名空间/组件名 （命名空间即组件包名，必须添加，否则无法发布）。
  "version": "0.1.5",                            //版本号。
  "dependencies": {                              //依赖, 不包括datav:/com/依赖。
    "bcore": "0.0.9",
    "jquery": "2.1.4",                           //所有依赖的版本号必须锁死。
    "lodash": "4.6.1"
  },
  "datav": {                                    //datav配置。
    "cn_name": "带标题的多维饼图",               //组件中文名。
    "protocol": 2,                             //协议版本号。
    "type": ["regular_pie"],                   //组件类型。
    "supportTheme": true,                      // 组件声明是否⽀持主题。
    "view": {
      "width": 300,
      "height": 200,
      "minWidth": 100,
      "minHeight": 50
    },
    "icon": "",                                    //组件图标链接地址。
    "apis": {                                      //组件接口，可以多个。
      "source": {                                  //接口名。
        "handler": "render",                       //处理接口返回的组件方法名。
        "description" : "多维度饼图接口",          //接口描述。
        "fields" : {                               //接口所需字段，可以多个。
          "x" : {                                  //字段名。
            "description" : "类目",                //字段描述。
            "type" : "string",                     //字段类型。
            "optional": true                       //可选字段。
          },
          "y" : {
            "description" : "值",
            "type" : "int"
          }
        }
      }
    },
    "config" : {                                 //组件配置，给编辑器识别用。
      "paxis" : {
        "type" : "group",                        //类型：组，详见<组件config配置说明>。
        "name" : "标签",
        "children" : {
          "dx" : {
            "type" : "text",                    //类型：文本，详见<组件config配置说明>。
            "name" : "标签距中心",
            "default" : 220
          }
        }
      },
      "title" : {
        "type" : "group",
        "name" : "标题",
        "children" : {
          "value" : {
            "hasVisibility" : "true",
            "visible" : "true",
            "type" : "text",
            "name" : "标题名",
            "default" : "我是标题"
          },
          "font-size" : {
            "type" : "number",                 //类型：数字，详见<组件config配置说明>。
            "name" : "字体",
            "min" : 10,
            "default" : 32,
            "max" : 100
          },
          "text-align" : {
            "name" : "对齐方式",
            "type" : "select",                //类型：下拉框，详见<组件config配置说明>。
            "options" : [
              {"name" : "左对齐", "value" : "left"},
              {"name" : "右对齐", "value" : "right"},
              {"name" : "居中对齐", "value" : "center"}
            ],
            "default" : "center"
          },
          "color" : {
            "name" : "字体颜色",
            "type" : "color",                  //类型：颜色，详见<组件config配置说明>。
            "default" : "#fff"
          },
          "background-color" : {
            "name" : "背景",
            "type" : "color",
            "default" : "#000"
          }
         }
        }
      }
    },
  "api_data":{                               //接口数据，可以多个。
    "source" : [                             //接口名，必须和apis中的接口名一致，限制6K。
      {"x": "普货", "y" : 5},
      {"x": "普货", "y" : 22},
      {"x": "泡货", "y" : 22},
      {"x": "设备", "y" : 14},
      {"x": "矿产", "y" : 15},
      {"x": "钢铁", "y" : 15},
      {"x": "建材", "y" : 12},
      {"x": "食品", "y" : 12},
      {"x": "粮食", "y" : 28}
    ],
  },
  "events": {                              //全局参数事件配置。
    "event-name": {                        //事件名。
      "description": "事件描述",           //事件描述。
      "fields": {                          //字段，可以多个。
        "value": {                         //字段名。
          "description": "值描述"          //字段描述。
        }
      }
    }
  },
  "publicHandler": {
    "show": {
      "name": "显示",
      "description"： "描述",
      "type": "object",                  // 可以为object、array、null和any，any表示任意类型。
      "fields": {
        "data": {
          "name": "数据",
          "type": "array",
          "children": {
                    ...
          }
        }
      }
    }
  },
}
```

## 配置项config字段说明

`config`配置用来说明组件有哪些配置。这些配置既用于传给组件，也用于说明编辑器的选项。

`config`配置有以下两个要求：

-   包含组件默认配置。
-   描述清楚配置的输入规范，以便编辑器进行识别。

`config`配置中的`type`字段用来配置组件的类型和样式。不同的`type`类型会展示不同的编辑器UI，合理使用`type`类型和配置项归类，可以极大提高组件的质量与用户体验，详情请参见[控件配置]()。

## apis字段与api\_data字段

-   `apis`字段

    该字段定义了组件接口名，以及该接口所需的字段。接口和字段均可为多个。

    ```
    "apis": {                                    
      "source": {                                
      "handler": "render",                     
        "description" : "多维度饼图接口",          
        "fields" : {                              
          "x" : {                                 
            "description" : "类目",                
            "type" : "string",                     
            "optional": true                       
          },
          "y" : {
            "description" : "值",
            "type" : "int"
          }
        }
      }，
      "source2":{
          ...                                     
      }
    }
    ```

    |字段名|含义|是否必选|备注|
    |---|--|----|--|
    |`apis`|组件接口|是|一个组件可以包含多个接口。|
    |`source`|接口名|否|可自定义。|
    |`handler`|处理接口返回的数据的方法名|是|该方法名必须在[index.js](/intl.zh-CN/开发指南/文档结构/index.js规范.md)源码中实现。|
    |`description`|接口描述|否|无。|
    |`fields`|接口所需字段|是|一个接口可以包含多个字段。|
    |`fields.x`|字段名|是|可自定义。|
    |`fields.x.description`|字段描述|否|无。|
    |`fields.x.type`|字段类型|否|包括number、string、boolean、object和array。|
    |`fields.x.optional`|是否为可选字段|否|为boolean类型。`true`表示对应字段为可选字段，`false`表示对应字段为必选字段。|

-   `api_data`字段

    该字段定义了接口数据，可以包含多个接口数据。接口名必须和`apis`中的接口名一致，限制为6KB（详情请参见注释）。

    ```
    "api_data":{                          
      "source" : [                       
        {"x": "普货", "y" : 5},
        {"x": "普货", "y" : 22},
        {"x": "泡货", "y" : 22},
        {"x": "设备", "y" : 14},
        {"x": "矿产", "y" : 15},
        {"x": "钢铁", "y" : 15},
        {"x": "建材", "y" : 12},
        {"x": "食品", "y" : 12},
        {"x": "粮食", "y" : 28}
      ],
    }
    ```

    |字段名|含义|是否必选|备注|
    |---|--|----|--|
    |`api_data`|组件接口数据|是|一个组件可以包含多个接口数据。|
    |`source`|接口名|否|必须和`apis`字段中的接口名一致，限制6KB。|


## events交互事件规范

DataV的交互事件由`emit`（组件代码中触发`emit`）和`events`描述（package.json的事件描述）组成。

-   `events`字段描述

    `events`字段在`datav`字段下，与`config`字段同级，定义了交互事件的事件名，描述以及变量名等。

    ```
    {
      "events": {                 
        "click-me": {      "description": "点击触发事件",           
          "fields": {                            
            "value": {                        
              "description": "点击值" 
            }
          }
        }
      }
    }
    ```

    |字段名|含义|是否必选|备注|
    |---|--|----|--|
    |`click-me`|事件名|是|可自定义。|
    |`description`|事件描述|否|用于描述该事件的具体作用。|
    |`fields`|字段|是|可包含多个字段名及其描述信息。|
    |`fields.value`|字段名|是|可自定义。|
    |`fields.value.description`|字段描述|否|无。|

-   `emit`触发

    `emit`方法作为一个基础类方法，会将事件名及需要的数据作为参数抛出，其他组件即可通过变量名获取到该组件的参数值，需要在[index.js](/intl.zh-CN/开发指南/文档结构/index.js规范.md)源码中实现（详情请参见注释）。

    ```
    render: function () {
      this.container.on('click', () => {
        this.emit('click-me', data)            // data必须为一个对象，而不是一个简单值，属性名即为变量名。
      })
    }
    ```


## type字段

`type`字段定义了该组件的组件类型（详情请参见注释）。

```
type: ["regular_bar", ...]  //一个组件可以属于多个组，多个组件类型以下划线分隔："type1_type2"。
  {                        // 常用组件类型。
    regular: "常规图表",
    map: "地图", 
    media : "媒体", 
    network: "关系网络", 
    text: "文字", 
    interact: "交互",
    material: "素材"
  }
```

## publicHandler字段

DataV的行为事件定义是通过`publicHandler`注册而成，示例如下。

```
"publicHandler": {
  "select": {
    "name": "选择",
    "description"： "选择某一项",
    "type": "object",    
    "fields": {
      "data": {
        "name": "数据",
        "type": "array",
        "children": {
               ...
        }
      }
    }
  }
}
```

如上示例注册了一个名称为`select`的行为事件，并且组件`index.js`中需要实现`select`方法，否则方法将报错。

**说明：**

-   当您还没有实现`show`、`hide`以及`updateOptions`方法时，DataV会自动帮您注册并实现这3个默认方法。
-   DataV为您注册的`updateOptions`需要您自行实现，如果没有实现，DataV会调用组件的`render`方法。

|字段名|含义|是否必选|备注|
|---|--|----|--|
|`name`|事件名|是|在节点编程配置中使用。|
|`description`|事件描述|否|无严格的字数限制。|
|`type`|事件第一入参类型|否|可选，固定为object。|
|`fields`|字段|否|无。|
|`fields.data.name`|字段名|是|无。|
|`fields.data.description`|字段描述|否|无。|
|`fields.data.type`|字段类型|是|可选，包括number、string、boolean、object和array。|
|`fields.data.children`|子节点|否|当`fields.data.type`为object或array时需要设置children 字段。|
|`fields.data.default`|默认值|否|当`fields.data.type`为number、string或boolean时，需要填写默认值。|
|`fields.data.optional`|是否可选|否|可选，为boolean类型。`true`表示对应字段为可选字段，`false`表示对应字段为必选字段。|

