bvansomeren.jail-setup
======================

This role sets up the host for simple jails; It downloads the current release if it doesn't exist yet and sets up jail.conf
The settings for this role are named the same as other roles that go together, this is intentional

Requirements
------------

None. FreeBSD with a zpool(1)

Role Variables
--------------

```
jail_location:             "/usr/local/jails"
jail_dataset:              "zroot/jails"
jail_template_dataset:     "zroot/jails/template"
```

Dependencies
------------

FreeBSD. This role is only tested on the latest production versions (11.x at this moment)

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      user: barry
      sudo: true
      roles:
      - role: bvansomeren.jail
        name: newjail
        hostname: newjail.local.domain
        extra_opts:
        - name: ip4.addr
          option: 10.0.1.53
      - role: bvansomeren.jail
        name: secondjail
        hostname: secondjail.local.domain
        extra_opts:
        - name: ip4.addr
          option: 10.0.1.54


License
-------

BSD

Author Information
------------------

Just reach out via Github
