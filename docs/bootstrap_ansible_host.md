# bootstrap_ansible_host playbook

This playbook automates the bootstrapping of an Ubuntu managed host, configuring a dedicated user account, SSH access, and sudo permissions. It's designed to be run on newly provisioned servers before they are fully integrated into your Ansible infrastructure.

Configuration details are obtained either through user prompts or by using values supplied via the extra variables flag (-e).

## Usage

Generate authentication key for new account:

```shell
ssh-keygen -t ed25519 -f ~/.ssh/keyfile
```

Examples:

```shell
ansible-playbook --key-file ~/.ssh/keyfile --inventory "root@10.0.0.2," bootstrap_ansible_host.yml

ansible-playbook --ask-pass --inventory "root@10.0.0.1," bootstrap_ansible_host.yml --extra-vars "@bootstrap_vars.yml"

ansible-playbook --ask-become-pass --key-file ~/.ssh/keyfile --inventory "hostname," bootstrap_ansible_host.yml

ansible-playbook --ask-pass --ask-become-pass --inventory "username@10.0.0.1," bootstrap_ansible_host.yml
```

## Requirements

- Target hosts must be Ubuntu systems.

## Variables

The playbook uses the following variables, which are prompted from the user:

- `umc_account_name_answer`: The name of the new user account. It's required to use a name other than `root`. Defaults to: `ansible`.

- `umc_account_password_answer`: The password for the new user account. Defaults to: random string.

- `umc_key_path_answer`: The path to the public SSH key file (`.pub`) that will be used for SSH authentication.

- `umc_authentication_required_answer`: Whether to require user authentication before running root commands. Defaults to: `True`.

- `umc_allowed_ip_answer`: The IP address allowed for SSH access. Use * to allow all IPs (less secure, use with caution). Defaults to: `*`.

## Templates

The playbook uses the following templates:

- `sudoers.j2`: Configures sudo permissions for the new user.
- `sshd.j2`: Configures the SSH server settings.

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
