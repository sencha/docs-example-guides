# Lab 4: Testing the Login Page

**Total Time: 20 minutes**

## Looking at the source

If you look at the source code for the [Login page](https://se.sencha.com/AssetRegister/Login.aspx), 
you should notice that the main part of the page looks something like the sample below. 

    ...
    <div class="group">
        <input name="email" type="email" id="email" /><span class="highlight"></span><span class="bar"></span>
        <label>Email</label>
    </div>
    <div class="group">
        <input name="password" type="password" id="password" /><span class="highlight"></span><span class="bar"></span>
        <label>Password</label>
    </div>
    <button type="submit" class="button buttonBlue wide" id="submit">Login
        <div class="ripples buttonRipples"><span class="ripplesCircle"></span></div>
    </button>
    ...

The Login page is a standard HTML page, and makes no use of Ext JS. This replicates a typical 
internal development scenario, where you may have a standard corporate single sign-on page that's used for 
authentication to all business apps, which then redirects to a separate application page upon successful login.

As you're dealing with standard HTML elements on the Login page, you can make use of the `ST.element` Future API for interacting with these fields and buttons.


## Identify Requirements

You will want to establish or collate a list of requirements for the Login page, that describe how
it should function and respond to different user actions. For example, this Login page could have
the following requirements, which we can base our tests on:

| Requirement |
| --- |
| Should not login without an email address or password specified |
| Should show an error when the entered email address doesn't exist |
| Should display an error when attempting to login with a valid email but an invalid password |
| Should login when valid login credentials have been provided and redirect to the app |


## Identify Locators

In order to start authoring end-to-end tests for the Login page, you need to identify
the locators that will be used for referencing each of the elements on the page. 

As this is a standard HTML page, you can look at the source code in the browser and 
establish valid locators that can be used. In this instance, we're going to use
the `id` attributes of each element. When converted to a locator, an `id` will
have a `@` prefix.

| Element | Locator |
| --- | --- |
| Email Address | `@email` |
| Password | `@password` |
| Submit Button | `@submit` |
| Reset Button | `@reset` |
| Error Text div | `@errors` |


## Author Tests

After identifying the locators, you can start to author your first test. 

1. Add a test to your `Login` test suite that will validate the first requirement in the table above.
  You should end up with something like below.

  **Hint:** As the Login page submits to the server (it does a full postback and reload), you will need to make
  use of the `.wait` API after the Submit button is clicked. This ensures that subsequent use of the
  Futures API will reference elements on the refreshed page.

    ```
    describe('Login', function() {
        it('Should not login without an email address or password specified', function() {
            ST.element('@submit')
                .click()
                .wait(2000);
                
            ST.element('@errors')
                .textLike('Email address is required')
                .textLike('Password is required');
        });
    });
    ```

1. Before we add our next test, we want to reset the state of the form between
  each test. In order to do that, we can use a `beforeEach()` Jasmine function that
  clicks on the form's reset button:
  
    ```
    describe('Login', function() {
        beforeEach(function() {
            ST.element('@reset')
                .click();
        });
    
        it('should not login without an email address or password specified', function() {
            ...
        });
    });
    ```

1. We can now test what happens when a user enters an email address that doesn't
  exist in the system:
  
    ```
    it('should show an error when the entered email address doesn\'t exist', function() {
        ST.element('@email')
            .focus()
            .type('invalidemail@domain.com');
            
        ST.element('@password')
            .focus()
            .type('test');
            
        ST.element('@submit')
            .click()
            .wait(2000);
        
        ST.element('@errors')
            .textLike('User with this email address not found');
    });
    ```

1. Then add a test that checks an appropriate message is shown when a user enters
  a valid email address, but an invalid password. Make sure to use your own email address:

    ```
    it('should display an error when attempting to login with a valid email but an invalid password', function() {
        ST.element('@email')
            .focus()
            .type('dan@sencha.com');
        
        ST.element('@password')
            .focus()
            .type('invalidpassword');
            
        ST.element('@submit')
            .click()
            .wait(2000);
        
        ST.element('@errors')
            .textLike('You entered an invalid password');
    });
    ```

1. Our final test will be to verify that valid credentials will log the user in,
  and redirect to the application interface. Make sure to use your own email address
  and password:
  
    ```
    it('should login when valid login credentials have been provided and redirect to the app', function() {
        ST.element('@email')
            .focus()
            .type('myemail@domain.com');
        
        ST.element('@password')
            .focus()
            .type('validpassword');
            
        ST.element('@submit')
            .click()
            .wait(2000)
            .getUrl(function(url) {
                expect(url).toContain('Default.aspx'); 
            });
    });
    ```

1. Save your test suite.

## Run Your Tests

You should now run your tests, to verify they work and run as expected.

1. In Sencha Studio, select the `End-to-End` Scenario in the tree

1. Under the list of Embedded browsers, check `Chrome`. By default, all tests
  will be run.
  
1. Click the `Run` button. After a few seconds, you should see a new Chrome browser window
  launched, and your tests will begin to run.
  
1. After the test run has completed, expand the `Login.js` scenario, and expand the
  test suite, and you'll be able to see the individual tests, which should have all passed.
  
## Summary

At the end of this lab, you should have a test suite that looks like the one shown below.

**Important:** If you copy and paste this code, please make sure you update the credentials 
that are being used in the final spec:

    describe('Login', function() {
        beforeEach(function() {
            ST.element('@reset')
                .click();
        });
        
        it('should not login without an email address or password specified', function() {
            ST.element('@submit')
                .click()
                .wait(2000);
                
            ST.element('@errors')
                .textLike('Email address is required')
                .textLike('Password is required');
        });
        
        it('should show an error when the entered email address doesn\'t exist', function() {
            ST.element('@email')
                .focus()
                .type('invalidemail@domain.com');
                
            ST.element('@password')
                .focus()
                .type('test');
                
            ST.element('@submit')
                .click()
                .wait(2000);
            
            ST.element('@errors')
                .textLike('User with this email address not found');
        });

        it('should display an error when attempting to login with a valid email but an invalid password', function() {
            ST.element('@email')
                .focus()
                .type('dan@sencha.com');
            
            ST.element('@password')
                .focus()
                .type('invalidpassword');
                
            ST.element('@submit')
                .click()
                .wait(2000);
            
            ST.element('@errors')
                .textLike('You entered an invalid password');
        });

        it('should login when valid login credentials have been provided and redirect to the app', function() {
            ST.element('@email')
                .focus()
                .type('myemail@domain.com');
            
            ST.element('@password')
                .focus()
                .type('validpassword');
                
            ST.element('@submit')
                .click()
                .wait(2000)
                .getUrl(function(url) {
                    expect(url).toContain('Default.aspx'); 
                });
        });
    });