logrotate Cookbook CHANGELOG
============================
This file is used to list changes made in each version of the
logrotate cookbook.

v2.2.0
------
# Compatibility Notes

The `compat_resource` dependency was removed. This means we now
require Chef 12.5 or higher. It also means we now better support Chef
13.

# Enhancements

- The global configuration now supports scripts.
- The package install action (upgrade by default) is now configurable
  via an attribute.
- The development environment now more closely follows modern cookbook
  practices.

# Bug Fixes

- ChefSpec matcher now correctly calls ChefSpec.define_matcher.
-
# Contributors

- Austin Heiman
- Baptiste Courtois
- Bogdan Katynski
- Thomas Dziedzic
- Tim Smith

v2.1.0
------

# Bug Fixes

- Restore `cookbook` parameter for `logrotate_app` resource due to
  popular demand.

- Add a `template_name` parameter to replace the 1.x `template`
  parameter. The name `template` can't be used inside a resource
  without conflicting with an attribute of the same name.

- Fix exception when `options` specified as a string rather than an
  array

v2.0.0
------

- Convert the logrotate_app definition to a resource
- Accept all options included in logrotate 3.9.2

# Known incompatibilities

- The `cookbook` parameter to `logrotate_app` is no longer accepted.


v1.9.2
------

## Bug Fixes

- Fix deprecation warnings from ChefSpec

v1.9.1
------

## Bug Fixes

- Fixes regression in the sharedscripts logrotate_app
  parameter (Bug #69)

v1.9.0
------

### Improvements

- All configuration options from the logrotate 3.8.8 manual page can
be used by the global configuration and the logrotate_app
definition.

- Berkshelf is no longer a development dependency of the
logrotate cookbook.

- Rubocop lint failures have been resolved.




v1.8.0
------

### Resolved Bugs

- `su` parameter now supported in global config.

### Improvements

- firstaction and lastaction attributes documented in the README
- rotate attribute documented in the README
- Use hash-rocket syntax in rspec matcher to maintain 1.9 support.

v1.7.0
------

### Bugs

- Use `raise` rather than Application.fatal! to prevent killing a
  daemonized chef-client

### Improvements

- Chefspec matcher for logrotate_app definition
- Support the following options: compressoptions, maxage,
  shred/shredcycles, extension, tabooext
- Add Solaris support


v1.6.0
------

### Bugs

- Fix documentation error

### Improvements

- Support for options "compresscmd", "uncompresscmd", "compressext"
- Allow nodateext as parameter for logrotate_app definition
- Move to chefspec ~> 3.0

v1.5.0
------

### Bugs
- Fix missing end tag in template
- Don't re-initialize constants.
- Fix rubocop finding

### Improvements
- [COOK-3911] Allow to use maxsize parameter.
- [COOK-4000] Allow to use dateyesterday option.
- [COOK-4024] Allow to use su parameter.
- [COOK-4175] Allows use of the dateformat parameter.
- Loosen test-kitchen version constraint
- Add rvm files to gitignore


v1.4.0
------
### Bug
- **[COOK-3632](https://tickets.chef.io/browse/COOK-3632)** - Raise Exception when adding more than one invalid option
- **[COOK-3141](https://tickets.chef.io/browse/COOK-3141)** - Do not duplicate template entires for multiple paths
- **[COOK-3034](https://tickets.chef.io/browse/COOK-3034)** - Update logrotate_app params to accept arrays and strings

### Improvement
- **[COOK-2646](https://tickets.chef.io/browse/COOK-2646)** - Add ability to choose file mode for logrotate template

v1.3.0
------
### Improvement
- **[COOK-3341](https://tickets.chef.io/browse/COOK-3341)** - Add optional `frequency` and `rotate` params when defined globally
- **[COOK-3298](https://tickets.chef.io/browse/COOK-3298)** - Use `Array` instead of `respond_to?(:each)`
- **[COOK-3285](https://tickets.chef.io/browse/COOK-3285)** - Change `logrotate.d` config file mode to `0644`
- **[COOK-3250](https://tickets.chef.io/browse/COOK-3250)** - Add `minsize`

### Bug
- **[COOK-3274](https://tickets.chef.io/browse/COOK-3274)** - Fix README typo that suggested the opposite action

### New Feature
- **[COOK-2923](https://tickets.chef.io/browse/COOK-2923)** - Add `olddir` option
- **[COOK-1651](https://tickets.chef.io/browse/COOK-1651)** - Add `dateext` ability

v1.2.2
-----
### Bug
- [COOK-2872]: Add firstaction/lastaction ability to logrotate
- [COOK-2908]: Argument error in `logrotate_app` definition

v1.2.0
-----
- [COOK-2401] - Add the ability to manage the global logrotate configuration

v1.1.0
-----
- [COOK-2218] - Logrotate size parameter

v1.0.2
-----
- [COOK-1027] - Add support for pre-/post-rotate commands
- [COOK-1338] - Update log rotate for more flexibility of rotate options
- [COOK-1598] - "Create" isn't a mandatory option
