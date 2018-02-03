# Notifications

Eyewitness has the ability to send multiple notifications using different drivers.


## Recipients

When on your Eyewitness dashboard, simply go to the settings option in the top right corner of your package. Here you can see a list of current recipients. Click the "new recipient" button to add another to the list.

You are able to choose from a number of different notification drivers, such as Email, Slack, Pushover etc. Choose the one that is suitable for you, and follow the instructions given.

Each recipient is also given the option which message severity notices they will receive. See below for more information.

By combining severity options with recipients, you can make inteliigent alerting. For example, you might set an "email" recipient to receive low, medium and high alerts. But then you set a "pushover" and "SMS" recipient for "high" alerts only.

### Test Message

Once you have configured your recipient(s) - you able send a `Test Message` notification to ensure the recipient is configured correctly and able to recieve alerts from Eyewitness. Simply click the hamburger icon on the far right of the recipient, and click "send test".


## Message severity

No two notifications are the same. You might want to be alerted and jump out of bed at 3am if your web server goes down, but you dont want your sleep disturbed if you SSL certificate is due to expire in 2 weeks.

Eyewitness allows you to customise the "severity" of each notification it sends. There are sensible defaults out of the box that should suit most situations, but you are free to change these yourself. When on your Eyewitness dashboard, simply go to the settings option in the top right corner of your package, and you'll see the severity configuration option.

By overriding the defaults you can choose which alerts you want to get out of bed for at 3am, and which ones you are happy to wait until you are ready.


## Remote

If you have a paid remote subscription, your local package will also alert the remote server if there is a problem. Your remote notification settings will be used **in addition** to your local settings.

So for most installations - the best option is to leave your local configuration recipients empty, and configure a master list on the remote server.

However you are free to include some addition local recipients. This might be useful if you want to have a specific notification for a certain user on a single application only.
