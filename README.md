# Ansible Role: Exegol  ([Ludus](https://ludus.cloud))

An Ansible role that installs [Exegol](https://docs.exegol.com/) *free* on a Debian based machines.
Quite useful when some operations cannot be performed over the WireGuard VPN and require an offensive machine in the range.

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
      - ludus_exegol
```

## Why exegol ?

Exegol is a Docker-based penetration testing platform designed to create isolated, reproducible, and customizable environments for security assessments. It is one of my go-to environments for internal pentesting, as it provides the latest [security tools](https://docs.exegol.com/images/tools).

Unlike Kali, it relies on Docker, allowing the creation of fully segregated environments for different clients without the need to duplicate entire Kali machines. This makes it easy to deploy and manage multiple testing environments efficiently.

Exegol also maintains a common baseline that can be centrally upgraded to meet the team's needs, ensuring consistency and efficiency across all users.

**Skeptic?** Give it a go in Ludus. Exegol is packed with useful features :smirk: 

![alt text](resources/Figure-4.png)

## Exegol License Notice

This role automates installation of [Exegol](https://exegol.com/) via `pipx`.
Exegol is governed by the [Exegol Software License (ESL)](https://raw.githubusercontent.com/ThePorgs/Exegol/refs/heads/master/LICENSE.md).

- **Non-commercial use** (research, learning, CTF): free
- **Commercial use** (pentesting engagements for clients): requires an Exegol subscription

## License

GPLv3

## Author Information

This role was created by [hugojcqs](https://github.com/hugojcqs), for [Ludus](https://ludus.cloud/).
