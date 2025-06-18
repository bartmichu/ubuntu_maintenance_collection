# bartmichu.ubuntu_maintenance - Ubuntu Maintenance Collection

This Ansible Collection provides playbooks for managing Ubuntu systems, including package upgrades, service restarts, and system reboots. These playbooks are designed to be modular and reusable, leveraging Ansible roles for specific tasks.

## Requirements

* Ansible Core 2.10 or later.
* Target hosts must be Ubuntu systems.

## Installation

You can install this collection from Ansible Galaxy:

```bash
ansible-galaxy collection install bartmichu.ubuntu_maintenance
```

## Playbooks

This collection includes the following playbooks:

* `bootstrap_ansible_host.yaml`
  Performs automated bootstrapping of an Ansible-managed host.

* `check_state.yaml`
  Checks the state of an Ubuntu system, including available package upgrades (security and regular), services requiring a restart, and whether a system reboot is needed. Provides a summary of the findings. (See `docs/check_state.md` for more details).

* `reboot_conditionally.yaml`
  Performs a system reboot only when necessary (due to pending updates or service restarts requiring a reboot) and when explicitly allowed via the `umc_reboot_allowed` variable. (See `docs/reboot_conditionally.md` for more details).

* `reboot_unconditionally.yaml`
  Performs an unconditional system reboot. Use with caution! (See `docs/reboot_unconditionally.md` for more details).

* `services_restart.yaml`
  Restarts services that require it, using the `needrestart` utility. Performs a check before and after attempting the restarts to identify which services were successfully restarted and which still require attention. (See `docs/services_restart.md` for more details).

* `shutdown_unconditionally.yaml`
  Performs an unconditional system shutdown. Use with caution! (See `docs/shutdown_unconditionally.md` for more details).

* `upgrade_all_reboot.yaml`
  Updates all upgradeable packages (including security updates) and reboots the system if necessary and allowed. (See `docs/upgrade_all.md` for more details).

* `upgrade_all.yaml`
  Updates all upgradeable packages (including security updates). Checks for required reboots and service restarts and reports on them. (See `docs/upgrade_all.md` for more details).

* `upgrade_security.yaml`
  Installs available security updates. Checks for required reboots and service restarts and reports on them. (See `docs/upgrade_security.md` for more details).

## Roles

See the individual role directories for their respective `README.md` files for more detailed information.

## Variables

Several playbooks in this collection use variables. Please refer to the documentation for each playbook for specific variable requirements. A key variable used across many playbooks is `umc_reboot_allowed`, which controls whether reboots are permitted, as well as `umc_services_reboot` and `umc_services_restart_allowed`.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
