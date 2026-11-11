# umc_system_reboot_check

## Description

Checks if a system reboot is required.

## Requirements

- Target hosts must be Linux systems that use the `/var/run/reboot-required` file to indicate a required reboot.

## Role Variables

This role does not use any input variables.

This role sets the following host facts:

- `_umc_global_reboot_needed`
