# Render Log Service data in DataV

The following sections describe how to configure DataV to render data from Log Service.

The following sections describe how to:

-   Create and configure Log Service to work with DataV \(set indexes\).
-   Create a sample dashboard.
-   Share the dashboard publicly.

## Prerequisites

-   You must have completed [Configure Log4JAppender with Kubernetes and Log Service](/intl.en-US/User Guide for Kubernetes Clusters/Observability/Log management/Configure Log4jAppender for Kubernetes and Log Service.md) and the service is currently running.
-   You must have purchased DataV Enterprise Edition.

## Configure Log Service

1.  Visit the Logstore List page within your project.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405088038_en-US.png)

2.  Click **Search** next to the name of your project. The following page is displayed:

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405098039_en-US.png)

3.  Create indices for all required fields. The following example creates an index for each item. Click**Index Attributes** from the upper menu of the page and click **Modify**.
4.  Verify the data from the Search & Analysis page:

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405098041_en-US.png)

5.  Once the data has been imported properly, switch to **Graph** view \(in the following graph, the axis is ‘time’\):

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405098042_en-US.png)


## Configure DataV

1.  Visit the DataV product page to create your first project.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405098043_en-US.png)

2.  Click **Create Project**, select a blank template, and click **Create**.
3.  Add a widget to the dashboard.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405108045_en-US.png)

    The widget displays some sample static dataset.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405108046_en-US.png)

4.  Click the widget and, select the Log Service \(SLS\) from Data Source Type from the **Data** tab on the right side.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405108047_en-US.png)

5.  Click **Create** in the Select Data Source. The New data dialog is displayed, fill in the relevant information, and click **OK**.

    **Note:** Make sure you add `http://` or `https://` in the Endpoint field.

6.  Once completed, select the newly created Source. The following example uses a simple example query:

    ```
    {
    "projectName": "k8s-logs",
    "logStoreName": "k8s-logstore",
    "topic": "",
    "from": "1518883200",
    "to": "1518969600",
    "query": "* | select count(1) as pv, date_format(from_unixtime(__time__ - __time__%3600) ,'%Y/%m/%d %H:%i:%s') as time group by time order by time limit 1000" ,
    "line": 100,
    "offset": 0
    }
    ```

    **Note:** from and to are the timestamps you can use to examine raw data in the Search console.

7.  Preview the data by clicking **View Data Response** button at the lower-side of the window. The following response result window is displayed:

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405108049_en-US.png)

8.  Click **Select Filter** and apply the following filter to make sure the `pv` is an integer, and click **OK**.

    ```
    return Object.keys(data).map((key) => {
     let d= data[key];
     d["pv"] = parseInt(d["pv"]);
     return d;
    }
    )
    ```

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405108050_en-US.png)

9.  Set the axes and verify the settings are set correctly.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405118052_en-US.png)

10. Click **Preview**.

    You can see that `x` and `y` use the correct data type, and `pv` is an integer.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15645553168054_en-US.png)

11. To share this dashboard publicly, click **Publish** in the upper-right corner of the page.

    An example of a completed and published DataV dashboard, using a dataset from a Log Service data, is as follows:

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15627405118056_en-US.png)

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/16936/15645553168057_en-US.png)


## Conclusion

You have successfully configured DataV and Log Service together on Alibaba Cloud and used Log Service to perform real-time monitoring by means of a custom dashboard.

## References

For more information on Log Service and containers, see

-   [Log Service](https://www.alibabacloud.com/product/log-service)
-   [Container Service](https://www.alibabacloud.com/product/container-service)

