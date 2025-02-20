# system_reboot_check

This Ansible role checks if a system reboot is required.

## Description

The `system_reboot_check` role checks for the existence of the `/var/run/reboot-required` file. This file is often created by package managers or other system tools after operations that require a reboot (e.g., kernel updates).

The role sets the `ubuntu_reboot_needed` host fact to `true` if the file exists, and `false` if it doesn't.

## Requirements

- Target hosts must be Linux systems that use the `/var/run/reboot-required` file to indicate a required reboot.

## Role Variables

This role does not use any input variables.
