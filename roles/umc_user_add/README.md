# umc_user_add

## Description

Adds and configures a local user account.

## Role Variables

This role uses the following input variables:

- `umc_user_add_name` (string) — Username to create or manage. Cannot be "root". Default: `""` (required).

- `umc_user_add_password_hash` (string) — Encrypted password hash for the account. Default: `""` (required).

- `umc_user_add_pubkey_path` (string) — Absolute path on the control node to the public key file (`*.pub`) to authorize for this user. Default: `""` (required).

- `umc_user_add_key_is_exclusive` (bool) — If `true`, replace the user's authorized_keys with only the provided key. If `false`, append the key if not already present. Default: `false`.

- `umc_user_add_is_admin` (bool) — If `true`, allow user account to perform administrative tasks with sudo. Default: `false`.

- `umc_user_add_sudo_passwordless` (bool) — If `true` and `umc_user_add_is_admin` is `true`, configure passwordless sudo for this user. Default: `false`.

- `umc_user_add_sudo_root_only` (bool) — If `true` and `umc_user_add_is_admin` is `true`, allow running commands via sudo as the root user only. Default: `true`.

- `umc_user_add_allowed_ip` (string) — IP (or CIDR) from which SSH connections with the installed key are allowed. Use `"*"` to allow any source. Default: `"*"`.

- `umc_user_add_allow_forwarding` (bool) — Whether to allow agent/port forwarding for the authorized key. Default: `false`.

- `umc_user_add_permit_tty` (bool) — Whether to permit a TTY for the authorized key. Default: `true`.
