# padding

Padding allows you to configure a padding suite that specifies the top, bottom, left, and right padding sizes for a widget.

## Fields

|Field|Description|Data type|Default value|Remarks|
|-----|-----------|---------|-------------|-------|
|`min`|The minimum value.|number|0|None|
|`max`|The maximum value.|number|Infinity|None|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|object|```
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

## Sample configurations

![Padding](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2347419061/p204904.png)

```
{
  "padding": {
    "type": "padding",
    "name": "Padding",
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

