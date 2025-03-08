## Requirment:

### Please Configure 'DNS (for IRAN)' for Configure Kubernetes-Cluster!~ .
```
inventory/group_vars/all.yaml (shekan_dns)
```
### Please Comment Configure DNS if you are out of IRAN for Configure Kubernetes-Cluster!~ .
```
inventory/group_vars/all.yaml (shekan_dns)
roles/preinstall/tasks/main.yml (Unlink resolv_conf, Create resolv_conf, Set DNS)
```
### Please Configure hosts.ini for Hosts, Domain and UserName!~ .
```
inventory/hosts.ini
```

### Recommended!~ .
```
You must Use Ubuntu 24.04~Noble for this Ansible (Tested in Ubuntu 24.04)
```

### Topology!~ .
### ------------
### (You Can Increase Master and Worker in Senario)


                        ------------                        ------------
                       | HA_PROXY 1 |                      | HA_PROXY 2 |
                        ------------                        ------------
                             |                                   |
                             |                                   |
                ------------------------------ -------------------------------
               |                              |                               |
               |                              |                               |
        --------------                 --------------                   --------------
       | K8S-Master 1 |               | K8S-Master 2 |                 | K8S-Master 3 |
        --------------                 --------------                   --------------
               |                              |                               |
               |                              |                               |
                ------------------------------ -------------------------------  
               |                              |                               |
               |                              |                               |
        --------------                 --------------                   --------------
       | K8S-Worker 1 |               | K8S-Worker 2 |                 | K8S-Worker 3 |
        --------------                 --------------                   --------------

  

## Run Ansible:
```
ansible-playbook -i inventory/hosts.ini main.yaml --become --become-method=sudo
```

Good Lock!~ .
