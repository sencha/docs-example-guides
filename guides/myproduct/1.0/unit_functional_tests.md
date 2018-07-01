#Unit vs Functional Testing

Tests written within Sencha Test will fall into the following categories: 

+ unit tests 

+ functional tests  

Knowing how to use each type of test to your advantage will ensure the highest 
degree of integrity within your applications.

##Testing Style Overview
Unit testing can be described as tests targeting the underlying code of an application. 
This style of testing may be of particular interest to application developers.  

Functional testing analyzes the running application instead of simply testing its pieces and parts.  
This style of testing may be of particular interest to quality assurance and end users.  

Let's clarify this generalized description by saying that unit tests are 
able to be performed without spinning up an application while functional tests 
require the application to be launched to perform testing.

This distinction is important because Sencha Test, along with Ext JS 5+, 
can test code without any UI present.  For example, you can test validations
within data models without a running application. Views used within an application 
can also be tested independently from the application. 

Many aspects of an application may be difficult or lengthy to test when testing through a 
running application.  A test may require you to first follow a specific set of navigational 
steps, or to be logged in as a particular user type.

For example, consider a scenario where you want to test that a "user" can edit a given
field versus an "admin" role on a “User Details” panel.  A functional test requires 
you to launch the app and sign in as a user, not an admin.  Then, perhaps navigate to a 
“User List” view, select a user from the list, and click an edit button to launch 
the “User Details” popup.  You would then need to evaluate the fields that “user” 
is eligible to edit. 

Ultimately, we simply want to know whether a “user” can edit certain fields in a view of 
type “User Details”.  With unit testing, just create a test that only launches 
the view that injects “user” permissions.  You can then evaluate the editability of
the fields based on permissions.

Before exploring functional testing, let’s look at some common unit testing use 
cases and how we can perform those tests using Sencha Studio.

##Unit Testing

### Assumptions:
 - You have already followed the [installation guide](./sencha_test_installation.html)
 - You have created a workspace with a classic sample application 
 - You have initialized the test project (Tests) for your application and created a 
 scenario to hold the tests.

**Note:** Unit tests do not require an application or the Sencha framework.  That
said, we're following this model to create a front-to-back guide path.

### Unit Testing Model Validation
For this unit test, let's test validation for our `User` model.  We want to 
ensure that the data stub representing inputted user data is valid within our parameters.

First, let’s add our `User` model class to our application by adding the following file: 
"{appName}/app/model/User.js":

	Ext.define('MyApp.model.User', {
	    extend: 'Ext.data.Model',
	    fields: ['first', 'last', 'fullname', 'username'],
	
	    validators: {
	        first: 'presence',
	        last: { type: 'length', min: 2 },
	        username: [
	            { type: 'exclusion', list: ['Admin', 'Operator'] },
	            { type: 'format', matcher: /([a-z]+)[0-9]{2,3}/i }
	        ]
	    }
	});

The “User” model can now be instantiated for test purposes.  Next, let’s add some data to 
the scenario that the test is able to access when validating our User model.  We’ll 
create a folder/file in the workspace root directory of: 
"{workspaceRoot}/shared/userdata.js".  The "userdata" file will contain the following:

	var __my_user_data = {
        	first: 'Rick',
        	last: 'Grimes',
        	username: 'rgrimes'
    	}

Next, we’ll add the "userdata" file to the test project so that any scenario’s tests may 
access it.  We’ll do this by clicking on the + Add button under the Additional Libraries 
header for the test project, double-click the default field value, click on the folder 
icon to bring up the file picker, and choose the “userdata.js” file from the 
“[workspaceRoot]/shared” directory.  Finally, click on the Save button in the top 
toolbar.

In this next step, we’ll create the unit test used to verify that the "userdata" values are 
validated by our “User” model class.  

First, create a Scenario by clicking on the "+ Add" button under the Scenarios heading in 
the Test Project view.  For the purpose of this guide, we’ll give it a name of “User Data”.  

Next, right-click on the "User Data" node in the workspace navigation tree and select 
"New > Jasmine Test Suite" and give the user validation test the name of 
“UserValidation”.  This adds the “UserValidation” test as a child of the “User Data” 
scenario.  

Click on the “UserValidation.js” node in the workspace validation tree to open the test editor view.

Finally, replace the placeholder test script with the following:

    describe("UserValidation", function() {
        it("should pass", function(done) {
            Ext.require('MyApplication.model.User', function () {
                var user = new MyApplication.model.User(__my_user_data),
                    failedValidation = user.getValidation().dirty;
                
                expect(failedValidation).toBe(!true);
                done();
            });
        });
    });


In this test, we’re expecting the model to validate the sample user data.  If you play 
the test in the Scenario's test runner, you should see that it does indeed pass!

### Unit Testing a Custom Button
In addition to testing non-view logic, we can also unit test pieces and parts of our 
larger application to ensure they’re working correctly.  In this test, let’s create a 
button with a badge that displays the text set in the button’s `badgeText` config.

To start, add the following folder/file to your application at: 
“{workspaceRoot}/app/view/button/BadgeButton.js”

    Ext.define('MyApplication.view.button.BadgeButton', {
        extend: 'Ext.button.Button',
        xtype: 'badgebutton',

        config: {
            badgeText: null
        },

        childEls: ['badgeEl'],

        cls: 'da-badge-button',

        hideBadgeOnDisabled: true,

        initRenderData: function() {
            return Ext.apply(this.callParent(), {
                badgeText: this.badgeText
            });
        },

        updateBadgeText: function(text) {
            var me = this;

            if (me.rendered) {
                me.badgeEl.setHtml(text).setVisible(text);
            } else {
                me.on('render', function() {
                    me.badgeEl.setVisibilityMode(Ext.dom.Element.DISPLAY);
                    me.badgeEl.setHtml(text).setVisible(text);
                });
            }
        },

        onDisable: function() {
            this.callParent();
            if (this.hideBadgeOnDisabled) {
                this.badgeEl.hide();
            }
        },
        onEnable: function() {
            this.callParent();
            this.badgeEl.show();
        }
    }, function(BadgeButton) {
        BadgeButton.prototype.renderTpl += '<span id="{id}-badgeEl" class="da-badgeElCls" data-ref="badgeEl">{badgeText}</span>';
    });

Next, create a new Scenario called “Badge Button” in our application’s test project and 
then right-click on the Scenario to create a new Jasmine Test Suite called “ButtonText”.  

We can add a single `describe()` with multiple `it()` specs in the badge button test 
suite. The description of each `it()` will show up as nodes under the scenario test tree 
under “ButtonText”.  

Enter the following test in the "ButtonText" tab.  This will allow studio to evaluate the badge
text and ensure the badge element is hidden when the button is disabled.

    describe("ButtonText", function() {
        var btn;
    
        beforeEach(function(){
            btn = Ext.create('MyApplication.view.button.BadgeButton', {
                renderTo: Ext.getBody()
            });
        });
    
        afterEach(function () {
            btn.destroy();
        });
    
        it("should have a badge of 2", function() {
            btn.setBadgeText('update');
            expect(btn.badgeEl.getHtml()).toBe('update');
        });
    
        it("badge should be hidden", function() {
            btn.setBadgeText('update');
            btn.disable();
            expect(btn.badgeEl.isVisible()).toBe(false);
        });
    });

Running the tests should show green checkmarks for both specs in "ButtonText".

## Functional Testing

Unit tests are agile and allow for discrete testing of internal code and isolated 
componentry.  Unit tests offer a great front line of defense when guarding against bugs 
introduced as an application evolves and becomes more complex.  However, functional testing 
has its place in the bug defense strategy as well and should not be discounted in 
favor of unit tests alone.

It's quite possible for a suite's unit tests to all pass, leading you to believe your 
application has been error-proofed. All this, only to discover that when you run the application, 
some dynamic element of the application environment wasn’t captured in the unit tests. 

For some operations, the only practical way to round out your test setup is to launch the 
application and put it through its paces.

### Complex Routing
One such example would be to navigate between views within an application.  
Let’s say your application has a parent container with a card view and two child views: 
Home and User List.  

Then, let's say you want to test whether the routing works to display a 
specific user’s details view when the URL has contains “#!/user/rgrimes”.  

Internally you have a route in the parent view’s viewController that routes based on “#!/user/” to the 
user panel and the user panel’s viewController opens the user details panel using the 
“/rgrimes” portion of the hash.  Testing this type of navigational logic is exactly where 
functional testing comes into its own.  The launching of the application takes care of 
presenting the main container and its children, which in turn spins up their respective 
viewControllers to manage the routing logic between views.

### Testing the Application Environment
Complex routeing is one scenario in which you’d want to spin up the application from Studio 
and run through test logic in order to validate the functionality of the app.  Another reason you 
may want to employ functional testing would be to test the application running in a 
real-world environment.

Imagine you’ve set up a unit test to ensure that “User Details” views are viewable by 
“users”, but editable by “supervisors” and “admins”.  You have a unit test to ensure that 
a “Weekly Overview” shows a single user’s details when viewed by a user, but an entire 
team roll-up when viewed by a supervisor.  

The “Admin Dashboard” that configures user roles is only accessible to admins and not 
supervisors and users.  With all of these unit tests in place you may feel that all 
bases are covered and every unique facet of the application has been tested so you may 
deploy.  Now imagine that the user launches the application and is unable to sign in 
because the connection to the server / database is broken.  A functional test that 
pulled down the user role information from the remote server would have secured this 
issue before the application deployed.

## Summary
Unit and functional testing are essential when safeguarding your application against bugs.  
Fortunately, Studio gives you the tools needed to manage and perform both.  This guide 
provides some simple examples for unit tests, but as you build out your test base, you’ll 
want to incorporate more than just direct logical testing.  You’ll want to simulate user 
interactions within the UI.  

To see how you can easily add simulated user interactions to your unit / functional tests, check 
out the Event Recorder guide (coming soon).
