# Map data format

This topic describes the GCJ-02 coordinate system and the GeoJSON data format used by DataV map widgets. You can obtain the GCJ-02 coordinate of a location on the map.

## GCJ-02 coordinate system

DataV map widgets use the GCJ-02 coordinate system. It is developed by the Chinese National Bureau of Surveying and Mapping. GCJ-02 uses an encryption algorithm to encrypt the latitude and longitude of a location by adding random offsets to the latitude and longitude. All maps published in mainland China, including electronic maps, must use GCJ-02 for initial encryption of geographical location data.

-   [JavaScript: conversion of the coordinate system](https://github.com/wandergis/coordtransform-cli?spm=a2c4g.11186623.2.5.whUmyN)
-   [JavaScript: conversion of the GeoJSON data](https://github.com/wandergis/coordtransform-cli?spm=a2c4e.11153940.blogcont554167.11.5aae1ab0TbZ6Z9)

## GeoJSON data format

DataV map widgets use geographic data in the GeoJSON format.

-   GeoJSON is used to present geospatial information based on JavaScript Object Notation \(JSON\).
-   You can use the online GeoJSON editor [geojson.io](http://geojson.io/?spm=a2c4g.11186623.2.7.whUmyN) to view or edit geospatial data.

## Coordinate picker in Google Maps

Use a coordinate picker in Google Maps to convert a location to a precise [GCJ-02](#section_tmg_qf5_q2b) coordinate.

For example, enter **Hangzhou, Zhejiang** on the left side of the page, right-click **West Lake** in the map, and select **What's here?** to obtain the coordinate of West Lake.

![Coordinate picker](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5435964951/p50362.png)

![Obtain the coordinate of West Lake](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/5435964951/p50376.png)

