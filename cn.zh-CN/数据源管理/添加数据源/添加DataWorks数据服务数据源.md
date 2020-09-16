---
keyword: 添加DataWorks数据服务数据源
---

# 添加DataWorks数据服务数据源

本文介绍在DataV中添加DataWorks数据服务数据源，并将通过DataWorks数据表生成的API，快速地展示在DataV可视化大屏中的方法。

已准备好待添加的DataWorks数据服务数据源。

-   DataWorks数据服务生成的API默认不支持HTTPS协议，所以请您在HTTP协议下打开DataV，即单击[http://datav.aliyun.com](http://datav.aliyun.com/)打开DataV。
-   如果您需要在HTTPS协议下使用DataWorks数据服务生成的API，请绑定证书到API网关，详细绑定过程请参见[如何使您的API支持HTTPS](https://help.aliyun.com/knowledge_detail/42126.html)。
-   DataWorks数据服务生成的API发布后会对接到API网关，直接使用API网关默认提供的二级域名会有每天限流1000次的限制，您可以在[API网关控制台](http://apigateway.console.aliyun.com)中为分组绑定独立域名来解除限流限制。

## 添加DataWorks数据服务数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**DataWorks数据服务**。

4.  填写**DataWorks数据服务**相关信息。

    ![添加DataWorks数据服务数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2605964951/p37989.png)

    |参数|说明|
    |--|--|
    |**自定义数据源名称**|数据源的显示名称，可以自由命名。|
    |**Region**|DataWorks项目所在的地域。|
    |**项目**|DataWorks项目（工作空间）。|
    |**AppKey**|拥有DataWorks数据服务中，某一项目访问权限的账号的AppKey ID，用于API调用（从DataWorks数据服务台获取）。|
    |**AppSecret**|拥有DataWorks数据服务中，某一项目访问权限的账号的AppSecret（从DataWorks数据服务台获取）。|

    **说明：**

    获取**AppKey**和**AppSecret**：在[DataWorks数据服务控制台](http://ds-cn-shanghai.data.aliyun.com)中，单击**服务管理** \> **API调用**，可获取您的**AppKey**和**AppSecret**。

    ![获取APPKey和APPSecret](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2605964951/p37990.png)

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用DataWorks数据服务数据源操作步骤

1.  准备通过**DataWorks数据服务**生成的API数据。

    登录[DataWorks数据服务控制台](http://ds-cn-shanghai.data.aliyun.com)，参见[生成API]()，使用数据服务生成API。

2.  登录[DataV控制台](https://datav.aliyun.com/)。

3.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

4.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

5.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

6.  在**设置数据源**页面中，选择**数据源类型**为**DataWorks数据服务**。

7.  在**选择已有数据源**列表中，选择您已经添加的**DataWorks数据服务**数据源 。

8.  在**选择API**列表中选择[第一步](#step_dt4_t7c_q0z)中生成的DataWorks数据服务API 。

9.  单击**预览数据源返回结果**，查看数据返回结果。


