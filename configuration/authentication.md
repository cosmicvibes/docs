# Authentication

## Default

The default authentication provided by Eyewitness is the use of `auth_token` and `secret_key` on the login page. Simply enter these two values on your login page, and you will be granted access to Eyewitness.

## Callback

To configure a callback access policy for Eyewitness, you can add the following to your `AppServiceProvider` (or similar location) at the top of the file:

    use Eyewitness\Eye\Eye;

then in the `register()` function

    Eye::auth(function ($request) {
        // return true / false;
    });

You are able to place any code that returns `true` or `false` inside the closure to determine if a user or request should be allowed access to Eyewitness.

## Custom

You can provide your own full custom authentication through any system or means you like, giving you complete control. Once you've decided which user(s) are able to access Eyewitness through your auth system, simply add the following data to their session, and they will have access to Eyewitness.

```
// Via a request instance...
$request->session()->put('eyewitness:auth', 1);

// Via the global helper...
session(['eyewitness:auth' => 1]);
```

When a user "logs out" from Eyewitness, this session key will be removed (but they will still be logged into your auth solution).

## Disabling login

If you run your own custom authentication, you can optionally disable the generic Eyewitness login system. This can be useful if you do not want to allow people to login using the `app_token` and `secret_key` at all, and plan on implementing your own auth. Simply edit your `config/eyewitness.php` file and add the following line

```diff
+ 'login_disabled' => true,
```
