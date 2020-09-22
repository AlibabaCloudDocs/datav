# DataV-WS服务使用说明

DataV-WS服务整合了静态文件服务和WebSocket服务。静态文件服务主要用于本地模型地址的加载，WebSocket服务符合蓝图编辑器WebSocket节点规范，使用该服务后，无需额外开发，在蓝图编辑器中能够直接使用该服务跨越多个同网段下的可视化应用进行通信。本文您介绍DataV-WS服务的详细功能。

## DataV-WS服务文档目录

![目录](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/6358788951/p112704.jpg)

**说明：** 请勿删除DataV-WS服务下的`assets`目录。

## 启动与停止DataV-WS服务

-   Windows：
    1.  下载[DataV-WS服务安装包](http://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_ws.zip)。
    2.  解压后双击打开datav\_ws\_win.exe文件。
    3.  打开文件后，看到如下指令，表示启动成功。

        ```
        Server listen on IP地址（如：127.0.0.1）:8181     
        ```

        **说明：** 启动后请勿关闭cmd运行框。

    4.  在DataV-WS服务开启后，可完成WebSocket服务、模型服务和静态资源服务的开发和演示等功能操作，详情请参见[配置DataV-WS服务](#section_cku_pi5_2ni)。
-   linux/mac：
    1.  执行如下命令，下载DataV-WS服务应用。

        ```
        wget http://sh-conf.oss-cn-shanghai.aliyuncs.com/doc_files/datav_ws.zip                      
        ```

    2.  解压安装包，打开终端，进入到服务所在目录，如datav-ws。
    3.  执行如下命令，服务默认在8081端口启动。

        ```
        chmod 777 ./
        sh exec.sh start
        ```

        您可以通过sh exec.sh stop命令，停止服务。

        您可以通过sh exec.sh restart命令，重启服务。

    4.  在DataV-WS服务开启后，可完成WebSocket服务、模型服务和静态资源服务的开发和演示等功能操作，详情请参见[配置DataV-WS服务](#section_cku_pi5_2ni)。

## 配置DataV-WS服务

可配置的服务包括WebSocket、模型服务和静态资源服务。

-   配置WebSocket服务。
    -   开发阶段：
        1.  在本地启动DataV-WS服务，详情请参见[启动与停止DataV-WS服务](#section_r1q_sp5_4o7)。
        2.  登录[DataV控制台](https://datav.aliyun.com/)。
        3.  创建[空白可视化应用](/cn.zh-CN/快速入门/制作可视化应用（空白画布篇）/创建可视化应用.md)。
        4.  单击**画布编辑器**页面左上角，单击**蓝图编辑器**图标，切换到**蓝图编辑器配置**页面。

            ![蓝图编辑器界面入口](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7358788951/p66701.png)

        5.  在**蓝图编辑器配置**页面，将左侧逻辑节点栏内的**WebSocket**节点拖至画布中。
        6.  设置蓝图编辑器内**WebSocket**节点的**socket服务地址**为：`ws://127.0.0.1:8181`。

            ![设置socket服务地址](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7358788951/p103301.png)

    -   演示阶段：
        1.  在演示机器上或同网段机器启动DataV-WS服务，详情请参见[启动与停止DataV-WS服务](#section_r1q_sp5_4o7)。
        2.  根据演示机器的IP地址，在演示机器的蓝图编辑器内添加一个**WebSocket**节点，并变更**WebSocket**节点的**socket服务地址**为：`ws://机器IP地址:8181`，即可完成多个同网段可视化应用的互相通信功能。
-   配置模型服务。
    -   开发阶段：
        1.  在本地启动DataV-WS服务，详情请参见[启动与停止DataV-WS服务](#section_r1q_sp5_4o7)。
        2.  将模型放入DataV-WS服务中的assets文件夹内。

            ![模型放入目录中](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7358788951/p112700.jpg)

        3.  登录[DataV控制台](https://datav.aliyun.com/)。
        4.  创建[空白可视化应用](/cn.zh-CN/快速入门/制作可视化应用（空白画布篇）/创建可视化应用.md)。
        5.  参见画布编辑器[添加组件](/cn.zh-CN/组件管理/添加组件.md)，在画布编辑器页面搭建所需要的**DataV 3D引擎**组件，并选择添加**模型加载器**子组件。

            **说明：** **DataV 3D引擎**为产品非通用组件。如有使用该组件的需求，请联系DataV销售人员进行线下购买后再使用。

        6.  设置**模型加载器**组件内的模型地址为：`http://IP地址:8181/模型文件名`。

            ![模型加载器地址](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7358788951/p103218.png)

    -   演示阶段：
        1.  将在开发阶段生成的datav\_ws文件夹复制到同网段演示机器上。
        2.  在可视化应用演示机器上启动DataV-WS服务，详情请参见[启动与停止DataV-WS服务](#section_r1q_sp5_4o7)。
        3.  打开需要演示的可视化应用即可获取服务上的模型内容。
-   配置静态资源服务。
    1.  在本地启动DataV-WS服务，详情请参见[启动与停止DataV-WS服务](#section_r1q_sp5_4o7)。
    2.  将静态资源（如图片）放入DataV-WS服务中的assets文件夹内。

        ![图片资源放置目录](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7358788951/p112703.jpg)

    3.  登录[DataV控制台](https://datav.aliyun.com/)。
    4.  创建[空白可视化应用](/cn.zh-CN/快速入门/制作可视化应用（空白画布篇）/创建可视化应用.md)。
    5.  参见画布编辑器[添加组件](/cn.zh-CN/组件管理/添加组件.md)，在画布编辑器页面搭建所需要的**单张图片**组件。
    6.  设置**单张图片**组件背景图编辑框的文件地址为：`http://IP地址:8181/p2544435894.webp`，即可直接获取服务上的图片内容。

        ![图片地址](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/7358788951/p103210.png)


## 其他文档

其他相关文档链接：[自建WebSocket节点服务说明](/cn.zh-CN/蓝图编辑器使用说明/逻辑节点配置/数据处理.md)。

