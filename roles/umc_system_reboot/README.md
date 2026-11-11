# umc_system_reboot

## Description

Reboots the target system.

## Role Variables

This role uses the following input variables:

- `umc_system_reboot_delay`: The time in seconds to wait after the reboot before continuing. Defaults to: `10`.

This role sets the following host facts:

- `_umc_global_reboot_successfull`
