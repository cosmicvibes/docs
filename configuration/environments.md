# Environments

Eyewitness will intelligently detect the current environment of your application and apply some default rules.


## Local and Testing environments

When your application is running in Local and Testing environment, no notifications will be sent by the package.

This is to ensure that you dont send out false alerts your database was just destroyed, sending your operations team into a panic. At the moment this cannot be overriden by any configuration option.


## All other environments

All other environments will allow for notifications etc to be sent by default.

If you want to disable Eyewitness notifications and remote monitoring (perhaps from a staging server) - you can add `'api_enabled' => false,` to your `config/eyewitness.php` file.

If you have a paid subscription you are able to use the same application token across all your environments (i.e. staging, production etc). Eyewitness will detect which environment your notification came from, and include that on any alerts sent.
