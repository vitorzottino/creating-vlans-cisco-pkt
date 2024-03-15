# Creating vlans and setting them

 
 ## On switch
 ### Creating vlan
``` 
ena
conf t
vlan <index>
vlan <name>
```

### Adding devices in the vlan
```
ena 
conf t
int "range" <interface>
switchport acess vlan <index>
```

### Setting a interfaces as trunk
```
int "range" <interface>
switchport mode trunk
switchport trunk allowed vlan <vlan;all>
```

## On router
### Adding ip address to vlan
```
ena
conf t
int <interface.subinterface>
encapsulation dot1q <index>
ip address <ip-address>
```

### Adding dhcp to vlan
```
ena
conf t
ip dhcp pool <name>
network <network ip> <mask>
default-route <gateway>
```