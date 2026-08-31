# bartmichu.ubuntu_maintenance - Ubuntu Maintenance Collection

This Ansible Collection provides playbooks for managing Ubuntu servers.

## Installation

You can install this collection from Ansible Galaxy:

```bash
ansible-galaxy collection install bartmichu.ubuntu_maintenance
```

## Playbooks

This collection includes the following playbooks:

* `add_user.yml`
  
  Adds and configures a local user account with SSH key and optional sudo privileges.
  Can be run on newly provisioned servers, before they are fully integrated into your Ansible infrastructure, to bootstrap a dedicated Ansible user account. See `docs/add_user.md` for more details.

* `add_user_key.yml`

  Installs a public key into the user's authorized_keys. It can optionally make the provided key the only authorized key (exclusive mode). See `docs/add_user_key.md` for more details.

* `check_state.yml`
  Checks the state of an Ubuntu system, including available package upgrades (security and regular), services requiring a restart, and whether a system reboot is needed. Provides a summary of the findings. See `docs/check_state.md` for more details.

* `reboot_conditionally.yml`
  Performs a system reboot only when necessary (due to pending updates or service restarts requiring a reboot) and when explicitly allowed via the `umc_global_allow_reboot` variable. See `docs/reboot_conditionally.md` for more details.

* `reboot_unconditionally.yml`
  Performs an unconditional system reboot. Use with caution! See `docs/reboot_unconditionally.md` for more details.

* `services_restart.yml`
  Restarts services that require it, using the `needrestart` utility. Performs a check before and after attempting the restarts to identify which services were successfully restarted and which still require attention. See `docs/services_restart.md` for more details.

* `shutdown_unconditionally.yml`
  Performs an unconditional system shutdown. Use with caution! See `docs/shutdown_unconditionally.md` for more details.

* `upgrade_all_reboot.yml`
  Updates all upgradeable packages (including security updates) and reboots the system if necessary and allowed. See `docs/upgrade_all.md` for more details.

* `upgrade_all.yml`
  Updates all upgradeable packages (including security updates). Checks for required reboots and service restarts and reports on them. See `docs/upgrade_all.md` for more details.

* `upgrade_security.yml`
  Installs available security updates. Checks for required reboots and service restarts and reports on them. See `docs/upgrade_security.md` for more details.

## Roles

See the individual role directories for their respective `README.md` files for more detailed information.

## Variables

Several playbooks and roles in this collection use variables, some of them are global. Please refer to the documentation for each role or playbook for specific variable requirements.

## Requirements

* Supported OS: Ubuntu 22.04 LTS, Ubuntu 24.04 LTS, Ubuntu 26.04 LTS
* Ansible Core: 2.15.0+

## License

This collection is licensed under the [MIT License](LICENSE).
