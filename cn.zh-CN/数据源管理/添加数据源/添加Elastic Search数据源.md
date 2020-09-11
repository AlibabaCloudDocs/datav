---
keyword: 添加Elastic Search数据源
---

# 添加Elastic Search数据源

本文档介绍在DataV中添加并使用Elastic Search数据源的方法。通过Elastic Search和DataV结合使用，可以实现数据分析和搜索结果的大屏展示。

## 操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**Elastic Search**。

4.  填写Elastic Search数据服务项目信息。

    ![添加Elasticsearch数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0586079951/p47872.png)

    **说明：** 为了让DataV服务能够使用Elastic Search数据源，需要让DataV获取阿里云Elastic Search数据服务的访问权限，从而获得关联的RAM角色。

    在**添加数据**对话框中，单击**获取实例列表**，在弹出的对话框中查看服务关联角色的介绍信息。

    ![查看关联角色信息](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/0586079951/p164509.jpg)

    -   **角色名称**：AliyunServiceRoleForDataVDataSourceES
    -   **系统权限策略**：AliyunServiceRolePolicyForDataVDataSourceES
    -   **权限说明**：允许DataV服务使用此角色访问您的Elastic Search产品服务。

        权限说明内容：

        ```
        {
          "Statement": [
            {
              "Effect": "Allow",
              "Action": [
                "elasticsearch:ListInstance",
                "elasticsearch:DescribeInstance"
              ],
              "Resource": "*"
            },
            {
              "Action": "ram:DeleteServiceLinkedRole",
              "Resource": "*",
              "Effect": "Allow",
              "Condition": {
                "StringEquals": {
                  "ram:ServiceName": "datasource-es.datav.aliyuncs.com"
                }
              }
            }
          ],
          "Version": "1"
        }
        ```

        如果您需要删除AliyunServiceRoleForDataVDataSourceES（服务关联角色），请参见[删除服务关联角色](/cn.zh-CN/角色管理/服务关联角色.md)。

        更多关于服务关联角色的信息，请参见[服务关联角色](/cn.zh-CN/角色管理/服务关联角色.md)。

    |参数|说明|
    |--|--|
    |**自定义数据源名称**|数据源的显示名称，可以自由命名。|
    |**Region**|Elastic Search实例的地域（默认选择**华东1区**）。|
    |**实例ID**|用于查询可用的Elastic Search实例ID。单击**获取实例列表**即可获取到Elastic Search的实例列表并进行查询，单击右侧下拉框选择列表中某一实例（或直接输入数据库名称选择已有实例）。 当单击**获取实例列表**时会自动创建角色访问权限，授权允许DataV使用此角色访问Elastic Search。 请参见[查看实例的基本信息](/cn.zh-CN/ES实例/实例管理/查看实例的基本信息.md)获取Elastic Search实例的ID。 |
    |**密码**|所选Elastic Search实例在被创建时设置的密码，不同实例的密码不同。|

    配置成功后，系统会自动进行测试连接。

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用Elastic Search数据源

在使用Elastic Search数据源之前，请先完成[Elastic Search数据源的添加](#section_1v5_irn_o02) 。

![已添加的Elasticsearch数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4606068951/p47894.png)

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4606068951/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**Elastic Search**。

6.  在**选择已有数据源**列表中选择配置完成的Elastic Search数据源。

7.  在**index**输入框中填写查询索引。

8.  在**Query**输入框中填写查询体，查询体为JSON对象。

    ![选择数据源类型](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5606068951/p47902.png)

9.  单击**预览数据源返回结果**，查看数据返回结果。


