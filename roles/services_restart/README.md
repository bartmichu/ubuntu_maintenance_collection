# services_restart

This Ansible role restarts services on the target system that require a restart, using `needrestart`.

## Description

The `services_restart` role uses the `needrestart` utility to identify and restart services that require it (i.e. after package upgrades or other system changes).

## Requirements

- Target hosts must have `needrestart` installed.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role does not use any variables.
