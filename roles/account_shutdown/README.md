# account_shutdown

This ansible role creates and configures a dedicated, restricted user account designed solely for initiating system shutdowns via SSH.

## Description

The `account_shutdown` role sets up a restricted user account that can remotely trigger a system shutdown via SSH. It:

- Creates a dedicated user with a secure password.

- Authorizes a specific SSH public key with limited access options.

- Restricts SSH access to a defined IP address.

- Allows passwordless sudo systemctl poweroff for the user.

- Validates inputs to ensure safe and correct configuration.

Ideal for automation tasks or remote-controlled shutdown scenarios.

## Requirements

- Target hosts must be Ubuntu systems.

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

This role uses the following variables:

- `umc_shutdown_account_name`: The desired username for the shutdown account (cannot be "root").

- `umc_shutdown_account_key_path`: The absolute path to the public key (`.pub` file) that will be authorized for this account.

- `umc_shutdown_account_allowed_ip`: The IP address from which this account is permitted to connect via SSH.
