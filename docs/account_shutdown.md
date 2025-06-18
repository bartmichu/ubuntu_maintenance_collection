# account_shutdown playbook

This playbook automates the creation and configuration of a dedicated, restricted user account designed solely for initiating system shutdowns via SSH.

## Requirements

- Target hosts must be Ubuntu systems.

- Following variables must be set: `umc_shutdown_account_name`, `umc_shutdown_account_key_path`, `umc_shutdown_account_allowed_ip`.

## Variables

The playbook uses the following variables:

- `umc_shutdown_account_name`: The desired username for the shutdown account (cannot be "root").

- `umc_shutdown_account_key_path`: The absolute path to the public key (`.pub` file) that will be authorized for this account.

- `umc_shutdown_account_allowed_ip`: The IP address from which this account is permitted to connect via SSH.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
