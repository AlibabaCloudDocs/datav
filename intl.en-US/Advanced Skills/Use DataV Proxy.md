# Use DataV Proxy

DataV Proxy provides a graphic user interface to configure DataV data proxies. You can use it to configure data queries without the need to access databases or compile APIs. This topic describes how to use DataV Proxy.

## How it works

1.  The DataV Proxy application obtains the encrypted SQL query strings and database IDs.
2.  The application connects to the database to query data.
3.  The application returns the results to the DataV console.

## Start the DataV Proxy application

-   Windows:
    1.  [Download the DataV Proxy software package](https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip).
    2.  Decompress the package and double-click the datav\_proxy\_wins.exe file.
    3.  Sign up and log on to the DataV Proxy application.
    4.  In the application, add a data source and query logs. For more information, see [Configure the DataV Proxy application](#section_ncg_mtb_dhb).
-   Linux or macOS:
    1.  Run the following command to download the DataV Proxy software package:

        ```
        wget https://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_proxy.zip                        
        ```

    2.  Decompress the package to the directory of the project.
    3.  Run the following commands to start DataV Proxy \(port 8001 is used by default\):

        ```
        chmod 777 ./*
        sh exec.sh start
        ```

        You can also run the sh exec.sh start -p \[Port number\] command to start DataV Proxy by using the specified port, for example, sh exec.sh start -p 8080.

        You can run the sh exec.sh stop command to stop DataV Proxy.

    4.  After you start DataV Proxy, access `http://Domain name or IP address:Port` in the browser.
        -   Set **Domain name or IP address** to the public IP address of the server where DataV Proxy is installed.
        -   Set **Port** to the port number used to start DataV Proxy.
    5.  Sign up and log on to the DataV Proxy application.
    6.  In the application, add a data source and query logs. For more information, see [Configure the DataV Proxy application](#section_ncg_mtb_dhb).

## Configure the DataV Proxy application

1.  Access `http://{IP address or domain name of the DataV Proxy server}:Port number`, for example, `http://12.12.12.12:8001`. The DataV Proxy configuration page appears.

    **Note:** You need to sign up and log on to the DataV Proxy application for the first access.

2.  Configure a data source.

    Configure the basic information of the database. After the configuration is complete, you can **test the database connectivity** and **SQL query operations** to ensure reliability of the data source.

    **Note:** Before you add a data source, add the `IP address or domain name of the DataV Proxy server` in [step 1](#li_c0z_k0f_j2j) to the whitelist of your database, for example, an ApsaraDB RDS for MySQL instance. For more information, see [Control access to an ApsaraDB RDS for MySQL instance](/intl.en-US/RDS MySQL Database/Quick start/Set the whitelist/Control access to an ApsaraDB RDS for MySQL instance.md).

    1.  Click **Data Source**, select a data source type, and click **add**.

        ![Configure the data source](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8276557851/p40925.png)

    2.  In the dialog box that appears, enter information of the data source.

        ![Data source information](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8276557851/p40926.png)

        |Parameter|Description|
        |---------|-----------|
        |id|The ID of the data source. This parameter can be customized and must be unique.|
        |host|The IP address or domain name of the server where the database resides.

 For example, if the data source is an ApsaraDB RDS for MySQL instance, set this parameter to the **external endpoint** of the instance. You can obtain the endpoint on the Basic Information page of the ApsaraDB for RDS console, for example, **rm-bp1xxxxxxxxxxxxxhmo.mysql.rds.aliyuncs.com**. |
        |user|The username used to log on to the database.|
        |password|The password used to log on to the database.|
        |database|The name of the database.|
        |port|The port number used to connect to the database. For example, the port number used to connect to ApsaraDB RDS MySQL instances is **3306** by default. |

    3.  Test the configured data source.

        Click **link** to test the connectivity of the database.

        Click **SQL**. In the dialog box that appears, enter an SQL statement to test data in the database.

        ![Data source test](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9276557851/p40927.png)

3.  Query logs.

    Specify keywords and a range of log rows to query the logs.

    ![Query logs](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9276557851/p40928.png)

    **Note:** In Windows, you can only view the logs but cannot query them based on keywords or the specified range of log rows.

4.  Generate a key.

    Click **create key/secret**. A **key** and a **secret** are generated, and the previous key becomes invalid.

    ![Generate a key](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9276557851/p40929.png)

    **Note:** The key is empty by default.


## Use the DataV Proxy application

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).
2.  Navigate to **Data Sources** \> **Add Source**.
3.  In the Add Data Source dialog box that appears, specify the required information.

    ![Add Data Source](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3000501161/p59464.png)

    |Parameter|Description|
    |---------|-----------|
    |Type|Select DataV Data Proxy Service.|
    |Name|The name of the data source. You can enter a name as needed.|
    |Domain Name|The IP address or domain name of the DataV Proxy server. You can obtain the value from the [Configure the DataV Proxy application](#li_c0z_k0f_j2j) section.|
    |Port|The port used to start DataV Proxy. You can obtain the value from the [Configure the DataV Proxy application](#li_c0z_k0f_j2j) section. By default, the port is **8001**.|
    |Key|Enter the **key** generated in step 4 in the [Configure the DataV Proxy application](#li_y67_4zf_iag) section.|
    |Secret|Enter the **secret** generated in step 4 in the [Configure the DataV Proxy application](#li_y67_4zf_iag) section.|
    |Database|The ID of the data source that is added to the DataV Proxy application.|

    After the preceding information is specified, DataV automatically checks the connectivity of the data source.

4.  Click **Obtain Databases** and select a database as the data source from the **database list**.

    **Note:** If the ID of the data source that is added to the DataV Proxy application is displayed in the list after you click **Obtain Databases**, the connection between DataV and the data source is established.

5.  Click **OK**.

    The data source is added. You can configure it in your widgets. For more information, see [t16561.md\#](/intl.en-US/Manage Widgets/Configure widget data.md).


