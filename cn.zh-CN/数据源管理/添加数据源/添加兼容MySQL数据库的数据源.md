# 添加兼容MySQL数据库的数据源

本文档介绍在DataV中添加兼容MySQL数据库数据源的方法，以及相关参数配置说明。通过兼容MySQL数据库的数据源，您可以使用旧版本的MySQL数据库作为组件的数据源。

已准备好待添加的兼容MySQL数据库数据源。

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**兼容MySQL数据库**。

4.  填写数据库信息。

    ![添加数据对话框](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4267092951/p7910.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的地址。 **说明：** 该地址是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的域名或IP地址。例如使用DLA的外网地址：umxxxxxxxx-31xxxxxx.cn-hangzhou.datalakeanalytics.aliyuncs.com。 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|
    |**insecureAuth**|开启后，能够兼容旧版本的MySQL数据库（低于5.2版本，不保证全部兼容）。|
    |**兼容 Azure Database for MySQL**|开启后，能够兼容微软的MySQL数据库。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

    以[Data Lake Analytics](https://help.aliyun.com/document_detail/70378.html)服务为例，配置信息示例如下图所示。

    ![添加Data Lake Analytics服务](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4267092951/p47761.png)

5.  连接成功后，单击**确定**，完成数据源添加。


