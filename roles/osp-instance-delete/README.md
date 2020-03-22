Role Name
=========
osp-instance-delete: this role will delete the deployed instance from Openstack


Requirements
------------
Openstack Platform and servers to delete

Role Variables
--------------
defaults/main.yml:
instances:
  - name: app1
    group: apps
    deploy: dev
    secgroup: apps

  - name: app2
    group: apps
    deploy: dev
    secgroup: apps

  - name: db
    group: appdbs
    deploy: dev
    secgroup: db

  - name: frontend
    group: frontends
    deploy: dev
    secgroup: frontend


Dependencies
------------
None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: osp-instance-delete, x: 42 }

License
-------

BSD
