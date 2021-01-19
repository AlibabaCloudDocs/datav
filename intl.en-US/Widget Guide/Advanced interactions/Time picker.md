---
keyword: [time picker, advanced interaction widget]
---

# Time picker

Time picker is a widget used for advanced interactions. It allows you to customize the settings of a calendar, including the background color, date and time style, and time format type. You can use a time picker to query data and dynamically display data of other widgets based on time. This topic describes configuration items of a time picker.

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

    ![Global Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2257401161/p43401.png)

    -   **Font**: the text font. The default font is **Microsoft YaHei**.

        **Note:** Select a font that is already installed on your system. If no font is installed on your system, the default font is used.

    -   **Text Box Style**
        -   **Indent**: the text indent in a text box.
        -   **Background Color**: the background color in a text box.
        -   **Normal Border Style**

            |Parameter|Description|
            |---------|-----------|
            |**Border Width**|The border width in the unit of pixels.|
            |**Border Color**|The border color.|
            |**Border Radius**|The border radius. The value range is 0–360. If the value is 0, the text box is square. If the value is 360, the text box is round.|

        -   **Border Style on Hover**

            |Parameter|Description|
            |---------|-----------|
            |**Border Width**|The border width when you move the pointer over a text box. The width is in the unit of pixels.|
            |**Border Color**|The border color displayed when you move the pointer over a text box.|
            |**Border Radius**|The border radius when you move the pointer over a text box. The value range is 0–360. If the value is 0, the text box is square. If the value is 360, the text box is round.|

        -   **Text Style**

            |Parameter|Description|
            |---------|-----------|
            |**Font Size**|The text font size.|
            |**Font Color**|The text color in a text box.|
            |**Font Weight**|The text font weight. The default value is **Normal**.|

-   **Calendar and Time Panel Style**: the calendar style that is displayed on the preview or configuration page after you click a time picker. The configuration parameters takes effect only on a PC.

    ![Calendar and Time Panel Style](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2257401161/p43402.png)

    -   **Height**: the height of a calendar.
    -   **Spacing Between Panel and Text Box**: the distance from the top of a calendar to the text box.
    -   **Border Radius**: the round border radius of a calendar. The value range is 0–360. If the value is 0, the calendar frame is square. If the value is 360, the calendar frame is round.
    -   **Background Color**: the background color of a calendar.
    -   **Top Bar Style**
        -   **Year and Month Style \(Calendar Panel\)**

            |Parameter|Description|
            |---------|-----------|
            |**Font Size**|The font size of year and month.|
            |**Font Color**|The font color of year and month.|
            |**Font Weight**|The font weight of year and month. The default value is **Normal**.|

        -   **Date Style \(Time Panel\)**

            |Parameter|Description|
            |---------|-----------|
            |**Font Size**|The font size of time.|
            |**Font Color**|The color of time.|
            |**Font Weight**|The font weight of time. The default value is **Normal**.|

        -   **Top Bar Height \(%\)**: the height of the top bar in a calendar. The value range is 10–20. This parameter is a percentage value based on the height of a calendar.
        -   **Margin for Prev Month and Next Month Buttons**: the distance between the icons of the previous month and next month in a calendar. The value range is 0–50.
        -   **Margin for Year and Month Drop-Down List Boxes**: the spacing between year and month in a calendar. The value range is 0–50.
        -   **Split Line Style**

            |Parameter|Description|
            |---------|-----------|
            |**Font Color**|The color of a split line at the top of a calendar.|
            |**Line Width**|The width of a split line at the top of a calendar.|

    -   **Calendar Box and Time Box Style**
        -   **Split Line Style**

            |Parameter|Description|
            |---------|-----------|
            |**Line Color**|The color of a split line for the main part in a calendar.|
            |**Line Width**|The width of a split line for the main part of a calendar.|

        -   **Height**: the height of the main part in a calendar.
    -   **Date Style**
        -   **Header Row Style**: the style of the header in a calendar table.

            |Parameter|Description|
            |---------|-----------|
            |**Background Color**|The background color in a calendar table.|
            |**Border Style**|The border width, border color, and round border radius in a calendar table. The value range of the round border radius is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
            |**Font Size**|The font size in a calendar table.|

        -   **Date Rows Style**: the row and column style in a calendar table.
            -   **Normal Style**

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of rows and columns in a calendar table.|
                |**Border Style**|The border width, border color, and round border radius of rows and columns in a calendar table. The value range of the round border radius is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
                |**Font Weight**|The font weight of rows and columns in a calendar table. The default value is **Normal**.|
                |**Font Color**|The font color of rows and columns in a calendar table.|

            -   **Style on Hover**: the display style when you move the pointer over a column or row in a calendar table.

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of a column or row in a calendar table when you move the pointer over the column or row.|
                |**Border Style**|The border width, border color, and round border radius when you move the pointer over a column or row in a calendar table. The value range of the round border radius is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
                |**Font Weight**|The font weight when you move the pointer over a column or row in a calendar table. The default value is **Normal**.|
                |**Font Color**|The font color when you move the pointer over a column or row in a calendar table.|

            -   **Selection Style**: the style displayed when you select a column or row in a calendar table.

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of a column or row in a calendar table when you select the column or row.|
                |**Border Style**|The border width, border color, and round border radius of a column or row in a calendar table when you select the column or row. The value range of the round border radius is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
                |**Font Weight**|The font weight of a column or row in a calendar table when you select the column or row. The default value is **Normal**.|
                |**Font Color**|The font color of a column or row in a calendar when you select the column or row.|

            -   **Current Date Style**: the display style of the current date in columns and rows in a calendar table.

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of the current date in columns and rows in a calendar table.|
                |**Border Style**|The border width, border color, and round border radius of the current date in columns and rows in a calendar table. The value range of the round border radius is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
                |**Font Weight**|The font weight of the current date in columns and rows in a calendar table. The default value is **Normal**.|
                |**Font Color**|The font color of the current date in columns and rows in a calendar table.|

            -   **Style for Dates of Prev and Next Months**: the display style of dates in the previous and next months in columns and rows in a calendar table.

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of dates in the previous and next months in columns and rows in a calendar table.|
                |**Border Style**|The border width, border color, and round border radius of dates in the previous and next months in columns and rows in a calendar table. The value range of the round border radius is 0–360. If the value is 0, the border is square. If the value is 360, the border is round.|
                |**Font Weight**|The font weight of dates in the previous and next months in columns and rows in a calendar table. The default value is **Normal**.|
                |**Font Color**|The font color of dates in the previous and next months in columns and rows in a calendar table.|

            -   **Style for Days of Week**: the display style of days in a week in the calendar header.

                |Parameter|Description|
                |---------|-----------|
                |**Font Color**|The font color of days in a week in the calendar header.|
                |**Font Weight**|The font weight of days in a week in the calendar header. The default value is **Normal**.|

    -   **Time Style**
        -   **Time Box Style**

            |Parameter|Description|
            |---------|-----------|
            |**Border Style**|The border width and color of a time box.|
            |**Font Size**|The font size of a time box.|

        -   **Time Rows Style**
            -   **Normal Style**

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of a time row.|
                |**Font Weight**|The font weight of a time row. The default value is **Normal**.|
                |**Font Color**|The font color of a time row.|

            -   **Style on Hover**: the display style when you move the pointer over a time row.

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of a time row when you move the pointer over this row.|
                |**Font Weight**|The font weight of a time row when you move the pointer over this row. The default value is **Normal**.|
                |**Font Color**|The font color of a time row when you move the pointer over this row.|

            -   **Selection Style**: the display style when you select a specific time row.

                |Parameter|Description|
                |---------|-----------|
                |**Background Color**|The background color of a time row when you select it.|
                |**Font Weight**|The font weight of a time row when you select this row. The default value is **Normal**.|
                |**Font Color**|The font color of a time row when you select this row.|

    -   **Bottom Bar Style**
        -   **Height**: the height of the bottom bar in a calendar.
        -   **Offset**: the distance between the bottom content and the bottom border.
        -   **Style for Current-Time Button**

            |Parameter|Description|
            |---------|-----------|
            |**Font Size**|The font size of a button at the moment.|
            |**Font color**|The font color of a button at the moment.|
            |**Font Weight**|The font weight of a button at the moment. The default value is **Normal**.|
            |**Left Offset**|The left offset of a button at the moment.|
            |**Top Offset**|The top offset of a button at the moment.|

        -   **Style for Panel Switchover Button**: the switchover button that can be used for a switchover between time selection and time point selection.

            |Parameter|Description|
            |---------|-----------|
            |**Font Size**|The font size of the panel switchover button.|
            |**Font Color**|The font color of the panel switchover button.|
            |**Font Weight**|The font weight of the panel switchover button. The default value is **Normal**.|
            |**Right Offset**|The right offset of the panel switchover button.|
            |**Top Offset**|The top offset of the panel switchover button.|

        -   **Style for Confirm Button**

            |Parameter|Description|
            |---------|-----------|
            |**Font Size**|The font size of the confirm button.|
            |**Font Color**|The font color of the confirm button.|
            |**Font Weight**|The font weight of the confirm button. The default value is **Normal**.|
            |**Right Offset**|The right offset of the confirm button.|
            |**Top Offset**|The top offset of the confirm button.|
            |**Background Color**|The background color of the confirm button.|
            |**Border Radius**|The round border radius of the confirm button. The value range is 0–360. If the value is 0, the button border is square. If the value is 360, the button border is round.|

    -   **Year Range**: the year range of a calendar. The value range is 1–50.
-   **Time Format**

    ![Format Settings](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2257401161/p43403.png)

    **Time Format**: a custom time format in accordance with the `%Y-%m-%d %H:%M:%S` format.


## Data

![Data tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2257401161/p43404.png)

The following figure shows sample data:

```
[
  {
    "time": "2018-08-08 08:08:08"
  }
]
```

time: the default time. The value is of the STRING type in accordance with the `%Y-%m-%d %H:%M:%S` format.

**Note:** If your data source is AnalyticDB for MySQL, ApsaraDB RDS for MySQL, or a database of other types and a time picker is required to present the time fields such as DateTime and Date, you can use SQL statements in DataV data configurations to convert the time format to a string.

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

In the right-side panel of the time picker widget, click the Interaction tab. Select the **Enable** check box on the right of **On current time change**. A **time picker** widget supports interaction configurations that allow you to change time data in the picker, trigger data requests, and return callback values. You can also use the interaction configurations for other widgets.

By default, the value configured for time on the Data tab is returned. For more information about the specific configuration, see [Configure a callback ID for a ticker board](/intl.en-US/Advanced Skills/Configure callback IDs for ticker boards.md).

## Configure interactions in Blueprint Editor

1.  In Canvas Editor, right-click a widget in the Layer panel and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p101929.png) icon in the upper-left corner of the page.
3.  In Blueprint Editor, click the **time picker** widget, you can view configuration parameters of the time picker in the canvas, as shown in the following figure.

    ![Configure interactions in Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3257401161/p51165.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Data Interface Request**|The event is triggered with the processed JSON data after a data interface request is responded and processed by using a filter. For specific data, see [Data](#section_xts_4js_gfb).|
        |**On current time change**|The event is triggered with a data item when the current time changes. The data item corresponds to the changed time.|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface**|Server data is requested again. The data sent by an upstream data processing node or layer node is used as a parameter. For example, if the API data source of a time picker is configured as `http://api.test` and the data transmitted to the **Request Data Interface** action is `{id: '1'}`, the final request interface is `http://api.test? id=1`.|
        |**Import Data Interface**|After data is processed in accordance with the widget drawing format, the widget is imported for redrawing. You do not need to request server data again. For specific data, see [Data](#section_xts_4js_gfb).|
        |**Obtain Current Value**|The current value of a time picker is obtained.|
        |**Restore Default Value**|The default value is restored.|
        |**Update Widget Configurations**|Style configurations of widgets are dynamically updated. Before you execute this action, click a time picker widget in Canvas Editor. In the right-side panel, click the **Settings** tab and click **Copy Configurations to...** to obtain widget configurations. Then, change the corresponding field value of the data processing node in Blueprint Editor as needed.|
        |**Show**|A time picker widget is shown without the need to specify parameters.|
        |**Hide**|A time picker widget is hidden without the need to specify parameters.|
        |**Hide/Show**|A time picker widget is hidden or shown.

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


