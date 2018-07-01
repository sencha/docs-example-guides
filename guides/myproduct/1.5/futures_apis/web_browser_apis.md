# Web Browser APIs

When writing tests, you may want to know details of the current browser 
in order to carry out a certain set of actions for a particular browser.

This is possible by using the [`ST.browser`](../../api/ST.browser.html) class, which contains a set of 
properties that help reveal details of the current browser.

## Browser Type

You can easily check whether a browser is Internet Explorer or Chrome:
 
    if (ST.browser.is.IE) {
        // IE specific code here
    }
    
    if (ST.browser.is.Chrome) {
        // Chrome specific code here
    } 

## Browser Version

You can also check the browser version:
 
    ST.browser.version
 
## Secure Connection
 
It's possible to check whether the application is running over a secure
`https://` connection:

    ST.isSecure

This returns as `true` if the app is running over a secure connection.

You could write a test that asserts this is true:

    expect(ST.isSecure).toBeTruthy();

## More Details

For more details see [the documentation on `ST.browser`](../../api/ST.browser.html).