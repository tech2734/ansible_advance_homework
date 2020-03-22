Role Name
=========
osp-servers: this role provisions the servers on openstack


Requirements
------------
Openstack Platform

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

vars/main.yml:
osp_servers:
  frontend:
    name: frontend
    state: present
    image: rhel-guest
    key_name: ansible_ssh
    flavor: m2.small
    security_group: frontend
    meta:
      - { group: frontends, deployment_name: QA}
  app1:
    name: app1
    state: present
    image: rhel-guest
    key_name: ansible_ssh
    flavor: m2.small
    security_group: apps
    meta:
      - { group: apps, deployment_name: QA}
  app2:
    name: app2
    state: present
    image: rhel-guest
    key_name: ansible_ssh
    flavor: m2.small
    security_group: apps
    meta:
      - { group: apps, deployment_name: QA}
  db:
    name: db
    state: present
    image: rhel-guest
    key_name: ansible_ssh
    flavor: m2.small
    security_group: db
    meta:
      - { group: appdbs, deployment_name: QA}


Dependencies
------------
None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: osp-servers, x: 42 }

License
-------

BSD
