---
keyword: button
---

# Button

Button is an interaction widget that allows you to customize the settings of a button in different states, including the color, size, tag content, and hyperlink. You can also use its interaction configurations with other widgets to show a linked page or prompt message in your project. This topic describes configuration items of a button.

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

    **Text**: the text you want to display on a button.

    ![Text](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9625108061/p41561.png)

-   **Normal Style**

    ![Normal Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9625108061/p41562.png)

    -   **Border Style**

        |Parameter|Description|
        |---------|-----------|
        |**Border Width**|The border width in the unit of pixels.|
        |**Border Color**|The border color. For more information about how to modify the border color, see [Configure item description](/intl.en-US/Widget Guide/Configure item description.md).|
        |**Border Radius**|The round border radius of a button. The value range is 0–360. If the value is 0, the button border is square. If the value is 360, the button border is round.|
        |**Line Type**|The border line type, which can be **Solid Line**, **Dashed Line**, **Dotted Line**, **Double Solid Line**, **Carved Effect**, **Embossed Effect**, **Sunken Effect**, or **Protrude Effect**.|

    -   **Background Style**

        |Parameter|Description|
        |---------|-----------|
        |**Background Color**|The background color.|
        |**Background Image**|To change a background image, you can click or drag a file to the square box, or enter the `URL` of an image in the Background Image field.|
        |**Background Image Repeats**|Turn on this switch to repeat a background image in a button when the image does not fully cover the button.|
        |**Fill Type**|The fill type of a background image, which can be **Cover**, **Contain**, or **Auto**.|

    -   **Text Style**: the style of texts in a button.

        |Parameter|Description|
        |---------|-----------|
        |**Font Color**|The default font color.|
        |**Font Style**|The font style, which can be **Normal**, **Italic**, or **Oblique**.|
        |**Font Weight**|The font weight.|
        |**Font**|The font family. The default value is **sans-serif**. **Note:** Select a font that is already installed on your operating system. If no font is installed, the default font is displayed. |
        |**Font Size**|The font size.|
        |**Text Alignment**|The text alignment mode, which can be **Align Left**, **Align Right**, or **Align Center**.|

-   **Style on Click**: the display style of a button when you click this button. Configure parameters by referring to Normal Style.
-   **Style on Hover**: the display style of a button when you move the pointer over this button. Configure parameters by referring to Normal Style.
-   **Hyperlink Configurations**: the hyperlink that you click to redirect to a specific page.

    ![Hyperlink Configurations](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9625108061/p41563.png)

    |Parameter|Description|
    |---------|-----------|
    |**URL**|The URL of a hyperlink.|
    |**Open Link in New Tab**|When this switch is turned on, you can open a link on a new tab. When this switch is turned off, you can open a link on the current tab.|


## Data

![Data tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9625108061/p41564.png)

The following figure shows sample data:

```
[
  {
    "value": "Value"
  }
]
```

value: allows you to set the value of an event node.

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

Select the **Enable** check box to enable interactions between widgets. When you click a button, a data request is triggered and the value configured on the Data tab is returned by default. For more information, see [Configure a callback ID for widgets](/intl.en-US/Advanced Skills/Widget interaction.md).

## Configure interactions in Blueprint Editor

1.  In Canvas Editor, right-click a widget in the Layer panel and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p101929.png) icon in the upper-left corner of the page.
3.  In Blueprint Editor, click the **button** widget in the Added Nodes panel, you can view events and actions supported by the button in the canvas, as shown in the following figure.

    ![Events and actions supported by a button](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9625108061/p51049.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Data Interface Request**|The event is triggered with the processed JSON data after a data interface request is responded and processed by a filter. For specific data, see [Data](#section_xts_4js_gfb).|
        |**On clicking the button**|The event is triggered with a data item when the button is clicked. The data item corresponds to the button.|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface**|This action is performed to request the server data again. The data sent by an upstream converter or layer node is used as a parameter. For example, if the API data source of a button is configured as `http://api.test` and the data transmitted to the **Request Data Interface** action is `{ id: '1'}`, the final request interface is `http://api.test?id=1`.|
        |**Import Data Interface**|After data of a widget is processed in accordance with its drawing format, the widget is imported for redrawing. You do not need to request server data again. For specific data, see [Data](#section_xts_4js_gfb).|
        |**Update Widget Configurations**|Style configurations of widgets are dynamically updated. Before this action is executed, you must click the widget in Canvas Editor, click the Settings tab in the right-side panel, and click **Copy Configurations to...** to obtain widget configurations.**** After that, change the style field for the data processing node in Blueprint Editor.|
        |**Show**|A widget is shown without the need to specify parameters.|
        |**Hide**|A widget is hidden without the need to specify parameters.|
        |**Hide/Show**|A widget is hidden or shown.|
        |**Move**|A widget is moved to a specified location.         ```
    {
      // The positioning type. to indicates absolute positioning, whereas by indicates relative positioning. The default value is to.
        "positionType": "to",
      // The location, which is indicated by the x and y coordinates.
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


