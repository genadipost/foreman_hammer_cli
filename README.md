Role Name
=========

Ansible role to install and configure [hammer-cli](https://github.com/theforeman/hammer-cli).
The role is based on [kostyrev role](https://github.com/kostyrev/ansible-role-foreman-hammer_cli).

Requirements
------------

Role Variables
--------------

| Name    | Description    | Required    | Default    | Values | Examples |
|:--|:--|:-:|:-:|:-:|:--|
| fetch_certificates | should the foreman ca be fetched | No | True | - | - |
| foreman_hammer_cli_config_group | Please fill the description. | No | root | - | - |
| foreman_hammer_cli_config_host_url | foreman server address | Yes | https://localhost/ | - | - |
| foreman_hammer_cli_config_mode | hammer cli config file mode | No | 416 | - | - |
| foreman_hammer_cli_config_owner | hammer cli config file owner | No | root | - | - |
| foreman_hammer_cli_config_password | hammer cli user password | No | changeme | - | - |
| foreman_hammer_cli_config_path | hammer cli config file path | No | /etc/hammer/cli.modules.d | - | - |
| foreman_hammer_cli_config_path_suffix | - | No |  | - | - |
| foreman_hammer_cli_config_refresh_cache | Check API documentation cache status on each request | No | false | - | - |
| foreman_hammer_cli_config_request_timeout | API request timeout | No | 120 | - | - |
| foreman_hammer_cli_config_username | hammer username | No | admin | - | - |
| foreman_hammer_cli_config_verify_ssl | hammer config file | No | true | - | - |

Dependencies
------------

* `genadipost.foreman_repositories`

Example Playbook
----------------

```yml
- hosts: localhost
  roles:
    - { role: genadipost.foreman_repositories, foreman_repositories_version: latest }
    - role: genadipost.foreman_hammer_cli
      foreman_hammer_cli_config_path: '~/.hammer/cli.modules.d'
      foreman_hammer_cli_config_host_url: https://localhost/
      foreman_hammer_cli_config_username: admin
      foreman_hammer_cli_config_password: admin
```

License
-------

BSD

Author Information
------------------

genadipost@gmail.com
