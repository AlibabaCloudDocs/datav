# array

You can configure a data series control to configure a series of data or a cycle of multiple colors. However, we recommend that you use a group of tabs instead.

## Configuration description

|Field|Description|Data type|Required?|Remarks|
|:----|:----------|---------|:--------|:------|
|`type`|The type of the control.|string|Yes|None.|
|`name`|The name of the control.|string|Yes|None.|
|`default`|The default value.|array|No|An array that consists of objects. The object attributes must be the same as the field names defined in the `child` field.|
|`child`|The name of the object.|object|No|Set the value of `type` in this field to `object`.|
|`child.child`|The attributes of the object.|object|No|This field defines the attributes and default values of the objects.|

**Note:** The value of the `default` field in a data series must be an object array. The attributes of the objects in the array must be defined in the `child.child` field, including the display name, type, and default value.

## Value description

|Condition|Data type|Example|Default value|
|---------|---------|-------|-------------|
|None|array|```
[
{"name": "Series 1", value: "Arrival"},
{"name": "Series 2", value: "Departure"}
]
```

|\[\]|

## Configuration examples

![Configuration example of a data series](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6079301161/p93718.png)

```
"array": {
    "name": "Data Series",
    "type": "array",
    "default": [
      {
        "name": "Series 1",
        "value": "Arrival"
      },
      {
        "name": "Series 2",
        "value": "Departure"
      }
    ],
    "child": {
      "name": "Series <%=i+1%>",
      "type": "object",
      "child": {
        "name": {
          "name" : "Series Name",
          "type": "text",
          "default": "Series"
        },
        "value": {
          "name" : "Series Value",
          "type": "text",
          "default": ""
        }
      }
    }
}
```

