# stepper

You can configure the step, maximum and minimum values, prefix, and suffix in a stepper control.

## Configuration description

|Field|Description|Type|Required?|Remarks|
|:----|:----------|----|:--------|:------|
|`name`|The name of the control.|string|Yes|None.|
|`type`|The type of the control.|string|Yes|None.|
|`default`|The default value.|number|No|If this field is not specified, the default value is empty.|
|`step`|The step.|number|Yes|None.|
|`min`|The minimum value.|number|Yes|None.|
|`max`|The maximum value.|number|Yes|None.|
|`prefix`|The prefix of the stepper.|string|No|None.|
|`suffix`|The suffix of the stepper.|string|No|None.|
|`precision`|The precision of the value in the stepper. It is indicated by the number of decimal places.|number|No|This field takes effect only for decimal values.|

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|number|`12`|`0`|

## Configuration example

![Stepper configuration example](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3679301161/p92931.png)

```
"stepper": {
  "name": "Moving Distance",
  "type": "stepper",
  "step": 1,
  "min": 0,
  "max": 15,
  "prefix": "Up:",
  "suffix": "px"
}
```

