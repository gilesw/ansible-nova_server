# ansible-nova\_server

Setup machines in Rackspace based on openstack heat template, templated by ansible variables

# Dependencies

In order to use this role you need a specific Python virtualenv. See venv directory for details.
You also need to be able to use the heat cli tool so the PATH might need adjusting

# Key config

see example\_templates/ for some example heat templates.

```
# this is templated in the inventory itself
src: "{{ inventory_dir }}/.files/nova_server/{{ nova_server_source_template }}"

# and injected into here, which the heat code then uses to build the server
nova_server_template: "{{ inventory_dir }}/.files/nova_server/built/{{ nova_server_stack_name }}.yml"
```

```
        nova_server_flavor: 30 GB Compute v1
        nova_server_system_volume: true
        nova_server_system_volume_size: 80
        nova_server_system_volume_type: SSD
        nova_server_system_snapshot_id: xxxxx
```


