# Ansible Role: Exegol  ([Ludus](https://ludus.cloud))

An Ansible role that installs [Exegol](https://exegol.readthedocs.io/en/latest/the-exegol-project/python-wrapper.html) on a Debian or Ubuntu machine.


## Requirements
- You need to supply a valid Exegol [image](https://exegol.readthedocs.io/en/latest/the-exegol-project/docker-images.html) name for this to be successful.

## Role Variables

Available variables are listed below, along with default values (see `defaults/main.yml`):
    
    # valid images: full, ad, web, light, osint, nightly
    image_to_install: "ad"

## Dependencies

None.

## Example Ludus Range Config

```yaml
ludus:
  - vm_name: "{{ range_id }}-exegol"
    hostname: "{{ range_id }}-exegol"
    template: debian-12-x64-server-template
    vlan: 20
    ip_last_octet: 2
    ram_gb: 4
    cpus: 4
    linux: true
    testing:
      snapshot: false
      block_internet: false
    roles:
      - hugojcqs.ludus_exegol
    role_vars:
      image_to_install: "ad"
```

## Why exegol ?

Exegol is a Docker-based penetration testing platform designed to create isolated, reproducible, and customizable environments for security assessments. It is one of my go-to environments for internal pentesting, as it provides the latest [security tools](https://exegol.readthedocs.io/en/latest/exegol-image/tools.html) and ensures a [reproducible](https://hub.docker.com/r/nwodtuhs/exegol/tags) setup for clients.

Unlike Kali, it relies on Docker, allowing the creation of fully segregated environments for different clients without the need to duplicate entire Kali machines. This makes it easy to deploy and manage multiple testing environments efficiently.

Exegol also maintains a common baseline that can be centrally upgraded to meet the team's needs, ensuring consistency and efficiency across all users.

**Skeptic?** Give it a go in Ludus. Exegol is packed with useful features :smirk: 

![alt text](resources/Figure-4.png)

## License

GPLv3

## Author Information

This role was created by [hugojcqs](https://github.com/hugojcqs), for [Ludus](https://ludus.cloud/).
