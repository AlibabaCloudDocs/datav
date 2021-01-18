# The Capsule Bar Chart widget

This topic describes the configuration items of the Capsule Bar Chart widget and how to use this widget. You can customize x-axis values as needed, and set data series to display differences between data categories.

## Settings

-   **Global Settings**

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1602972851/p11546.png)

    -   **Font Family**: The font of the displayed text. The default font is **Microsoft YaHei**.
    -   **Bar**
        -   **Inner Padding**: The spacing between the bars. The value range is from 0 to 1.
        -   **Outer Padding**: The spacing between the top bar and the top border, and the spacing between the bottom bar and the bottom border. The value range is from 0 to 1.
        -   **Capsule Padding**: The spacing between the bars and the capsule borders.
        -   **Border Color**: The color of the capsule borders. For information about how to set a color, see [Color picker](/intl.en-US/Widget Guide/Configure item description.md).
        -   **Border Size**: The width of the capsule borders.
        -   **Padding Color**: The color of the bar borders.
    -   **Margin**
        -   **Top**: The spacing between the bars and the top border of the chart.
        -   **Bottom**: The spacing between the bars and the bottom border of the chart.
        -   **Left**: The spacing between the bars and the left border of the chart.
        -   **Right**: The spacing between the bars and the right border of the chart.
    -   **Label**: The labels on the bars. To display the labels, click the **Eye** icon.
        -   **Text Style**
            -   **Font Size**: The font size of the label text.
            -   **Font Color**: The font color of the label text.
            -   **Font Weight**: The font weight of the label text.
        -   **Position**: The position of the labels. The available options are Right, Middle, and Left.
-   **X Axis**: The style of the x-axis. To display the x-axis, click the **Eye** icon.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1602972851/p11554.png)

    -   **Text Style**
        -   **Font Size**: The font size of the text along the x-axis.
        -   **Font Color**: The font color of the text along the x-axis.
        -   **Font Weight**: The font weight of the text along the x-axis.
    -   **Axis Label**: To display the axis labels, click the **Eye** icon.
        -   **Max**: The format of the maximum value along the x-axis.
            -   Maximum Data Value: If you select this option, the maximum value is used.
            -   Automatic Rounding: If you select this option, the system calculates the value according to the maximum value, minimum value, and number of axis labels.
        -   **Quantity**: The number of axis labels.
        -   **Display Format**: The display format of the axis labels. You can customize the display format or select a format as needed. If you select Auto, the default format is displayed.
        -   **Angle**: The angle of the axis labels. The available options are Horizontal, Slant, and Vertical.
    -   **Unit**: The unit of the label text along the x-axis. To display the unit option, click the **Eye** icon.
    -   **Axis Line**: To display the axis line, click the **Eye** icon.
        -   **Color**: The color of the axis line.
    -   **Grid Lines**: To display the grid lines, click the **Eye** icon.
        -   **Color**: The color of the grid lines.
-   **Y Axis**: The style of the y-axis. To display the y-axis, click the **Eye** icon.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1602972851/p11555.png)

    -   **Text Style**
        -   **Font Size**: The font size of the text along the y-axis.
        -   **Font Color**: The font color of the text along the y-axis.
        -   **Font Weight**: The font weight of the text along the y-axis.
    -   **Axis Label**: To display the axis labels, click the **Eye** icon.
        -   **Angle**: The angle of the axis labels. The available options are Horizontal, Slant, and Vertical.
    -   **Axis Line**: To display the axis line, click the **Eye** icon.
        -   **Color**: The color of the axis line.
    -   **Grid Lines**: To display the grid lines, click the **Eye** icon.
        -   **Color**: The color of the grid lines.
-   **Legend**: To display the legend items, click the **Eye** icon.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/1602972851/p11557.png)

    -   **Text Style**
        -   **Font Size**: The font size of the legend text.
        -   **Font Color**: The font color of the legend text.
        -   **Font Weight**: The font weight of the legend text.
    -   **Layout**: The layout of the legend items.
        -   **Margin**
            -   **Horizontal Interval**: The horizontal spacing between two legend items. This parameter is available only if the chart has multiple series of data.
            -   **Vertical Interval**: The spacing between the legend items and the top border of the chart, and the spacing between the legend items and the bottom border of the chart.
        -   **Position**: Optional. The position of the legend items.
-   **Series**: To add or delete a series, click **+** or click the **Trash** icon.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2602972851/p11558.png)

    -   **Series Name**: The name of a series. You can set a name for the series as needed. If the series does not have a name, the value of s is automatically displayed as the series name. If the series has a name, make sure that the data is displayed in the correct order. For more information about how to configure a data series, see [Frequently asked questions \(User self-check process\)](/intl.en-US/FAQ/Frequently asked questions (User self-check process).md).
    -   **Color**: The fill color type of a series. The available options are Solid Fill and Gradient Fill.
-   **Animation**: The animation of the bars. To display the animation option, click the **Eye** icon.

    ![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2602972851/p21378.png)

    -   **Original Duration**: The period of time needed for the first time the widget renders the animation. The unit is milliseconds.
    -   **Easing**: The animation easing. You can select an easing effect as needed.
    -   **Animations of All Series In Sequence**: If you select this check box, the animations of all bars in the chart are displayed in sequence. If you clear this check box, the animations of all bars in the chart are displayed at the same time.
    -   **Duration for Data Update**: The period of time needed for the widget to render the animation after data is updated. The unit is milliseconds.
    -   **Update from Latest Status**: If you select this check box, the animation begins from the bar where the data is updated. If you clear this check box, the animation begins from the starting point of the y-axis.

## Data

![](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/2602972851/p11559.png)

The JSON example in the preceding figure is as follows:

```
[
  {
    "x": "Inner Mongolia",
    "y": "400",
    "s": "1"
  },
  {
    "x": "Inner Mongolia",
    "y": "180",
    "s": "2"
  },
  {
    "x": "Zhejiang",
    "y": "200",
    "s": "1"
  },
  {
    "x": "Zhejiang",
    "y": "100",
    "s": "2"
  },
  {
    "x": "Liaoning",
    "y": "25",
    "s": "1"
  },
  {
    "x": "Liaoning",
    "y": "125",
    "s": "2"
  },
  {
    "x": "Jilin",
    "y": "190",
    "s": "1"
  },
  {
    "x": "Jilin",
    "y": "110",
    "s": "2"
  },
  {
    "x": "Heilongjiang",
    "y": "90",
    "s": "1"
  },
  {
    "x": "Heilongjiang",
    "y": "60",
    "s": "2"
  },
  {
    "x": "Anhui",
    "y": "240",
    "s": "1"
  },
  {
    "x": "Anhui",
    "y": "170",
    "s": "2"
  }
]
```

-   x: The category text of each bar.
-   y: The actual data value of each bar.
-   s: Optional. The series data.

## Interaction

This widget is not connected to any events yet.

