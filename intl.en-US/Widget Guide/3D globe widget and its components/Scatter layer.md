---
keyword: Scatter layer of the 3D globe widget
---

# Scatter layer

The scatter layer is a component of the global 3D widget. It allows you to present geographical information by using scattered dots. You can configure the style and data of the scatter layer, including the dot size, color, latitude, and longitude. This topic describes the configuration items of the scatter layer.

Click **Scatter Layer** under **Components**. The Settings tab of **Scatter Layer** appears.

**Note:** If **Components** does not contain **Scatter Layer**, add the **Scatter Layer** component. For more information, see [3D globe](/intl.en-US/Widget Guide/3D globe widget and its components/3D globe.md).

## Settings

![Settings tab of the scatter layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9786401161/p72989.png)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Animation Range**: the animation range of the scattered dots. Valid value: 0 to 3.
-   **Animation Speed**: the animation speed of the scattered dots. Valid value: 0 to 0.1.
-   **MaxValue Radius**: the radius of the largest dot. Valid value: 1 to 100.
-   **MinValue Radius**: the radius of the smallest dot. Valid value: 1 to 50.
-   **Scale**: the ratio of the scatter layer and the radius of the 3D globe. The larger the value, the farther the scatter layer is from the center of the 3D globe. Valid value: 0.9 to 1.5. If the value is 1, the scatter layer overlaps the 3D globe surface.
-   **Scatter Style**

    |Parameter|Description|
    |---------|-----------|
    |**Inner Color**|The inner color of the scattered dots.|
    |**Outer Color**|The outer color of the scattered dots.|
    |**Gradient Count**|The gradient degree of the scattered dots. Valid values: 0.1 to 30.|


## Data

![Data tab of the scatter layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9786401161/p73075.png)

Sample code in the preceding figure:

```
[
  {
    "lat": 62.103883,
    "lng": -106.523438,
    "value": 51
  },
  {
    "lat": 50.064192,
    "lng": -74.179688,
    "value": 94
  },
  {
    "lat": 43.068888,
    "lng": -104.765625,
    "value": 90
  },
  {
    "lat": -16.299051,
    "lng": -58.007812,
    "value": 36
  },
  {
    "lat": 37.996404,
    "lng": 85.432403,
    "value": 83
  },
  {
    "lat": 30.44572,
    "lng": 94.922655,
    "value": 55
  },
  {
    "lat": 24.203949,
    "lng": 105.823615,
    "value": 29
  },
  {
    "lat": 17.644022,
    "lng": -10.898438,
    "value": 23
  },
  {
    "lat": 34.597042,
    "lng": -84.726562,
    "value": 70
  },
  {
    "lat": 51.618017,
    "lng": -61.523437,
    "value": 18
  },
  {
    "lat": 34.016242,
    "lng": -104.765625,
    "value": 42
  }
]
```

|Parameter|Description|
|---------|-----------|
|adcode|Optional. The region code of a dot.|
|lng|Optional. The longitude of a dot.|
|lat|Optional. The latitude of a dot.|
|value|The size of a dot.|

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

1.  In the canvas editor of the 3D globe widget, click the ![Add to Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89089.jpg) icon next to **Scatter Layer** under **Components**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Scatter Layer** in the Added Nodes pane. You can configure parameters of the scatter layer on the canvas.

    ![Parameters of the scatter layer in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9786401161/p87829.jpg)

    -   **Event**

        **On Completion of Scatter Data Request**

        After data of the scatter layer is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_xir_oc6_ign).

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Scatter Data**|This action takes parameters passed by an upstream data processing node or widget and requests data from the server. For example, the scatter layer uses the API data source `http://api.test`, and the data passed to the **Request Scatter Data** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Import Scatter Data**|This action imports data from the API to render the scatter layer and dose not request data from the server. For more information, see [Example data](#section_xir_oc6_ign).|
        |**Show**|This action shows the component and does not need parameter input.|
        |**Hide**|This action hides the component and does not need parameter input.|


