---
keyword: [One-click beautification, One-click beautification of DataV]
---

# One-click beautification

This topic describes how to use the One-click beautification function of DataV. The One-click beautification function allows you to quickly adjust the layout of your project and use built-in styles to enrich the content of your project. This provides an easy way to design the overall style of your project.

## Procedure

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  On the **Projects** tab, [create a project](/intl.en-US/Manage Projects/Create a project.md) or move the pointer over an existing project and click **Edit**.

3.  In Canvas Editor, click **Beautify Toolbox** in the toolbar.

    ![Beautify Toolbox](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7435117951/p93745.png)

4.  In the left pane, click the **One-click beautification** tab.

    If the **One-click beautification** function is not enabled, you can click the ![Eye icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7435117951/p98501.jpg) icon or **Quick Applied** to enable this function.

    **Note:** You can click ![Eye icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7435117951/p98499.jpg) on the left of **One-click beautification** to enable or disable this function.

5.  On the **One-click beautification** tab, configure the overall style and layout of your project.

    The **One-click beautification** tab contains two sections: **Overall style** and **Layout setting**. For more information about parameters in the two sections, see [Parameters](#section_dsx_7d7_iog).

6.  Preview the beautification effect in the canvas. If you are satisfied with the effect, click **Apply**.

    **Warning:** The applied beautification configurations overwrite the original configurations of your projects. This may change the widgets in your project. Exercise caution when you perform this operation.

    If you are not satisfied with the beautification effect, click **Cancel** to cancel the beautification effect.

7.  After the One-click beautification function is configured, you can click the [Preview](/intl.en-US/Manage Projects/Preview a project.md) or [Publish](/intl.en-US/Manage Projects/Publish a project.md) icon to view the beautification effect of your project.


## Parameters

On the **One-click beautification** tab, you can configure the following parameters:

-   **Overall style**: Click the square box in Overall style to select a built-in style and click a blank area on the One-click beautification tab to make the style take effect.

    **Note:**

    -   DataV provides 20 built-in styles for you to select. More built-in styles will be provided in later versions.
    -   After an overall style is applied, if you need to select another style in subsequent operations, the applied style is replaced with the selected style. The operations include modifying configurations and adding widgets for your project.
    ![Style selection](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3715501161/p100073.png)

-   **Heading**: the heading style of visual groups in your project. You can click the ![Eye icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3715501161/p93768.jpg) icon to cancel or apply the heading style.

    |Parameter|Description|
    |---------|-----------|
    |**Subtitle**|If you turn on the switch, the subtitle in a heading is displayed. If you turn off the switch, the subtitle in a heading is not displayed.|
    |**Text alignment**|Specifies how texts in a heading are aligned. You can select **Align Default**, **Align Left**, **Align Center**, or **Align Right**.|

-   **Title**: the title style of visual groups in your project. You can click the ![Eye icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3715501161/p93768.jpg) icon to cancel or apply the title style.

    |Parameter|Description|
    |---------|-----------|
    |**Subtitle**|If you turn on the switch, the subtitle in a title is displayed. If you turn off the switch, the subtitle in a title is not displayed.|
    |**Text alignment**|Specifies how texts in the title are aligned. You can select **Align Default**, **Align Left**, **Align Center**, or **Align Right**.|
    |**Exclusion type**|If you select **Map** or **Ticker Board** for Exclusion type, the applied title style does not take effect for these widgets. If you do not select Map or Ticker Board, the applied title style takes effect for all widgets in your project. **Note:** Only the **Map** and **Ticker Board** options are provided for this parameter. For other widgets, you must specify whether to apply the title style. |

-   **Background**: the background style of visual groups in your project. You can click the ![Eye icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3715501161/p93768.jpg) icon to cancel or apply the background style.

    **Exclusion type**: If you select **Map** or **Ticker Board** for Exclusion type, the applied background style does not take effect for these widgets. If you do not select Map or Ticker Board, the applied background style takes effect for all widgets in your project.

    **Note:** Only the **Map** and **Ticker Board** options are provided for this parameter. For other widgets, you must specify whether to apply the background style.

-   **Layout setting**: the overall layout of visual groups in your project.
    -   **Space**: the margin style of visual groups in your project.

        |Parameter|Description|
        |---------|-----------|
        |**Screen padding**|The margin between borders of visual groups and canvas borders in your project.|
        |**Group margin**|The margin between borders of visual groups in your project.|
        |**Group padding**|The margin between widgets and borders of visual groups.|

    -   **Alignment threshold**: the thresholds used to optimize the page layout. You can adjust the thresholds to make the alignment relationship between widgets more obvious.

        |Parameter|Description|
        |---------|-----------|
        |**Guideline thresholds X and Y**|The thresholds to merge the visual guides in X and Y coordinates. **Note:** If two independent visual guides are used in your project and a large spacing gap exists between widgets, you can adjust these thresholds to reduce the gap. |
        |**Snap thresholds X and Y**|The thresholds to snap visual guides in X and Y coordinates for widgets. **Note:** If visual guides are used but widgets are not aligned, you can adjust these thresholds to align the widgets. |

    -   **Keep group**: If you use the One-click beautification function to optimize the layout in your project, the group structure of widgets in your project is not considered unless otherwise specified. If you turn on this switch, grouped widgets in your project automatically form an independent visual group. If you want to form a visual group by using the widgets that are not grouped, manually group these widgets with a Title widget \(if required\) and turn on this switch.

## Examples

![Before the One-click beautification function is enabled](../images/p94001.png "Before the One-click beautification function is enabled")

![Default overall style after the One-click beautification function is enabled](../images/p94002.png "Default overall style after the One-click beautification function is enabled")

![Layout after Guideline threshold Y is adjusted](../images/p94003.png "Layout after Guideline threshold Y is adjusted")

![Layout after Snap threshold Y is adjusted](../images/p94005.png "Layout after Snap threshold Y is adjusted")

