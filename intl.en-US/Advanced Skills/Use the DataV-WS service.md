# Use the DataV-WS service

DataV-WS integrates the static file service and WebSocket. The static file service is used to load local model addresses. WebSocket can be used in the blueprint editor to connect multiple projects in the same network range without additional development. This topic describes how to use DataV-WS.

## DataV-WS document directories

![Directories](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1485570061/p112704.jpg)

**Note:** Do not delete the `assets` directory.

## Start and stop DataV-WS

-   Windows:
    1.  Download the [DataV-WS installation package](http://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_ws.zip).
    2.  Decompress the package and double-click the datav\_ws\_win.exe file.
    3.  View the returned message. If the following information appears, DataV-WS is started:

        ```
        Server listen on IP address:8181 (for example, 127.0.0.1:8181)     
        ```

        **Note:** Do not close the command prompt after the start.

    4.  Develop and demonstrate WebSocket and the static file service after you start DataV-WS. For more information, see [Configure DataV-WS](#section_cku_pi5_2ni).
-   Linux or macOS:
    1.  Run the following command to download the DataV-WS installation package:

        ```
        wget http://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_ws.zip                      
        ```

    2.  Decompress the package, start the terminal, and enter the service directory, for example, datav-ws.
    3.  Run the following commands to start DataV-WS \(port 8001 is used by default\):

        ```
        chmod 777 ./
        sh exec.sh start
        ```

        You can run the sh exec.sh stop command to stop DataV-WS.

        You can run the sh exec.sh restart command to restart DataV-WS.

    4.  Develop and demonstrate WebSocket and static file service after you start DataV-WS. For more information, see [Configure DataV-WS](#section_cku_pi5_2ni).

## Configure DataV-WS

You can configure WebSocket and the static file service.

-   Configure WebSocket.
    -   Development:
        1.  Start DataV-WS on your local computer. For more information, see [Start and stop DataV-WS](#section_r1q_sp5_4o7).
        2.  Log on to the [DataV console](https://datav.alibabacloud.com/).
        3.  Create an empty [DataV project](/intl.en-US/Quick Start/Create a project (blank canvas)/Create a project.md).
        4.  In the upper-left corner of the **canvas editor**, click the **Blueprint Editor** icon. The **blueprint editor** appears.

            ![Blueprint editor](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1485570061/p66701.png)

        5.  In the **blueprint editor**, drag and drop the **WebSocket** node to the canvas.
        6.  Click the **WebSocket** node in the blueprint editor and set **Socket Endpoint** to `ws://127.0.0.1:8181`.

            ![Socket Service Address](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1485570061/p103301.png)

    -   Demonstration:
        1.  Start DataV-WS on a demonstration server that is in the same network range as the development server. For more information, see [Start and stop DataV-WS](#section_r1q_sp5_4o7).
        2.  Add a **WebSocket** node. Set **Socket Endpoint** of the **WebSocket** node to `ws://IP address of the demonstration server:8181`. The projects that use the two WebSocket nodes can communicate with each other.
-   Configure the static file service.
    1.  Start DataV-WS on your local computer. For more information, see [Start and stop DataV-WS](#section_r1q_sp5_4o7).
    2.  Add static files \(such as images\) to the assets directory.

        ![Image resource directory](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1485570061/p112703.jpg)

    3.  Log on to the [DataV console](https://datav.alibabacloud.com/).
    4.  Create an empty [DataV project](/intl.en-US/Quick Start/Create a project (blank canvas)/Create a project.md).
    5.  In the canvas editor, add an **image** widget. For more information, see [Add a widget](/intl.en-US/Manage Widgets/Add a widget.md).
    6.  Set **Background Image** to `http://IP address:8181/p2544435894.webp` so that the project can obtain the image from DataV-WS.

        ![Image address](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/1485570061/p103210.png)


## References

[t1840716.md\#section\_lun\_rky\_rx9]()

