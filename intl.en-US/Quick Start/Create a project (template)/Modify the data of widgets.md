# Modify the data of widgets

After a project is created, you can modify widget data as needed.

-   The following example demonstrates how to modify the data of a widget that uses a **static data source**. You can directly paste the prepared data to the static data editor in the Configure Datasource pane. If you want to use a **CSV file**, a **database**, or other data sources for your project, [add a data source](/intl.en-US/Manage Data Sources/Add data sources/Overview.md) first.
-   If you want to use **API** as a data source, set the data source type to API. For more information about whether to select **Initiate Request from Server \(Applicable when cross-origin access fails\)** when you configure an API data source, see [Cross-origin data configuration](https://help.aliyun.com/document_detail/64140.html?spm=a2c4g.11186623.6.791.28d524a3MrlT6u).

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  On the **Projects** tab, select an existing project and click **Edit**.

3.  In the left-side Layers pane, click a widget.

4.  In the right-side pane, click the **Data** tab, and click **Set** next to Static Data.

5.  In the **Configure Datasource** pane, select **Static Data** from the **Data Source Type** drop-down list.

6.  In the static data editor, modify the data of the template or paste the prepared data in the JSON format.

    ![Static data editor](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8266369951/p96719.png)

    **Note:** The field names in the data that you configure must be the same as those in the widget settings.

    After the data configuration is complete, you can click the ![Refresh](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8083746061/p95948.png) icon in **Data Response Result** in the **Configure Datasource** pane.

    After the data response is returned, the system displays **Completed** and **Matched** on the **Data** tab.

    ![Configuration succeeded](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8266369951/p10324.png)

7.  Configure the data of other widgets in your project in the same way.


