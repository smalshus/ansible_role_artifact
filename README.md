# Amtega issue role

This is an [Ansible](http://www.ansible.com) role to download several kinds or artifacts. Currently http/https and gitlab/github artifacts are supported.

## Requirements

[Ansible 2.6+](http://docs.ansible.com/ansible/latest/intro_installation.html)

## Role Variables

A list of all the default variables for this role is available in `defaults/main.yml`.

For each artifact the role setups a fact named `artifact_result_<artifactid>` with the following structure:

{
  download_path: <path to the downloaded artifact>
}

## Dependencies

None.

## Example Playbook

This is an example playbook:

``` yaml
---
- name: artifact role sample
  hosts: localhost
  roles:  
    - amtega.artifact
  vars:
    artifact:
      name: myartifact
      type: gitlab
      url: https://mygitlab.org/path_to_artifact/artifact.tar.gz
      dest: /tmp
      private_token: my_gitlab_private_token
```

## Testing

Tests are based on docker containers. You can setup docker engine quickly using the playbook `files/setup.yml` available in the role [amtega.docker_engine](https://galaxy.ansible.com/amtega/docker_engine).

Once you have docker, you can run the tests with the following commands:

```shell
$ cd amtega.artifact/tests
$ ansible-playbook main.yml
```

## License

Copyright (C) 2018 AMTEGA - Xunta de Galicia

This role is free software: you can redistribute it and/or modify
it under the terms of:
GNU General Public License version 3, or (at your option) any later version;
or the European Union Public License, either Version 1.2 or – as soon
they will be approved by the European Commission ­subsequent versions of
the EUPL;

This role is distributed in the hope that it will be useful,
but WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
GNU General Public License for more details or European Union Public License for more details.

## Author Information

- Juan Antonio Valiño García.
