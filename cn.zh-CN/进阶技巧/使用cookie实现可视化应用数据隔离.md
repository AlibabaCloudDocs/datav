# 使用cookie实现可视化应用数据隔离

当您在DataV中使用API数据源时，可以使用cookie，实现不同的用户登录系统时，只能看到自己的数据，保证可视化应用数据的安全性。

## 原理说明

1.  当您将DataV页面通过iframe的方式嵌入自己的业务系统时，在用户登录的情况下，业务系统会在cookie中会带有Session\_Id之类的用户登录信息。
2.  当使用API数据源，并且选中了**需要cookie（不选择代理并且需要获取cookie时使用）**时，DataV会在HTTP请求中带上该页面的cookie信息，其中包含用户的登录信息。

    ![勾选cookie](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9409788951/p129287.png)

    **说明：** 当选中需要cookie时，不能同时选中服务器代理请求。如果API数据源存在跨域受限问题 ，详情请参见[跨域数据配置](/cn.zh-CN/进阶技巧/跨域数据配置.md)中的**跨域资源共享**。

3.  此时服务端会对请求进行用户验证，通过后返回该用户的数据，从而实现不同用户登录只看到自己数据，而看不到其他用户的数据。

    ![原理说明](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/zh-CN/9409788951/p75822.png)


