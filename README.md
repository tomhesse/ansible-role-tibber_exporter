Role Name
=========

An Ansible Role that installs the [Tibber Exporter](https://github.com/terjesannum/tibber-exporter) on Linux.

Requirements
------------

None.

Role Variables
--------------

Available variables are listed below, along with default values (see defaults/main.yml):

    tibber_exporter_version: 3.6.4

Version that will be installed.

    tibber_exporter_binary_local_dir: ""

Local binary that will be installed instead of the remote one.

    tibber_exporter_binary_url: "https://github.com/{{ _tibber_exporter_repo }}/releases/download/tibber-exporter-{{ tibber_exporter_version }}/                           tibber-exporter-{{ tibber_exporter_version }}-linux-{{ go_arch }}.tar.gz"

Remote location of the binary.

    tibber_exporter_skip_install: false

Skip installation and only manage the configuration.

    tibber_exporter_binary_install_dir: "/usr/local/bin"
    tibber_exporter_system_group: "tibber-exp"
    tibber_exporter_system_user: "{{ tibber_exporter_system_group }}"

Tibber Exporter installation options.

    tibber_exporter_archive_path: "/tmp"

Download location for the binary.

Dependencies
------------

None.

Example Playbook
----------------

```yaml
- hosts: all
  roles:
    - role: tomhesse.tibber_exporter
      vars:
        tibber_exporter_api_token: "Your-Tibber-API-Token"
```

License
-------

MIT / BSD

Author Information
------------------

This role was created in 2024 by [tomhesse](https://www.tomhesse.xyz/).
