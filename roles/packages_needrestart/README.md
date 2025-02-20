# packages_needrestart

This Ansible role installs the `needrestart` utility on Ubuntu systems.

## Description

The `packages_needrestart` role ensures that the `needrestart` utility, used for detecting and managing required service restarts after system updates, is installed on target systems. It also installs the `libpam-systemd` package, which is a dependency for `needrestart` to function correctly, especially within systemd environments.

## Requirements

- Target hosts must be Ubuntu-based systems with APT package management.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role does not use any input variables.
