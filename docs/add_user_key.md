# add_user_key interactive playbook

This playbook installs a public key into the user's authorized_keys. It can optionally make the provided key the only authorized key (exclusive mode).

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `umc_user_key_add`

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
