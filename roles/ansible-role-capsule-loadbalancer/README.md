Capsule Load Balancer
=========

Role to configure two Satellite Capsules for Load Balancing. This role does *NOT* configure the load balancer itself. 

Requirements
------------

This role assumes that 2 new Satellite Capsules have been installed and configured. 

Role Variables
--------------

See below for examples and explanation of defaults/variables.

| variable name  | example  | description |   |   |
|---|---|---|---|---|
| domain  | example.com  | domain name of the capsules
| sat_server  | sat6-master-01.example.com  |  FQDN of the Satellite server
| capsule1  | sat6-lb-capsule-01.{{ domain }}   | FQDN of the first Capsule server
| capsule2  | sat6-lb-capsule-02.{{ domain }}   | FQDN of the second Capsule server
| org | ORG | Organization Name
| location | LOC | Location Name 
| cert_path1 | /tmp/{{ capsule1 }}.tar | path to store the cert tarball during installation
| cert_path2 | /tmp/{{ capsule2 }}.tar | path to store the cert tarball during installation
lb_server | capsule.{{ domain }} | FQDN of the virtual IP/Load Balancer CNAME
