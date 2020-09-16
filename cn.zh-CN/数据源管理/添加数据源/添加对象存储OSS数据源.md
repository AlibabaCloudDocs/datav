---
keyword: 添加对象存储OSS数据源
---

# 添加对象存储OSS数据源

本文档为您介绍在DataV中添加对象存储OSS数据源的方法，以及相关参数配置说明。使用阿里云对象存储服务（Object Storage Service，简称OSS），您可以通过网络随时存储和调用文本、图片、音频和视频等各种非结构化数据文件。

已准备好待添加的对象存储OSS数据源。

## 添加对象存储OSS数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**对象存储 OSS**。

4.  填写OSS相关信息。

    ![添加OSS数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8005964951/p32329.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，您可以自由命名。|
    |**AK ID**|拥有目标OSS访问权限的账号的AccessKey ID。|
    |**AK Secret**|拥有目标OSS访问权限的账号的AccessKey Secret。|
    |**Region**|目标OSS的Region信息。进入[OSS控制台](https://oss.console.aliyun.com/)，单击您的Bucket名称进行获取。![OSS Region信息](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/8005964951/p32341.png)

上图中的OSS Bucket位于上海区域，所以**Region**填写为**oss-cn-shanghai**。 |

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用对象存储OSS数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**对象存储 OSS**。

6.  在**选择已有数据源**列表中选择配置完成的**对象存储 OSS**数据源。

7.  在下方**文件路径**编辑框中，填写需要的文件路径。

8.  单击**预览数据源返回结果**，查看数据返回结果。

    内容格式要求如下。

    -   文件必须为JSON文本格式。
    -   文件路径格式：oss://bucket/file。例如您的Bucket名为myBucket，文件为test.json，应该填写oss://myBucket/test.json。

