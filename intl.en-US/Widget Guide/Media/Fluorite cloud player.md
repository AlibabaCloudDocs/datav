---
keyword: fluorite cloud player
---

# Fluorite cloud player

A fluorite cloud player belongs to the Media category. It allows you to play videos with the original display aspect ratio in your project. RTMP and HLS video streams are supported. You can configure the video stream URL. This topic describes the configuration items of a fluorite cloud player.

## Settings

![Settings tab of the fluorite cloud player](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3553401161/p87946.jpg)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Size**: indicates the size of a widget, including its pixel width and height. You can click the ![Proportional resizing](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53660.png) icon to proportionally adjust the width and height of a widget. After you click this icon again, you can adjust the width and height as needed.
-   **Position**: the position of a widget, which is indicated by pixel **X** and **Y** coordinates. **X-coordinate** indicates the pixel distance between the upper-left corner of the widget and the left border of the canvas. **Y-coordinate** indicates the pixel distance between the upper-left corner of the widget and the upper border of the canvas.
-   **Rotation Angle**: the angle of a rotation that uses the center point of a widget as the rotation point. The unit is degrees \(°\). You can use one of the following methods to control the rotation angle of a widget:
    -   Directly enter the degrees in the Rotation Angle spin box or click the plus sign \(+\) or minus sign \(-\) to increase or decrease the value in the Rotation Angle spin box.
    -   Drag the black dot in the ![Rotation control icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53668.png) icon.
    -   Click the ![Horizontal flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53669.png) icon to horizontally flip a widget.
    -   Click the ![Vertical flip](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p53670.png) icon to vertically flip a widget.
-   **Opacity**: the opacity of a widget. Valid values: 0 and 1. If this parameter is set to **0**, the widget is hidden. If this parameter is set to **1**, the widget is completely displayed. Default value: **1**.
-   **Video Stream URL**: the URL of the video stream. You can also configure the URL on the **Data** tab. The configuration on the Data tab takes effect in preference to the configuration on the Settings tab.
-   **Video Stream Type**: the protocol of the video stream. Valid values: **RTMP** and **HLS**.

    **Note:** You must specify a video stream URL. However, the fluorite cloud player on a web page cannot be integrated based on client authentication. You can access the [fluorite cloud platform](https://open.ys7.com) to obtain the video stream URL.

-   **Video Loop**: specifies whether to play the video on a continuous loop. If you turn off the switch, the video is played only once.
-   **Muted Play**: specifies whether to play the video in mute mode.
-   **Hide Video Controls**: specifies whether to hide the video control bar.

## Data

![Data tab of the fluorite cloud player](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5087240061/p12753.png)

source: the URL of the video stream. This parameter is optional. It functions the same as the **Video Stream URL** parameter on the Settings tab. If you configure both parameters, this parameter takes effect in priority.

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

1.  In the canvas editor, right-click the fluorite cloud player and select **Add to Blueprint Editor**.
2.  Click the ![Blueprint editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner.
3.  In the blueprint editor, click **Fluorite Cloud Player** in the Added Nodes pane. You can configure the parameters on the canvas.

    ![Parameters of the fluorite cloud player in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3553401161/p69871.jpg)

    -   **Event**

        **On Completion of Data Interface Request**

        After data is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_atz_kyr_q2b).

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Data Interface**|This action uses data passed by another widget or a data processing node as parameters to request data from the server. For example, the fluorite cloud player uses the API data source `http://api.test`, and the data passed to the **Request Data Interface** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import Data Interface**|This action imports data from the API to render the widget and dose not request data from the server. For more information, see [Example data](#section_atz_kyr_q2b).|
        |**Clear**|This action clears the video stream URL and does not need parameter input. You can use this action to switch between videos or stop the video playback.|
        |**Update Widget Configurations**|This action dynamically updates the style configurations of the widget. You must click **Copy Configurations to Clipboard** on the **Settings** tab in the canvas editor. Then, paste the data to the box of a data processing node in the blueprint editor and configure the field values.|
        |**Show**|This action shows the widget and does not need parameter input.|
        |**Hide**|This action hides the widget and does not need parameter input.|
        |**Show/Hide**|This action shows or hides the widget.|
        |**Mobile**|This action moves the widget to a specified position.         ```
    {
      // The type of position. Valid values: to (absolute position) and by (relative position). Default value: to.
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


