# ansible-capsule-haproxy

Roles for Satellite 6.4 Capsule Loadbalanced configuration

### Prerequisites
- Capsules installed and connected to a Satellite.
- HAProxy Server built and networked.
- DNS CNAME for the VIP created

### Role Explaination


#### HAProxy Configuration

`ansible-role-capsule-haproxy` will configure an HAProxy server to listen and loadbalance the ports defined in the Satellite Capsule Load Balancing Guide.


https://access.redhat.com/documentation/en-us/red_hat_satellite/6.4/html/load_balancing_guide/index#installing-the-load-balancer

#### Capsule Configuration defaults
`ansible-role-capsule-loadbalancer` will configure Capsules to be load balanced. Currently only supports 2 Capsules. 


| variable name  | example  | description |
|---|---|---|
| domain  | example.com  | domain name of the capsules
| sat_server  | sat6-master-01.example.com  |  FQDN of the Satellite server
| capsule1  | sat6-lb-capsule-01.{{ domain }}   | FQDN of the first Capsule server
| capsule2  | sat6-lb-capsule-02.{{ domain }}   | FQDN of the second Capsule server
| org | ORG | Organization Name
| location | LOC | Location Name 
| cert_path1 | /tmp/{{ capsule1 }}.tar | path to store the cert tarball during installation
| cert_path2 | /tmp/{{ capsule2 }}.tar | path to store the cert tarball during installation
lb_server | capsule.{{ domain }} | FQDN of the virtual IP/Load Balancer CNAME


