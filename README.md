
# Ansible Role:  `paperless`

Ansible role to install and configure [paperless-ngx](https://github.com/paperless-ngx/paperless-ngx).


[![GitHub Workflow Status](https://img.shields.io/github/actions/workflow/status/bodsch/ansible-paperless/main.yml?branch=main)][ci]
[![GitHub issues](https://img.shields.io/github/issues/bodsch/ansible-paperless)][issues]
[![GitHub release (latest by date)](https://img.shields.io/github/v/release/bodsch/ansible-paperless)][releases]
[![Ansible Downloads](https://img.shields.io/ansible/role/d/bodsch/paperless?logo=ansible)][galaxy]

[ci]: https://github.com/bodsch/ansible-paperless/actions
[issues]: https://github.com/bodsch/ansible-paperless/issues?q=is%3Aopen+is%3Aissue
[releases]: https://github.com/bodsch/ansible-paperless/releases
[galaxy]: https://galaxy.ansible.com/ui/standalone/roles/bodsch/paperless/

## Requirements & Dependencies

Ansible Collections

- [bodsch.core](https://github.com/bodsch/ansible-collection-core)
- [bodsch.docker](https://github.com/bodsch/ansible-collection-docker) (min. version: 1.2.0)
- [bodsch.scm](https://github.com/bodsch/ansible-collection-scm)

```bash
ansible-galaxy collection install bodsch.core
ansible-galaxy collection install bodsch.docker
ansible-galaxy collection install bodsch.scm
```
or
```bash
ansible-galaxy collection install --requirements-file collections.yml
```

## tested operating systems

* ArchLinux
* Debian based
    - Debian 12
    - Ubuntu 22.04

## usage


```yaml
paperless_version: 2.14.7

paperless_release: {}

paperless_direct_download: false

paperless_user:
  owner: paperless
  group: paperless
  home: /home/paperless

paperless_install_path: "/opt/paperless"

paperless_service:
  state: started
  enabled: true
  command: "docker compose"

paperless_compose_networks: []
  # - name: paperless
  #   state: present
  #   enable_ipv6: false
  #   ipam:
  #     driver: default
  #     config:
  #       - subnet: "172.10.10.0/24"

paperless_compose_services: []
  # - name: broker
  #   image: docker.io/library/redis:7
  #   restart: unless-stopped
  #   volumes:
  #     - redisdata:/data

paperless_compose_volumes: []
  # - name: redisdata

paperless_config:
  usermap:
    uid: ""                             # 1000
    gid: ""                             # 1000
  url: ""                               # https://paperless.example.com
  secret_key: ''                        # change-me
  time_zone: ''                         # Europe/Berlin
  ocr_languages: []
    # - deu
    # - eng
  ocr_default_language: ''              # deu
```


## Contribution

Please read [Contribution](CONTRIBUTING.md)

## Development,  Branches (Git Tags)

The `master` Branch is my *Working Horse* includes the "latest, hot shit" and can be complete broken!

If you want to use something stable, please use a [Tagged Version](https://github.com/bodsch/ansible-paperless/-/tags)!

---

## Author and License

- Bodo Schulz

## License

[Apache](LICENSE)

**FREE SOFTWARE, HELL YEAH!**

