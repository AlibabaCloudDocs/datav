# 添加AnalyticDB for PostgreSQL数据源

本文档为您介绍在DataV中添加AnalyticDB for PostgreSQL数据源的方法。

已准备好待添加的AnalyticDB for PostgreSQL数据源。

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**AnalyticDB for PostgreSQL**。

4.  填写数据库信息。

    ![添加AnalyticDB for PostgreSQL数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9079822951/p7956.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的URL地址。 **说明：** 此处的URL地址不是官网页面的URL，也不是本机的IP，是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的URL地址。

例如使用外网环境下的阿里云AnalyticDB for PostgreSQL，域名示例为：gp-bp1uxxxxxxxxxxxxxx0o.gpdb.rds.aliyuncs.com，可在[AnalyticDB for PostgreSQL控制台](https://gpdbnext.console.aliyun.com/gpdb/)的基本信息页面获取。 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

5.  连接成功后，单击**确定**，完成数据源添加。


