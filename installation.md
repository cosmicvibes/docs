# Installation guide

## 1. Install via composer

Add the package to your `composer.json` file

    composer require eyewitness/eye


## 2. Add to providers (Laravel 5.4 or below)

If you are running Laravel 5.5 or higher you can skip this step.

If you are running Laravel 5.4 or less, you then need to add the Eyewitness service provider to your `config/app.php` providers array:

    Eyewitness\Eye\EyeServiceProvider::class,


## 3. Run installer

Now just run the package installer which will handle everything out of the box:

    php artisan eyewitness:install

You might need to clear your config cache and restart your queues for the changes to take effect. The installer will detect this and advise what is required.


## 4. Config

That is it. Eyewitness is now installed and running. There are a few optional configuration choices you can make at `config/eyewitness.php`.

You should also log into the package at `www.yourdomain.com/eyewitness` and set some notification recipients.


## Upgrading from an older version of Eyewitness?

Due to the significant changes from the previous package versions, the simplest and safest way to upgrade from v1 or v2 is remove the old package, delete the old configuration file at `config\eyewitness.php` - and then follow the installation guidelines above.

