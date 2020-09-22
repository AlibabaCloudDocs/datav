# Use cookies to isolate data of a DataV project

If you use an API data source in a DataV project, you can configure cookies to allow different users to view their own data after they log on to the system. This ensures data security in the project.

## How it works

1.  If you embed a DataV project into the web page of your business system by using an iframe, the web page requests contain user logon information, for example, Session\_Id in cookies when a user logs on.
2.  If you use an API data source and select **Cookie Required \(Applicable when Initiate Request from Server is not selected and cookies are required\)**, DataV adds cookies in HTTP requests. The cookies contain user logon information.

    ![Cookie Required](https://static-aliyun-doc.oss-cn-hangzhou.aliyuncs.com/assets/img/en-US/5780470061/p129287.png)

    **Note:** If cross-origin requests are required, select Initiate Request from Server \(Applicable when cross-origin access fails\). For more information, see [Cross-origin data configuration](/intl.en-US/Advanced Skills/Cross-origin data configuration.md).

3.  When users log on and request the DataV project, the server verifies user information in the requests and returns data to users based on the information. Individual users can view only their own data.

