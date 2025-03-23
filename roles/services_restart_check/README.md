# services_restart_check

This Ansible role uses `needrestart` to identify services that require a restart and registers them as a host fact.

## Description

The `services_restart_check` role leverages the `needrestart` utility to determine which services need to be restarted after system changes (like kernel updates or library upgrades).

The role sets a host fact `umc_services_to_restart` with the names of the services.

## Requirements

- Target hosts must have `needrestart` installed.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role doesn't use any variables.
