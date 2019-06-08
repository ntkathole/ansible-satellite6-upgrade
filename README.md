# Ansible Role for Satellite6 upgrade
Ansible role that helps you to perform Satellite 6 Upgrade.

## Configuration

This role will automatically perform installation/upgrade of foreman-maintain, perform upgrade check and finally upgrade the satellite.

### Variables

* 'distribution': Satellite 6 target version distribution. Options : 'CDN' or 'DOWNSTREAM'
* 'target_version': Target version to upgrade satellite. ex: 6.4.z, 6.5, 6.5.z, 6.6, etc.
* 'whitelist_options': List of labels of steps to be skipped from satellite-maintain. ex: disk-performance
* 'satellite_maintain_state' : State of satellite-maintain rpm. Deafult : latest

### Sample Usage

The following example ensures that satellite 6.4 is upgraded to satellite 6.5.

```ansible
---
- hosts: all
  become: true
  roles:
    - satellite6_upgrade
  vars:
    distribution: 'CDN'
    target_version: '6.5'
    whitelist_options: 'disk-performance"
```
