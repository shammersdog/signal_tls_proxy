Role Name
=========

An all-in-one role designed to deploy Signal's TLS Proxy to circumvent government censorship. Installs varius utilities for troubleshooting, Docker-CE from official Docker repositories, fail2ban for SSH, disables password SSH login, and creates and starts the TLS Proxy automatically given your domain name.

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

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

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

Shammersdog - [[https://shamme.rs]] - [[sham@huskypa.ws]]
