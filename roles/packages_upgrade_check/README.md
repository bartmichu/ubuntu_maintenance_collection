# packages_upgrade_check

This Ansible role checks for available package upgrades, including security upgrades, on Ubuntu systems and registers them as host facts.

## Description

The `packages_upgrade_check` role uses `apt-get --simulate upgrade --verbose-versions` to identify packages that can be upgraded without actually performing the upgrade.

The results are stored in `umc_upgradeable_packages` and `umc_upgradeable_packages_security` host facts for use by other roles or plays. This allows you to separate the check for upgrades from the actual upgrade process, providing more flexibility in how you manage upgrades.

## Requirements

- Target hosts must be Ubuntu-based systems with APT package management.

## Role Variables

This role does not use any input variables.
