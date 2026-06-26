# check_state playbook

This playbook checks the state of an Ubuntu system, including available package upgrades (security and regular), services requiring a restart, and whether a system reboot is needed. It leverages several roles to perform these checks and provides a summary of the findings.

This playbook is designed to be a check only. It does not perform any actual updates or reboots. Separate playbooks should be used for those actions.

Define `umc_global_allow_reboot` and `umc_global_services_require_reboot` appropriately before running the playbook. This is typically done at the playbook level, command line, or in an inventory file.

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `umc_packages_update_cache`
  - `umc_packages_needrestart`
  - `umc_packages_upgrade_check`
  - `umc_services_restart_check`
  - `umc_system_reboot_check`

## Variables

- `umc_global_allow_reboot`: A boolean variable that controls whether the system is allowed to reboot. Set to true to allow reboots, and false to prevent them. Defaults to: `false`.

- `umc_global_services_require_reboot`: A boolean indicating if a reboot is required due to service restarts. Defaults to: `false`.

- This playbook also relies on facts set by the included roles.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
