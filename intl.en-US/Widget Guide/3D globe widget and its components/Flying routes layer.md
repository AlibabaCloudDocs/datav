---
keyword: flying routes layer of the 3D globe widget
---

# Flying routes layer

The flying routes layer is a component of a 3D globe widget. It allows you to present origin-destination data, such as of logistics and transactions, in the format of lines called flying routes. You can configure the speed, height, hue, start latitude/longitude, and end latitude/longitude of a flying route. This topic describes the configuration items of the flying routes layer.

Click **Flying Routes Layer** under **Components**. The Settings tab of **Flying Routes Layer** appears.

**Note:** If **Components** does not contain **Flying Routes Layer**, add the **Flying Routes Layer** component. For more information, see [3D globe](/intl.en-US/Widget Guide/3D globe widget and its components/3D globe.md).

## Settings

![Settings tab of the flying routes layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6486401161/p72922.png)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Height**: the height of the flying routes layer from the 3D globe.
-   **Fly Speed**: the flying speed of the routes.
-   **Hue**: the hue of the flying routes.
-   **Line Width**: the weight of the flying routes.
-   **Density**: the density of the flying routes.

## Data

![Data tab of the flying routes layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6486401161/p72931.png)

Sample code in the preceding figure:

```
[
  {
    "from": "4.21875,21.943046",
    "to": "113.911722,30.748697"
  },
  {
    "from": "94.220067,39.910476",
    "to": "112.857638,35.173107"
  },
  {
    "from": "117.428724,41.246858",
    "to": "117.427149,26.428056"
  },
  {
    "from": "135.005796,35.746795",
    "to": "114.966156,31.351459"
  },
  {
    "from": "128.678669,47.042308",
    "to": "114.614653,33.13559"
  },
  {
    "from": "37.265625,3.162456",
    "to": "114.614395,30.142406"
  },
  {
    "from": "72.421875,45.828799",
    "to": "100.899788,34.014409"
  },
  {
    "from": "-98.789063,38.548165",
    "to": "115.669547,34.01474"
  },
  {
    "from": "-103.359375,54.572062",
    "to": "0.703125,47.517201"
  },
  {
    "from": "-98.4375,40.979898",
    "to": "-3.164063,53.956086"
  },
  {
    "from": "138.164063,-23.563987",
    "to": "114.61447,31.050538"
  }
]
```

|Parameter|Description|
|---------|-----------|
|from|The start longitude and latitude of a flying route. Separate the longitude and latitude with a comma \(,\).|
|to|The end longitude and latitude of a flying route. Separate the longitude and latitude with a comma \(,\).|

|Parameter|Description|
|---------|-----------|
|**Controlled Mode**|If you turn on the switch, data is not requested when a widget is initialized. Data requests are triggered only based on callback IDs or the method configured in Blueprint Editor. If you turn off the switch, data requests are automatically triggered. By default, the switch is turned off.|
|**Auto Data Request**|After you select the Auto Data Request check box, you can enable dynamic polling, and manually specify the polling interval. If you do not select this check box, data is not automatically requested. You must manually refresh the page to request data or use Blueprint Editor or callback ID events to trigger data requests.|
|**Data Source**|In the right-side panel of Canvas Editor, click the Data tab. Click **Set** next to **Static Data**. In the Configure Datasource panel, select a data source from the Data Source Type drop-down list. Enter code for data query in the code editor, click Preview Data Response to preview the response of the data source, and then view the response. For more information, see [Configure widget data](/intl.en-US/Manage Widgets/Configure widget data.md).|
|**Data Filter**|If you select the Data Filter check box, you can convert the data structure, filter data, and perform simple calculations. If you click the plus sign \(+\) next to **Add Filter**, you can configure the script for the data filter in the editor that appears. For more information, see [Use the data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).****|
|**Data Response Result**|The response to a data request. If the data source changes, you can click the ![Refresh icon ](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9064108061/p89093.png) icon next to Data Response Result to view the data response in real time.|

## Interaction

This component does not support interaction events.

## Interaction configuration in the blueprint editor

1.  In the canvas editor of the 3D globe widget, click the ![Add to Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89089.jpg) icon next to **Flying Routes Layer** under **Components**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Flying Routes Layer** in the Added Nodes pane. You can configure parameters of the flying routes layer on the canvas.

    ![Parameters of the flying routes layer in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6486401161/p87799.jpg)

    -   **Event**

        **On Completion of Flying Routes Data Request**

        After data of the flying routes layer is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_xrj_v4z_bpk).

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Flying Routes Data**|This action takes parameters passed by an upstream data processing node or widget and requests data from the server. For example, the flying routes layer uses the API data source `http://api.test`, and the data passed to the **Request Flying Routes Data** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import Flying Routes Data**|This action imports data from the API to render the flying routes layer and dose not request data from the server. For more information, see [Example data](#section_xrj_v4z_bpk).|
        |**Show**|This action shows the component and does not need parameter input.|
        |**Hide**|This action hides the component and does not need parameter input.|


