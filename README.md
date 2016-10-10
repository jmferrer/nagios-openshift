# nagios-openshift
Monitorize OpenShift using Nagios.

## roles
* nagios-server: debian 8 server
* openshift-nodes-master: master nodes non scheduleable
* openshift-nodes-infra: nodes with router and other infrastructure services
* openshift-nodes-app: nodes with apps

## plugins
In https://github.com/jmferrer/nagios-openshift/tree/master/roles/nagios-openshift-master/files

### check_availability
Checks the percentage of availability: https://github.com/jmferrer/nagios-openshift/blob/master/roles/nagios-openshift-master/files/check_availability

* OK: all OK

* Warning: a zone is down.

* Critical: a zone is down and some other servers are down in other zone.

### check_etcd_cluster_health
Check etcd cluster health.

### check_nodes
Check the status of nodes.

### check_service
Useful to check origin-master, openvswitch, ...

## requirements
All requirements are satisfied with this playbooks.
* selinux
* iptables

## result

![alt tag](https://raw.githubusercontent.com/jmferrer/nagios-openshift/master/nagios-screenshot.png)
