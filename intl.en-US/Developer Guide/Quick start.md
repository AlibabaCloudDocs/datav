# Quick start

This topic describes how to use DataV to develop widgets.

## Before you begin

1.  Download and install [NodeJS](https://nodejs.org). We recommend that you install a version between 8.0.0 \(included\) and 10.12.0.

    **Note:** You can use Node Version Manager \(NVM\) to manage multiple NodeJS versions. With NVM, you can install another version of NodeJS without the need to uninstall the existing version. For information about how to install NVM, visit [GitHub: Node Version Manager](https://github.com/creationix/nvm).

2.  After you install NVM, run the `node -v` and `npm -v` commands in the macOS terminal or Windows command prompt to view the NodeJS and npm versions.

## Install the development tool

1.  Run the following command in the macOS terminal or Windows command prompt to install the tool:

    ```
    npm install --registry=https://registry.npm.taobao.org datav-cli -g
    ```

2.  After the installation is successful, run the `datav --version` command to view the version of the tool.

## Set the language

The default language of the DataV development tool is `English`. You can run the `datav locale` command to change the default language.

The command returns the following message:

```
? What is your language? (Use arrow keys)
> English
  Chinese
  Japanese
```

Press the **↑** and **↓** arrow keys to select a language and press **Enter**.

If you want the language to change based on the region of your Alibaba Cloud account, log on to the DataV developer console and run the `datav locale-clear | datav lc` command to clear the language setting. You can use the `datav locale` command to set a default language again.

## Log on to the DataV developer console

Run the `datav login` command in the macOS terminal or Windows command prompt to log on to the DataV developer console. During the command execution, enter the following information.

|Item|Description|
|----|-----------|
|`UID`|Enter your username that is displayed in the upper-right corner of the DataV console. If you are a RAM user, enter the username of your Alibaba Cloud account.|
|`Developer Token`|Enter the developer token that is obtained from the **Widgets** tab in the DataV console.|
|`Do you want to set an alias?`|Press Y or N.|
|`Alias`|Enter an alias.|

If the system prompts that **the configuration is successful**, you have logged on to the DataV developer console.

**Note:** If you only want to create or preview widgets, you do not have to log on to the DataV developer console. You only need to log on if you want to publish widgets.

## Generate a widget package

Run the `datav init` command in the macOS terminal or Windows command prompt to generate a widget package. During the command execution, you need to enter the following information.

|Item|Description|
|----|-----------|
|`? Widget Name`|The name you want to use for the widget. It can only contain letters, digits, and hyphens \(-\).|
|`? Widget Display Name`|The name you want to display for the widget in the widget list of a project.|
|`? Widget Description`|Enter a description for the widget.|
|`? Select Template from Template List` `Basic text`

 `Basic text (international edition)`

|The template you want to use for the widget. Valid values: `Basic text` \| `Basic text (international edition)`. Press the **↑** and **↓** arrow keys to select a template and press **Enter**. |

If the system prompts that **the widget has been created**, the widget package is generated.

![Widget created](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9618557851/p33821.png)

## Preview a widget

You can run the following commands in the macOS terminal or Windows command prompt to preview a widget:

```
cd <Widget name>
datav run
```

If the system prompts that **the service has started**, Google Chrome is opened to display the preview of the widget.

![Service started](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9618557851/p33822.png)

**Note:**

-   If Google Chrome does not open automatically, you may not have installed it. You need to install Google Chrome and manually access localhost:1111/ to preview the widget.
-   If a message is displayed, indicating that you have already activated a service on this port, port 1111 is occupied by another application. You can run the `datav run -p 1112` command to change the preview service port to 1112.
-   If you access localhost:1111/ but the preview of the widget is not displayed, check whether you have mapped localhost to 127.0.0.1 in the hosts file.

The following figure shows the preview of a widget.

![Widget preview](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9618557851/p33823.png)

The preview page consists of a canvas, bottom toolbar, and right-side panel.

-   Canvas
    -   The canvas displays the widget and all changes to it in real time.
    -   Widget settings on the right-side panel are shown on the canvas.
    -   You can drag and drop the borders to resize the widget.
-   Bottom toolbar

    You can change the language of the widget.

-   Right-side panel

    The right-side panel includes four tabs: **Settings**, **Data**, **Interaction**, and **Publish**.

    |Tab|Description|
    |---|-----------|
    |**Settings**|This tab contains the style settings of the widget. If you change the settings, the changes take effect immediately on the canvas. For example, if you adjust the **font size** slider, the font size of the text in the widget changes accordingly. Click **Save** to save the current settings as default for a widget.![Settings tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9618557851/p33824.png) |
    |**Data**|This tab provides the API data of the widget. The data changes take effect on the widget immediately. Click **Save** to save the current data as default for the widget.![Data tab](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9618557851/p33825.png) |
    |**Interaction**|This tab provides interactions between the widget and other widgets.![Interaction panel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9618557851/p33826.png) |
    |**Publish**|This tab provides the type, icon, and publish version of the widget. Click **Publish** in the upper-right corner to publish the widget.![Publish panel](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/0718557851/p33827.png) |


## Publish a widget

You can use one of the following methods to publish a widget:

-   Method 1 \(recommended\)

    Go to the directory of the widget and run the datav publish command. The widget is compressed and published to a server in the same region as your Alibaba Cloud account.

-   Method 2

    Go to the directory of the widget and run the datav package command. A tar.gz package named in the format of `Component-Version` is generated in the parent directory. Upload the package to datav.aliyun.com to publish the widget.

-   Method 3

    On the widget preview page, click **Publish**.


