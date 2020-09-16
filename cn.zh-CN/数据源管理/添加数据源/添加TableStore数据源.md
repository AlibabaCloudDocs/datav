---
keyword: 添加TableStore数据源
---

# 添加TableStore数据源

本文档介绍在DataV中添加TableStore数据源的方法，以及相关参数配置说明。

已准备好待添加的TableStore数据源。

## 添加TableStore数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**TableStore**。

4.  填写TableStore相关信息。

    ![添加Table Store数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32624.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，您可以自由命名。|
    |**AK ID**|拥有TableStore访问权限的账号的AccessKey ID。|
    |**AK Secret**|拥有TableStore访问权限的账号的AccessKey Secret。|
    |**外网**|Table tore的[服务地址](/cn.zh-CN/功能介绍/基础概念/服务地址.md)，需要根据访问的TableStore实例来填写。|

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用TableStore数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**TableStore**。

6.  在**选择已有数据源**列表中选择配置完成的TableStore数据源。

7.  在**选择操作**列表中选择需要的操作。

    系统支持以下两种操作：

    -   `getRow`：对应TableStore的GetRow API，详情请参见[GetRow API 参考](/cn.zh-CN/API 参考/API 概览/GetRow.md)。
    -   `getRange`：对应TableStore的GetRange API，详情请参见[GetRange API 参考](/cn.zh-CN/API 参考/API 概览/GetRange.md)。
8.  在**选择操作**编辑框中输入查询语句。

    -   查询参数必须为JSON对象。
    -   选择`getRow`操作时，需要根据指定的主键读取单行数据。

        参数格式如下。

        ```
        {
        "table_name": "test",
        "rows": {
        "id": 2
        },
        "columns": [
        "id",
        "test"
        ]
        }
        ```

        |参数|说明|
        |--|--|
        |table\_name|填写您需要查询的Table名。|
        |rows|填写行的过滤条件，将筛选出符合条件的行返回。如果您需要在rows里面添加column作为查询条件，那么所添加的column必须是建立过索引的。|
        |columns|填写需要返回的列名。|

    -   选择`getRange`操作，可读取指定主键范围内的数据，参数格式如下。

        ```
        {
        "table_name": "test",
        "direction": "FORWARD",
        "columns": [
        "id",
        "test"
        ],
        "range": {
        "limit": 4,
        "start": {
        "id": "InfMin"
        },
        "end": {
        "id": 3
        }
        }
        }
        ```

        |参数|说明|
        |--|--|
        |table\_name|填写您需要查询的Table名。|
        |direction|查询的顺序。|
        |columns|填写需要返回的列名。|
        |limit|读取最多返回的行数。|
        |start|指定读取时的起始列，返回的结果中包含当前起始列，所列出的column必须是已经建立索引的列。|
        |end|指定读取时的结束列，返回的结果中不包含当前结束列，所列出的column必须是已经建立索引的列。|

        **说明：** start和end参数中，可以使用InfMin和InfMax表示最小值和最大值 。

9.  单击**预览数据源返回结果**，查看数据返回结果。


## 调用示例

1.  准备TableStore数据。

    您需要先在[TableStore控制台](https://ots.console.aliyun.com/)[创建实例](t20264.md#)并[存储数据]()。如下图创建了一个名称为**test1948**的实例，里面有3行数据，每行数据有两个列：`id(主键, integer)`和`test(string)`。

    ![Table Store数据](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32810.png)

2.  配置数据源。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32811.png)

3.  查询参数。

    -   使用`getRow`方式查询。

        ![getRow方式查询数据](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32812.png)

        数据响应结果如下。

        ![getRow查询响应结果](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32813.png)

    -   使用`getRange`方式查询。

        ![getRange方式查询数据](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32814.png)

        数据响应结果如下。

        ![getRange查询响应结果](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0281594951/p32815.png)

    **说明：** 在使用getRange方式查询参数的时候，过滤条件start为id：InfMin，end为id：3，最后查出来 id为1和2两行记录。因为getRange并不包含end的行，即不包含id为3的行。


