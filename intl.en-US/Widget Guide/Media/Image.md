---
keyword: image widget
---

# Image

An image widget belongs to the Media category. It allows you to custom background images for projects and other widgets. When you configure an image widget, you can specify the source URL of an image and the destination URL that the image points to. This topic describes the configuration items of the image widget.

## Settings

![Settings tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3905108061/p100085.png)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Size**: indicates the size of a widget, including its pixel width and height. You can click the ![Proportional resizing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53660.png) icon to proportionally adjust the width and height of a widget. After you click this icon again, you can adjust the width and height as needed.
-   **Position**: the position of a widget, which is indicated by pixel **X** and **Y** coordinates. **X-coordinate** indicates the pixel distance between the upper-left corner of the widget and the left border of the canvas. **Y-coordinate** indicates the pixel distance between the upper-left corner of the widget and the upper border of the canvas.
-   **Rotation Angle**: the angle of a rotation that uses the center point of a widget as the rotation point. The unit is degrees \(°\). You can use one of the following methods to control the rotation angle of a widget:
    -   Directly enter the degrees in the Rotation Angle spin box or click the plus sign \(+\) or minus sign \(-\) to increase or decrease the value in the Rotation Angle spin box.
    -   Drag the black dot in the ![Rotation control icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53668.png) icon.
    -   Click the ![Horizontal flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53669.png) icon to horizontally flip a widget.
    -   Click the ![Vertical flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53670.png) icon to vertically flip a widget.
-   **Opacity**: the opacity of a widget. Valid values: 0 and 1. If this parameter is set to **0**, the widget is hidden. If this parameter is set to **1**, the widget is completely displayed. Default value: **1**.
-   **Background Image**: You can enter the source URL of the image or click **Change** in the image box to upload an image. You can also click Delete in the image box and click the image box to upload a new image. Alternatively, click the **Data** tab and enter the source URL of the background image in the img field. If you specify source URLs on both the **Settings** and **Data** tabs, the URL on the **Data** tab takes effect in priority.
-   **Repeat**: the repetition pattern of the background image. Valid values: **No repeat**, **Repeat X and Y**, **Repeat X**, and **Repeat Y**.
-   **Fillet**: the corner radius of the image. Valid value: 0 to 360. If the value is 0, the image is a rectangle. If the value is 360, the image is a circle.
-   **Hyperlink**: the destination URL that the image points to. If you click the image widget on the preview or publish page, the image redirects you to the specified URL.

    |Parameter|Description|
    |---------|-----------|
    |**Hyperlink**|You can specify the destination URL that the image points to on the Settings tab or in the url parameter on the **Data** tab. If you specify destination URLs on both the **Settings** and **Data** tabs, the **URL** on the **Data** tab takes effect in priority.|
    |**Open Link in New Tab**|If you turn on the switch, after you click the background image, the URL is opened on a new page. Otherwise, the URL is opened on the current page.|


## Data

![Data tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3905108061/p100089.jpg)

Sample code:

```
[
  {
    "img": "http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/pic/64800/cn_zh/1557279879979/datav.png",
    "url": "https://help.aliyun.com/product/43570.html"
  }
]
```

|Parameter|Description|
|---------|-----------|
|img|Optional. The source URL of the background image. If you specify source URLs in both the Background Image parameter on the Settings tab and the img parameter on the Data tab, the URL in the **Background Image** parameter does not take effect. The URL in the **Background Image** parameter takes effect only when you leave the img parameter empty.|
|url|Optional. The destination URL that the image points to. If you specify destination URLs in both the Hyperlink parameter on the Settings tab and the url parameter on the Data tab, the URL in the **Hyperlink** parameter does not take effect. The URL in the **Hyperlink** parameter takes effect only when you leave the url parameter empty.|

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

![Interaction tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3905108061/p104034.jpg)

|Interaction event|Description|
|-----------------|-----------|
|**On Current Image Clicked**|Select the **Enable** check box to enable this interaction event. When you click the image, a data request is triggered to pass callback IDs. This allows you to dynamically load image data. By default, the img and url parameters are passed. For more information, see [Configure a callback ID](/intl.en-US/Advanced Skills/Widget interaction.md).|
|**Moving in the Mouse**|Select the **Enable** check box to enable this interaction event. After you move the pointer over the image, a data request is triggered to pass callback IDs. This allows you to dynamically load image data. By default, the img and url parameters are passed. For more information, see [Configure a callback ID](/intl.en-US/Advanced Skills/Widget interaction.md).|
|**Moving Out the Mouse**|Select the **Enable** check box to enable this interaction event. After you move the pointer out of the image, a data request is triggered to pass callback IDs. This allows you to dynamically load image data. By default, the img and url parameters are passed. For more information, see [Configure a callback ID](/intl.en-US/Advanced Skills/Widget interaction.md).|

## Interaction configuration in the blueprint editor

1.  In Canvas Editor, right-click a widget in the Layer panel and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p101929.png) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Image** in the Added Nodes pane. You can configure the image parameters on the canvas.

    ![Image parameters in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3905108061/p100076.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Data Interface Request**|After data is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_atz_kyr_q2b).|
        |**On Current Image Clicked**|When you click the image, this event is triggered to pass image data.|
        |**Moving in the Mouse**|When you move the pointer over the image, this event is triggered to pass image data.|
        |**Moving Out the Mouse**|When you move the pointer out of the image, this event is triggered to pass image data.|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface**|This action uses data passed by another widget or a data processing node as parameters to request data from the server. For example, the image uses the API data source `http://api.test`, and the data passed to the **Request Data Interface** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import Data Interface**|This action imports data from the API to render the widget and dose not request data from the server. For more information, see [Example data](#section_atz_kyr_q2b).|
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


