# Impacts of updating Google Chrome to v80

After you update Google Chrome to v80, API data of DataV projects may fail to be returned or displayed. This topic describes the background and solutions for this issue.

## Background

Google released [Chrome v80](https://www.chromestatus.com/features/schedule) on February 4, 2020. This version of Google Chrome gradually blocks third-party cookies. By default, a [SameSite=Lax](https://www.chromestatus.com/feature/5088147346030592) attribute is added for all cookies, and requests that contain insecure cookies with the [SameSite=None](https://www.chromestatus.com/feature/5633521622188032) attribute are rejected. This prevents cross-site request forgery \(CSRF\) attacks.

## How can I determine whether updating Google Chrome to v80 will affect my DataV project?

1.  Open `chrome://flags/#same-site-by-default-cookies` in Google Chrome and set **SameSite by default cookies** to **Enabled**.
2.  Open `chrome://flags/#cookies-without-same-site-must-be-secure` in Google Chrome and set **Cookies without SameSite must be secure** to **Enabled**.
3.  Restart Google Chrome and access a DataV project. Check whether all data is returned and displayed as expected.
    -   If yes, updating Google Chrome to v80 does not affect your project.
    -   If no, the update affects your project. You can troubleshoot the issue based on the following scenarios.

## Scenario 1: You project uses an API data source

Description: The widget in your project uses an API data source. Requests to call the API contain user logon information in cookies to obtain data from a third-party website.

Impact: Widget data cannot be returned and displayed as expected.

Solution: Determine whether the API requests use HTTPS or HTTP.

-   HTTPS

    Check whether the settings of `Set-Cookie` in the request header contain `SameSite=None` and `Secure`. If no, add `SameSite=None` and `Secure` to the settings of `Set-Cookie`.

-   HTTP
    1.  Open `chrome://flags/#same-site-by-default-cookies` in Google Chrome and set **SameSite by default cookies** to **Disabled**.
    2.  Open `chrome://flags/#cookies-without-same-site-must-be-secure` in Google Chrome and set **Cookies without SameSite must be secure** to **Disabled**.
    3.  Restart Google Chrome.

