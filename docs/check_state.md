# check_state playbook

This playbook checks the state of an Ubuntu system, including available package upgrades (security and regular), services requiring a restart, and whether a system reboot is needed. It leverages several roles to perform these checks and provides a summary of the findings.

This playbook is designed to be a check only. It does not perform any actual updates or reboots. Separate playbooks should be used for those actions.

Define `umc_reboot_allowed` and `umc_services_reboot` appropriately before running the playbook. This is typically done at the playbook level, command line, or in an inventory file.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `packages_update_cache`
  - `packages_needrestart`
  - `packages_upgrade_check`
  - `services_restart_check`
  - `system_reboot_check`

## Variables

- `umc_reboot_allowed`: A boolean variable that controls whether the system is allowed to reboot. Set to true to allow reboots, and false to prevent them. Defaults to: `false`.

- `umc_services_reboot`: A boolean indicating if a reboot is required due to service restarts. Defaults to: `false`.

- This playbook also relies on facts set by the included roles.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
