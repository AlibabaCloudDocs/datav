# DataV Proxy configuration in Linux {#concept_w2c_3fq_p2b .concept}

With the DataV Proxy service, you can configure data queries without the need for opening a database or building an API. The DataV Proxy service sends encrypted SQL strings and the ID of a database to an application. Then the application connects to the database, obtains the query results, and returns the results to DataV.

Click [here](https://files.alicdn.com/tpsservice/3b30abf1b9f8a2056cc135d2a6587bb9.zip) to download a sample application published on GitHub. The application can be deployed to an ECS instance. Before performing the following procedure, you need to prepare the MySQL database and tables that need to be displayed.

The following procedure uses a Node.js sample application, or you can use a new developed application.

1.  Buy an ECS instance. You can use the lowest possible configuration and upgrade it based on your requirements.
2.  Deploy the code and start the service.
3.  Configure the database.
4.  Configure the database to DataV.

## Purchase an ECS server {#section_owz_vn1_r2b .section}

To purchase a cost-effective ECS server, we recommend that you:

-   Select **Pay-As-You-Go** as a **billing option**.
-   Select **Public Image** from the **Images** section, and select **CentOS 7.4 64-bit**.
-   Select **PayByTraffic** from the **Network Billing Method** section.
-   Select a data disk if you have any special requirements.
-   Select other configurations and complete the purchase according to the preceding figure.

## Deploy the code and start the service {#section_tzv_qfc_yfb .section}

1.  Run the following commands to download the DataV Proxy sample application and extract it.

    ``` {#codeblock_v6t_e7q_cuy}
    wget https://files.alicdn.com/tpsservice/3b30abf1b9f8a2056cc135d2a6587bb9.zip
    unzip 3b30abf1b9f8a2056cc135d2a6587bb9.zip
    cd {decompressed directory}
    ```

    **Note:** If the system displays **unzip command is not found**, you need to first run `yum install unzip` and then continue the following commands.

2.  Run the following commands to install Node.js and dependencies.

    ``` {#codeblock_q0y_26o_u9z}
    wget -qO- https://raw.githubusercontent.com/creationix/nvm/v0.33.11/install.sh | bash
    bash
    nvm install 8.9
    npm install pm2 -g
    npm install --registry=https://registry.npm.taobao.org
    ```

3.  Run the following command to run the DataV Proxy sample application.

    ``` {#codeblock_zzy_qqe_8t3}
    pm2 start app.js
    ```

4.  Run the following command to view the running status of the application.

    ``` {#codeblock_kcb_wbw_ggu}
    pm2 status
    ```

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/156194695033646_en-US.png)

    If the running status is **online**, it indicates that the application is activated successfully, and you can continue with the following steps:

    -   Run node ./bin/info.js to view the domain name, port, Key, Secret, and configured database information of the Data Proxy.

        ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/156194695133650_en-US.png)

        **Note:** You need to save the information that is used when configuring a DataV data source.

    -   To change the Key, use node ./bin/genkv.js to generate a new one.
    -   Access `http://domain name:port/status` to verify server status. The domain name is the public network IP of your ECS instance. The port is the port you have identified, which usually is `9998`.

## Configure the database {#section_e1t_xfc_yfb .section}

1.  [Database whitelist settings](reseller.en-US/User Guide/Manage data sources/Database whitelist settings.md#) and authorize remote connections.
2.  In the directory where DataV Proxy is located, run `vim config.js`, open config.js, and add a database to the database filed , as shown in the following example.

    ``` {#codeblock_t7c_bmi_2ox}
    databases: [
        {
          id: 'test', // Make sure that there are no repeated IDs. Then, input them into the DataV backend “database” field. 
          type: 'mysql', // rds, ads
          host: '127.0.0.1', // Domain name and IP address
          user: 'root', // User name
          password: 'root', // Password
          database: 'test', // Database name
          port: 3306 // Port
        },
        {
          // ... 
        },
        //... Enter the database you want to add here. 
      ]
    ```

3.  After the configuration is complete, perform the following commands separately and restart the MySQL database and the DataV Proxy application.

    ``` {#codeblock_32m_oem_acx}
    systemctl restart mysqld.service
    ```

    ``` {#codeblock_dn7_wr4_1jo}
    pm2 restart 0
    ```


## Configure the data source to DataV {#section_mpz_xfc_yfb .section}

1.  Use the HTTP protocol to enter the [DataV console](http://partners-intl.console.aliyun.com/#/datav).
2.  Select **Data Sources** \> **Add Source**.
3.  On the **New Data Source** page, go to the **Type** drop-down list and select **DataV Data Proxy Service**.
4.  Enter the information from the previous Deployment section \(outlined in red\) into the following input box. For more information about the parameters, see [Add DataV Data Proxy Service](reseller.en-US/User Guide/Manage data sources/Add data sources/Add DataV Data Proxy Service.md#).

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/15619469519303_en-US.png)

5.  In the data settings field, go to **Data Source Type** and select **Database**. Custom the data source based on the preceding figure.

    ![](http://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/16583/15619469518648_en-US.png)


**Note:** 

-   This service SDK only provides HTTP services. If you need HTTPS services, you must apply for an HTTPS certificate recognized by Google Chrome.
-   We recommend you enable HTTP services until the HTTPS certificate is applied.

## O & M {#section_v3y_x41_r2b .section}

-   Check real-time logs

    ``` {#codeblock_bsm_qrn_srm}
    pm2 logs
    ```

-   Check history logs

    ``` {#codeblock_3fx_umn_ph5}
    ls -al . /{The directory where DataV Proxy is located}/logs
    ```

-   Restart

    ``` {#codeblock_mi5_f7d_9ks}
    pm2 restart all
    ```

-   Start service

    ``` {#codeblock_kv3_32y_8t6}
    pm2 start app.js
    ```


