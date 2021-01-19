# Chrome升级到80版本后可能产生的影响及解决方案

Chrome（谷歌浏览器）升级到80版本后，可能会导致DataV组件的API数据无法正常返回和展示。本文介绍此类问题的产生背景及解决方案。

## 背景

谷歌在2020年2月4号发布的Chrome80版本（[schedule](https://www.chromestatus.com/features/schedule)）会逐渐屏蔽第三方Cookie，即默认为所有Cookie加上`SameSite=Lax`属性（[Cookies default to SameSite=Lax](https://www.chromestatus.com/feature/5088147346030592)），并且拒绝为不安全的Cookie设置`SameSite=None`属性（[Reject insecure SameSite=None cookies](https://www.chromestatus.com/feature/5633521622188032)），这样是为了从源头屏蔽跨站请求伪造CSRF（Cross Site Request Forgery）漏洞。

## 如何提前判断升级Chrome80版本是否对可视化应用有影响？

1.  在Chrome中打开`chrome://flags/#same-site-by-default-cookies`，将**SameSite by default cookies**设置为**Enabled**。
2.  再打开`chrome://flags/#cookies-without-same-site-must-be-secure`，将**Cookies without SameSite must be secure**设置为**Enabled**。
3.  重启浏览器，打开正在使用的DataV可视化应用，检查所有数据是否正常返回和展示。
    -   如果数据正常返回，则升级Chrome80版本对您的可视化应用没有影响。
    -   如果数据没有正常返回，则升级Chrome80版本会对您的可视化应用产生影响，请谨慎升级。并根据以下场景进行排查和解决。

## 问题场景一：使用API数据源

场景描述：组件的数据源为API类型，且该API请求需要用户登录信息（cookie）才能从第三方网站获取相关的数据。

影响：组件数据无法正常返回和展示。

解决方案：判断API使用的传输协议类型为HTTPS还是HTTP。

-   使用HTTPS协议

    检查响应头中的`Set-Cookie`配置是否包含了`SameSite=None`和`Secure`。如果没有包含，请在响应头中的`Set-Cookie`配置中添加`SameSite=None`和`Secure`。

-   使用HTTP协议
    1.  在Chrome中打开`chrome://flags/#same-site-by-default-cookies`，将**SameSite by default cookies**设置为**Disabled**。
    2.  再打开`chrome://flags/#cookies-without-same-site-must-be-secure`，将**Cookies without SameSite must be secure**设置为**Disabled**。
    3.  重启浏览器。

