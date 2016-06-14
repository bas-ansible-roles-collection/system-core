# System Core (`system-core`)

Master: [![Build Status](https://semaphoreci.com/api/v1/bas-ansible-roles-collection/system-core/branches/master/badge.svg)](https://semaphoreci.com/bas-ansible-roles-collection/system-core)
Develop: [![Build Status](https://semaphoreci.com/api/v1/bas-ansible-roles-collection/system-core/branches/develop/badge.svg)](https://semaphoreci.com/bas-ansible-roles-collection/system-core)

Meta role for including roles related to system setup and security

**Part of the BAS Ansible Role Collection (BARC)**

**This role uses version 0.3.1 of the BARC flavour of the BAS Base Project - Pristine**.

## Overview

* Meta role for including roles related to system setup and security

## Quality Assurance

This role uses manual and automated testing to ensure its features work as advertised.
See [here](tests/README.md) for more information.

## Ansible compatibility

* this role supports Ansible 1.8 or higher in the 1.x series
* this role supports Ansible 2.x

**Note:** Support for Ansible 1.x is deprecated by this role, future versions will support Ansible 2.x only.

More information on Ansible compatibility is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Ansible-compatbility).

## Dependencies

* [**bas-ansible-roles-collection.system-users**](https://galaxy.ansible.com/bas-ansible-roles-collection/system-ssh/)
  * Minimum version: *0.2.0*
* [**bas-ansible-roles-collection.system-hostname**](https://galaxy.ansible.com/bas-ansible-roles-collection/system-ssh/)
  * Minimum version: *0.1.1*
* [**bas-ansible-roles-collection.system-security**](https://galaxy.ansible.com/bas-ansible-roles-collection/system-ssh/)
  * Minimum version: *0.1.0*

More information on role dependencies is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-dependencies)

## Requirements

* none

More information on role requirements is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-requirements)

## Limitations

* none

More information on role limitations is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-limitations)

## Usage

### BARC Manifest

By default, BARC roles will record that they have been applied to a system, this is termed the BAS Manifest.
The specific local facts set for this role are:

* `ansible_local.barc_system_core.general.role_applied` - (boolean) records whether a role has been applied
* `ansible_local.barc_system_core.general.role_version` - (string) records the version of the role that was applied

**Note:** You **SHOULD** use this feature to determine whether this role has been applied to a system.
If you do not want these facts to be set by this role, you **MUST** skip the **BARC_SET_MANIFEST** tag.

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Role-Manifest)

### Avoid listing this role as a dependency in other roles

This role is concerned with configuring a machine to a base state. In some cases this is not desirable such as when 
running within a CI or other managed environment.

For this reason this role **SHOULD NOT** be listed as a direct dependency of other roles. Instead this role should be
listed *alongside* other roles in a playbook. This ensures users can *opt-in* to this role where desired, rather than
forcing users to *opt-out* which is more complex.

### When to use this role

This role **SHOULD** be used on machines provisioned by BAS, except where advised not to be BAS ICT. This is to ensure
all machines follow minimum conventions for networking and security. Other users may use this role as they see fit.

Due to the nature of this role it is recommended to apply this role first within playbooks.

E.g.

```yaml
- name: setup web-servers
  hosts: all
  become: yes
  vars: []
  roles:
    - bas-ansible-roles-collection.system-core
    - bas-ansible-roles-collection.nginx
```

### What are meta-roles

More information is available in the 
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Meta-roles).

### Typical playbook

```yaml
---

- name: ...
  hosts: all
  become: yes
  vars: []
  roles:
    - bas-ansible-roles-collection.system-core
```

### Tags

BARC roles use standardised tags to control which aspects of an environment are changed by roles.
Tasks in this role will 'tag' themselves with these tags as appropriate, typically in `tasks/main.yml`.

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Appendix-B---BARC-Standardised)

### Variables

#### *system_core_barc_role_name*

* **MUST NOT** be specified
* specifies the name of this role within the BAS Ansible Roles Collection (BARC) used for setting local facts
* see the *BARC roles manifest* section for more information
* example: `system_core`

#### *system_core_barc_role_version*

* **MUST NOT** be specified
* specifies the name of this role within the BAS Ansible Roles Collection (BARC) used for setting local facts
* see the *BARC roles manifest* section for more information
* example: `2.0.0`

## Developing

### Issue tracking

Issues, bugs, improvements, questions, suggestions and other tasks related to this package are managed through the
[BAS Ansible Roles Collection](https://jira.ceh.ac.uk/projects/BARC) (BARC) project on Jira.

This service is currently only available to BAS or NERC staff, although external collaborators can be added on request.
See our contributing policy for more information.

More information is also available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Issue-Tracking)

### Source code

All changes should be committed, via pull request, to the canonical repository:

`ssh://git@stash.ceh.ac.uk:7999/barc/system-core.git`

A read-only mirror of this repository is maintained on GitHub:

`git@github.com:bas-ansible-roles-collection/system-core-NAME.git`

More information is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Source-Code)

### Contributing policy

This role welcomes contributions, see `CONTRIBUTING.md` for our general policy.

### Release procedure

The general release procedure for BARC roles is available in the
[BARC General Documentation](https://antarctica.hackpad.com/BARC-Overview-and-Policies-SzcHzHvitkt#:h=Release-procedures)

## Licence

Copyright 2016 NERC BAS.

Unless stated otherwise, all documentation is licensed under the Open Government License - version 3.
All code is licensed under the MIT license.

Copies of these licenses are included within this role.
