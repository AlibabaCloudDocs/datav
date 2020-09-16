---
keyword: 添加OpenAPI数据源
---

# 添加OpenAPI数据源

本文档为您介绍在DataV中添加OpenAPI数据源的方法，以及相关参数配置说明。OpenAPI是阿里云提供的云产品开放接口的调用方式，使用OpenAPI可以方便地调用各云产品提供的API接口，轻松实现控制及查询等功能。在DataV中，最常见的场景是使用OpenAPI调用其他的云产品的API，获取数据并展示出来。

已准备好待添加的OpenAPI数据源。

## 添加OpenAPI数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**OpenAPI**。

4.  填写OpenAPI相关信息。

    ![添加Open API数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1305964951/p32819.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，您可以自由命名。|
    |**EndPoint**|OpenAPI的服务地址，需要您从云产品的API文档处获取。例如ECS的OpenAPI服务地址为`ecs.aliyuncs.com`，云监控杭州region的OpenAPI[服务地址](/cn.zh-CN/API参考/调用API.md)为`metrics.cn-hangzhou.aliyuncs.com`。|
    |**APIVersion**|云产品的API版本，您可以从云产品的API文档获取，如云监控的[API版本](/cn.zh-CN/API参考/调用API.md)为`2017-03-01`。|
    |**AppKey**|可以调用OpenAPI的账号的AccessKey ID。|
    |**AppSecret**|可以调用OpenAPI的账号的AccessKey Secret。|

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用OpenAPI数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**OpenAPI**。

6.  在**选择已有数据源**列表中选择配置完成的**OpenAPI**数据源。

7.  填写**接口名称**。

    在编辑框中填写需要调用的接口名称，即API调用中的Action参数。取值来自云产品提供的API列表，比如云监控的`QueryMetricList`。

8.  填写**返回结果路径**。

    取OpenAPI返回结果的一部分作为返回结果路径。

    例如OpenAPI返回：

    ```
    {
        "data": [
            {
                "x": 1,
                "y": 2
            },
            {
                "x": 2,
                "y": 4
            }
        ]
    }
    ```

    如果**返回结果路径**中填写**data**，则数据响应结果为：

    ```
    [
        {
            "x": 1,
            "y": 2
        },
        {
            "x": 2,
            "y": 4
        }
    ]
    ```

    **说明：** 这个转换可以在过滤器中进行，此处可以留空不填。

9.  在下方的编辑框中输入查询参数。

    -   查询参数为OpenAPI的接口参数，以JSON对象的形式填写。
    -   参数名参考云产品API的入参说明。
    -   回调ID在JSON对象的value中填写。
    以云监控的[QueryMetricList](/cn.zh-CN/API参考/云产品时序指标类监控数据/DescribeMetricList.md) API为例，查询参数如下所示。

    ```
    // 使用回调 id: myInstanceId。
                {
                  "Period": 600,
                  "StartTime": "2018-11-20 11:30:00",
                  "EndTime": "2018-11-21 11:30:00",
                  "Metric": "cpu_idle",
                  "Project": "acs_ecs_dashboard",
                  "Dimensions": "{instanceId:':myInstanceId'}"
                }
    ```

10. 单击**预览数据源返回结果**，查看数据返回结果。


