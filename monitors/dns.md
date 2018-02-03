# DNS monitor

Using your configured domains, Eyewitness will keep an eye on your DNS configuration. In the event any changes are detected, you will be alerted. This can be useful in case of unauthorised changes (including a hack of your DNS provider), or against accidential changes.


## Notifications

The DNS monitor will only send out one alert:

### Change

In the event a change to your DNS is detected, Eyewitness will send you a notification. You can then view the new DNS, along with the history of any previous configurations, on your Eyewitness dashboard.


## Configuring domains

You can read more about configuring your monitored DNS domains [here](configuration\general.md#dns)


## Disabling DNS monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

    - 'monitor_dns' => true,
    + 'monitor_dns' => false,
