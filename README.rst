ansible-role-pm2
================

pm2 for ansible

|Build Status| |GitHub issues| |GitHub license|

:Version: 0.0.0
:Web: https://github.com/equipindustry/ansible-role-pm2
:Download: https://github.com/equipindustry/ansible-role-pm2
:Source: https://github.com/equipindustry/ansible-role-pm2
:Keywords: ansible-role-pm2

.. contents:: Table of Contents:
    :local:

Ansible Galaxy role for `Pm2`_.

Requirements:
-------------

List of applications:

- `Pyenv`_
- `Docker`_

Install
-------

Install it with the following command:

.. code-block:: bash

    $ ansible-galaxy install equipindustry.pm2


Using ``requirements.yml``:

.. code-block:: yaml

    - src: equipindustry.pm2


Role Variables
--------------

The default role variables in ``defaults/main.yml`` are:

.. code-block:: yaml

    ---
    # pm2_cmds:
    #   - run: sendSignal             # pm2 command name
    #     args: SIGUSR2 my-app        # optional arguements to pass
    #     path: /var/www/myapp        # optional chdir path
    #     ignore_errors: yes          # optional don't fail on pm2 errors
    #     env:                        # optional environment settings
    #       NODE_ENV: production
    # pm2_apps:
    #   - run: pm2.json               # you can also run a .js file like app.js
    #     cmd: start                  # optional command to run on the app
    #     args: --name console_error  # optional arguements to pass i.e. to app.js
    #     path: /var/www/myapp        # optional chdir path
    #     env:                        # optional environment settings
    #       NODE_ENV: production
    # pm2_post_cmds:
    #   - run: save                   # pm2 command name
    #     args:                       # optional arguements to pass
    #     path: /var/www/myapp        # optional chdir path
    #     ignore_errors: yes          # optional don't fail on pm2 errors
    #     env:                        # optional environment settings
    #       NODE_ENV: production
    #


    # list of commands to run
    # note: these will be executed before managing apps
    pm2_cmds:
    # note: delete all apps initially on every run so only configured apps exist
    - run: delete all
    # default env to run on cmds
    pm2_cmds_default_env: {}
    # list of post commands to run
    # note: these will be executed after managing apps
    pm2_post_cmds: []
    # default env to run on post cmds
    pm2_post_cmds_default_env: {}
    # list of paths to JSON app declarations
    pm2_apps: []
    # default env to run on apps
    pm2_apps_default_env: {}
    # default command to run on apps
    pm2_apps_default_cmd: start
    # delete all initially on every run
    pm2_apps_delete_all: yes
    # install upstart
    pm2_upstart: yes
    # start on boot
    pm2_service_enabled: yes
    # service name for startup system
    pm2_service_name: pm2-init.sh
    # current state: started, stopped
    pm2_service_state: started
    # version
    pm2_version:
    # user to run pm2 commands
    pm2_user: "{{ ansible_user_id }}"
    # startup platform
    pm2_platform:

Dependencies
------------

- Ansible >= 2.4
- installed nodejs

Example Playbook
----------------

See the `examples <./examples/>`__ directory.

To run this playbook with default settings, create a basic playbook like
this:

.. code:: yaml

        - hosts: servers
          roles:
            - equipindustry.pm2

Quick Start
===========

- Fork this repository

Usage
-----

- Install dependences

.. code-block:: bash

  λ make setup

Support
-------

If you want to support this project, i only accept ``IOTA`` :p.

.. code-block:: bash

    Address: FTDCZELEMOQGL9MBWFZENJLFIZUBGMXLFVPRB9HTWYDYPTFKASJCEGJMSAXUWDQC9SJUDMZVIQKACQEEYPEUYLAMMD


Team
----

+---------------+
| |Luis Mayta|  |
+---------------+
| `Luis Mayta`_ |
+---------------+

License
-------

MIT

Changelog
---------

Please see `CHANGELOG`_ for more information what
has changed recently.

Contributing
------------

Contributions are welcome!

Review the `CONTRIBUTING`_ for details on how to:

* Submit issues
* Submit pull requests

Contact Info
------------

Feel free to contact me to discuss any issues, questions, or comments.

* `Email`_
* `Twitter`_
* `GitHub`_
* `LinkedIn`_
* `Website`_
* `PGP`_

|linkedin| |beacon|

Made with :coffee: and :pizza: by `Luis Mayta`_ and `equipindustry`_.

.. Links
.. _`changelog`: CHANGELOG.rst
.. _`contributors`: docs/source/AUTHORS.rst
.. _`contributing`: docs/source/CONTRIBUTING.rst

.. _`equipindustry`: https://github.com/equipindustry
.. _`Luis Mayta`: https://github.com/luismayta


.. _`Github`: https://github.com/luismayta
.. _`Linkedin`: https://pe.linkedin.com/in/luismayta
.. _`Email`: slovacus@gmail.com
    :target: mailto:slovacus@gmail.com
.. _`Twitter`: https://twitter.com/slovacus
.. _`Website`: https://luismayta.github.io
.. _`PGP`: https://keybase.io/luismayta/pgp_keys.asc

.. |Build Status| image:: https://travis-ci.org/equipindustry/ansible-role-pm2.svg
    :target: https://travis-ci.org/equipindustry/ansible-role-pm2
.. |GitHub issues| image:: https://img.shields.io/github/issues/equipindustry/ansible-role-pm2.svg
    :target: https://github.com/equipindustry/ansible-role-pm2/issues
.. |GitHub license| image:: https://img.shields.io/github/license/mashape/apistatus.svg?style=flat-square
    :target: LICENSE

.. Team:
.. |Luis Mayta| image:: https://github.com/luismayta.png?size=100
    :target: https://github.com/luismayta

.. Footer:

.. |linkedin| image:: http://www.linkedin.com/img/webpromo/btn_liprofile_blue_80x15.png
    :target: https://pe.linkedin.com/in/luismayta
.. |beacon| image:: https://ga-beacon.appspot.com/UA-65019326-1/github.com/equipindustry/ansible-role-pm2/readme
    :target: https://github.com/equipindustry/ansible-role-pm2

.. Dependences:

.. _Pyenv: https://github.com/pyenv/pyenv
.. _Docker: https://www.docker.com/
.. _Pm2: https://pm2.io