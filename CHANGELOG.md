# System Core (`system-core`) - Change log

All notable changes to this role will be documented in this file.
This role adheres to [Semantic Versioning](http://semver.org/spec/v2.0.0.html).

Remember: Make sure to update system_core_barc_role_version variable when a new version is released.

## [Unreleased][unreleased]

## 0.3.0 - 14/06/2016

### Added

* Improved local fact checking for BARC manifest
* Added dependency on system-groups role to ensure secondary groups needed by system-users role will exist

### Fixed

* Invalid variable value for BARC manifest role name, `-`'s are not allowed
* Minor README typos
* Incorrect variable name in reminder to change the role manifest version variable in the change log

### Changed

* Role refactored to use version 0.3.1 of the Pristine BARC project template

## 0.2.0 - 05/02/2016

### Added

* Guidance notes for using role
* Local facts to record this role has been applied to a system and its version, plus supporting documentation sections
* Missing 'hostname' role for use when testing

### Fixed

* Added missing 'BARC_INSTALL' tag
* Added missing instructions for setting up CI for the master branch
* Testing role dependencies should always use latest versions
* Wording for why we need to pull in dependencies of this role when testing
* Pinning Ansible to pre-2.0 version in CI

### Changed

* Migrating from new Ansible Galaxy namespace, from 'BARC' to 'bas-ansible-roles-collection'
* Migrating from old Ansible Galaxy 'categories' to new 'tags' meta-data
* Migrating from old Repository in 'antarctica' to 'bas-ansible-roles-collection'
* Migrating from old Semaphore 'antarctica' organisation to 'bas-ansible-roles-collection'
* Simplifying CI setup tasks

## 0.1.0 - 01/12/2015

### Added

* Initial version
