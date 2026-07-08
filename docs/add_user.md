# add_user playbook

This playbook creates or updates a local user account, installs an SSH public key (controls whether other authorized keys are preserved), optionally restricts SSH access by source IP, and can grant administrative (sudo) access, including passwordless sudo.

Can be run on newly provisioned servers, before they are fully integrated into your Ansible infrastructure, to bootstrap a dedicated Ansible user account.

Configuration details are obtained either through user prompts or by using values supplied via inventory. Ehe extra variables flag (`--extra-vars`) can be used as well.

## Examples

```shell
eval $(ssh-agent -s)
ssh-add ~/.ssh/keyfile
ansible-playbook --inventory "root@10.0.0.2," --ssh-common-args="-o ForwardAgent=yes -o IdentityFile=~/.ssh/keyfile" add_user.yaml --extra-vars "@vars_ansible_user.yaml"
```

## Requirements

- Target hosts must be Ubuntu systems.

- This playbook relies on the following roles:
  - `umc_user_add`

## License

This playbook is licensed under [MIT License](https://opensource.org/licenses/MIT).
