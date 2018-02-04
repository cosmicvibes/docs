# General Configuration

Eyewitness comes pre-configured with a range of sensible out of the box options as default. However we provide the ability to change these to suit your individual application requirements.

All changes below are relating to `config/eyewitness.php`


## Base URL

By default the eyewitness package is available at `www.yourdomain.com/eyewitness`. You are able to change the base URI of `eyewitness` to anything else you like. This might be to prevent clashes, or to provide obscurity of information.

    `'base_url' => 'other/example',`


## Eyewitness helper

Throughout the package we will display introductory/helper information on each page to help you navigate your way around. Once you are familar with Eyewitness you can choose to turn these off.

    - 'display_helpers' => true,
    + 'display_helpers' => false,


## Eyewitness history

You can configure the length of time that Eyewitness keeps local history relating to your queues, cron schedulers etc. By default this is set to 45 days. You are welcome to change this to a longer or shorter to suit your needs.

    - 'days_to_keep_history' => 45,
    + 'days_to_keep_history' => 30,


## Configure standard monitoring modules

You can turn off certain parts of the monitoring. For example, if your application does not use queues, you should turn that off.

    'monitor_scheduler' => true,
    'monitor_database' => true,
    'monitor_composer' => true,
    'monitor_queue' => true,
    'monitor_dns' => true,
    'monitor_ssl' => true,


## Eyewitness database storage connection

Eyewitness will create a number of tables to store data it collects. By default the package will use your normal database connection - but you are able to specifiy a specific connection if required.

This means you can keep the Eyewitness data seperate from your application, and seperates your backups, migrations etc.

To setup a new database specifically for Eyewitness to store information, add a new connection to your `config/database.php`, then include the connection name in the eyewitness configuration:

    - 'database_connection' => env('EYEWITNESS_DATABASE_CONNECTION', null),
    + 'database_connection' => 'eyewitness_db,


## Capture cron scheduler output

If your cron schedulers are being monitored, then Eyewitness will capture the output from the cron job by default. This allows you to view the output online at a later stage if needed.

If you set this to false, no cron output will not be captured or stored.

    - 'capture_cron_output' => env('EYEWITNESS_CAPTURE_CRON_OUTPUT', true),
    + 'capture_cron_output' => env('EYEWITNESS_CAPTURE_CRON_OUTPUT', false),


## Domains

During your Eyewitness installation you would have been asked for a domain to monitor. These domain(s) are monitored for SSL and DNS changes.

You can change that choice, and add multiple domains for the one application. This can be useful for subdomain monitoring.

    - 'application_domains' => ['www.yourdomain.com'],
    + 'application_domains' => ['www.yourdomain.com', 'subdomain.yourdomain.com'],


## Databases

If your application uses multiple databases, then you can list them below and each will be monitored to ensure they are online and available.

The array should contain names corresponding to one of the connections listed in your `config/database.php` configuration file. Each database can contain alerts for the size of the database. You can disable size alerts by setting their value to `0`.

*Note:* a null value will simply use the "default" connection - which is sufficient for most applications.

    'database_connections' => [
        [
            'connection' => 'mysql',
            'alert_greater_than_mb' => 500,
            'alert_less_than_mb' => 200,
        ]
    ],

You can monitor multiple database connections as well:


    'database_connections' => [
        [
            'connection' => 'mysql',
            'alert_greater_than_mb' => 500,
            'alert_less_than_mb' => 200,
        ],
        [
            'connection' => 'other_example',
            'alert_greater_than_mb' => 0,
            'alert_less_than_mb' => 0,
        ]
    ],


## Composer.lock

A daily check of your composer.lock file will occur against the SensioLabs Security check at https://security.sensiolabs.org/

You can change the location of your `composer.lock` file. You only need to modify this config if your lock file is in a different location than the default location.

    - 'composer_lock_file_location' => base_path('composer.lock'),
    + 'composer_lock_file_location' => '/path/to/composer.lock',`


## API Proxy

If your application is behind a firewall that requires a proxy to gain access - you can add the proxy details to the config file. This proxy array will be directly passed to Guzzle as a header option, so please refer to the Guzzle documentation on how to configure the proxy headers for your application.

    + `api_proxy` => ['port' => 1234, 'username' => example],
