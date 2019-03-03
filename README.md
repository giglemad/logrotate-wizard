Logrotate-wizard
=========

Logrotate-wizard installs a given version of logrotate from source. The
installation is lightweight and do not overwrite an existing one.

Requirements
------------

This role is suited for debian / ubuntu linux distributions. Feel free to
contribute for other types of linux distributions.

Role Variables
--------------

The only variable you need is `logrotate_version`. The role will get the given
version to build from git repository tagged with`logrotate_version`.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: all
      roles:
         - { role: logrotate-wizard, logrotate_version: '3.15.0' }

License
-------

MIT

Author Information
------------------

Hugo Lepetit, github: giglemad
