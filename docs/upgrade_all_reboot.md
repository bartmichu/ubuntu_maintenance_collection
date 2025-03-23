# upgrade_all_reboot playbook

This playbook updates all upgradeable packages (including security updates) on Ubuntu systems and reboots the system if necessary and allowed. It leverages several roles to perform the update process, including checking for required reboots and service restarts.

Define `umc_reboot_allowed` and `umc_services_reboot` appropriately before running the playbook. This is typically done at the playbook level, command line, or in an inventory file.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `packages_update_cache`
  - `packages_needrestart`
  - `packages_upgrade_check`
  - `packages_upgrade_all`
  - `system_reboot_check`
  - `services_restart_check`
  - `system_reboot`

## Variables

- `umc_reboot_allowed`: A boolean variable that controls whether the system is allowed to reboot. Set to true to allow reboots, and false to prevent them. Defaults to: `false`.

- `umc_services_reboot`: A boolean indicating if a reboot is required due to service restarts. Defaults to: `false`.

- This playbook als relies on facts set by the included roles.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
