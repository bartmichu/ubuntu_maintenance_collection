# restart_services playbook

This playbook restarts services on Ubuntu systems that require it, using the `needrestart` utility. It performs a check before and after attempting the restarts to identify which services were successfully restarted and which still require attention.

Define `umc_global_allow_services_restart` appropriately before running the playbook. This is typically done at the playbook level, command line, or in an inventory file.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `umc_packages_update_cache`
  - `umc_packages_needrestart`
  - `umc_services_restart_check`
  - `umc_services_restart`

## Variables

- `umc_global_allow_services_restart`: A boolean variable that controls whether the services are allowed to be restarted. Set to true to allow service restarts, and false to prevent them.

- This playbook also relies on facts set by the included roles.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
