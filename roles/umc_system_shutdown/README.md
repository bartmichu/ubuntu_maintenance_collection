# umc_system_shutdown

## Description

Shuts down the target system.

## Role Variables

This role uses the following input variables:

- `umc_system_shutdown_delay`: The delay in seconds before the system shuts down. This should be an integer. Defaults to: `0`.

- `umc_system_shutdown_message`: The message to be displayed to users before the system shuts down. Defaults to: `System shutting down, initiated by Ansible.`.

This role sets the following host facts:

- `_umc_global_shutdown_successfull`
