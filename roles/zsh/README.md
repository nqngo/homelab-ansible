# Ansible Role: zsh

This Ansible role installs the Zsh shell and sets it as the default shell for the ansible user. It also configures `.zshrc` and `.zshenv` with my defaults.

## Requirements

None.

## Role Variables

The role has the following variables:

- `zsh_bin_path`: The path to the Zsh executable. The default value is `/usr/bin/zsh`.
- `zshrc_path`: The path to the `.zshrc` file. The default value is `$HOME/.zshrc`.
- `zshenv_path`: The path to the `.zshenv` file. The default value is `$HOME/.zshenv`.

You can customize these variables to suit your needs by setting them in your playbook.

## Role Defaults

- [`.zshrc`](templates/.zshrc.j2)
- [`.zshenv`](templates/.zshenv.debian.j2)

## Dependencies

None.

## Example Playbook

Here's an example playbook that uses the `zsh` role:

```
- name: Install Zsh shell
  hosts: your_host
  roles:
    - role: zsh
```
