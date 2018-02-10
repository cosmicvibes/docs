# Requirements

## System

In order to run Eyewitness you require:

- Laravel 5.1 or higher
- PHP 5.6 or higher
- A database (any type)
- Cache (any type)


## Scheduler

Eyewitness requires the Laravel scheduler cron is running in order to perform some of the tests (even if you do not want to monitor the scheduler itself). You do not need to make any changes to your scheduler - Eyewitness will handle this automatically. Please see the Laravel documentation here for further information if you do not already have a scheduler configured.


## Guzzle

Eyewitness will automatically include Guzzle during installation if you do not already have it (depending upon your composer configuration).
