# Navigation and URL APIs

During a test, you may want to navigate to a particular page, set the 
route of the application, or simply get the current URL.

All of this is possible through some of the Sencha Test APIs, as described
below.

## Getting the Current URL

In order to get the current URL, you can do the following:

    ST.getUrl(function(url) {
        expect(url).toContain('Default.aspx');
    });

A callback function is defined within the call to `getUrl()`, which will 
have a reference to the retrieved URL.

## Setting the URL

You can navigate to a particular URL using the `ST.navigate` method:

    ST.navigate('https://myapp.domain.com');

**Note:** Navigating to a new page is only supported in WebDriver scenarios. For In-Browser
scenarios, the `ST.navigate` API can only be used for navigating to a particular route within
the current page.

For applications that support routing or deep linking, you can set the `#` anchor value:

    ST.navigate('#user/12');