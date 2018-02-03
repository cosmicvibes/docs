# Load balanced applications

Eyewitness supports applications that run over multiple servers.


## Deploying Eyewitness to a load balanced server cluster

Eyewitness should be installed and configured in your development environment as you would for any changes to your code. Then deploy your changes to all servers as part of your deployment process.

Each server should have the same `EYEWITNESS_APP_TOKEN` and `EYEWITNESS_SECRET_KEY` used. If you have a paid subscription, each server should also have the same `EYEWITNESS_SUBSCRIPTION_KEY` on all.

Dont forget to ensure you run `config:cache`, `route:cache` and `queue:restart` after deploying to production if you use those features, to ensure Eyewitness is correctly loaded by your production environment.


## Caching for multiple load balanced applications

Eyewitness uses the built in Laravel caching system to perform some of the functions. If you are running a load balanced application across multiple servers, Eyewitness requires your cache to be single shared across all instances.

This is a typical configuration for load balanced applications, so it is likely you already have this by default.
