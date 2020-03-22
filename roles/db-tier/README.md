Role Name
=========
db-tier: configuration and installation of database host for 3 tier application
This role was replaced with geerlingguy.postgresql for the database setup tier

Requirements
------------
database server

Role Variables
--------------
N/A

Dependencies
------------
geerlingguy.postgresql

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: db-tier, x: 42 }

License
-------

BSD
