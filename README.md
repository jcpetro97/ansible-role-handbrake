
# Ansible Role: Handbrake

This role installs Handbrake using the stebbins PPA.

## Requirements

None.

## Role Variables

Variables are located in `defaults/main.yml`:

```yaml
handbrake_repo_debian: ppa:stebbins/handbrake-releases
handbrake_gtk_packege: handbrake-gtk
handbrake_cli_packege: handbrake-cli
handbrake_repo_desired_state: present
handbrake_desired_state: present

```

|Variable | Value (default)| Description|
|---------| ---------------| -----------|
|handbrake_repo_debian| `ppa:stebbins/handbrake-releases`  | Handbrake PPA|
|handbrake_gtk_packege|`handbrake-gtk`| This is the gui-based handbrake package|
|handbrake_cli_packege|`handbrake-cli`| This is the cli-based handbrake package|
|handbrake_repo_desired_state| `present`|Desired state of the repo.  It can be either present or absent|
|handbrake_desired_state| `present`|Desired state of the package.  It can be present,latest or absent. |

## Dependencies

None

## Example Playbook

Default role execution

```yaml
- hosts: all
  roles:
    - Handbrake
```

Install the latest version of Handbrake.

```yaml
- hosts: all
  roles:
    - Handbrake
  vars:
    handbrake_desired_state: latest
```

How to remove Handbrake packages

```yaml
- hosts: servers
  roles:
    - Handbrake
  vars:
    handbrake_desired_state: absent
```

