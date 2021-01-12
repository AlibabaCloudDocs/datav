# Bubble chart

You can add one or more bubble charts to a project to display data in different time periods.

## Style

-   **Global Settings**
    -   **Font Family**: To set the font of the displayed text, click the drop-down arrow and select the target font. The default font is **Microsoft YaHei**.
    -   **Margin**

        -   **Top**: To adjust the spacing between the chart and the top border, enter a value, or click **+** or **-**.
        -   **Bottom**: To adjust the spacing between the chart and the bottom border, enter a value, or click **+** or **-**.
        -   **Left**: To adjust the spacing between the chart and the left border, enter a value, or click **+** or **-**.
        -   **Right**: To adjust the spacing between the chart and the right border, enter a value, or click **+** or **-**.
        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333311803_en-US.png)

-   **X Axis**
    -   **Text Style**
        -   **Font Size**: To change the font size of the text along the x-axis, enter a value, or click **+** or **-**.
        -   **Font Color**: To change the font color of the text along the x-axis, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        -   **Font Weight**: To set the font weight of the text along the x-axis, click the drop-down arrow and select the target font weight.
    -   **Axis Label**: To display the axis labels, click the **Eye** icon.
        -   **Data Type**: To set the data type of the axis labels, click the drop-down arrow and select the target type.
            -   Numeric
            -   Category
            -   Time
        -   **Data Format**: To set the data format, click the drop-down arrow and select the target format.

            **Note:** This option is displayed only when **Data Type** is set to Time. The data format must match the time format.

        -   **Display Format**: To set the display format of the data, click the drop-down arrow and select the target format.

            **Note:** The data along the x-axis can be displayed in time or numeric format. If you select the time format, keep the decimal digits as needed. If you select the numeric format, set the year, month, day, hour, and second as needed.

        -   **Max**: You can customize the maximum time or number value to be displayed. The maximum value can be displayed in time or numeric format.
        -   **Min**: You can customize the minimum time or number value to be displayed. The minimum value can be displayed in time or numeric format.

            **Note:** The default minimum and maximum values are auto. If auto is displayed, the minimum and maximum values of the axis labels are automatically calculated and displayed.

        -   **Unit**: You can customize the unit of data along the x-axis as needed. If the spacing between the chart and the right border is too small, the unit will not be displayed. The unit can be in time or numeric format.
        -   **Quantity**: To change the number of x-axis labels, enter a value, or click **+** or **-**.
        -   **Angle**: To set the angle of the x-axis labels, click the drop-down arrow and select the target angle.
            -   Horizontal
            -   Slant
            -   Vertical
    -   **Axis Line**: To display the axis line, click the **Eye** icon.
        -   **Color**: To change the color of the x-axis line, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
    -   **Grid Lines**: To display the grid lines, click the **Eye** icon.

        -   **Color**: To change the color of the grid lines, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333311804_en-US.png)

-   **Y Axis**
    -   **Text Style**
        -   **Font Size**: To change the font size of the text along the y-axis, enter a value, or click **+** or **-**.
        -   **Font Color**: To change the font color of the text along the y-axis, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        -   **Font Weight**: To set the font weight of the text along the y-axis, click the drop-down arrow and select the target font weight.
    -   **Axis Label**: To display the axis labels, click the **Eye** icon.
        -   **Min**: To set the format of the minimum value along the y-axis, click the drop-down arrow and select the target format.
            -   Minimum data value
            -   Automatic rounding
        -   **Max**: To set the format of the maximum value along the y-axis, click the drop-down arrow and select the target format.
            -   Maximum data value
            -   Automatic rounding
        -   **Quantity**: To change the number of y-axis labels, enter a value, or click **+** or **-**.
        -   **Display Format**: To set the display format of the axis labels, click the drop-down arrow and select the target format.
        -   **Angle**: To set the angle of the y-axis labels, click the drop-down arrow and select the target angle.
            -   Horizontal
            -   Slant
            -   Vertical
    -   **Axis Unit**: To display the axis unit, click the **Eye** icon.
        -   **Unit**: You can customize the unit of data along the y-axis as needed.
    -   **Axis Line**: To display the axis line, click the **Eye** icon.
        -   **Color**: To change the color of the y-axis line, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
    -   **Grid Lines**

        -   **Color**: To change the color of the grid lines, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333311805_en-US.png)

-   **Bubbles**

    -   **Map by Y-Axis**
        -   If you select this option, the minimum and maximum radii of the bubbles are mapped according the minimum and maximum values along the y-axis.
        -   If you clear this option, you need to customize the value range of the bubbles to control the bubble radii
            -   **Min**: You can set the minimum value for a bubble, and the system will compare the value you set with the r value in the data pane. If the r value is smaller than the set value, the bubble is not displayed. If the r value is greater than the set value, the bubble is displayed. The radius of the bubble = \(r value – the minimum value\)/the maximum value × r value.
            -   **Max**: You can set the maximum value for a bubble, and the system will compare the value you set with the r value in the data pane. If the r value is smaller than the set value, the bubble is not displayed. If the r value is greater than the set value, the bubble is displayed. The radius of the bubble = \(r value – the minimum value\)/the maximum value × r value.
    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333411815_en-US.png)

-   **Legend**
    -   **Text Style**
        -   **Font Size**: To change the font size of the legend text, enter a value, or click **+** or **-**.
        -   **Font Color**: To change the font color of the legend text, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        -   **Font Weight**: To set the font weight of the legend text, click the drop-down arrow and select the target font weight.
    -   **Layout**

        -   **Margin**
            -   **Horizontal Interval**: To adjust spacing 1 \(spacing between the legend item or legend items and the right border of the chart\) and spacing 2 \(spacing between the legend item or legend items and the left border of the chart\), enter a value, or click **+** or **-**. The setting takes effect only when two or more series are set.
            -   **Vertical Interval**: To adjust spacing 1 \(spacing between the legend item or legend items and the top border of the chart\) and spacing 2 \(spacing between the legend item or legend items and the bottom border of the chart\), enter a value, or click **+** or **-**.
        -   **Position**: To set the position of one or more legend items, click the drop-down arrow and select the target position.
            -   Top center
            -   Top left
            -   Top right
            -   Bottom center
            -   Bottom left
            -   Bottom right
        ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333411820_en-US.png)

-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.

    -   **Series Name**: You can set a name for the series as needed.
    -   **Color**: To set the fill color type of the center point of the bubbles, click the drop-down arrow and select the target type. To change the fill color, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        -   Solid fill
        -   Gradient fill: You can select two colors as the gradient colors.
        -   To change the gradient angle, enter a value or drag the slider. The value range is from 0 to 360.
    -   **Outline Color**: To change the outline color of the bubbles, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333411828_en-US.png)

-   **Animation**: To display the animation option, click the **Eye** icon.

    -   **Original Duration**: To change the duration to which the widget renders the animation for the first time, enter a value, or click **+** or **-**. The unit is milliseconds.
    -   **Easing**: To set animation easing, click the drop-down arrow and select the target effect.
    -   **Duration for Data Update**: To change the animation duration when data changes, enter a value, or click **+** or **-**. The unit is milliseconds.
    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333421469_en-US.png)


## Data

-   x: label along the x-axis
-   y: data along the y-axis
-   r: radius of the bubbles in the bubble chart \(This field takes effect when the data is not mapped by the y-axis.\)
-   s: \(optional\) series, which indicates the data category

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/21295/155840333411829_en-US.png)

## Interaction

This widget is not connected to any events yet.

