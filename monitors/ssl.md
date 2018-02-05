# SSL monitor

Using your configured domains, Eyewitness will keep an eye on your SSL configuration.

The SSL checks are performed with the assistance of the wonderful people at www.htbridge.com - who's SSL API is used. This API will ensure your certificate is valid, in date, and monitor the "grade" given.

This check occurs once per hour. The exact time is configured by the package during the installation, to help keep the load balanced and even on the API.


## Notifications

The SSL monitor will send out a number of different alerts.

### Expiring

If your SSL certificate is due to expire shortly, Eyewitness will send out *one* warning of the upcoming expiration. You should take steps to ensure it is renewed before the expiration date.

### Invalid

If your certificate is marked invalid by the API during the scan, Eyewitness will send out a notification. You should action this urgently, as users will likely be affected.

### Revoked

If your certificate has been revoked (for any reason), Eyewitness will send out a notification. You should action this urgently, as users will likely be affected.

### Grade Change

One of the great features provided by [www.htbridge.com](https://https://www.htbridge.com/ssl/) is a "grade" (or score) for your SSL configuration. This grade can be used to not only ensure your certificate is valid, but that it is configured properly. This includes when new vulnerabilities are found in the future, your configuration might need updating.

A score ranges from A+ all the way down to F. In the event your SSL certificate score changes, you will be notified. You are able to look at your score on the Eyewitness dashboard, and there will always be a link to the [www.htbridge.com](https://https://www.htbridge.com/ssl/) API with the full results report page.

If your score drops suddenly, you should investigate further, as it may be an early sign of a server error, or of a new public vulnerability that your application is exposed to.


## Configuring domains

You can read more about configuring your monitored SSL domains [here](\configuration\general.md#domains)


## Disabling SSL monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

```diff
- 'monitor_ssl' => true,
+ 'monitor_ssl' => false,
```
