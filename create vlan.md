# Creating vlans and setting them

 
 ## On switch
 ### Creating vlan
```shell
ena
conf t
vlan <index>
name <name>
```

### Adding devices in the vlan
```shell
ena 
conf t
int "range" <interface>
switchport access vlan <index>
```

### Setting a interfaces as trunk
```shell
int "range" <interface>
switchport mode trunk
switchport trunk allowed vlan <vlan;all>
```

## On router
### Adding ip address to vlan
```shell
ena
conf t
int <interface.subinterface>
encapsulation dot1q <index>
ip address <ip-address>
```

### Adding dhcp to vlan
```shell
ena
conf t
ip dhcp pool <name>
network <network ip> <mask>
default-route <gateway>
```