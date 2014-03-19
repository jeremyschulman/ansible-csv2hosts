### ansible-csv2hosts

Demo - CSV to Ansible 'hosts' and 'host_vars'

### Demo

To create the `hosts` and `host_vars` files:

    user@linux> python csv2hosts.py
    
The demo is hardcoded to use the CSV file called 'data.csv'.

To run the Ansible playbook to template build a file for each host:

    user@linux> ansible-playbook build_conf -i hosts
    
The output of the ansible run should look like this:
````
[jeremy@stargate ansible-csv2hosts]$ ansible-playbook -i hosts build_conf 

PLAY [all] ******************************************************************** 

TASK: [building config] ******************************************************* 
changed: [twb-sf-rtr1]
changed: [twb-sf-rtr2]

PLAY RECAP ******************************************************************** 
twb-sf-rtr1                : ok=1    changed=1    unreachable=0    failed=0   
twb-sf-rtr2                : ok=1    changed=1    unreachable=0    failed=0   
````
    
### Clean-up

The demo repository includes the files created *after* the demo as run.  If you want to remove everything
that was built by the demo, do the following:

    user@linux> rm hosts
    user@linux> rm host_vars/*
    user@linux> rm *.conf
    
Then re-run the demo

