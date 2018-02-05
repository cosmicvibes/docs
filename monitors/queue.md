# Queue monitor

Eyewitness will automatically detect all running queues in your application and begin to monitor them. Each queue tube can have different alerts and configurations applied to ensure they are monitored correctly.

## Requirements

The Eyewitness Queue monitor supports all Laravel drivers, including Beanstalkd, SQS, Redis and Database. If you need another driver supported please contact us and we'll look into it.

## History

A list of history of each queue, including average wait times, pending jobs count etc is available. You can keep an eye on the overall trends of each queue, to make sure they are running as expected.


## Notifications

The Queue monitor has a number of different notifications it can send out. All notifications can be customised per "queue" on the respective settings page of each queue.

### Failed

If you queue has a failed job, you will receive a notification from Eyewitness. You can disable failed alerts for individual queues in their respective settings page.

### Offline

If your queue stops sending heartbeats as it processes jobs, Eyewitness will send you an alert. This is most likely due to the queue being stopped (or frozen). However, sometimes due to long running queue jobs, it might be a false message. You can configure the alert heartbeat threshold in the individual queue settings page, to make it longer if needed. By default it is set to 120seconds, which should be sufficient for most applications.

### Online

Once your queue starts processing jobs again, Eyewitness will send you an alert the queue is healthy again.

### FailedCountExceeded

By default this alert is disabled - but you can set a limit on the number of failed jobs you will accept for this queue. Once that limit is reached, Eyewitness will send you an alert.

### FailedCountOk

If you queue was previously unhealthy due to too many failed jobs, we will alert you when the situation is resolved.

### PendingCountExceeded

By default this alert is disabled - but you can set a limit on the number of pending jobs you will accept for this queue. Once that limit is reached, Eyewitness will send you an alert.

### PendingCountOk

If you queue was previously unhealthy due to too many pending jobs, we will alert you when the situation is resolved.

### WaitLong

By default this alert is disabled - but you can set a limit on the length of time jobs can wait before they are processed for this queue. Once that limit is reached, Eyewitness will send you an alert.

### WaitOk

If you queue was previously unhealthy due to too long waiting jobs, we will alert you when the situation is resolved.


## Laravel Horizon

Laravel Horizon is the amazing Redis queue management package put together by Taylor Otwell. Currently Eyewitness is not compatbile with Horizon - but integration is coming shortly. In the meantime if you are already running Horizon, you can simply disable the Eyewitness queue monitor.

In the near future you will be able to have Horizon "power" your queues, and Eyewitness can report on what Horizon is doing from a single interface. Contact us if you would like to assist in the beta testing of this feature soon: support@eyewitness.io.


## Disabling Queue monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

```diff
- 'monitor_queue' => true,
+ 'monitor_queue' => false,
```
