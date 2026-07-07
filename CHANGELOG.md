# Changelog

This changelog begins at version 3.2.0 and lists only subsequent major, breaking changes.

## 4.0.0

- Remove the `user_shutdown_add` playbook, as it was just a wrapper for a single role.

- Rename `account_shutdown` role to `user_shutdown_add`.

- Prefix all role names with `umc` (Ubuntu Maintenance Collection) to prevent namespace conflicts.

- Prefix all variable names with `umc` (Ubuntu Maintenance Collection) to prevent namespace conflicts.

- Rename `bootstrap_ansible_host` playbook to `bootstrap_ansible_user`.

- Add `global` to global variable names.

## 5.0.0

- Rename `umc_user_add_password` to `umc_user_add_password_hash`.

- Rename `umc_user_add_key_path` to `umc_user_add_pubkey_path`.

- Remove the `bootstrap_ansible_user` playbook. Use the universal `add_user` playbook instead.
