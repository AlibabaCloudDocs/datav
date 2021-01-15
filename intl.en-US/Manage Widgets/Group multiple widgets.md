---
keyword: [group widgets, apply 3D transformation]
---

# Group multiple widgets

You can group multiple widgets to adjust their size, position, opacity, and 3D transformation as a whole and implement widget carousel in the group.

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  On the **Projects** page, click the project that you create.

    If you have not created a project, see [Create a project by using a template](/intl.en-US/Manage Projects/Create a project.md).

3.  In the **Layer** pane or on the canvas, select multiple widgets that you want to group.

    **Note:** If you have not added widgets to the canvas, see [Add a widget](/intl.en-US/Manage Widgets/Add a widget.md).

    Press and hold the **Ctrl** key in Windows or the **command** key in macOS and click the widgets to select them. You can also drag the pointer on the canvas to select multiple widgets.

4.  Right-click the widgets and select **Group**, or click the ![Group icon](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7647557851/p9224.png) icon in the lower part of the **Layer** pane.

5.  After you group the widgets, you can adjust their size, position and opacity as a whole.

6.  On the Settings tab of the widget group, turn on **Apply 3D Transformation** and configure **3D Transformation** settings in **Perspective Distance** and **Perspective Origin**. This allows you to present the widgets from different perspectives.

    -   **3D Transformation**: Click the ![Horizontal](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3811630161/p95437.jpg) or ![Vertical](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3811630161/p94077.jpg) icon to horizontally or vertically arrange the widgets in the group.

        ![3D Transformation](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/3811630161/p96755.png)

        Click the thumbnail of a widget in the group and configure 3D transformation settings of the widget.

        |Parameter|Description|
        |---------|-----------|
        |**Rotation**|The rotation axis of the widget. Valid values: **X Axis**, **Y Axis**, and **Z Axis**.|
        |**Scale**|The scale values of the widget in the x axis and y axis. Turn on **Scaling Lock** to lock the ratio of the x axis and y axis. When you change the scale value on one axis, the scale value of the other axis changes in the same ratio. If you turn off the switch, changes to one axis do not affect the other.|
        |**Translation**|The distances to move the widget along the x, y, and z axes.|

    -   **Perspective Distance**: the perspective distance of the widget when you view the widget from the z axis.

        **Note:** The perspective distance cannot be smaller than 0. Otherwise, the widget disappears from the canvas. Unit: pixels.

    -   **Perspective Origin**: the vanishing point where you look at the widget from a three-dimension space. You can set the position of the vanishing point in the x and y axes. Valid values: 0 to 100%.
7.  After you complete configurations in **Apply 3D Transformation**, configure [carousel of widgets in the group]().

    You can right-click the widget group and select **Ungroup** to ungroup the widgets. After you ungroup the widgets, you can move them individually again.

    **Note:** After you select multiple widgets on the canvas or in the Layer pane, you can also press **Ctrl+G** to group them and **Ctrl+Shift+G** to ungroup them.


