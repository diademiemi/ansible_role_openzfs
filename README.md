Ansible Role OpenZFS
=========

[![Molecule Test](https://github.com/diademiemi/ansible_role_openzfs/actions/workflows/molecule.yml/badge.svg)](https://github.com/diademiemi/ansible_role_openzfs/actions/workflows/molecule.yml)

This is an Ansible role to install and configure openzfs.

For Debian-based distros, a working DKMS is assumed.

Requirements
------------
These platforms are supported:
- Ubuntu 20.04
- Ubuntu 22.04
- Debian 10
- Debian 11
- Debian 12
- EL 8 (Tested on Rocky Linux 8)
- EL 9 (Tested on Rocky Linux 9)
- Fedora 38
- openSUSE Leap 15.5

<!--
- List hardware requirements here  
-->

Role Variables
--------------

Variable | Default | Description
--- | --- | ---
`openzfs_enable_load_keys_service` | `false` | Enable the `zfs-load-key.service` service
<!--
`variable` | `default` | Variable example
`long_variable` | See [defaults/main.yml](./defaults/main.yml) | Variable referring to defaults
`distro_specific_variable` | See [vars/debian.yml](./vars/debian.yml) | Variable referring to distro-specific variables
-->

Dependencies
------------
<!-- List dependencies on other roles or criteria -->
None

Example Playbook
----------------

```yaml
- name: Use diademiemi.openzfs role
  hosts: "{{ target | default('openzfs') }}"
  roles:
    - role: "diademiemi.openzfs"
      tags: ['diademiemi', 'openzfs', 'setup']    ```

```

License
-------

MIT

Author Information
------------------

- diademiemi (@diademiemi)

Role Testing
------------

This repository comes with Molecule that run in Podman on the supported platforms.
Install Molecule by running

```bash
pip3 install -r requirements.txt
```

Run the tests with

```bash
molecule test
```

These tests are automatically ran by GitHub Actions on push. If the tests are successful, the role is automatically published to Ansible Galaxy.

