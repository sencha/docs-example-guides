# Controlling an Application with Router

On a normal website, a user navigates to and from different pages as they click links or
fill out forms.  However, in a single page application, a user's interaction doesn't load
a new page.  Instead, it is handled within a single page and components react to that
interaction.  So how do you still allow users to use the browser's forward and back
buttons? The answer is to digest URI hash changes with Ext JS 5's new Router.

## What Routing Is Used For

Routing can be used to track the application state through the use of the browser history
stack.  Routing also allows for deep linking into the application which allows a direct
link to a specific part of your application.  This is very useful for users so they can
bookmark your app and even send links to someone else to gain direct access to that part
of the application.

## What Routing Is Not Used For

Routing should not be used to store any data or session, data should be stored in a
persistent data source such as a cookie or localstorage.  Routing is only a means of
tracking the application's state.

## What is the Hash?

Browsers navigate the internet using a URI which consists of many parts. Let's look at a
sample URI:

    https://www.example.com/apps/users#user=1234

This should look relatively familiar.  However, you may not recognize `#user=1234`.  This
section of the URI is called the "hash" or fragment identifier. For more information on
the hash, please read this resource http://en.wikipedia.org/wiki/Fragment_identifier. This
hash provides a way for an application to control the history stack of the browser without
reloading the current page.  As the hash changes, the browser adds that whole URI to the
history stack, which then allows you to utilize the browser's forward / back buttons to
traverse URIs including the hashes that may have changed. For instance, what happens if
you update the hash to:

    https://www.example.com/apps/users#user/5678

The browser fires a `hashchange` event that we can then utilize within the application.
A user can then click the back button to go back to the `#user=1234` hash.  This
notification then allows you to react to the change within your application.  It is
important to mention that the hash is not sent to the server.  The hash is typically
digested within the client's interpretation of the URI.  The Ext JS Router relies on the
browser's hash functionality to allow application state tracking and deep linking.

## Implement Routing in your Application

The Router class is a new addition to Ext JS 5 that was built to make hash change
interpretation very simple in an MVC application.  We have always had Ext.util.History,
which you could use to react to the hash changes.  However, this Ext.util.History offers a
much more manual process and a proper Router class was needed.  The Router provides simple
integration into an Ext JS 5 MVC application by defining routes in a view controller.  A
route is a string that is matched to the hash and allows for deep linking within your Ext
application.  Here is a basic example controller implementing Router:

    Ext.define('MyApp.view.main.MainController', {
        extend : 'Ext.app.ViewController',

        routes : {
            'users' : 'onUsers'
        },

        onUsers : function () {
            //...
        }
    });

This route will react to the `#users` hash and will execute the `onUsers` method scoped to
the controller instance.  As you can see, the `routes` config is placed within the
`config` object instead of on the root level.

## Updating the Hash

To update the hash, a controller has a redirectTo method.

    this.redirectTo('user/1234');

This will update the hash to be `"#user/1234"` and any routes configured to recognize the
hash will be executed.

The `redirectTo` method also accepts a second argument to pass in `options`. The options are:

 - **`force`** If `true`, this will force the Router to react even if the hash in the
 address bar is the same as the hash that is being passed to `redirectTo`.
 - **`replace`** By default, the hash will be changed and a new entry in the browser's
 history will be created.  This means the browser's back button can go back to the previous
 hash.  If `true`, the current entry in the browser's history will be replaced by the
 hash that was passed to `redirectTo`.

**Note:** _For backwards compatibility, the `options` can be a boolean.  In this case,
it is setting the `force` option.

## Default Token

When an application starts, it may be configured to add a default hash if one is not
provided. For instance, if the application shows a dashboard when the `#home` hash is
used, you may want to add the `#home` hash to the URI if no other hash exists.  To enable
a default hash, you can use the `defaultToken` config in the `/app/view/Application.js`
file, which can be found within your application:

    Ext.define('MyApp.Application', {
        extend : 'Ext.app.Application',

        //...

        defaultToken : 'home'
    });

When the application is started, it will check the current hash of the URI. If there is a
hash defined, it will execute the route handlers. If no hash is found, it will add the
`#home` hash and any route handlers will get executed to handle it appropriately.

## Hashes with Parameters

An application can also identify parameters within hashes.  A user ID is an example of a
parameter you may want to include in a hash.  We mentioned using `#user/1234` as a hash
earlier within the guide.  In this case, we may want the `1234` to be an id parameter. You
would then set up your controller to react to the `#user/1234` hash:

    Ext.define('MyApp.view.main.MainController', {
        extend : 'Ext.app.ViewController',

        routes : {
            'user/:id' : 'onUser'
        },

        onUser : function (id) {
            //...
        }
    });

The route we used was `'user/:id'` and the colon, `:`.  This signifies that there is a
parameter and your application will pass that parameter to the onUser method as an
argument.  The method will receive the same number of arguments passed to it in the same
order as specified in the route, which allows for easy inclusion of multiple parameters.

## Hash Parameter Formatting

The application may want to enforce a specific format for the user ID.  The ID is numeric
In the case we've explored so far.  You may also use the route to equate to an object by
using the `conditions` config:

    Ext.define('MyApp.view.main.MainController', {
        extend : 'Ext.app.ViewController',

        routes : {
            'user/:id' : {
                action     : 'onUser',
                conditions : {
                    ':id' : '([0-9]+)'
                }
            }
        },

        onUser : function (id) {
            //...
        }
    });

Let's walk through this example.  First, the 'onUser' method is now moved to the action
config.  This will work similarly to when we passed the string to the route. We then use
the conditions config to provide an object. The key we want to control is the parameter
name with the colon and we provide a Regular Expression string (not a Regular Expression
object).  For the `:id` condition, we use `([0-9]+)`, which will allow numbers between 0
and 9 with any length and will remember the match.  We use a string because a Regular
Expression object is made to match the entire hash, so if there are multiple parameters in
the route we need to concatenate the Regular Expression strings together into a single
Regular Expression object. If you do not provide a condition for a parameter, it will
default to:

    ([%a-zA-Z0-9\\-\\_\\s,]+)

## Route Handling

There may be times when an application needs to prevent the handling of a route.  In this
case, we may want to check administrative rights to determine whether or not the current
user is allowed to view a portion of the application. The route can be configured to use a
`before` action, which may stop the current route, stop all routes or continue on with the
route execution.

This example will continue the route execution:

    Ext.define('MyApp.view.main.MainController', {
        extend : 'Ext.app.ViewController',

        routes : {
            'user/:id' : {
                before  : 'onBeforeUser',
                action  : 'onUser'
            }
        },

        onBeforeUser : function (id, action) {
            Ext.Ajax.request({
                url     : '/security/user/' + id,
                success : function() {
                    action.resume();
                }
            });
        },

        onUser : function (id) {
            //...
        }
    });

In the `onBeforeUser` method, the `:id` parameter is passed as an argument, but the last
argument is an `action`.  If you execute the `resume` method on the `action`, the route
will continue to execute and the `onUser` method will then be called.  Notice that we can
wait for an AJAX request to complete before we need to continue the route execution.

We can expand on this example by telling the application to stop current route execution
by executing the `stop` method:

    Ext.define('MyApp.view.main.MainController', {
        extend : 'Ext.app.ViewController',

        routes : {
            'user/:id' : {
                before  : 'onBeforeUser',
                action  : 'onUser'
            }
        },

        onBeforeUser : function (id, action) {
            Ext.Ajax.request({
                url     : '/security/user/' + id,
                success : function () {
                    action.resume();
                },
                failure : function () {
                    action.stop();
                }
            });
        },

        onUser : function (id) {
            //...
        }
    });

The `before` action also supports promises.  Instead of executing `resume` or `stop` on the `action`
argument, you can return a promise and `resolve` or `reject` it.  On resolution of that promise, the
action will be resumed or stopped:

    Ext.define('MyApp.view.main.MainController', {
        extend : 'Ext.app.ViewController',

        routes : {
            'user/:id' : {
                before  : 'onBeforeUser',
                action  : 'onUser'
            }
        },

        onBeforeUser : function (id) {
            return new Ext.Promise(function (resolve, reject) {
                Ext.Ajax.request({
                    url     : '/security/user/' + id,
                    success : function () {
                        resolve()
                    },
                    failure : function () {
                        reject();
                    }
                });
            });
        },

        onUser : function (id) {
            //...
        }
    });

**Note:** _Whether you use the `action` argument or return a promise is your choice.  With either means,
a resolution needs to happen.  Either the `action` argument gets it's `resume` or `stop` method executed,
or the promise is resolved or rejected._

## Handling Unmatched Routes

If the hash was changed but there is no route that was found to match the hash, the Router
will do nothing; the Router will not attempt to change the hash and will leave the
unmatched hash alone.  The Router will fire the `unmatchedroute` event on the application
instance which is listenable in the `Ext.application` call:

    Ext.application({
        name : 'MyApp',

        listen : {
            controller : {
                '#' : {
                    unmatchedroute : 'onUnmatchedRoute'
                }
            }
        },

        onUnmatchedRoute : function (hash) {
            //...
        }
    });

The Router will also fire a global event:

    Ext.application({
        name : 'MyApp',

        listen : {
            global : {
                unmatchedroute : 'onUnmatchedRoute'
            }
        },

        onUnmatchedRoute : function (hash) {
            //...
        }
    });

Global events can also be listened to directly on the `Ext` namespace:

    Ext.on('unmatchedroute', function (hash) {
        //...
    });

## Using Multiple Routes in a Single Hash

Since Ext JS applications can be complex, there may be times where we need to use multiple
routes in a single hash. The Router is set up to handle this so there is no extra set up
to the routes that are configured in the controllers. Instead, you can delimit the hash
with a pipe: `|`. An example hash could be

    #user/1234|messages

In this case, we want to show user details for the user with an id of `1234`, but also
show messages. Each route will execute in the order dictated by the hash.  They are then
sandboxed from each other.  In simpler terms, if you stop the `user/1234` route, the
`messages` route will continue execution.  It's important to note that the execution order
of the individual routes is the same order as the routes are in the hash.  The `user/1234`
route will always execute before the `messages` route for the above example.

You may modify the delimiter, by changing the `Ext.route.Router.multipleToken`
property.

To work with multiple routes, the `redirectTo` method can also accept an object.  This
can give you control of what part of the complete hash should be updated or even removed.
Say we have 3 different routes (they can be in different controllers also):

    routes: {
        'bar' : 'onBar',
        'baz' : {
            action : 'onBaz',
            name   : 'bazRoute'
        },
        'foo' : 'onFoo'
    }

The `baz` route has a new config called `name`. The reason for this is each route is now
named so we can reference it easier.  By default, the name is the url that is passed as
the key in the `routes` object; `bar` and `foo` are the names of the others.  We have
`bar`, `bazRoute` and `foo` as the names of our three routes.

The initial hash can be set by first passing a string to make the hash exactly this:

    this.redirectTo('foo');

Now the hash will be `#foo`.  We can add another token to that hash by passing a string
with both tokens delimited by the `multipleToken` property like we've been doing or
by passing an object:

    this.redirectTo({
        bar : 'bar'
    });

Now the hash is `#foo|bar`.  Let's inspect what just happened.  We started with `#foo`
as our hash and we passed an object into `redirectTo` and passed the `bar` key.  This
key is expected to be the name of the route we are referencing, this where the named
concept is key; for complex urls that are passed, a name is a handy way to reference
it.  If the value is falsy and the named route is found in the hash, it will be
removed.  If the value is truthy and the named route is found in the hash, that part
of the hash will be replace with the new value.  If the named route is not found in
the hash, it is then appended to the hash.  If we wanted to replace the `foo` route,
we can pass a value in for it:

    this.redirectTo({
        foo : 'foober'
    });

Now the hash is `#foober|bar`, notice the order of the individual tokens in the hash
is preserved.  Let's look at a more complex example:

    this.redirectTo({
        bar      : 'barber',
        bazRoute : 'baz',
        foo      : null
    });

In this example, we are removing one, updating another and adding one.  The hash would
now be `#barber|baz`.  With passing an object, you have much better control over what
the hash will be without concerning what the current hash is, Ext JS will handle it
for you.

## Automatic Hashbang Support

If your application requires hashbang instead of a regular hash, Ext JS can now handle
this automatically for you.  `Ext.util.History` is the class that handles setting and
getting the hash from the browser and is where Ext JS can automatically make the hash
a hashbang with a simple property:

    Ext.util.History.hashbang = true;

Now, it will automatically use hashbangs.  Your routes will still look the same:

    routes : {
        'foo' : 'onFoo'
    }

And the use of the `redirectTo` method is the same:

    this.redirectTo('foobar');

    this.redirectTo({
        foo : 'foobar'
    });

But `Ext.util.History` automatically makes the hash `#!foobar` for you.  The Router
can also set this property for you by using the new `router` config on the application:

    Ext.application({
        name : 'MyApp',

        router : {
            hashbang : true
        }
    });

You can also use the setter method on the Router:

    Ext.route.Router.setHashbang(true);

**Note:** _A hashbang is just a hash, just with a `!` after the `#`. This means you
cannot mix and match hash and hashbangs, it's either-or._

## Suspending and Resuming the Router

If you need to make the Router wait for some process to finish so that no changes in
the hash are reacted to, you can suspend the Router.  Once suspended, any hash changes
that occur will be queued and executed once resumed.  A common use case is delaying
routes from executing when an application is starting until a store or user session
is checked.  Here is an example:

    Ext.application({
        name : 'MyApp',

        defaultToken : 'home',

        launch : function () {
            var me = this;

            Ext.route.Router.suspend();

            me
                .checkUserSession()
                .then(me.onUser.bind(me), me.onUserError.bind(me));
        },

        onUser : function (user) {
            MyApp.$user = user;

            Ext.route.Router.resume();
        },

        onUserError : function (error) {
            // handle error

            // do not execute queued hash changes
            Ext.route.Router.resume(true);

            this.redirectTo('login');
        }
    });

If you know you do not want to queue any hash changes, the `suspend` method can take
an argument when `false`:

    Ext.route.Router.suspend(false);

## Wildcard Action

If you want to handle a route being executed prior to all configured routes, you can
specify a wildcard route.  These wildcard routes will execute prior to other routes:

    routes : {
        '*'   : 'onRoute',
        'foo' : 'onFoo'
    }

    routes : {
        '*'   : {
            before : 'onBeforeRoute',
            action : 'onRoute'
        },
        'foo' : 'onFoo'
    }

The wildcard route is dictated by passing `*` as the url of the route.  It's actions
will be executed prior to the `foo` route.

## Global Events

Ext JS also exposes certain global events.  These events are fired on the `Ext` namesapce
and can be listened to from the `Ext` namespace or the global event domain.  Here are
the events:

 - **`beforeroutes`** Fires prior to any route being executed.  Returning `false` allows
 cancelation of enacting on the routes.
 - **`beforeroute`** Fires prior to each route being executed.  Returning `false` allows
 cancelation of enacting on that one route.
 - **`unmatchedroute`** Fires when a route is not matched on a token.  This is also fired
 on the application instance if one is present.

 As mentioned, there are two ways to listen for these events.  The more recommended way
 is listening via the global event domain in a controller/viewcontroller:

     listen : {
         global : {
             beforeroutes : 'onBeforeRoutes'
         }
     },

     onBeforeRoutes : function (action, tokens) {
         return tokens.length === 1;
     }

Or you can listen via the `Ext` namespace:

     Ext.on('unmatchedroute', function (token) {
         Ext.Msg.alert('Unmatched Route', '"' + token + '" was not matched!');
     });

## The `Action` Class

In a `before` action, you have seen the `action` argument.  This is an instance of
`Ext.route.Action` and allows more than just resuming or stopping the action.  This
class actually allows code to be more dynamic as well by allowing you to add `before`
and `action` actions even during execution:

    onBeforeUser : function (id, action) {
        return new Ext.Promise(function (resolve, reject) {
            action.before(function (id, action) {
                action.action(function (id) {
                    //...
                });

                action.resume();
            });

            Ext.Ajax.request({
                url     : '/security/user/' + id,
                success : function () {
                    resolve()
                },
                failure : function () {
                    reject();
                }
            });
        });
    }

In this example, we add a new `before` action that will get appended onto the array
of `before` actions being executed (it will be executed last).  Within that `before`
action, we also add a new `action` action that will get appended onto the array of
`action` actions.  Notice the `id` parameter is still passed to the new actions.

If you wanted to know about when the action has been fully resolved or rejected
(all `before` and `action` actions have completed), the `action` class has a `then`
method:

    onBeforeUser : function (id, action) {
        var me = this;

        return new Ext.Promise(function (resolve, reject) {
            action.then(Ext.bind(me.onFinish, me), Ext.bind(me.onRejection, me));

            //...
        });
    }

If at any point, you wanted to stop the action class from executing other `before`
or `action` actions, the action class has a `stop` method that will stop it's
execution:

    onBeforeUser : function (id, action) {
        try {
            this.foo();
        } catch (e) {
            action.stop();
        }
    }

## Router in a non-MVC/non-MVVM world

A new mixin was created in Ext JS 6.5.0 where now routes can be defined in any class:

    Ext.define('MyClass', {
        mixins : [
            'Ext.route.Mixin'
        ],

        routes : {
            'foo' : 'onFoo'
        },

        constructor : function (config) {
            this.initConfig(config);
        },

        doSomething : function () {
            this.redirectTo('foo');
        },

        onFoo : function () {
            //...
        }
    });

This allows applications that do not employ the MVC or MVVM architecture to still
use the Router functionality.
