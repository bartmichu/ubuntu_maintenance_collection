# system_reboot

This Ansible role reboots the target system.

## Description

The `system_reboot` role uses the `ansible.builtin.reboot` module to initiate a system reboot. It allows you to specify the post reboot delay to allow the system to come back online before proceeding with subsequent tasks.

The role sets a host fact `umc_reboot_successfull` to `true` if the reboot was successful, and `false` otherwise.

## Requirements

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role uses the following variables:

- `umc_post_reboot_delay`: The time in seconds to wait after the reboot before continuing. Defaults to: `10`.
