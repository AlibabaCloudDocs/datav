# 配置VPC数据源

本文档介绍在DataV中配置专有网络VPC（Virtual Private Cloud）内数据源的方法。通过专有网络VPC数据源的配置，您可以将专有网络VPC内的数据库接入到DataV中，并作为组件的数据源进行大屏展示。

了解专有网络VPC，详情请参见[什么是专有网络](/intl.zh-CN/产品简介/什么是专有网络.md)。

1.  登录[DataV控制台](https://datav.alibabacloud.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**RDS for MySQL**。

4.  在列表中选择**内网**，并选择RDS实例所在的区域。

5.  打开**VPC**开关，并填写数据库信息。

    ![填写数据库信息](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/zh-CN/8775711951/p9304.png)

    除了传统的数据库配置外，您还需要配置数据库的**VPC ID**和**实例ID**。这两种ID都可以在阿里云控制台中获取。

    -   通过[RDS控制台](https://rdsnext.console.aliyun.com/)获取**VPC ID**和**实例ID**。

        ![获取VPC ID](../images/p8636.png "获取数据库实例ID")

        ![获取实例ID](../images/p8637.png "获取VPC ID")

    -   如果您的数据库安装在VPC内的ECS上，则需要配置该ECS的**VPC ID**和**实例ID**。

        ![配置ECS的VPC ID和实例ID](../images/p8638.png "获取ECS的实例ID")

        ![配置ECS的VPC ID和实例ID](../images/p8639.png "获取ECS的VPC ID")

    配置完成后，系统会自动进行测试连接，验证数据库是否能连通正常。

    **说明：** 如果您的RDS for MySQL数据库是从经典网络切换到专有网络VPC网络的，且通过以上方法无法连通数据源，那么可以通过以下方式解决：

    -   方法一：在获取到的**VPC ID**和**实例ID**后面添加**-1**，再重新测试连接。如果依然无法连通，可尝试方法二。
    -   方法二：调用RDS for MySQL的[查询实例详细信息](/intl.zh-CN/API 参考/实例/查询实例详细信息.md)接口，获取**VPC ID**和**实例ID**再重新测试连接。如果依然无法连通，可联系阿里云技术支持工程师解决。
6.  测试连接通过后，单击**完成**，完成数据源添加。

    配置完成后，您就可以使用该专有网络VPC内的数据库作为组件的数据源了。


