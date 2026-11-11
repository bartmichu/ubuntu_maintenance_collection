# umc_user_shutdown_add

## Description

Creates a restricted user dedicated to system shutdown.

## Role Variables

This role uses the following input variables:

- `umc_user_shutdown_add_name`: The desired username for the shutdown account (cannot be "root"). Defaults to: `""`, which is not a valid value.

- `umc_user_shutdown_add_key_path`: The absolute path to the public key (`.pub` file) that will be authorized for this account. Defaults to: `""`, which is not a valid value.

- `umc_user_shutdown_add_allowed_ip`: The IP address from which this account is permitted to connect via SSH. Defaults to: `"*"`.
