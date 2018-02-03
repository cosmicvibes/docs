# Database monitor

As everyone would know - you should **never** enable `debug` mode on your production server. Doing so puts your application at significant risk of compromise.

Eyewitness automatically monitors your application to make sure debug mode is never enabled on your production server.


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


## Configuration

You can read more about configuring your `composer.lock` location [here](configuration\general.md#database)


## Disabling database monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

    - 'monitor_database' => true,
    + 'monitor_database' => false,
