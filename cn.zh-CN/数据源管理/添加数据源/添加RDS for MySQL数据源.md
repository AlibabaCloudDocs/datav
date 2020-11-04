# 添加RDS for MySQL数据源

本文档为您介绍在DataV中添加RDS for MySQL数据源的方法。

已准备好待添加的RDS for MySQL数据源。

## 通过内网添加数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**RDS for MySQL**。

4.  在列表中选择**内网**，并选择RDS实例所在的区域。

    ![选择内网](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9957092951/p7824.png)

5.  选择内网数据库的网络类型（包括**专有网络**和**经典网络**）。

    -   **专有网络**
        1.  打开**VPC**开关，进入**专有网络**模式。

            ![VPC网络数据源参数](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9957092951/p55579.png)

        2.  填写数据库信息。

            **说明：** 如果您需要新建数据库，请参见[创建数据库](/cn.zh-CN/RDS MySQL 数据库/数据库/创建数据库.md)。

            |参数|说明|
            |--|--|
            |**名称**|数据源的显示名称，可以自由命名。|
            |**域名**|连接数据库的地址。 **说明：** 该地址是DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的域名或IP地址。

例如使用内网环境下的阿里云RDS for MySQL，域名示例为：rm-bpxxxxxxxxx33150.mysql.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。 |
            |**VPC ID**|VPC实例的ID，此VPC为您的RDS for MySQL实例所在的VPC。可进入[RDS管理控制台](https://rdsnext.console.aliyun.com/)，在**实例列表** \> **基本信息** \> **网络类型**中获取。![获取VPC ID](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8244964951/p55693.png) |
            |**实例ID**|VPC下数据库实例的ID，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。|
            |**用户名**|登录数据库的用户名。|
            |**密码**|登录数据库的密码。|
            |**端口**|数据库设置的端口。|
            |**数据库**|当前所选数据库的名称。|

        3.  数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。
    -   **经典网络**
        1.  关闭**VPC**开关，进入**经典网络**模式。
        2.  填写数据库信息。

            ![添加RDS for MySQL数据源（内网）经典网络](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0067092951/p7826.png)

            **说明：** 如果您需要新建数据库，请参见[创建数据库](/cn.zh-CN/RDS MySQL 数据库/数据库/创建数据库.md)。

            |参数|说明|
            |--|--|
            |**名称**|数据源的显示名称，可以自由命名。|
            |**域名**|连接数据库的地址。 **说明：** 该地址是DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的域名或IP地址。

例如使用内网环境下的阿里云RDS for MySQL，域名示例为：rm-bpxxxxxxxxx33150.mysql.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。 |
            |**用户名**|登录数据库的用户名。|
            |**密码**|登录数据库的密码。|
            |**端口**|数据库设置的端口。|
            |**数据库**|当前所选数据库的名称。|

        3.  数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。
6.  测试连接通过后，单击**确定**，完成数据源添加。

    新添加的数据源会自动列在数据源列表中。


## 通过外网添加数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**RDS for MySQL**。

4.  在列表中选择**外网**。

    如果需要设置外网地址，请参见[设置连接地址]()。

5.  填写数据库信息。

    ![添加RDS for MySQL数据源（外网）](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0067092951/p7829.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的地址。 **说明：** 该地址是DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的域名或IP地址。

例如使用外网环境下的阿里云RDS for MySQL，域名示例为：rm-bpxxxxxxxxxco.mysql.rds.aliyuncs.com，可在[RDS管理控制台](https://rdsnext.console.aliyun.com/)的实例基本信息页面获取。 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

6.  测试连接通过后，单击**确定**，完成数据源添加。

    新添加的数据源会自动列在数据源列表中。


