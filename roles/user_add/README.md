# user_add

Add and configure a local user account with SSH key and optional sudo privileges.

## Description

This Ansible role creates or updates a local user account, installs an SSH public key (controls whether other authorized keys are preserved), optionally restricts SSH access by source IP, and can grant administrative (sudo) access, including passwordless sudo.

## Requirements

- Ansible must be able to execute commands with `become` privileges.

## Role Variables

- `user_add_name` (string) — Username to create or manage. Cannot be "root". Default: `""` (required).

- `user_add_password` (string) — Encrypted password hash for the account. Default: `""` (required).

- `user_add_key_path` (string) — Absolute path on the control node to the public key file (`*.pub`) to authorize for this user. Default: `""` (required).

- `user_add_key_is_exclusive` (bool) — If `true`, replace the user's authorized_keys with only the provided key. If `false`, append the key if not already present. Default: `false`.

- `user_add_is_admin` (bool) — If `true`, allow user account to perform administrative tasks with sudo. Default: `false`.

- `user_add_passwordless_sudo` (bool) — If `true` and `user_add_is_admin` is `true`, configure passwordless sudo for this user. Default: `false`.

- `user_add_allowed_ip` (string) — IP (or CIDR) from which SSH connections with the installed key are allowed. Use `"*"` to allow any source. Default: `"*"`.

- `user_add_allow_forwarding` (bool) — Whether to allow agent/port forwarding for the authorized key. Default: `false`.

- `user_add_permit_tty` (bool) — Whether to permit a TTY for the authorized key. Default: `true`.
