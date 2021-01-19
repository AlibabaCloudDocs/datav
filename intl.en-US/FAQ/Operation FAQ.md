# Operation FAQ

This topic describes DataV operations.

## Where can I watch DataV tutorial videos?

You can visit the following links to watch the tutorial videos:

-   [Data operations](http://etaop4p.gensee.com/webcast/site/vod/play-c3c757a445a44dcfa776c60e13607359?spm=a2c4g.11186623.2.5.7Gt0W3)
-   [DataV design and operations](http://etaop4p.gensee.com/webcast/site/vod/play-a5c38710ca184de3b84e8225537a6cd1?spm=a2c4g.11186623.2.6.7Gt0W3)

## How can I draw map borders?

You can obtain the corresponding GeoJSON data and paste it to the **Geographical Boundaries** area of the **Choropleth Layer** child widget in the **Basic Flat Map**. You can customize the border style in the **Mapping** field based on the codes of different areas.

## How can I configure a data source for a carousel table?

You can input data in the data panel of a carousel table widget and run SQL statements to query the data by using the table as a 2D table. The aliases of the fields are used as table headers.

```
select field1 as "Column 1", filed2 as "Column 2", field3 as "Column 3" from table
```

## How can I configure a data source for a flying routes layer?

If you are using an SQL data source, you must obtain data of the from and to fields, and separate the longitude and latitude in each field with a comma \(,\). This process is slightly different from the process for using static data or calling the API.

## How can I configure the widget interaction function?

The widget interaction function is currently being tested. For more information, see [Widget interaction](/intl.en-US/Advanced Skills/Widget interaction.md).

## How can I filter data by passing parameters into a URL?

You can define your variables in SQL by using `:dot-id`, for example, `select car_speed, car_color, car_name from table where car_ID = :dot-id`.

You can also pass these variables into a URL to filter the returned data, for example, `http://datav.aliyun.com/...?spm=xxxxx&dot_id=10102`.

