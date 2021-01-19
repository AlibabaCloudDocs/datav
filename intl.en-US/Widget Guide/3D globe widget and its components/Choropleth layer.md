---
keyword: choropleth layer of the 3D globe widget
---

# Choropleth layer

The choropleth layer is a component of the 3D globe widget. It allows you to display regional geographic information in the 3D globe widget. You can configure the style and data of the choropleth layer to present boundary data of the GeoJSON format and render the map of a region. This topic describes the configuration items of the choropleth layer.

Click **Choropleth Layer** under **Components**. The Settings tab of **Choropleth Layer** appears.

**Note:** If **Components** does not contain **Choropleth Layer**, add the **Choropleth Layer** component. For more information, see [3D globe](/intl.en-US/Widget Guide/3D globe widget and its components/3D globe.md).

## Settings

![Settings tab of the choropleth layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3386401161/p72780.png)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Fill color**: the color settings of the choropleth layer.

    |Parameter|Description|
    |---------|-----------|
    |**MinValue Color**|The color of the region that has the smallest value on the Data tab . For more information, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).|
    |**MaxValue Color**|The color of the region that has the largest value on the Data tab.|
    |**NoData Color**|The color of regions that do not have data. If you have not configured the adcode parameter for a region on the Data tab, **NoData Color** takes effect for this region.|

-   **Outline Settings**

    |Parameter|Description|
    |---------|-----------|
    |**Outline Color**|The color of region boundary lines.|
    |**Outline Width**|The width of region boundary lines.|
    |**Opacity**|The opacity of region boundary lines.|

-   **Scale**: the ratio of the choropleth layer to the radius of the 3D globe. The larger the value, the farther the choropleth layer is from the center of the 3D globe. Valid value: 0.8 to 1.5. If the value is 1, the choropleth layer is aligned with the surface of the 3D globe.

## Data

The Data tab of the choropleth layer contains **Mapping Data** and **Geographical Boundaries**.

-   **Mapping Data**

    ![Data tab of the choropleth layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3386401161/p72783.png)

    Sample code in the preceding figure:

    ```
    [
      {
        "adcode": "710000",
        "value": 0.774761951295659
      },
      {
        "adcode": "330000",
        "value": 0.7794583269860595
      },
      {
        "adcode": "110000",
        "value": 0.6869565532542765
      },
      {
        "adcode": "120000",
        "value": 0.9352621990256011
      },
      {
        "adcode": "130000",
        "value": 0.8719353775959462
      },
      {
        "adcode": "140000",
        "value": 0.20899744261987507
      },
      {
        "adcode": "150000",
        "value": 0.22816960071213543
      },
      {
        "adcode": "210000",
        "value": 0.8665573971811682
      },
      {
        "adcode": "220000",
        "value": 0.8985264701768756
      }
    ]
    ```

    |Parameter|Description|
    |---------|-----------|
    |adcode|The code of a region.|
    |value|The value of a region. **MaxValue Color**, **MinValue Color**, **NoData Color** of the choropleth layer are rendered based on this parameter. **Note:** DataV obtains the ranges of region values based on the value parameter and determines color gradient from the maximum value to the minimum value. |

-   **Geographical Boundaries**: You can customize geographical boundary data in the GeoJSON format to define a region at the choropleth layer. For more information about the GeoJSON format and how to obtain data, see [Map data format](/intl.en-US/Widget Guide/Basic flat map widgets/Map data format.md).

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

1.  In the canvas editor of the 3D globe widget, click the ![Add to Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89089.jpg) icon next to **Choropleth Layer** under **Components**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Choropleth Layer** in the Added Nodes pane. You can configure parameters of the choropleth layer on the canvas.

    ![Parameters of the choropleth layer in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3386401161/p87789.jpg)

    -   **Events**

        |Event|Description|
        |-----|-----------|
        |**On Completion of Geographical Boundaries Request**|After data of the geographical boundaries is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_91y_08w_c1t).|
        |**On Completion of Mapping Data Request**|After data of the regions is returned by the API and processed by filters, this event is triggered to pass JSON-format data. For more information, see [Example data](#section_91y_08w_c1t).|

    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Request Mapping Data**|This action takes parameters passed by an upstream data processing node or widget and requests region data from the server. For example, the choropleth layer uses the API data source `http://api.test`, and the data passed to the **Request Mapping Data** action is `{ id: '1'}`. As a result, the `http://api.test? id=1` API is called to request data.|
        |**Request Geographical Boundaries**|This action takes parameters passed by an upstream data processing node or widget and requests geographical boundary data from the server. For example, the choropleth layer uses the API data source `http://api.test`, and the data passed to the **Request Geographical Boundaries** action is `{ id: '1'}`. As a result, the `http://api.test?id=1` API is called to request data.|
        |**Import Mapping Data**|This action imports region data from the API to render the component and dose not request data from the server. For more information, see [Example data](#section_91y_08w_c1t).|
        |**Import Geographical Boundaries**|This action imports geographical boundary data from the API to render the widget and dose not request data from the server. For more information, see [Example data](#section_91y_08w_c1t).|
        |**Show**|This action shows the component and does not need parameter input.|
        |**Hide**|This action hides the component and does not need parameter input.|


