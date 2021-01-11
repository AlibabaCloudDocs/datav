# Configure the data source for a widget

This topic describes how to configure the data source for a widget in DataV and introduces sections in the **Set Data Source** pane, including Data Source, Data Filter, and Data Response Result.

## Configure a data source

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  On the **Projects** page, click the project that you create.

    If you have not created a project, see [Create a project by using a template](/intl.en-US/Manage Projects/Create a project.md).

3.  In the canvas editor, click a widget in the **Layer** pane or on the canvas.

    **Note:** If you have not added widgets to the canvas, see [Add a widget](/intl.en-US/Manage Widgets/Add a widget.md).

4.  On the right of the canvas editor, click the Data icon.

5.  On the Data tab, click **Set**.

    ![Set Data Source](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5997531061/p54852.png)

6.  In the **Set Data Source** pane, modify the data source type and script, configure a data filter, and preview the data response.


## Modify the data source type and script

1.  In the **Set Data Source** pane, select a data source type from the **Data Source Type** list.

    For more information about the supported data source types and configurations, see [Manage data sources](/intl.en-US/Manage Data Sources/Add data sources/Overview.md).

    **Note:** If you use an API data source, you can configure cross-origin access and obtain cookies of user clients. For more information, see [Cross-origin data configuration](/intl.en-US/Advanced Skills/Cross-origin data configuration.md) and [Use cookies to isolate data of a DataV project](/intl.en-US/Advanced Skills/Use cookies to isolate data of a DataV project.md).

2.  In the editing box, modify the data source script.

    In the lower-right corner of the editing box, click the ![Full Screen](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p132694.png) icon to edit the data source script in full screen. Click the ![Copy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p132696.png) icon to copy the data source script.

3.  After you configure the script, click **Preview Data Response** to preview the response result.

    ![Modify the data source script](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p54865.png)


## Configure a data filter

Data filters allow you to convert the data structure, filter data, and perform simple calculations.

1.  In the **Set Data Source** pane, select **Data Filter** to enable the data filter function.

    ![Configure a data filter](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p54866.png)

2.  Click the plus sign \(**+**\) on the right to add a data filter.

3.  In the filter editing box, enter code to filter widget data.

4.  Click **Test** to view the filter result.

    For more information about data filters, see [Description of data filter](/intl.en-US/Manage Widgets/Widget data filter/Use the data filter.md).


## View fields in the data response result

The fields, mappings, and descriptions of the widget data are listed in the data response result. You can only view the data response result and cannot modify it.

![Fields in the data response result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p54867.png)

## View the data response result

In the **Set Data Source** pane, view the data response result in the **Data Response Result** section.

The **Data Response Result** section displays data used by the widget in real time. If the data source of the widget changes, this section displays the latest data. If the widget data is not loaded in time, you can click the ![Refresh icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p132699.png) icon to obtain the latest data.

In the lower-right corner of the data editing box, click the ![Full Screen](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p132694.png) icon to view the data response result in full screen. Click the ![Copy](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p132696.png) icon to copy the data response result.

![Data Response Result](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/6997531061/p54868.png)

