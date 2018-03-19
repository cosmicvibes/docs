# Changelog

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
