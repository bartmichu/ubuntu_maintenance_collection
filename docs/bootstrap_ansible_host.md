# bootstrap_ansible_host playbook

This playbook automates the bootstrapping of an Ubuntu managed host, configuring a dedicated user account, SSH access, and sudo permissions.

Configuration details are obtained either through user prompts or by using values supplied via the extra variables flag (-e).

## Requirements

- Target hosts must be Ubuntu systems.

## Variables

The playbook uses the following variables, which are prompted from the user:

- `umc_account_name_answer`: The name of the new user account. Defaults to: `ansible`.

- `umc_account_password_answer`: The password for the new user account. Defaults to: random string.

- `umc_key_path_answer`: The path to the public SSH key file (`.pub`).

- `umc_authentication_required_answer`: Whether to require user authentication before running root commands. Defaults to: `True`.

- `umc_allowed_ip_answer`: The IP address allowed for SSH access. Defaults to: `*`.

## Templates

The playbook uses the following templates:

- `sudoers.j2`: Configures sudo permissions for the new user.
- `sshd.j2`: Configures the SSH server settings.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
