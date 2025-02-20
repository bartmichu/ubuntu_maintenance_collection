# system_shutdown

This Ansible role gracefully shuts down the target system.

## Description

The `system_shutdown` role uses the `community.general.shutdown` module to initiate a system shutdown. It allows you to specify both the delay before shutdown and a custom message that will be displayed to users.

The role sets a host fact `ubuntu_shutdown_successfull` to `true` if the shutdown was successful, and `false` otherwise.

## Requirements

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role uses the following variables:

- `ubuntu_shutdown_delay`: The delay in seconds before the system shuts down. This should be an integer. Defaults to: `0`.

- `ubuntu_shutdown_message`: The message to be displayed to users before the system shuts down. Defaults to: `System shutting down, initiated by Ansible.`.
