# Ansible Role: oh-my-posh

![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/nqngo/homelab-ansible/role-oh-my-posh.yml?label=molecule&logo=docker)

This Ansible role installs Oh-My-Posh and configures it to be used as the default shell prompt. It supports three CPU architectures: `x86_64`, `aarch64`, and `armhf`.

## Requirements

None.

## Role Variables

The role has the following variables:

- `shellrc_path`: The path to the shell configuration file. The default value is `$HOME/.zshrc`.
- `omp_bin_src`: The URL of the Oh-My-Posh binary. The default value is `"https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/posh-linux-{{ omp_arch }}"`. The script will dheck the CPU architecture and set the `omp_arch` variable accordingly. (`amd64`, `arm64`, `arm`)
- `omp_bin_dest`: The destination path of the Oh-My-Posh binary. The default value is `"/usr/local/bin/oh-my-posh"`.
- `omp_theme_src`: The URL of the Oh-My-Posh themes archive. The default value is `"https://github.com/JanDeDobbeleer/oh-my-posh/releases/latest/download/themes.zip"`.
- `omp_theme_dir`: The path to the Oh-My-Posh themes directory. The default value is `$HOME/.poshthemes`.

You can customize these variables to suit your needs by setting them in your playbook.

## Dependencies

None.

## Example Playbook

Here's an example playbook that uses the `oh-my-posh` role:

```
- name: Install Oh-My-Posh
  hosts: your_host
  roles:
    - role: oh-my-posh
```

## Tasks

Here are the tasks performed by the `oh-my-posh` role:

1. Check the CPU architecture and set the `omp_arch` variable accordingly.
2. Fail if the CPU architecture is not supported.
3. Install Oh-My-Posh by downloading the binary file from the specified URL and setting its permissions.
4. Create the Oh-My-Posh themes directory and set its permissions.
5. Install the Oh-My-Posh themes by downloading the themes archive from the specified URL and extracting it to the themes directory.
6. Copy your own Oh-My-Posh themes to your home directory.
7. Configure the shell to use Oh-My-Posh by adding the necessary options to the shell configuration file.
