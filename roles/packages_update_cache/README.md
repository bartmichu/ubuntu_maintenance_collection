# packages_update_cache

This Ansible role updates the APT package repositories cache on Ubuntu systems.

## Description

The `packages_update_cache` role uses the `ansible.builtin.apt` module to refresh the local cache of available packages from the configured APT repositories. This ensures that subsequent package installation or upgrade tasks have access to the latest package information.

## Requirements

- Target hosts must be Ubuntu-based systems with APT package management.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role does not use any variables.
