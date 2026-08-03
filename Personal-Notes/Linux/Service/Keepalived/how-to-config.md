## Configuration

### keepalived.conf

````
global_defs {
    ...
}

vrrp_script chk_service {
    ...
}

vrrp_instance VI_1 {
    ...
}

virtual_server {
    ...
}
````

### Explain

`global_defs`: common config for keepalived
`vrrp_script`: define health check for keepalived.
`vrrp_instance`: config VRRP, VIP, Priority,...
`virtual_server`: for LVS Load Balancing
