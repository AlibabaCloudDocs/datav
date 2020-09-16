# 添加DataV数据代理服务

本文档介绍在DataV中添加DataV数据代理服务数据源的方法，以及相关参数配置说明。使用DataV数据代理服务，您无需暴露数据库的公网IP，就可以连接自建的数据库，提高数据安全性。

已准备好待添加的DataV数据代理服务数据源。

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**DataV数据代理服务**。

    **说明：**

    -   该服务SDK只提供HTTP服务。如果您需要使用HTTPS服务，则需要申请一个Chrome认可的HTTPS 证书，申请方法请在谷歌浏览器中搜索。
    -   在使用HTTPS服务之前，请确保DataV页面是使用HTTP协议打开的（该策略可确保HTTPS网站的安全）。
4.  填写数据库信息。

    ![添加DataV数据代理服务](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2367092951/p7911.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|DataV Proxy服务器所在IP地址或域名，如果您使用的是ECS服务器，则应该配置为ECS服务器的公网IP。详情请参见[DataV Proxy应用使用说明](/cn.zh-CN/进阶技巧/DataV Proxy应用使用说明.md)。|
    |**端口**|DataV Proxy安装完成后，系统会自动生成端口号，一般为8001。详情请参见[DataV Proxy应用使用说明](/cn.zh-CN/进阶技巧/DataV Proxy应用使用说明.md)。|
    |**Key**|DataV Proxy安装完成后，系统会自动生成Key。详情请参见[DataV Proxy应用使用说明](/cn.zh-CN/进阶技巧/DataV Proxy应用使用说明.md)。|
    |**Secret**|DataV Proxy安装完成后，系统会自动生成Secret。详情请参见[DataV Proxy应用使用说明](/cn.zh-CN/进阶技巧/DataV Proxy应用使用说明.md)。|
    |**数据库**|展示DataV Proxy应用中，已经添加的数据源的ID。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

5.  连接成功后，单击**确定**，完成数据源添加。


