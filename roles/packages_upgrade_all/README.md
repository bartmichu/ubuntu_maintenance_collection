# packages_upgrade

This Ansible role upgrades all installed packages on Ubuntu systems using `apt`. It also captures a summary of the upgrade process.

## Description

The `packages_upgrade` role uses the `ansible.builtin.apt` module to upgrade all installed packages to their latest available versions.

The role registers the output of the upgrade command and extracts a summary line containing information about upgraded packages. This summary is stored in the `umc_upgrade_summary` host fact.

## Requirements

- Target hosts must be Ubuntu-based systems with APT package management.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role doesn't use any variables.
