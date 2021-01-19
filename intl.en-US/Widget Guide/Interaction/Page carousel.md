---
keyword: page carousel
---

# Page carousel

The page carousel widget belongs to the Interact category. It allows you to rotate web pages in your DataV project. You can configure the attributes of a page on the Data tab, including the page ID, name, and URL. This topic describes the configuration items of the page carousel widget.

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
-   **Carousel**: specifies whether to enable automatic carousel of multiple pages.
-   **Intervals \(s\)**: the interval to rotate the pages. This parameter appears only when you turn on **Carousel**.

## Data

The Data tab of the page carousel widget contains **Data Interface \(All Pages\)** and **Data Interface \(Current Page\)**.

-   **Data Interface \(All Pages\)**

    ![Data Interface (All Pages)](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8765936061/p47080.png)

    Sample code in the preceding figure:

    ```
    [
      {
        "id": 0,
        "serieName": "Project 1",
        "url": "https://m.aliyun.com/?utm_content=se_1435405"
      },
      {
        "id": 1,
        "serieName": "Project 2",
        "url": " https://hd.m.aliyun.com/act/detail-datav.html"
      },
      {
        "id": 2,
        "serieName": "Project 3",
        "url": " https://tianchi.aliyun.com/markets/tianchi/outsource/ai/mobile"
      }
    ]
    ```

    |Parameter|Description|
    |---------|-----------|
    |id|The ID of a page in the widget.|
    |serieName|The name of a page in the widget.|
    |url|The URL of a page in the widget.|

-   **Data Interface \(Current Page\)**

    ![Data Interface (Current Page)](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8765936061/p47103.png)

    id: the ID of a page in the widget.

    -   If the widget uses a static data source, the id field specifies the ID of the initial page. The ID must be consistent with the id parameter configured in **Data Interface \(All Pages\)**.
    -   If the widget uses a dynamic data source, such as a database or API, the value of the id parameter can be dynamically obtained from an interaction widget, such as a timeline and tab list. You can change an element in the interaction widget to rotate to a specific page. The value format of the id parameter returned by the dynamic data source must be the same as the value format of this id parameter and must be consistent with the id parameter configured in **Data Interface \(All Pages\)**.
    We recommend that you configure a dynamic data source. For more information, see [Widget interaction](/intl.en-US/Advanced Skills/Widget interaction.md) and [t17483.md\#](/intl.en-US/Advanced Skills/Configure callback IDs for ticker boards.md).


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

1.  In Canvas Editor, right-click a widget in the Layer panel and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p101929.png) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Page Carousel** in the Added Nodes pane. You can configure the widget parameters on the canvas.

    ![Parameters in node programming](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5805108061/p50868.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Data Interface \(All Pages\) Request**|After data of the page carousel widget is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_48a_z8n_yw2).|
        |**On Completion of Data Interface \(Current Page\) Request**|After data of the current page is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_48a_z8n_yw2).|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface \(All Pages\)**|This action takes parameters passed by an upstream data processing node or widget and requests data of the page carousel widget from the server. For example, the page carousel widget uses the API data source `http://api.test`, and the data passed to the **Request Data Interface \(All Pages\)** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Request Data Interface \(Current Page\)**|This action takes parameters passed by an upstream data processing node or widget and requests data of the current page from the server. For example, the page carousel widget uses the API data source `http://api.test`, and the data passed to the **Request Data Interface \(Current Page\)** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import Data Interface \(All Pages\)**|This action imports data from the API to render the widget and dose not request data from the server. For more information, see [Example data](#section_48a_z8n_yw2).|
        |**Import Data Interface \(Current Page\)**|This action imports data from the API to render the current page and dose not request data from the server. For more information, see [Example data](#section_48a_z8n_yw2).|
        |**Obtain Current Page Information**|This action returns parameters such as id and url of the current page. For more information, see [Example data](#section_48a_z8n_yw2).|
        |**Update Widget Configurations**|This action dynamically updates the style configurations of the widget. You must click **Copy Configurations to Clipboard** on the **Settings** tab in the canvas editor. Then, paste the data to the box of a data processing node in the blueprint editor and configure the field values.|
        |**Show**|This action shows the widget and does not need parameter input.|
        |**Hide**|This action hides the widget and does not need parameter input.|
        |**Show/Hide**|This action shows or hides the widget.|
        |**Move**|This action moves the widget to a specified position.         ```
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


