---
keyword: [text box, advanced interaction widget]
---

# Text box

Text box is a widget used for advanced interactions. It allows you to customize the background color, text style, border style, and button style in various states. It can be used as an input form in a DataV project to submit user input to the backend for processing. This topic describes the configuration items of a text box widget.

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
-   **Text Box Style**

    ![Text Box Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0947401161/p41632.png)

    -   **Placeholder**: the text you want to display in a text box. You can also configure this parameter on the Data tab.

        **Note:**

        -   The placeholder obtained from the **Data** tab takes precedence.
        -   The value of this parameter is displayed only after the value field on the **Data** tab is cleared.
    -   **Indent**: the indent of texts in a text box.
    -   **Background Color**: the background color of a text box. For more information about how to modify the background color, see the color picker description in [Configure item description](/intl.en-US/Widget Guide/Configure item description.md).
    -   **Text Style**: the style of texts in a text box.

        |Parameter|Description|
        |---------|-----------|
        |**Font Color**|The font color of texts in a text box.|
        |**Font Style**|The font style of texts in a text box, which can be set to **Normal**, **Italic**, and **Oblique**.|
        |**Font Weight**|The font weight of texts in a text box.|
        |**Font**|The font family of texts in a text box. **Note:** Only fonts that are installed on the operating system are displayed. If the selected font is not installed, the default font is displayed. |
        |**Font Size**|The font size of texts in a text box.|

    -   **Border Style**

        |Parameter|Description|
        |---------|-----------|
        |**Border Width**|The border width in the unit of pixel.|
        |**Border Color**|The border color.|
        |**Border Radius**|The border radius. The value range is 0–360. If the value is 0, a square text box is displayed. If the value is 360, a round text box is displayed.|
        |**Line Type**|The line type of the border, which can be **Solid Line**, **Dashed Line**, **Dotted Line**, **Double Solid Line**, **Carved Effect**, **Embossed Effect**, **Sunken Effect** or **Protrude Effect**.|

-   **Button Style**: the style of the button on the right of a text box.

    ![Button Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1947401161/p41633.png)

    -   **Text**: the text in the button.
    -   **Button Width**: the button width.

        **Note:** If the button width is too small, the text cannot be displayed completely.

    -   **Normal Style**
        -   **Background Color**: the background color of the button.
        -   **Border Style**

            |Parameter|Description|
            |---------|-----------|
            |**Border Width**|The width of the button border.|
            |**Border Color**|The color of the button border.|
            |**Border Radius**|The border radius of the button. The value range is 0–360. If the value is 0, a square button border is displayed. If the value is 360, a round button border is displayed.|
            |**Line Type**|The line type, which can be **Solid Line**, **Dashed Line**, **Dotted Line**, **Double Solid Line**, **Carved Effect**, **Embossed Effect**, **Sunken Effect**, or **Protrude Effect**.|

        -   **Text Style**

            |Parameter|Description|
            |---------|-----------|
            |**Font Color**|The font color of texts in the button.|
            |**Font Style**|The font style of texts in the button.|
            |**Font Weight**|The font weight of texts in the button.|
            |**Font**|The font family of texts in the button. **Note:** Only fonts that are installed on the operating system are displayed. If the selected font is not installed, the default font is displayed. |
            |**Font Size**|The font size of text in the button.|

    -   **Style on Click**: the display style of the button on the right of the text box when you click the button. For more information, see **Normal Style**.
    -   **Style on Hover**: the display style of the button on the right of the text box when you move the pointer over the button. For more information, see **Normal Style**.

## Data

![Data in a text box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1947401161/p41634.png)

The following figure shows sample data:

```
[
  {
    "value": "Value"
  }
]
```

value: content displayed in a text box. After this field is configured, the configuration data overwrites **Placeholder** in Text Box Style. This field can be empty. When it is empty, the value of Placeholder is displayed.

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

![Interaction tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1947401161/p105004.jpg)

Widget interactions are enabled when you select the **Enable** check box on the right of **On current value change** and **On button clicked**. A **text box** widget supports interaction configurations that allow you to change content in the text box, trigger data requests, and return callback values. You can also use the interaction configurations for other widgets.

By default, value configured on the Data tab is returned. For more information about the specific configuration, see [Configure a callback ID for a ticker board](/intl.en-US/Advanced Skills/Configure callback IDs for ticker boards.md).

## Configure interactions in Blueprint Editor

1.  In Canvas Editor, right-click a widget in the Layer panel and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p101929.png) icon in the upper-left corner of the page.
3.  In Blueprint Editor, click a text box widget in the Added Nodes panel, you can view configuration parameters of the widget in the canvas, as shown in the following figure.

    ![Events and actions supported by a text box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1947401161/p51111.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Data Interface Request**|The event is triggered with the processed JSON data after a data interface request is responded and processed by a filter. For specific data, see [Data](#section_xts_4js_gfb).|
        |**On current value change**|The event is triggered with a data item when the current value changes. The data item corresponds to the changed value.|
        |**On button clicked**|The event is triggered with a data item when the button is clicked. The data item corresponds to the clicked button.|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface**|This action is performed to request the server data again. The data sent by an upstream data processing node or layer node is used as a parameter. For example, if the API data source of a text box is configured as `http://api.test` and the data transmitted to the **Request Data Interface** action is `{id: '1'}`, the final request interface is `http://api.test? id=1`.|
        |**Import Data Interface**|After data of a widget is processed in accordance with its drawing format, the widget is imported for redrawing. You do not need to request the server data again. For specific data, see [Data](#section_xts_4js_gfb).|
        |**Obtain Current Value**|The value in the current text box is obtained.|
        |**Restore Default Value**|The default value is restored.|
        |**Update Widget Configurations**|Style configurations of widgets are dynamically updated. Before this action is executed, you must click the widget in Canvas Editor, click the Settings tab in the right-side panel, and click **Copy Configurations to...** to obtain widget configurations. After that, change the style field for the data processing node in Blueprint Editor.|
        |**Show**|A widget is shown without the need to specify parameters.|
        |**Hide**|A widget is hidden without the need to specify parameters.|
        |**Hide/Show**|A widget is hidden or shown.

        ```
    {
      // true indicates that a widget is shown, whereas false indicates that a widget is hidden.
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
        // The animation curve. You can set this parameter to linear|easeInOutQuad|easeInOutExpo.
        "animationEasing": "linear"
      }
    }
        ``` |


