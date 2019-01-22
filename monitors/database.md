# Database monitor

Eyewitness can keep an eye on your various application databases to ensure they are available at all times. This is especially important if your database sits on a different server than your application, as sometimes network or server problems can take the database offline (which your web application stays online).


## Notifications

The database monitor will send out one of the following alerts:

### Offline

If Eyewitness detects the database connection is offline or not working, a notification will be sent.

### Online

If a previously failed database connection is now back online, Eyewitness will send you a notification.

### SizeLarge

Each database connection can have a size alert if the database goes above a certain threshold. If this occurs, Eyewitness will send you a notification. You can set the size to be `0` to disable this alert.

### SizeSmall

Each database connection can have a size alert if the database goes below a certain threshold. If this occurs, Eyewitness will send you a notification. You can set the size to be `0` to disable this alert.

### SizeOk

If a database that previously had size problems (small or large) - but they are not resolved, a notification will be sent out.

## Disabling database monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

```diff
- 'monitor_database' => true,
+ 'monitor_database' => false,
```
