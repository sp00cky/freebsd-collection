# freebsd-collection
[![galaxy](https://img.shields.io/badge/dynamic/json?style=flat&label=galaxy&prefix=v&url=https://galaxy.ansible.com/api/v3/collections/charlesrocket/freebsd/&query=highest_version.version)](https://galaxy.ansible.com/ui/repo/published/charlesrocket/freebsd/)
[![CI](https://github.com/charlesrocket/freebsd-collection/actions/workflows/ci.yml/badge.svg)](https://github.com/charlesrocket/freebsd-collection/actions/workflows/ci.yml)

Ansible collection for FreeBSD servers and desktops.

### Installation

`requirements.yml`:

```yaml
collections:
  - name: charlesrocket.freebsd
```

### Usage

See [profiles](https://charlesrocket.github.io/freebsd-collection/docsite/profiles)/[variables](https://github.com/charlesrocket/freebsd-collection/tree/trunk/profiles/charlesrocket).

## Example

<img src="assets/screenshot.png" alt="screenshot" width="900"/>

```sh
# run as user
ansible-galaxy collection install charlesrocket.freebsd
```

This fetches the profile variables from the github repo, defined in
'playbooks/station.yml:20', as long the profile name defined in the 
extra variable for ansible playbooks (-e) does **not** start with a "/".

```sh
ansible-playbook charlesrocket.freebsd.station -c \
    local -i "localhost," -e "profile=bigmac"
```

You can pass also more than one extra variable (-e) to the ansible playbook,
if you fetch the profile variables from github.

```sh
ansible-playbook charlesrocket.freebsd.station -c \
    local -i "localhost," -e "profile=bigmac" -e "profile_version=awesome"
```

If you want load the profile variables from a local folder (... -e "profile=/bigmac"),
no more extra variables can be passed.

  - If you pass just the foldername, all `.yml`, `.yaml` will be read and loaded.
    ```sh
    ansible-playbook charlesrocket.freebsd.station -c \
        local -i "localhost," -e "profile=/bigmac"
    ```
  - You can pass also a specific file name instead.
    ```sh
    ansible-playbook charlesrocket.freebsd.station -c \
        local -i "localhost," -e "profile=/bigmac/awesome.yml"
    ```
