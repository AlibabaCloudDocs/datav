# FAQ about map tiles

This topic provides answers to commonly asked questions about map tiles.

## How do I call a map tile in a local area network \(LAN\)?

You can cache an online tile on your web server and name it in a standard format, for example, \[Zoom level\]/\[Row number\]/\[Column number\].png. Then, you can call the tile by using a URL, for example, http://ip:port/path\_to\_your\_tile\_directory/\{z\}/\{x\}/\{y\}.png.

## What are the coordinate systems and service standards for map tiles in DataV?

Coordinate systems: DataV supports the WGS 84 and GCJ-02 coordinate systems. Map tiles are projected by using Web Mercator \(SRID 3857\).

Service standards:

-   Google Maps uses the Tile Map Service \(TMS\) standard.
-   AMAP accesses a map tile by using a URL, for example, `http://webrd03.is.autonavi.com/appmaptile? lang=en_us&size=1&scale=1&style=8&x={x}&y={y}&z={z}`. In the example URL, \{\} indicates a placeholder. You must replace a placeholder with the row number or column number of a map tile.

## How do I use data in the WGS 84 format in AMAP?

AMAP supports the GC-J02 coordinate system. You must convert the data format from WGS 84 to GC-J02. For more information, see [Converting the coordinate system](http://github.com/wandergis/coordtransform).

## How do I cache map tiles?

DataV does not provide services or tools to cache map tiles. You can use a map downloader or write code to cache map tiles.

