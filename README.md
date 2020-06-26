
[![Build Status](https://travis-ci.org/open-io/ansible-role-openio-tuned.svg?branch=20.04)](https://travis-ci.org/open-io/ansible-role-openio-tuned)
# Ansible role `tuned`

- install tuned
- activate openio profile

## Requirements

- Ansible 2.9+

## Role Variables


| Variable   | Default | Comments (type)  |
| :---       | :---    | :---             |
| `openio_tuned_configname` | `tuned.conf` | file name in openio_tuned_sysconfig_dir |
| `openio_tuned_cpu` | `"{{ cpu_performance }}"` | dict of settings CPU |
| `openio_tuned_disk` | `"{{ disk_rotational }}"` | dict of settings DISK |
| `openio_tuned_package_upgrade` | `"{{ openio_package_upgrade | d(false) }}"` | Set the packages to the latest version (to be set in extra_vars) |
| `openio_tuned_profile_name` | `openio` | Name of the tuned profile |
| `openio_tuned_redis_hosts` | `"{{ groups['redis'] | d([]) }}"` | Ansible group of hosts for the redis backend |
| `openio_tuned_scsi_host` | `"{{ scsi_host_performance }}"` | dict of settings SCSI HOST |
| `openio_tuned_sysconfig_dir` | `/etc/tuned/openio` | Folder of the profile openio_tuned_configname |
| `openio_tuned_sysctl` | `"{{ sysctl_standard_redis }}"` | dict of settings SYSCTL |
| `openio_tuned_vm` | `"{{ vm_thp_madvise }}"` | dict of settings VM |


## Dependencies

No dependencies.

## Example Playbook

```yaml
- hosts: all
  become: true

  roles:
    - role: tuned
```


```ini
[all]
node1 ansible_host=192.168.1.173
```

## Contributing

Issues, feature requests, ideas are appreciated and can be posted in the Issues section.

Pull requests are also very welcome.
The best way to submit a PR is by first creating a fork of this Github project, then creating a topic branch for the suggested change and pushing that branch to your own fork.
Github can then easily create a PR based on that branch.

## License

GNU AFFERO GENERAL PUBLIC LICENSE, Version 3

## Contributors

- [Cedric DELGEHIER](https://github.com/cdelgehier) (maintainer)
