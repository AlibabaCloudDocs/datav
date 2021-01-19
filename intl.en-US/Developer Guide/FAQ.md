# FAQ

## How and where can I find widget templates?

In the command line, install datav-cli and use the datav init command to download and install widget templates. For more information, see [Install DataV development tools](/intl.en-US/Developer Guide/Quick start.md).

## Why did my widgets fail to publish?

Widgets may fail to publish due to one of the following reasons:

-   Widgets are not authorized to be published.

    Widgets are not authroized to be published because they are not preceded by the widget package name \(the name field in package.json\). The correct widget name format is @namespace/xxx \(with @namespace being the widget package name\).

-   Widgets are still under review or their review failed.

    If your widget has not passed review after much time, contact Alibaba Cloud technical support.


## How do I write a data event so that, when I trigger the event, other widgets listen?

To write a data event so that, when the event is triggered, other widgets can listen, the procedure is as follows:

1.  In the package.json file, under the datav field, define the event name events in the correct format.
2.  In the index.js file, use the `this.emit(event_name,value)` method to send the event name and parameters.

    **Note:** The value parameter must be an object, rather than a basic type value.

3.  In the Data pane, other widgets must use the format of a colon plus a parameter name \(: xxx\) to call the corresponding data of this parameter.

## How can I write an ECharts widget?

For information about how to write an ECharts widget, see [ECharts widget encapsulation guide](/intl.en-US/Developer Guide/Guide to ECharts widget encapsulation.md).

## Why did I my local picture fail to upload?

If you need to use a local static file as a resource path, you need to create a resources file in the root directory where your widget is located, put resources, such as pictures into the directory, and call the path, such as, ./resources/xxx.png.

## Why am I unable to find the packages of my program?

If you continue to receive an error that indicates that packages were not found after you run the npm install command, remove the datav-cli tool and reinstall it.

## Why have my widgets not passed review yet?

If your widgets have not passed review after much time, contact Alibaba Cloud technical support.

## Why do I suddenly not have permission to publish widgets?

If you are using the DataV Developer Edition and have not uploaded any widgets or tutorials for two months, your permission will be remoked. You can re-apply for the permission or contact Alibaba Cloud technical support.

## Why did my widgets work properly locally, but an error occured when they were used in DataV?

This may have been caused by one of the following reasons:

-   Setting data to null is not supported by the widget.
-   jQuery was modified in the widget code. More specifically, jquery have been reassigned.
-   The window object was modifed in the widget code.
-   When several widgets were added, modified configurations did not take effect, check if your widget codes have a CSS file.
-   The DOM model was modified outside of the container.
-   When using jQuery to access the DOM model, the `$(‘.classname’)` operation is not allowed. Rather, you must search for DOM nodes in the container.

## Why am I unable to find my widgets on the edit page?

To view your widgets, go to **My Widgets** on the top navigation bar.

## Why are buyers unable to find my widgets after they bought them?

Buyers probably cannot find your widgets because your widget classification may not be set properly. For more information, see [type fields](/intl.en-US/Developer Guide/Document structure/Specifications of a package.json file.md).

