# Feature introduction

This topic describes the features that you need to know about before you configure a project.

You need to use the following features when you create a project:

-   [Spatial interpolation](#section_94t_hh8_idy).
-   [Isosurface layer widget](#section_9ar_u3a_wt2).
-   [Timeline widget](#section_93c_jci_xc3).

## Spatial interpolation

Spatial interpolation is used to convert scattered measurement data into a continuous statistical surface to assess the distribution patterns of spatial information.

Spatial interpolation allows you to calculate the data of any other locations based on the data from known monitoring stations. Then, you can fill in the colors based on the temperature ranges to generate an isothermal map.

In this example, DataV interpolates the known measurement data of scattered points into a continuous statistical surface to produce an isothermal map.

![Style change of an isothermal map](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8956557851/p47657.png)

## Isosurface layer widget

DataV provides an isosurface layer widget that is used for lightweight analysis. This widget helps you create a raster map based on known vectors. For example, you can use the isosurface layer widget to generate a real-time nationwide air quality map.

![Add an isosurface layer widget](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/4151860161/p9377.png)

## Timeline widget

The timeline widget allows you to view air quality changes over a period of time.

![Add a timeline widget](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5151860161/p9378.png)

You can configure a callback ID in the timeline widget, so it can interact with other widgets. Specifically, the data of other widgets is automatically updated when the time on the timeline is changed. After you add the callback ID to other widgets, DataV automatically triggers a data request whenever the time changes and adds the callback ID and its value to the API parameter lists of these widgets. Example:

-   Original API address: `http://127.0.0.1:8888/aqi`
-   API address after a callback is triggered: `http://127.0.0.1:8888/aqi? date=2017012722`

In the preceding example, the callback ID is `date,2017012722`.

**Note:** You can also use the callback ID in a SQL statement in the format of `:Callback ID`.

-   Initial SQL statement: `select :date as value;`
-   SQL statement after a callback is triggered: `select '2017022722' as value`

