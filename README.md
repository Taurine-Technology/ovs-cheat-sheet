# OVS Cheat Sheet
Useful Open vSwitch Commands in one place

## ovs-vsctl

### Ports/Interfaces
- Add a port and set its interface request number for a bridge named _ovs-br_:
```
sudo ovs-vsctl add-port ovs-br eth1 -- set interface eth1 ofport_request=1
```
- Enable LLDP
```
sudo ovs-vsctl set interface eth1 lldp:enable=true
```

### Controllers
- Set a controller to out of band on a bridge named _ovs-br_:
```
sudo ovs-vsctl set controller ovs-br connection-mode=out-of-band
```

### Bridges
- Set the DPID of a bridge named _ovs-br_:
```
sudo ovs-vsctl set bridge ovs-br other-config:datapath-id=0000000000000001
```
- Show bridge details for bridge named _ovs-br_:
```
sudo ovs-ofctl -O OpenFlow13 show ovs-br
```
- Set OpenFlow version of a bridge named _ovs-br_:
```
ovs-vsctl set bridge ovs-br protocols=OpenFlow13
```
