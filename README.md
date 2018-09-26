# Ansible Tower PoC for Cisco NX-OSv

The purpose of project are...
1. How to do automated integration with Red Hat Ansible Tower and Cisco NX-OSv
2. Provide sample playbooks based on nxos ansible modules

## Ansible Playbook Features
- [x] Test reachability
- [x] Backup switch configuration
- [x] Show version

## Ansible Tower Workflow Screenshot

## Validation

```
$ ansible-playbook show_version.yml
PLAY [nxos] ***********************************************************************************************************************************************************************************

TASK [Run show version on remote devices] *****************************************************************************************************************************************************
Thursday 27 September 2018  00:33:52 +0800 (0:00:00.045)       0:00:00.045 ****
ok: [n9k-1.pichuang.local]
ok: [n9k-2.pichuang.local]

TASK [Print result] ***************************************************************************************************************************************************************************
Thursday 27 September 2018  00:33:55 +0800 (0:00:02.550)       0:00:02.595 ****
ok: [n9k-1.pichuang.local] => {
    "msg": {
        "changed": false,
        "failed": false,
        "stdout": [
            {
...
...

PLAY RECAP ************************************************************************************************************************************************************************************
n9k-1.pichuang.local       : ok=2    changed=0    unreachable=0    failed=0
n9k-2.pichuang.local       : ok=2    changed=0    unreachable=0    failed=0

Thursday 27 September 2018  00:33:55 +0800 (0:00:00.156)       0:00:02.752 ****
===============================================================================
Run show version on remote devices ----------------------------------------------------------------------------------------------------------------------------------------------------- 2.55s
Print result --------------------------------------------------------------------------------------------------------------------------------------------------------------------------- 0.16s

```

## Pre-requisites
- Cisco NS-OSv 7.0.3 or 9.2.11
- Red Hat Ansible Tower
- Git Server for version control (e.g GitHub)
- Develop environment for write-up Ansible playbook. Please check the section `Installation` for more detais

## Installation
1. Install Ansible from Red Hat repository
2. Clone repos `git clone https://github.com/pichuang/ansible-nxos-poc`
3. Install all dependencies by running `pip install -r requirements.txt`
4. (Optional) For security issue, you can encryt the secrect file via `ansible-vault encrypt/decrypt`

## References
- [GitHub - jedelman8/nxos-ansible](https://github.com/jedelman8/nxos-ansible)
- [NETWORK DEVICE AUTHENTICATION WITH ANSIBLE 2.3](https://www.ansible.com/blog/network-device-authentication-with-ansible-2-3)
- [NXOS Platform Options](https://docs.ansible.com/ansible/2.6/network/user_guide/platform_nxos.html#example-nx-api-group-vars-nxos-yml)
- [Ansible Modules - NXOS](https://docs.ansible.com/ansible/devel/modules/list_of_network_modules.html#nxos)
