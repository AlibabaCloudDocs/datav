# Manage widget groups

If you use the **Enterprise** edition or a higher edition of DataV, you can develop your own widgets and upload them to a widget group. You can also authorize other users to access your widget groups. This allows you to share widgets with other users.

Custom widgets are supported in the **Enterprise** edition or higher. You must upgrade your DataV instance as required.

## Create a widget group

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  On the left of the **Widgets** page, select **Widget Groups**.

3.  On the **Widget Groups** page, click **Create Widget Group**.

    ![Create Widget Group](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8657411161/p37024.png)

4.  In the **Create Widget Group** dialog box, enter the required information and click **Create**.

    ![Create Widget Group](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7308531061/p37023.png)

    |Parameter|Description|
    |---------|-----------|
    |**Group ID**|The ID of the widget group. The ID must be 1 to 20 characters in length and can only contain letters, digits, periods \(.\), and hyphens \(-\). It must not contain spaces and cannot start with a digit. The required format is **xxx.xxx** or **xxx-xxx**. We recommend that you specify an ID in the format of **Company name.Group name** or **Company name-Group name**. The group ID cannot be modified after you create the widget group. Example: **alibaba-interaction**.|
    |**Display Name**|The display name of the widget group. The display name must be 1 to 20 characters in length and can be modified after you create the widget group.|
    |**Group Cover**|Click the **Group Cover** image box to change the cover image of the group, or drag and drop an image to the **Group Cover** image box. The image size cannot be larger than 200 KB.|
    |**Description**|The description of the widget group. The description cannot be more than 100 characters in length and can be modified after you create the widget group.|

5.  Wait for the created widget group to be reviewed. The review is complete within one or two days.

    **Note:** If you want your widget group to be quickly reviewed, join the DingTalk group provided in the announcement on the top of the DataV console and contact DataV technical support engineers.

    -   If the review is successful, choose **Widgets** \> **Widget Group** \> **View** to view the reviewed widget group and upload widgets to the group.

        **Note:** After you create a widget group, DataV generates a **developer token** for you. It is the credential to log on to the DataV developer console. For more information, see [Develop DataV widgets](/intl.en-US/Developer Guide/Quick start.md).

    -   If the review fails, check whether the widget group information contains the following errors:

        -   The group ID contains characters that are not allowed or reserved keywords.
        -   The display name contains reserved keywords.
        -   The group cover image is invalid.
        After you check for the errors, click the **Refresh** icon. In the **Edit** dialog box, modify the invalid information and click Edit to submit the widget group for review again. You can also click the **Delete** icon to delete the failed widget group and create a new group for review.

        **Note:** If you fix the preceding errors but the review fails again, contact DataV technical engineers.


## Upload a widget

After a widget group is created, you can upload widgets to the group.

1.  On the Widget Groups page, move the pointer over the reviewed widget group and click **View**.

    ![View a widget group](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7308531061/p54808.png)

2.  On the Widgets page, click **Upload**.

3.  In the Upload dialog box, click the **Upload Widget** box or drag and drop the widget package to the box to upload a widget.

    **Note:** The widget package cannot exceed 20 MB in size and must be a .tar.gz file.

4.  After the widget package is uploaded, click **Save** to save the widget to the DataV widget group.

    **Note:** If you use the Enterprise edition of DataV, you can upload up to three widgets to a group. If you use the Professional edition, the number of widgets that you can upload is not limited.


## Authorize a widget group to another user

You can authorize your widget group to another user. This allows you to share the widgets in the group.

**Note:** If you want to authorize your widget group to another user, you must upgrade you DataV instance to the **Professional** edition.

1.  Log on to the [DataV console](https://datav.alibabacloud.com/).

2.  On the left of the **Widgets** page, select **Widget Groups**.

3.  On the Widget Groups page, click the ![Authorize](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7308531061/p132823.png) icon on the upper-right corner of the widget group.

    ![Authorize](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7308531061/p37036.png)

4.  In the **Authorize** dialog box, specify the required information.

    ![Authorize dialog box](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7308531061/p37031.png)

    |Parameter|Description|
    |---------|-----------|
    |**Transfer ID**|Enter the transfer ID of the user whom you want to authorize. You can move the pointer over the username in the upper-right corner of the DataV console to obtain the transfer ID. **Note:** Transfer IDs are case-sensitive. |
    |**Authorization Levels**|Specify an authorization level. Valid values: **Subscriber** and **Developer**.     -   **Subscriber**: The authorized user can only view widgets that are brought online on the **Widgets** page.
    -   **Developer**: The authorized user can develop and upload widgets, and view widgets that are under review and that are brought online on the **Widgets** page. |
    |**Expiration Time**|Click the time picker to select the expiration time of the authorization.|

5.  Click the ![Authorize](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/7308531061/p132823.png) icon on the upper-right corner of the widget group to authorize more users and view **authorized records**.


## Search for an authorized user and revoke the authorization

In the **Authorization Records** section, search for an authorized user or revoke the authorization.

-   In the upper-right corner of the **Authorization Records** section, enter the **transfer ID** of a user in the **search box** to search for the authorized user.

    ![Authorization Records](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8308531061/p37047.png)

-   Find an authorized user and click **Revoke Authorization** in the **Actions** column to revoke the authorization.

    ![Revoke Authorization](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8308531061/p37048.png)

    **Note:** The authorization cannot be restored after it is revoked. Proceed with caution.


## Edit a widget group

In the upper-right corner of a widget group, click the ![Edit](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/9657411161/p132825.png) icon to modify **Display Name**, **Group Cover**, and **Description**. You cannot modify **Group ID**.

![Edit a widget group](https://static-aliyun-doc.oss-accelerate.aliyuncs.com/assets/img/en-US/8308531061/p37089.png)

