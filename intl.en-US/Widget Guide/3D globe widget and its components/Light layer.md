---
keyword: light layer of the 3D globe widget
---

# Light layer

The light layer is a component of the 3D globe widget. It allows you to simulate the light and color on the outer surface of the earth. You can configure the style of the light layer, including the light intensity and color. This topic describes the configuration items of the light layer.

Click **Light Layer** under **Components**. The Settings tab of **Light Layer** appears.

**Note:** If **Components** does not contain **Light Layer**, add the **Light Layer** component. For more information, see [3D globe](/intl.en-US/Widget Guide/3D globe widget and its components/3D globe.md).

## Settings

![Setting tab of the lighting layer](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9886401161/p73083.png)

-   **Search for Configurations**: In the right-side panel of Canvas Editor, click the **Settings** tab, and click **Search for Configurations** in the upper-right corner. Enter the required configuration item in the **search** box, and click the search icon to quickly locate the configuration item. Fuzzy match is supported. For more information, see [Search for widget configuration items]().
-   **Ambient Light**

    |Parameter|Description|
    |---------|-----------|
    |**Ambient Color**|The color of the ambient light. For more information, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).|
    |**Ambient Intensity**|The intensity of the ambient light.|

-   **Spot Light**

    |Parameter|Description|
    |---------|-----------|
    |**Spot Color**|The color of the spot light. For more information, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).|
    |**Spot Intensity**|The intensity of the spot light.|

-   **Radius**: the radius of the light range. Valid values: 1 to 16.

## Data

This component does not support data configuration.

## Interaction

This component does not support interaction events.

## Interaction configuration in the blueprint editor

1.  In the canvas editor of the 3D globe widget, click the ![Add to Blueprint Editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89089.jpg) icon next to **Light Layer** under **Components**.
2.  Click the ![Blueprint Editor icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3519036061/p89087.jpg) icon in the upper-left corner of the page.
3.  In the blueprint editor, click **Light Layer** in the Added Nodes pane. You can configure parameters of the light layer on the canvas.

    ![Light layer parameters in the blueprint editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9886401161/p87832.jpg)

    -   **Event**: The light layer does not support events.
    -   **Actions**

        |Action|Description|
        |------|-----------|
        |**Show**|This action shows the component and does not need parameter input.|
        |**Hide**|This action hides the component and does not need parameter input.|


