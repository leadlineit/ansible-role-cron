# Ansible Role Cron

![Build Status](https://github.com/leadlineit/ansible-role-cron/actions/workflows/ansible-galaxy-ci.yml/badge.svg)
[![Galaxy Role](https://img.shields.io/badge/Ansible--Galaxy-leadlineit.cron-blue.svg?logo=ansible&logoColor=white)](https://galaxy.ansible.com/leadlineit/cron/)

This role helps to configure cron.d files on a Debian (stretch/buster/bullseye).

Requirements
------------

This role requires Ansible 2.5 or higher.

Role Variables
--------------

```yaml
---
cron:
  - file: name-of-file
    record:
      - name: name-of-job1 ## At 03:33 on day-of-month 3 and on Wednesday in March.” 
        user: root
        minute: 33
        hour: 3
        month_day: 3
        month: 3
        weekday: 3
        job: /usr/local/bin/some_script_for_backup.sh > /dev/null
        state: present
      - name: name-of-job2 ## At 00:50 on Friday
        user: some-user
        minute: 50
        hour: 0
        weekday: 5
        job: /usr/local/bin/some_old_script.sh > /dev/null
        state: absent
```

Some of this variable an optional.
Default value for this variables:

```yaml
---
cron:
    record:
        user: root
        minute: *
        hour: *
        month_day: *
        month: *
        weekday: *
```
Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

```yaml
- hosts: servers
  roles:
    - { role: leadlineit.cron, tags: cron }
```

License
-------

MIT

Author Information
------------------

This role was created by Stas Stavnichuk.
