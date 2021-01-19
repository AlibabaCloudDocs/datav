---
keyword: earth layer of the 3D globe widget
---

# Earth layer

The earth layer is a component of the 3D globe widget. You can configure the style of the map and atmosphere layer. This topic describes the configuration items of the earth layer.

Click **Earth Layer** under **Components**. The Settings tab of **Earth Layer** appears.

**Note:** If **Components** does not contain **Earth Layer**, add the **Earth Layer** component. For more information, see [3D globe](/intl.en-US/Widget Guide/3D globe widget and its components/3D globe.md).

## Settings

![Settings tab of an earth layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7586401161/p72936.jpg)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Earth**: the style of the map.

    **Map Type**: the type of the map, which determines the style of the map. Valid values: **Terrain**, **Satellite**, **Particle**, **Administrative Regions**, and **Customization**. You can configure **Scale**, **Asperity Degree**, **Map Color**, **Floodlight Color**, and **Highlight Color** for each map type.

-   **Atmosphere Layer**: the style of the atmosphere layer.

    |Parameter|Description|
    |---------|-----------|
    |**Show Atmosphere**|Specifies whether to show the atmosphere layer.|
    |**Color**|The color of the atmosphere layer.|
    |**Scale**|The ratio of the atmosphere layer to the radius of the 3D globe. The larger the scale value, the larger the atmosphere layer. If the scale value is 1, the atmosphere overlaps the globe surface. Valid values: 0.9 to 1.5.|


## Data

This component does not support data configuration.

## Interaction

This component does not support interaction events.

## Interaction configuration in the blueprint editor

1.  In the canvas editor of the 3D globe widget, click the ![Add to Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89089.jpg) icon next to **Earth Layer** under **Components**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Earth Layer** in the Added Nodes pane. You can configure parameters of the earth layer on the canvas.

    ![Earth layer parameters in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7586401161/p87815.jpg)

    -   **Event**: The earth layer does not support events.
    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Show**|This action shows the component and does not need parameter input.|
        |**Hide**|This action hides the component and does not need parameter input.|


