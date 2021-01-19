---
keyword: 3D globe widget
---

# 3D globe

The 3D globe widget provides a container for its components. This widget allows you to present multiple types of global geographic information in the 3D format from different viewpoints. You can add components such as the earth layer and flying routes layer, and configure the rendering mode, background, and camera viewpoint. This topic describes the configuration items of the 3D globe widget.

## Settings

-   **Components**
    -   Add a component.
        1.  In the canvas editor, click the globe widget and go to the **Settings** tab.
        2.  Click the ![Add](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2115108061/p127829.png) icon on the left of **Components**.
        3.  Select one or more components and click **Add Component**.

            After a component is added, it appears under **Components**.

            ![Add Component](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2115108061/p72407.png)

        4.  Click an added component and configure its parameters.
        5.  After the configuration is complete, click the ![Back icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2115108061/p89287.jpg) icon to go back to the Settings tab of **Globe** and configure other components.
    -   Copy, edit, or delete a component: Move the pointer over the component and click the ![Copy icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16572/155840370639964_en-US.png) icon to copy the component. Click the ![Edit icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16572/155840370639965_en-US.png) icon to edit the component. Click the ![Delete icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16572/155840370639966_en-US.png) icon to delete the component.
-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Size**: indicates the size of a widget, including its pixel width and height. You can click the ![Proportional resizing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53660.png) icon to proportionally adjust the width and height of a widget. After you click this icon again, you can adjust the width and height as needed.
-   **Position**: the position of a widget, which is indicated by pixel **X** and **Y** coordinates. **X-coordinate** indicates the pixel distance between the upper-left corner of the widget and the left border of the canvas. **Y-coordinate** indicates the pixel distance between the upper-left corner of the widget and the upper border of the canvas.
-   **Rotation Angle**: the angle of a rotation that uses the center point of a widget as the rotation point. The unit is degrees \(°\). You can use one of the following methods to control the rotation angle of a widget:
    -   Directly enter the degrees in the Rotation Angle spin box or click the plus sign \(+\) or minus sign \(-\) to increase or decrease the value in the Rotation Angle spin box.
    -   Drag the black dot in the ![Rotation control icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53668.png) icon.
    -   Click the ![Horizontal flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53669.png) icon to horizontally flip a widget.
    -   Click the ![Vertical flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53670.png) icon to vertically flip a widget.
-   **Opacity**: the opacity of a widget. Valid values: 0 and 1. If this parameter is set to **0**, the widget is hidden. If this parameter is set to **1**, the widget is completely displayed. Default value: **1**.
-   **Global Options**
    -   **Camera Rotation**

        |Parameter|Description|
        |---------|-----------|
        |**Horizontal**|The longitude of the camera viewpoint on the Earth.|
        |**Vertical**|The latitude of the camera viewpoint on the Earth.|

    -   **Camera Center**: the offset of the Earth relative to the x, y, and z axes.
    -   **Camera Distance**: the distance between the camera and the Earth. The Earth becomes smaller if you increase the value.
    -   **Auto Rotation Speed**: the rotation speed of the Earth. Valid values: 0 to 1. If the value is 0, the rotation stops.
    -   **Map Interaction**: specifies whether to enable map interaction. If you enable map interaction, you can drag, zoom in, and zoom out the map on the preview or publish page.
    -   **Carousel Options**

        |Parameter|Description|
        |---------|-----------|
        |**Carousel**|Specifies whether to rotate the longitudes and latitudes configured on the Data tab in sequence.|
        |**Duration**|The time required for the animation to switch from one pair of longitude and latitude to another.|
        |**Delay**|The duration for which the animation remains on one pair of longitude and latitude.|


## Data

The Data tab of a 3D globe widget contains **Positions Carousel** and **Data Response Result**.

In the **Positions Carousel** section, you can configure the lat and lng parameters.

![Data tab of the 3D globe widget](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3115108061/p72493.png)

Sample code in the preceding figure:

```
[
  {
    "lat": 37.77,
    "lng": -122.41
  },
  {
    "lat": 37.56,
    "lng": -77.42
  },
  {
    "lat": 50.1,
    "lng": 8.63
  },
  {
    "lat": 1.58,
    "lng": 103.79
  },
  {
    "lat": 22.27,
    "lng": 114.16
  },
  {
    "lat": 39.9,
    "lng": 116.4
  },
  {
    "lat": 31.23,
    "lng": 121.47
  },
  {
    "lat": 35.17,
    "lng": 134.03
  },
  {
    "lat": -35.38,
    "lng": 149.25
  }
]
```

|Parameter|Description|
|---------|-----------|
|lat|The latitude of a location.|
|lng|The longitude of a location.|

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

This widget does not support interaction events.

## Interaction configuration in the blueprint editor

1.  In the canvas editor, right-click the 3D globe widget and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **3D Globe** in the Added Nodes pane. You can configure parameters of the widget on the canvas.

    ![Parameters of the 3D globe widget in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3115108061/p87780.jpg)

    -   **Event**

        **On Completion of Positions Carousel Request**

        After data of the 3D globe widget is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_si4_uon_sou).

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Positions Carousel**|This action takes parameters passed by an upstream data processing node or widget and requests data from the server. For example, the 3D globe widget uses the API data source `http://api.test`, and the data passed to the **Request Positions Carousel** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import Positions Carousel**|This action imports data from the API to render the widget and dose not request data from the server. For more information, see [Example data](#section_si4_uon_sou).|
        |**Update Widget Configurations**|This action dynamically updates the style configurations of the widget. You must click **Copy Configurations to Clipboard** on the **Settings** tab in the canvas editor. Then, paste the data to the box of a data processing node in the blueprint editor and configure the field values.|
        |**Show**|This action shows the widget and does not need parameter input.|
        |**Hide**|This action hides the widget and does not need parameter input.|
        |**Hide/Show**|This action shows or hides the widget. Example:

        ```
    {
      // true: shows the widget. false: hides the widget.
      "status": true,
      // The show animation settings.
      "animationIn": {
        // The animation type. Valid value: fade. If you leave this parameter empty, no animation is configured.
        "animationType": "fade",
        // The animation duration, in ms.
        "animationDuration": 1000,
        // The animation effect. Valid values: linear, easeInOutQuad, and easeInOutExpo.
        "animationEasing": "linear"
      },
      // The hide animation settings.
      "animationOut": {
        // The animation type. Valid value: fade. If you leave this parameter empty, no animation is configured.
        "animationType": "fade",
        // The animation duration, in ms.
        "animationDuration": 1000,
        // The animation effect. Valid values: linear, easeInOutQuad, and easeInOutExpo.
        "animationEasing": "linear"
      }
    }
        ``` |
        |**Move**|This action moves the widget to a specified position. Example:

        ```
    {
      // The type of the position. Valid values: to (absolute position) and by (relative position). Default value: to.
        "positionType": "to",
      // The position that consists of the x and y coordinates.
      "attr": {
        "x": 0,
        "y": 0
      },
      // The animation settings.
      "animation": {
        "enable": false,
        // The animation duration.
        "animationDuration": 1000,
        // The animation effect. Valid values: linear, easeInOutQuad, and easeInOutExpo.
        "animationEasing": "linear"
      }
    }
        ``` |


