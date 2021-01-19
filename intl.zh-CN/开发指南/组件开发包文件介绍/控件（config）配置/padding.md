# padding

padding表示组件的配置项类型为边距套件，支持定义上下左右四个边的内边距数值。

## 配置项说明

|字段|含义|数据类型|默认值|备注|
|--|--|----|---|--|
|`min`|最小值|number|0|无。|
|`max`|最大值|number|Infinity|无。|

## 值说明

|条件|数据类型|示例|默认值|
|--|----|--|---|
|无|object|```
{
  "top": 5,
  "bottom": 10,
  "left": 10,
  "right": 5
}
```

|```
{
  "top": 5,
  "bottom": 10,
  "left": 10,
  "right": 5
}
``` |

## 配置示例

![内边距](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/2334968061/p204904.png)

```
{
  "padding": {
    "type": "padding",
    "name": "内边距",
    "default": {
      "top": 5,
      "bottom": 10,
      "left": 10,
      "right": 5
    },
    "min": 0,
    "max": 1000
  }
}
```

