# reboot_conditionally playbook

This playbook performs a system reboot on Ubuntu systems only when necessary and allowed. It checks for conditions that require a reboot (e.g., kernel updates, package updates requiring a restart, or service restarts requiring a reboot) and then proceeds with the reboot only if explicitly allowed.

Define `umc_reboot_allowed` and `umc_services_reboot` appropriately before running the playbook. This is typically done at the playbook level, command line, or in an inventory file.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `packages_update_cache`
  - `packages_needrestart`
  - `system_reboot_check`
  - `services_restart_check`
  - `system_reboot`

## Variables

- `umc_reboot_allowed`: A boolean variable that controls whether the system is allowed to reboot. Set to true to allow reboots, and false to prevent them. Defaults to: `false`.

- `umc_services_reboot`: A boolean indicating if a reboot is required due to service restarts. Defaults to: `false`.

- This playbook als relies on facts set by the included roles.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
