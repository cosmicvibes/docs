# Changelog

## 3.0.0-beta8 - 11th June 2018

### Changed
- Sonar queue checking will no longer artifically inflate the queue counter ([#1623d55](https://github.com/eyewitness/eye/commit/1623d55b9cb364d472458f259004d7f457d0e3cc))
- Improve custom monitor graphs to not include null values ([#12de88b](https://github.com/eyewitness/eye/commit/12de88be5f14be4544c6ad6b73ced88a588d6c67))

### Fixed
- Fixed bug with disabled logins and custom authentication ([#c50bc25](https://github.com/eyewitness/eye/commit/c50bc25dd9cde5ddb4dc64c59900ab431837db3b))
- Fixed OnOneServer support ([#dc10cd3](https://github.com/eyewitness/eye/commit/dc10cd3655298351abbf61159bae49062793b6c9))

## 3.0.0-beta7 - 30th May 2018

### Changed
- Update cron file names to use underscores instead of dashes ([#424d3a8](https://github.com/eyewitness/eye/commit/424d3a8e4b2aaf6bcc253afb172aab7ff37b54e3))

### Fixed
- Updated SSL check due to unexpected API change ([#34e6a1a](https://github.com/eyewitness/eye/commit/34e6a1a989cd6a578363b58262940bc4861d0d57))
- Corrected Slack metadata attachment ([#af5f44e](https://github.com/eyewitness/eye/commit/af5f44e51cfe130baba1452ee1e656af29f690b8))

## 3.0.0-beta6 - 12th May 2018

***If you are using a previous version of the Eyewitness beta - you must run `php artisan migrate` for this patch to update a table***

### Added
- New optional for schedulers, to allow for a window of time for them to run ([see docs](monitors\scheduler.md#conditional-schedules)) ([#3e5aec1](https://github.com/eyewitness/eye/commit/3e5aec1b5c1268582339c384f5e97dfa4be688c6))
- Scheduler history is now paginated for large lists ([#57b1e05](https://github.com/eyewitness/eye/commit/57b1e05ceecb79cad9a002fa7e2c8803db53991b))

### Changed
- Remove unused Queue history loading ([#65289a2](https://github.com/eyewitness/eye/commit/65289a2760710405cd9f327a31dfc7c3e4f294ab))
- Refactor the Scheduler history to be more efficient ([#8f4fb5d](https://github.com/eyewitness/eye/commit/8f4fb5dae833dcc620ae67b75f4c4359963192d2))

### Fixed
- Fix failing Overdue message errors ([PR #33](https://github.com/eyewitness/eye/pull/33))


## 3.0.0-beta5 - 19th March 2018

### Fixed
- Provide better backward support for Laravel 5.1 and Laravel 5.2 ([#02f5ad4](https://github.com/eyewitness/eye/commit/02f5ad4b7c6a70f322897e4f91f62fc981669307))
- Fix a race condition on scheduler working notifications ([#feef36d](https://github.com/eyewitness/eye/commit/feef36d82c0a2cde37bedcf667f7f8ec2bacde56))
- Improve resilience of failed queue payload decoding ([#0fc61e4](https://github.com/eyewitness/eye/commit/0fc61e489481daf57c7979e861497cfe86eb85e9))


## 3.0.0-beta4 - 11th March 2018

### Fixed
- Make SSL checks more resilient to API failures ([#cdbc598](https://github.com/eyewitness/eye/commit/cdbc598693428a8652a179f5ea33a1efe458fa43))
- Make queue connections more resilient to config errors ([#6602a84](https://github.com/eyewitness/eye/commit/6602a84b12769edca90b6e5781bb3cb71b4894a7))
- Fixed relationship on hasOne causing timeouts ([#0df3eb8](https://github.com/eyewitness/eye/commit/0df3eb83bb8d88158486f2973b701951c4c55aca))


## 3.0.0-beta4 - 22nd Feburary 2018

### Fixed
- Fixed scheduler option for Windows servers ([see docs](configuration\general.md#disable-scheduler-background-tasks)) ([#f4fa90d](https://github.com/eyewitness/eye/commit/f4fa90dc976c410475580fbb6da8f5873782496f))

### Added
- New option for disabling default login ([see docs](configuration\authentication.md)) ([#c95b0d8](https://github.com/eyewitness/eye/commit/c95b0d8488d7fffec1f0ea112a7f66a80daa7416))
- Added debug page for better remote support ([#953df48](https://github.com/eyewitness/eye/commit/953df48483ecffd8bcb8c8d85c6295412191b70d))


## 3.0.0-beta3 - 17th Feburary 2018

### Added
- New option for callback authentication ([see docs](configuration\authentication.md)) ([#939e9fc](https://github.com/eyewitness/eye/commit/939e9fcd7e963face3bcf91c6f1e053c39b8a1d))

## 3.0.0-beta2 - 14th Feburary 2018

### Fixed
- Various bug fixes relating to SSL and DNS checks ([#681f41e](https://github.com/eyewitness/eye/commit/681f41e4f3450aa4df6078f93e9df102380603a6))
- Fix debug status on overview page ([#b2f8d2c](https://github.com/eyewitness/eye/commit/b2f8d2ceda7eee1359a46bd540221ab1cff8083f))

## 3.0.0-beta1 - 11th Feburary 2018

###
- Added default lengths to string database tables of 191 to provide full comptability for all drivers ([#2d7eebb](https://github.com/eyewitness/eye/commit/2d7eebbfc96cc22e23978c7e0dfc7eb8c46dcda7))

## 3.0.0-beta - 7th Feburary 2018

### Changed
- version 3.0 of Eyewitness is a complete and total rewrite of the package from the ground up.
