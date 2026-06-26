# reboot_conditionally playbook

This playbook performs a system reboot on Ubuntu systems only when necessary and allowed. It checks for conditions that require a reboot (e.g., kernel updates, package updates requiring a restart, or service restarts requiring a reboot) and then proceeds with the reboot only if explicitly allowed.

Define `umc_global_allow_reboot` and `umc_global_services_require_reboot` appropriately before running the playbook. This is typically done at the playbook level, command line, or in an inventory file.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `umc_packages_update_cache`
  - `umc_packages_needrestart`
  - `umc_system_reboot_check`
  - `umc_services_restart_check`
  - `umc_system_reboot`

## Variables

- `umc_global_allow_reboot`: A boolean variable that controls whether the system is allowed to reboot. Set to true to allow reboots, and false to prevent them. Defaults to: `false`.

- `umc_global_services_require_reboot`: A boolean indicating if a reboot is required due to service restarts. Defaults to: `false`.

- This playbook also relies on facts set by the included roles.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
