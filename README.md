Signal TLS Proxy Ansible Role
=============================

An all-in-one role designed to deploy [Signal's TLS Proxy](https://github.com/signalapp/Signal-TLS-Proxy) to circumvent government censorship. Installs varius utilities for troubleshooting, Docker-CE from official Docker repositories, fail2ban for SSH, disables password SSH login, and creates and starts the TLS Proxy automatically given your domain name.

Requirements
------------

* Debian-based distribution install (apt only)
* Domain name you own or manage
* SSH keypair for authenticating with your system
    * Passwords for SSH gets disabled unless you use var `allow_pass: true`
* Ideally a fresh system
    * Alternatively, a system not already running Docker or using ports 80 or 443

Role Variables
--------------

| Variable       | Purpose                                                            | Default      |
|----------------|--------------------------------------------------------------------|--------------|
| `git_dir`      | Where Ansible will clone the [official Signal TLS proxy repo to.   | `/opt/proxy` |
| `domain`       | Your FQDN that you want to launch a proxy using.                   |              |
| `allow_pass`   | Whether or not to allow password login via SSH.                    | `false`      |
| `update_proxy` | Force pulling from the Git repo listed above. (currently untested) | `false`      |


Example Playbook
----------------

    - hosts: servers
      roles:
        - { role: shammersdog.signal_tls_proxy, git_dir: /opt/proxy, domain: proxy.example.com }

License
-------

MIT

Author Information
------------------

Shammersdog - https://shamme.rs - sham@huskypa.ws
