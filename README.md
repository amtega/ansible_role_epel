# Ansible EPEL repository role

This is an [Ansible](http://www.ansible.com) role which manages EPEL repository.

## Requirements

- Ansible >= 2.4

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

## Dependencies

None.

## Example Playbook

This is an example playbook:

```yaml
---

- hosts: all
  roles:
    - epel_repository

  vars:
    epel_repository_state: present

    epel_repository_enabled: 1
    epel_repository_debuginfo_enabled: 1
    epel_repository_source_enabled: 1

    epel_repository_testing_enabled: 1
    epel_repository_testing_debuginfo_enabled: 1
    epel_repository_testing_source_enabled: 1
```

## Testing

Test are based on docker containers. You can run the tests with the following commands:

```shell
$ cd epel_repository/test
$ ansible-playbook main.yml
```

If you have docker engine configured you can avoid running dependant 'docker_engine' role (that usually requries root privileges) with the following commands:

```shell
$ cd epel_repository/test
$ ansible-playbook --skip-tags "role::docker_engine" main.yml
```

## License

Not defined.

## Author Information

- Juan Antonio Valiño García ([juanval@edu.xunta.es](mailto:juanval@edu.xunta.es)). Amtega - Xunta de Galicia
