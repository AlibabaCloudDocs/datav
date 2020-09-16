---
keyword: 添加阿里云API网关数据源
---

# 添加阿里云API网关数据源

本文档介绍在DataV中添加阿里云API网关数据源的方法，以及相关参数配置说明。阿里云API网关即API托管服务，涵盖API发布、管理、运维、售卖的全生命周期管理。

已准备好待添加的阿里云API网关数据源。

## 添加阿里云API网关数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的数据**页面中，单击**添加数据**。

3.  从**类型**列表中，选择**阿里云API网关**。

4.  填写API网关信息。

    ![添加API网管数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4030567951/p32305.png)

    |参数|说明|
    |--|--|
    |**名称**|数据源的显示名称，您可以自由命名。|
    |**域名**|API网关的调用域名。您可以进入[API网关控制台](https://apigateway.console.aliyun.com/)查看。|
    |**AppKey**|API网关接口的调用AppKey。请参见[获取API定义](https://help.aliyun.com/document_detail/42740.html)，获取相关接口的AppKey。|
    |**AppSecret**|API 网关接口的调用AppSecret。请参见[获取API定义](https://help.aliyun.com/document_detail/42740.html)，获取相关接口的AppSecret 。|

5.  信息填写完成后，单击**确定**，完成数据源的添加。

    新添加的数据源会自动显示在数据源列表中。


## 使用阿里云API网关数据源操作步骤

1.  登录[DataV控制台](https://datav.aliyun.com/)。

2.  在**我的可视化**页面中，将鼠标移动至需要编辑的可视化应用上，单击**编辑**。

3.  在画布编辑页面，单击画布中的某一组件。

    如果画布中还没有组件，请先添加组件，详情请参见[添加组件](/cn.zh-CN/组件管理/添加组件.md)。

4.  在画布右侧的组件配置面板中，单击**数据** \> **配置数据源**。

    ![配置数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/2637420061/p65745.png)

5.  在**设置数据源**页面中，选择**数据源类型**为**阿里云API网关**。

6.  在**选择已有数据源**列表中选择配置完成的**阿里云API网关**数据源。

7.  在下方**HTTP Method**列表中选择一种请求方式，可选择**GET**、**POST**、**PATCH**、**PUT**、**DELETE**、**HEAD**和**OPTIONS**这七种请求方式，具体这几种请求方式的解释说明，请参见[常用的请求方式](https://developer.aliyun.com/article/53549?spm=a2c6h.14164896.0.0.5d4a5100YThAJM)。

8.  在下方**请求URL**编辑框中，填写需要请求的接口URL路径。

9.  根据您在**HTTP Method**内选择的不同请求方式，可在下方**Header（请求头）**和**Body（请求体）**中填写相应的请求函数值。

10. 单击**预览数据源返回结果**，查看数据返回结果。


## 使用示例

1.  获取阿里云API网关接口。

    阿里云API网关是面向用户的产品，您可以通过以下两种方式获取API网关接口。

    -   将您的API托管在API网关，通过DataV调用API网关来调用您的接口，接入方式请参见[阿里云API网关官方帮助文档](https://help.aliyun.com/product/29462.html)。
    -   在阿里云的[云市场](https://market.aliyun.com/)中，购买相关的API服务，通过DataV调用相关的结果，获取API服务的返回结果，例如IP定位等服务。
2.  在DataV中配置API数据源，并将结果展示在可视化应用中。

    本文以云市场的API服务为例，配置方法如下。

    1.  购买云市场API服务。

        ![购买云市场API服务](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/4030567951/p32312.png)

        购买完成后进入**API网关管理控制台**页面，可以看到该接口的**AppKey**、**AppSecret**信息，将这些信息填写到DataV的数据源处。

        ![APPKey和APPSecret信息](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5030567951/p32313.png)

    2.  获取API服务的域名、路径和参数，在API说明页面查询API定义。

        以其中的**IP定位**接口为例，可以查看到这个接口的相关信息。

        ![IP定位接口信息](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5030567951/p32314.png)

        -   **域名**：iploc.market.alicloudapi.com
        -   **请求URL**：/v3/ip
        -   **请求参数**：ip
    3.  配置数据源。

        ![配置阿里云API数据源](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5030567951/p32315.png)

    4.  填写查询参数。

        ![填写查询参数](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5030567951/p32316.png)

    5.  查看查询结果。

        ![查看查询结果](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5030567951/p32317.png)

    6.  使用回调参数。

        ![使用回调参数](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/5030567951/p32318.png)


