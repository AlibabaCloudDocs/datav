---
keyword: 添加业务实时监控服务ARMS数据源
---

# 添加业务实时监控服务ARMS数据源

本文档为您介绍在DataV中添加实时监控服务ARMS数据源的方法，以及相关参数配置说明。业务实时监控服务（Application Real-Time Monitoring Service，简称ARMS）是一款APM类的监控产品。用户可基于ARMS的前端、应用和自定义监控功能，快速构建实时的应用性能和业务监控能力。

已准备好待添加的业务实时监控服务ARMS数据源。

## 添加业务实时监控服务ARMS数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**业务实时监控服务**。

4.  填写ARMS相关信息。

    ![添加业务实时监控服务ARMS数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1405964951/p34197.png)

    |参数|说明|
    |--|--|
    |**自定义数据源名称**|数据源的显示名称，您可以自由命名。|
    |**AK ID**|拥有ARMS访问权限的账号的AccessKey ID（从ARMS控制台获取）。|
    |**AK Secret**|拥有ARMS访问权限的账号的AccessKey Secret（从ARMS控制台获取）。|

5.  单击**确定**，完成数据源的添加。


## 使用业务实时监控服务ARMS数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**业务实时监控服务**。

6.  在**选择已有数据源**列表中选择配置完成的**业务实时监控服务**数据源。

7.  在下方**请求URL**编辑框中，填写ARMS数据集DataV接入链接 。详情请参见[自定义监控：将ARMS数据导入到DataV](https://help.aliyun.com/video_detail/57624.html?spm=5176.11065259.1996646101.searchclickresult.5bf86894T8WAcO)。

8.  单击**预览数据源返回结果**，查看数据返回结果。


