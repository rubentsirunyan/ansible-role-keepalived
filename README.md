Ansible Role: Keepalived
=========

This role sets up highly available Linux machines that share a virtual IP using keepalived.

Requirements
------------

None.

Role Variables
--------------

`keepalived_auth_pass`: Password for authentication between keepalived nodes.
`keepalived_role`: The initial role of the node. Values are `MASTER`(default) or `BACKUP`.
`keepalived_router_id`: Keepalived Router ID. The default value is `42`, because it is the answer to life, the universe and everything.
`keepalived_interface`: The interface to share between the nodes. The default value is `eth0`
`keepalived_virtual_ip`: The virtual IP address to share.
`keepalived_check_process`: The name of the process to monitor. The default value is `keepalived`
`keepalived_master_priority`: The priority of the master node.
`keepalived_backup_priority`: The priority of the backup node.

Dependencies
------------

None.

Example Playbook
----------------

    - hosts: linux_routers
      roles:
        - role: rubentsirunyan.keepalived
          vars:
              keepalived_role: MASTER
              keepalived_virtual_ip: 192.168.42.1
              keepalived_interface: eth0

License
-------

BSD

Author Information
------------------

This role is created by Ruben Tsirunyan https://github.com/rubentsirunyan