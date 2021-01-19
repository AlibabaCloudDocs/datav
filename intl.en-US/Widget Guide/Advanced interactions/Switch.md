---
keyword: [switch, advanced interaction widget]
---

# Switch

Switch is a widget used for advanced interactions. It functions as a physical switch, allowing you to open or close a project. You can use interaction configurations to define the information you want to show or hide when the switch is turned on or off. This topic describes configuration items of a switch.

## Settings

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Size**: indicates the size of a widget, including its pixel width and height. You can click the ![Proportional resizing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53660.png) icon to proportionally adjust the width and height of a widget. After you click this icon again, you can adjust the width and height as needed.
-   **Position**: the position of a widget, which is indicated by pixel **X** and **Y** coordinates. **X-coordinate** indicates the pixel distance between the upper-left corner of the widget and the left border of the canvas. **Y-coordinate** indicates the pixel distance between the upper-left corner of the widget and the upper border of the canvas.
-   **Rotation Angle**: the angle of a rotation that uses the center point of a widget as the rotation point. The unit is degrees \(°\). You can use one of the following methods to control the rotation angle of a widget:
    -   Directly enter the degrees in the Rotation Angle spin box or click the plus sign \(+\) or minus sign \(-\) to increase or decrease the value in the Rotation Angle spin box.
    -   Drag the black dot in the ![Rotation control icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53668.png) icon.
    -   Click the ![Horizontal flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53669.png) icon to horizontally flip a widget.
    -   Click the ![Vertical flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53670.png) icon to vertically flip a widget.
-   **Opacity**: the opacity of a widget. Valid values: 0 and 1. If this parameter is set to **0**, the widget is hidden. If this parameter is set to **1**, the widget is completely displayed. Default value: **1**.
-   **Global Style**

    ![Global Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5057401161/p41906.png)

    **Turn On by Default**: If it is turned on, the switch is turned on by default. If it is turned off, the switch is turned off by default.

-   **Background Style**

    ![Background Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5057401161/p41907.png)

    -   **Border Style**

        |Parameter|Description|
        |---------|-----------|
        |**Border Width**|The border width.|
        |**Border Color**|The border color. For more information, see [Configure item description](/intl.en-US/Widget Guide/Configure item description.md).|
        |**Border Radius**|The border radius. The value range is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
        |**Line Type**|The line type of a border, which can be **Solid Line**, **Dashed Line**, **Dotted Line**, **Double Solid Line**, **Carved Effect**, **Embossed Effect**, **Sunken Effect**, or **Protrude Effect**.|

    -   **Background Color**

        |Parameter|Description|
        |---------|-----------|
        |**On-state Color**|The background color when a switch is turned on.|
        |**Off-state Color**|The background color when a switch is turned off.|

-   **Button Style**

    ![Button Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6057401161/p41908.png)

    -   **Border Style**

        |Parameter|Description|
        |---------|-----------|
        |**Border Width**|The border width of a switch.|
        |**Border Color**|The border color of a switch.|
        |**Border Radius**|The border radius of a switch. The value range is 0–360. If the value is 0, the switch border is square. If the value is 360, the switch border is round.|
        |**Line Type**|The border line type of a switch, which can be **Solid Line**, **Dashed Line**, **Dotted Line**, **Double Solid Line**, **Carved Effect**, **Embossed Effect**, **Sunken Effect**, or **Protrude Effect**.|

    -   **Background Color**: the background color of a switch.

## Data

![Data tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6057401161/p41909.png)

The following figure shows sample data:

```
[
  {
    "onValue": 1,
    "offValue": 0,
    "state": 0
  }
]
```

|Field|Description|
|-----|-----------|
|onvalue|The data returned when a switch is turned on. The default value is 1.|
|offvalue|The data returned when a switch is turned off. The default value is 0.|
|state|The switch status, which must be set to 0 or 1. 0 indicates that a switch is turned off. 1 indicates that a switch is turned on.|

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

Widget interactions are enabled when you select the **Enable** check box on the right of **On state change**. Switch widgets that have interaction configurations do not allow you to customize other callback variables. You can only turn on or off a switch to trigger a data request, return a callback value, and use the value for other widgets.

By default, value configured on the Data tab is returned. If the **switch** is turned on, onvalue will be returned. If the **switch** is turned off, offvalue will be returned. For more information, see [Configure a callback ID for a ticker board](/intl.en-US/Advanced Skills/Configure callback IDs for ticker boards.md).

## Configure interactions in Blueprint Editor

1.  In Canvas Editor, right-click a widget in the Layer panel and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p101929.png) icon in the upper-left corner of the page.
3.  In Blueprint Editor, click a **switch** widget in the Added Nodes panel, you can view events and actions supported by the switch in the canvas, as shown in the following figure.

    ![Events and actions supported by a switch](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6057401161/p51163.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Data Interface Request**|The event is triggered with the processed JSON data after a data interface request is responded and processed by a filter. For specific data, see [Data](#section_xts_4js_gfb).|
        |**On state change**|The event is triggered with a data item when the state changes. The data item corresponds to the changed state.|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface**|This action is performed to request the server data again. The data sent by an upstream data processing node or layer node is used as a parameter. For example, if the API data source of a switch is configured as `http://api.test` and the data transmitted to the **Request Data Interface** action is `{ id: '1'}`, the final request interface is `http://api.test?id=1`.|
        |**Import Data Interface**|After data is processed in accordance with the widget drawing format, the widget is imported for redrawing. You do not need to request the server data again. For specific data, see [Data](#section_xts_4js_gfb).|
        |**Obtain Current Switch State**|The current switch state is obtained.|
        |**Set Current Switch State**|The current switch state is set.|
        |**Restore Default Value**|The default value is restored.|
        |**Update Widget Configurations**|Widget style configurations are updated dynamically. Before you execute this action, click a switch widget in Canvas Editor. In the right-side panel, click the **Settings** tab and click **Copy Configurations to...** to obtain widget configurations. Then, change the corresponding field value of the data processing node in Blueprint Editor as needed.|
        |**Show**|A switch widget is shown without the need to specify parameters.|
        |**Hide**|A switch widget is hidden without the need to specify parameters.|
        |**Hide/Show**|A switch widget is hidden or shown.

        ```
    {
      //true indicates that a widget is shown, whereas false indicates that a widget is hidden.
      "status": true,
      // Animation is displayed.
      "animationIn": {
        // The animation type, which can be set to fade. If it is not specified, no animation is displayed.
        "animationType": "fade",
        // The duration in which animation is displayed. It is in the unit of milliseconds.
        "animationDuration": 1000,
        // The function that is used to display animation. You can set this parameter to linear|easeInOutQuad|easeInOutExpo.
        "animationEasing": "linear"
      },
      // Animation is hidden.
      "animationOut": {
        // The animation type, which can be set to fade. If it is not specified, no animation is displayed.
        "animationType": "fade",
        // The duration in which animation is hidden. It is in the unit of milliseconds.
        "animationDuration": 1000,
        // The function that is used to hide animation. You can set this parameter to linear|easeInOutQuad|easeInOutExpo.
        "animationEasing": "linear"
      }
    }
        ``` |
        |**Move**|A widget is moved to a specified location.

        ```
    {
      // The positioning type. to indicates absolute positioning, whereas by indicates relative positioning. The default value is to.
        "positionType": "to",
      // The location, which is indicated by both the x and y coordinates.
      "attr": {
        "x": 0,
        "y": 0
      },
      // The animation type.
      "animation": {
        "enable": false,
        // The animation duration.
        "animationDuration": 1000,
        // The animation curve, which can be set to linear|easeInOutQuad|easeInOutExpo.
        "animationEasing": "linear"
      }
    }
        ``` |


