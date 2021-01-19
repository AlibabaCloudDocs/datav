---
keyword: InfoWindow layer of the 3D globe widget
---

# InfoWindow layer

An InfoWindow layer is a component of the 3D globe widget. It allows you to display geographical details in your DataV project. You can configure the style and data of an info window, including the size, color, content, longitude, and latitude. This topic describes the configuration items of the InfoWindow layer.

Click **InfoWindow Layer** under **Components**. The Settings tab of **InfoWindow Layer** appears.

**Note:** If **Components** does not contain **InfoWindow Layer**, add the **InfoWindow Layer** component. For more information, see [3D globe](/intl.en-US/Widget Guide/3D globe widget and its components/3D globe.md).

## Settings

![Settings tab of an InfoWindow layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p72967.png)

-   **Scale**: the distance between the InfoWindow layer and the globe.
-   **InfoWindow Options**

    **Size**: the size of the InfoWindow layer.


## Data

![Data tab of the InfoWindow layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p72981.png)

Sample code in the preceding figure:

```
[
  {
    "type": "dom",
    "id": 1,
    "latlngs": {
      "lng": -180.1904296,
      "lat": 7.29701788
    },
    "content": {
      "title": "NO.2",
      "content": "This is the content of an info window.",
      "width": 900,
      "height": 350,
      "paddingLeft": 90,
      "paddingRight": 60,
      "paddingTop": 110,
      "titleFontSize": 45,
      "titleColor": "#fbf320",
      "contentColor": "#000",
      "contentFontSize": 40,
      "fontFamily": "Microsoft Yahei, serif",
      "bgImgUrl": "https://img.alicdn.com/tps/TB1bymmOFXXXXaxXpXXXXXXXXXX-2201-753.png"
    }
  },
  {
    "type": "dom",
    "id": 2,
    "latlngs": {
      "lng": -20.83203125,
      "lat": 13.94426488
    },
    "content": {
      "title": "NO.1",
      "content": "This is the content of an info window.",
      "width": 900,
      "height": 350,
      "paddingLeft": 90,
      "paddingRight": 60,
      "paddingTop": 110,
      "titleFontSize": 45,
      "titleColor": "#fbf320",
      "contentColor": "#000",
      "contentFontSize": 40,
      "fontFamily": "Microsoft Yahei, serif",
      "bgImgUrl": "https://img.alicdn.com/tps/TB1bymmOFXXXXaxXpXXXXXXXXXX-2201-753.png"
    }
  }
]
```

|Parameter|Description|
|---------|-----------|
|type|The type of an info window.|
|id|The ID of an info window.|
|latlngs|The latitude and longitude where an info window is located.|
|content|The information displayed in an info window, which contains the following fields: -   title: the title of an info window.
-   content: the content of an info window.
-   width: the width of an info window. Unit: pixels.
-   height: the height of an info window. Unit: pixels.
-   paddingLeft: the space between the content and the left border of an info window. Unit: pixels.
-   paddingRight: the space between the content and the right border of an info window. Unit: pixels.
-   paddingTop: the space between the content and the top border of an info window. Unit: pixels.
-   titleFontSize: the font size of the title.
-   titleColor: the color of the title.
-   contentColor: the color of the content.
-   contentFontSize: the font size of the content.
-   fontFamily: the font of the title and content. Specify a font that is installed on your operating system. If the specified font is not installed, the default font is used.
-   bgImgUrl: the URL of the background image. |

## Interaction

This component does not support interaction events.

## Interaction configuration in the blueprint editor

1.  In the canvas editor of the 3D globe widget, click the ![Add to Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89089.jpg) icon next to **InfoWindow Layer** under **Components**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **InfoWindow Layer** in the Added Nodes pane. You can configure parameters of the InfoWindow layer on the canvas.

    ![InfoWindow layer parameters in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89296.jpg)

    -   **Event**

        **On Completion of InfoWindow Request**: After data of the InfoWindow layer is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_fs2_smq_1lq).

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request InfoWindow**|This action takes parameters passed by an upstream data processing node or widget and requests data from the server. For example, the InfoWindow layer uses the API data source `http://api.test`, and the data passed to the **Request InfoWindow** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import InfoWindow**|This action imports data from the API to render the InfoWindow layer and dose not request data from the server. For more information, see [Example data](#section_fs2_smq_1lq).|
        |**Show**|This action shows the component and does not need parameter input.|
        |**Hide**|This action hides the component and does not need parameter input.|


