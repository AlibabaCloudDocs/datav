---
keyword: 添加日志服务SLS数据源
---

# 添加日志服务SLS数据源

本文档介绍在DataV中添加日志服务SLS数据源的方法，以及相关参数配置说明。日志服务（Log Service，简称SLS）是针对实时数据的一站式服务。

已准备好待添加的日志服务SLS数据源。

## 添加日志服务SLS数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**简单日志服务SLS**。

4.  填写**简单日志服务SLS**相关信息。

    ![添加SLS数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/1505964951/p34422.png)

    |参数|说明|
    |--|--|
    |**自定义数据源名称**|数据源的显示名称，您可以自由命名。|
    |**AppKey**|拥有目标SLS访问权限的账号的AccessKey ID。|
    |**AppSecret**|拥有目标SLS访问权限的账号的AccessKey Secret。|
    |**EndPoint**|填写SLS服务的EndPoint。请参见[日志服务入口文档](/cn.zh-CN/开发指南/API 参考/服务入口.md)，根据您SLS服务的网络类型和所在区域进行填写。 例如VPC网络下，上海区域的**EndPoint**填写为**https://cn-shanghai-intranet.log.aliyuncs.com**。 |

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用日志服务SLS数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**简单日志服务SLS**。

6.  在**选择已有数据源**列表中选择配置完成的日志服务数据源。

7.  在下方**查询**编辑框中输入查询参数 。

    支持以JSON对象为查询参数进行查询。 可填写的查询参数为：

    ```
    {
    "projectName": "test",
    "logStoreName": "access-log",
    "topic": "test",
    "from": 1509897600,
    "to": 1509984000,
    "query": "" ,
    "line": 100,
    "offset": 0
    }
    ```

    **说明：** 其中query参数的查询语法请参见[查询语法](/cn.zh-CN/查询与分析/查询语法与功能/查询语法.md)。

8.  单击**预览数据源返回结果**，查看数据返回结果。


