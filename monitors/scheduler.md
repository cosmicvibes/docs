# Scheduler monitor

Eyewitness will automatically detect all scheduled cron jobs in your application and begin to monitor them. Each scheduled cron job can have different alerts and configurations applied to ensure they are monitored correctly.


## History

A list of history of each cron job, including the run time and exit status of the job is available. If you are allowing cron output to be captured, that will also be available for you to review if needed. You can keep an eye on the overall trend times of each job, to make sure they are running as expected.


## Notifications

The Scheduler monitor has a number of different notifications it can send out

### Error

If your schedule job exits with a "non-zero" exit status, Eyewitness will send you an alert that the job failed. You can review the history of the cron job to see any output, along with your log files, to determine what the problem was.

### Missed

Eyewitness knows when each scheduled job *should* run. In the event a job does not run (for any reason) - you will be notified. This could be an indication that the scheduler itself has stopped working, or that a particular job is not able to run anymore due to a change in configured times.

### Overdue

If a cron job starts to execute, but takes a long time and never sends a signal that it has completed, an Overdue notification will be sent out. There are two possibilites here;

The first possibility is the job failed, but in a way that it never notified Laravel of the problem. This is rare, but could occur (such as during a server reboot).

The second possibiltiy is the job is still actually running, but has significatnly exceed all expectations. Unfortunately it is not easy to determine if that has occured - but your logs might give an indication of any problems. If the job does eventually complete, you will be notified. If this becomes a regular occurance - you can set the `slow` notification time to be larger, as this is used to help guide the expectations of how long a job might run for.

### Fast

If a cron job runs faster than your configured alert threshold, you will be notified, including how long the job actually took to run. You can set the threshold for fast notifications on each cron job, to make sure it is appropriate for that schedule. You can also set the threshold to `0` to disable the alert for that scheduled job.

### Slow

If a cron job runs slower than your configured alert threshold, you will be notified, including how long the job actually took to run. You can set the threshold for slow notifications on each cron job, to make sure it is appropriate for that schedule. You can also set the threshold to `0` to disable the alert for that scheduled job.

### Working

Once a scheduled cron job that was previously failing is now working again, you will be notified.


## Updating scheduled jobs

A safety feature of Eyewitness is any changes to a scheduled cron job will not remove the old configuration. It will instead duplicate the scheduled job to its own monitor, leaving the old monitor to eventually "fail" when it is not run.

This is a very intended safety feature. The reason is to ensure you do not accidentilly remove or change a scheduled job you did not intend for. For example, can you imagine if you accidentilly changed your daily backup to be a yearly backup by mistake? With Eyewitness, you would know this has occured.


## "Unnamed Closure" cron jobs

In order to be able to identify each scheduler cron job as it is running, Eyewitness uses the Laravel computed `mutex`. Each mutex is unique, but requires a description or name to be generated. Typically all schedule jobs have this, however if you are running a `Closure` based schedule command - you might need to manually add a name to the job to allow Eyewitness to identify it.

Jobs that appear in your Scheduler list as `Unnamed Clourse` - then you should add a `->name('example')` to the end of your schedule job. Each name should be unique, and will be used to identify that specific closure job.


## Disabling Scheduler monitor

You can disable this monitor by modifying your `config/eyewitness.php` file:

    - 'monitor_scheduler' => true,
    + 'monitor_scheduler' => false,

*note*: Even if you disable the scheduler monitor - you must still run the scheduler for Eyewitness to be able to monitor the other parts of your application.
