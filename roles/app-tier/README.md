Role Name
=========

App tier role for 3tier application setup.

Requirements
------------

Infrastructure to deploy onto.

Role Variables
--------------

vars/main.yml:
tomcat_web_root:  /usr/share/tomcat/webapps/ROOT

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: app-tier, x: 42 }

License
-------

BSD
