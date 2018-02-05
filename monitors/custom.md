# Custom monitor

Custom monitors are super powerful, and one of the most exciting features of Eyewitness.

You can create *fully* integrated monitors into Eyewitness, which are seemless and act and appear as if they are one of the standard monitors. This means Eyewitness can grow with you and your application, to monitor literally anything you can think of.

All you need is to write a small PHP script of what you want to monitor, and Eyewitness will handle everything else, including sending notifications and tracking the trend of the job over time.

We've tried to make custom monitors as simple as possible out of the box, but if delve into the underlying class, you'll see some extra options available for advanced requirements.

## How to make

Lets say you want to make a monitor, to check if a 3rd party API is online. Lets use `Spotify` as an example.

### 1. Create a monitor using our new built in `make` command:

    php artisan make:witness Spotify

A new class will be created at `app\Eyewitness\Spotify.php`. *Note: you are welcome to move this anywhere - you are not restricted and can use any location or namespace that suits you.*

Once you open the `app\Eyewitness\Spotify.php` file - you'll see a list of stubs with sensible defaults taken care of.

### 2. Set a display name

The `$displayName` is used to give your custom monitor a pretty name to be used throughout the website and notifications.

```diff
- public $displayName = 'My Witness';
+ public $displayName = 'Spotify Monitor';
```

### 3. Set an icon

Custom monitors have a default icon. But you can pick from over 75 different icons, allowing you to have an icon that best represents your monitor.

```diff
- public $icon = 'parking-sensors';
+ public $icon = 'check-simple';
```

### 4. Set a schedule

You can now set the frequency you want this monitor to run. We use the same schedule logic as cron jobs - so you have the full power to define how often you want to monitor your system.

Lets set this example to be once per hour:

```diff
- public $schedule = '* * * * *';
+ public $schedule = '0 * * * *';
```

### 5. Set the run() logic

This is the last and easy bit - simply place your monitoring logic into the `run()` function. You are free to do *anything* that you want inside this function. Simply return `true` for a pass and return `false` for a fail. In addition any uncaught exceptions will also be treated as a fail.

```diff
public function run()
{
- //
+ // place your PHP logic here
}
```

### 6. Track the monitor value (optional)

Sometimes just knowing if a monitor is "up" or "down" is not enough. Using our Spotify example, lets assume we also want to try the time the API took to respond. This can be useful to display on a graph over time, which Eyewitness will handle for you automatically.

To include a value in your monitor - simply include the following somewhere inside of your `run()` command:

```diff
+ $this->setValue(5);
```

We've used `5` as an example here - but you can place any `numeric` number there.


## Registering a custom monitor to Eyewitness

So you've made a custom monitor. Lets use the `Spotify` example from above.

To add it simply modify your `config/eyewitness.php` file like this:

```diff
- 'custom_witnesses' => [],
+ 'custom_witnesses' => [
+      \App\Eyewitness\Spotify::class,
+ ],
```

You can add multiple custom monitors as well, even from different namespaces (so you can create your own packages to share):

```diff
- 'custom_witnesses' => [],
+ 'custom_witnesses' => [
+      \App\Eyewitness\Spotify::class,
+      \App\Eyewitness\Websocket::class,
+      \My\Package\Example\Printer::class,
+ ],
```

Once the custom monitor(s) are registered - you can log into your Eyewitness dashboard and they should appear in your menu immediately.

*Note: dont forget to run `php artisan config:cache` if you have that enabled, to ensure your settings are updated.*

## Notifications

The Custom monitor will send one of two notifications.

### Failed

If your custom monitor was healthy, and becomes sick, you will receive a notification from Eyewitness.

### Passed

If your custom monitor was sick, and becomes healthy, you will get a Passed notification from Eyewitness.

## Status Hooks

You can hook into the lifecycle when your monitor is switching health status for the first time.

### Failing Hook

If your custom witness fails for the first time (i.e. switches from a healthy status to a sick status) - you can add some additional code you want to run. *Remember: Eyewitness will automatically notify you, so you do not need to duplicate that functionality.*

```diff
* /**
+  * @return void
+  */
+ public function failing()
+ {
+     // your logic here
+ }
```

### Recovering Hook

If your custom witness recovers for the first time (i.e. switches from a sick status to a healthy status) - you can add some additional code you want to run. *Remember: Eyewitness will automatically notify you, so you do not need to duplicate that functionality.*

```diff
* /**
+  * @return void
+  */
+ public function recovering()
+ {
+     // your logic here
+ }
```

## Share the love

Got a new custom monitor your wrote? Interested in sharing it to other users of Eyewitness?

We are in the early stages of adding a free marketplace area of example custom monitors. Tweet a gist, or email us a copy at "feedback@eyewitness.io", and we'll add it to the growing list (your name and credit will be included of course).
