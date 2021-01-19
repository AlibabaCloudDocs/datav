# index.js规范

index.js文件是组件的主入口文件。本文档提供了一个示例供您参考，并介绍了index.js文件中的常用函数。

查看模板案例[example组件](http://docs-aliyun.cn-hangzhou.oss.aliyun-inc.com/assets/attach/64800/cn_zh/1553828656284/index.js)。

## 常用函数

|函数|说明|
|--|--|
|`render(array: data)`|默认渲染方法。当组件被初始化后，组件渲染逻辑被调用，入参为数据。

需要能够支持重渲染，即保证同样的数据输入，能够渲染出同样的效果。 |
|`updateOptions(object: config)`|更新组件配置，接收的入参`config`是修改后的新配置。|
|`emit(string: event_name, object: value)`|抛出事件，抛出的`value`需要为object类型。|
|`resize(int: width, int: height)`|缩放，当组件被拖拽、缩放时被调用。|
|`clear()`|清理，当组件被清理时被调用。|
|`destroy()`|销毁，当组件被销毁时调用。|
|`require(*)`|支持 js、html。|
|`getThemableConfig(themeConfig)`|设置主题配置，当配置组件的主题时被调用，返回主题与组件配置的映射关系，同时使⽤`themeConfig`中提供的主题配置项进行主题配置。调用前需要在组件配置中，使用`supportTheme`字段声明组件是否支持主题配置，设置为`true`表示支持，更多详情请参见[getThemableConfig\(themeConfig\)函数说明](#section_ck7_stj_ehj)。|

## getThemableConfig\(themeConfig\)函数说明

`getThemableConfig(themeConfig)`函数的作用是使用`themeConfig`中的配置，配置组件主题，并返回主题与组件配置的映射关系。

`getThemableConfig(themeConfig)`函数调用示例如下。

```
getThemableConfig: function(themeConfig) {
 if (!themeConfig) return null;
 const themeMap = {
 color: themeConfig.textColor,
 bgColor: palette[0]
 }
 return themeMap;
}
```

`themeConfig`示例如下。

```
{
  "bgColor": "#202020",        // 背景颜色
  "textColor": "#FFFFFF",     // 文本颜色
  "axisColor": "#FFFFFF",    // 坐标轴颜色
  "assistColor": "#FFFFFF", // 辅助信息颜色
  "palette": [             // 系列颜色
    "#85A5FF",
    "#597EF7",
    "#2F54EB",
    "#1D39C4",
    "#10239E",
    "#061178",
    "#030852"
  ]
}
```

