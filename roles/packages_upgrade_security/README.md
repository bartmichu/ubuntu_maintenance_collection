# packages_upgrade_security

This Ansible role installs available security upgrades on Ubuntu systems.

## Description

The `packages_upgrade_security` role identifies and installs security upgrades.

The role captures the output of the upgrade process and extracts a summary line which is stored as a `umc_upgrade_summary` host fact.

## Requirements

- Target hosts must be Ubuntu-based systems with APT package management.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role does not use any input variables.
