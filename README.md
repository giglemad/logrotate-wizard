Logrotate-wizard
=========

Logrotate-wizard installs a given version of logrotate from source. The
installation is lightweight and do not overwrite an existing one.

Logrotate-wizard is *not a package manager*, and thus does not manage the
dependencies and or install/update triggers.

It should be used for debug purposes or hotfix purposes only. A legit use would
be the need to use a version of logrotate before it is packaged for your
distributions. It will break and do nasty things if you don't pay attention.

Use official packages back as soon as possible. Wizardry is dangerous, dont use
it too often

Requirements
------------

This role is suited for debian / ubuntu linux distributions. Feel free to
contribute for other types of linux distributions.

Role Variables
--------------

The only compulsory variable is `logrotate_version`. The role will get the given
version to build from git repository tagged with`logrotate_version`.
It is not set by default on purpose so you pick carefully the version you want
to install. You can play this role several times with different
`logrotate_version` values.

You can tell `logrotate-wizard` to manage your anacron files (located in
/etc/cron.daily /etc/cron.monthly etc.)

Those cron scripts are run by /etc/crontab, which in turns use `run-parts` on
each directory. The default packaged files for cron use an absolute path to call
`logrotate`. If you need your cron to call the `logrotate_version` of your
choice, please set `manage_cron` to true (default is false)

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
