# umc_user_key_add

Add an SSH public key to a user's authorized_keys on Ubuntu systems.

## Description
This role installs a public key into the user's authorized_keys. It can optionally make the provided key the only authorized key (exclusive mode).

## Requirements

- Ansible must be able to execute commands with `become` privileges.
- Ansible (core) with ansible.posix collection (authorized_key).
- Control node must have access to the public key file path provided (lookup performed on control node).

## Role variables

- `umc_user_key_add_username` (string) — Username to manage. Default: `""` (required).

- `umc_user_key_add_pubkey_path` (string) — Absolute path on the control node to the public key file (`*.pub`) to authorize for this user. Default: `""` (required).

- `umc_user_key_add_is_exclusive` (bool) — If `true`, replace the user's authorized_keys with only the provided key. If `false`, append the key if not already present. Default: `false`.
