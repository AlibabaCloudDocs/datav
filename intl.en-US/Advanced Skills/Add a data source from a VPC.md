# Add a data source from a VPC

This topic describes how to configure a data source from a VPC. You can configure a database in the VPC as the data source of widgets in your DataV project.

For more information about VPC, see [What is a VPC?](/intl.en-US/Product Introduction/What is a VPC?.md)

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  Click **Data Sources** and then **Add Source**.

3.  In the **Type** drop-down list, select **RDS for MySQL**.

4.  In the next drop-down list, select **Intranet**.

5.  Turn on **VPC** and enter the database information.

    ![Database information](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4399557851/p9304.png)

    You can obtain the **VPC ID** and **Instance ID** in the Alibaba Cloud console.

    After you enter the database information, DataV automatically tests whether the database can be connected.

6.  After the database passes the connectivity test, click **OK**.

    You can use the database in the VPC as the data source of widgets.


