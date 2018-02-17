# Authentication

## Default

The default authentication provided by Eyewitness is the use of `auth_token` and `secret_key` on the login page.

Simply enter these two values on your login page, and you will be granted access to Eyewitness.

## Custom

To configure a custom access policy for Eyewitness, you can add the following to your `AppServiceProvider` (or similar location) at the top of the file:

    use Eyewitness\Eye\Eye;

then in the `register()` function

    Eye::auth(function ($request) {
        // return true / false;
    });

You are able to place any code that returns `true` or `false` inside the closure to determine if a user or request should be allowed access to Eyewitness.
