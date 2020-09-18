---
keyword: [添加交互式分析 Hologres数据源, 交互式分析 Hologres]
---

# 添加交互式分析Hologres数据源

本文档介绍在DataV中添加并使用交互式分析Hologres数据源的方法。通过交互式分析独立数据源与DataV的深度合作，您可以将Hologres高效查询的数据，快速对接DataV，实现数据的可视化展示。

已准备好待添加的交互式分析Hologres数据源。

## 添加交互式分析Hologres数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**交互式分析 Hologres**。

4.  填写**交互式分析 Hologres**数据源相关信息。

    ![交互式分析 Hologres数据源面板](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2805964951/p112718.jpg)

    **说明：** 如果您需要新建数据库，请参见[创建数据库](/cn.zh-CN/快速入门/创建数据库.md)。

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，可以自由命名。|
    |**域名**|连接数据库的地址。 **说明：** 该地址是需要DataV服务器能够通过公网或阿里云部分Region内网访问您数据库的域名或IP地址。

例如使用阿里云交互式分析Hologres，可在[Hologres管控台](https://hologram.console.aliyun.com/#/instance)的实例配置中查看实例ID。如该实例ID为：`xxxxxxxx-cn-xxxk3ovx003`，则实例域名示例为：`xxxxxxxx-cn-xxxk3ovx003-cn-beijing-internal.hologres.aliyuncs.com:80`。 |
    |**用户名**|登录数据库的用户名。|
    |**密码**|登录数据库的密码。|
    |**端口**|数据库设置的端口。|
    |**数据库**|当前所选数据库的名称。|

    数据库信息填写完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

5.  测试连接通过后，单击**确定**，完成数据源添加。

    新添加的数据源会自动列在数据源列表中。


