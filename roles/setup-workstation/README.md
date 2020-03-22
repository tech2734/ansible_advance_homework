Role Name
=========
setup-workstation: this role will prepare the workstation and openshift environment


Requirements
------------
Server as workstation and Openshift Platform

Role Variables
--------------
vars/main.yml:

osp_networks:
  # Public Facing Network   
  external:
    cloud_name: ospcloud
    network_name: ext_network
    subnet_name: ext_subnet
    cidr_network: "10.10.10.0/24"
    state: present
    external: true


  # Private Facing Network   
  internal:
    cloud_name: ospcloud
    network_name: int_network
    subnet_name: int_subnet
    cidr_network: "20.20.20.0/24"
    state: present
    external: false

  # Public Facing Router connecting the two networks
osp_router:
  router:
    cloud_name: ospcloud
    state: present
    name: router
    network: ext_network

Dependencies
------------
None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: setup-workstation, x: 42 }

License
-------

BSD
