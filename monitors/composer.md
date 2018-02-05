# Composer monitor

Eyewitness will check your `composer.lock` file for any packages and versions that contain publically known vulnerabilities.

This check is performed against the SensioLabs security API (with their permission). You can read more about the security API here: https://security.sensiolabs.org/

The API check will occur once per day. The exact time of this check is dynamically set during your installation. This is to help spread the load to the SensioLabs API evenly throughout the day.


## Notifications

The composer monitor will only send out one of two alerts:

### Risk

In the event an issue with your composer file is detected, a `Risk` notification will be sent. You can view the details of the package with the known vulnerability on your Eyewitness dashboard. You should consider upgrading the affected package, or switching to another solution.

### Safe

Once your `composer.lock` file is fixed and no longer contains any know vulnerabilities, a `Safe` notification will be sent to confirm everything is ok now.


## Configuration

You can read more about configuring your `composer.lock` location [here](configuration\general.md#composer.lock)


## Disabling composer monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

```diff
- 'monitor_composer' => true,
+ 'monitor_composer' => false,
```
