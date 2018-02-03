# Debug monitor

As everyone would know - you should **never** enable `debug` mode on your production server. Doing so puts your application at significant risk of compromise.

Eyewitness automatically monitors your application to make sure debug mode is never enabled on your production server.


## Notifications

The debug monitor will only send out one of two alerts:

### Enabled

If Eyewitness detects `debug` mode has been enabled on your produciton server - it will send out an immediate alert.

### Disabled

Once `debug` mode has been correctly disabled on your production server, Eyewitness will send a notification to let you know everything is ok now.


## Disabling debug monitor

At this stage it is not possible to disable the debug monitor. Realistically there is never a reason to have it enabled on production.
