ansible-keepalived: Ansible role for setting up keepalived 
Toni Comerma - tcomerma (at) gmail.com
============================================================

This role sets up keepalived for an standard setup of:
  - One virtual IP
  - Two hosts

You just need to provide an small amount of information to have it running
  - Add "keepalived" role to both hosts
  - Add variable keepalived_role: "master" | "slave" to the appropiate hosts 
  - Add variable keepalived_shared_ip: "floating IP address" to both hosts

Other variables can be configured, overwriting defaults/main.yml

Keepalived can watch processes to influence on which node should be the master. Setting
variable "keepalived_check_process" to the name of the process will do. I use keepalived
to give high availability to haproxy, so I use.

keepalived_check_process: "haproxy"



Testing & trying
------------------

Quite simple if you have vagrant installed.

$ git clone https://github.com/tcomerma/ansible-keepalived.git
$ cd ansible-keepalived
$ vagrant up

