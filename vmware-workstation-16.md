# Fedora 32 and vmware-workstation 16
## Symptoms:

- virtual machine cannot connect to network with such messsages in logs
```
VNET: MACVNetPortOpenDevice: Ethernet0: can't open vmnet device (No such device or address)
VNET: MACVNetPort_Connect: Ethernet0: can't open data fd
```
- by `ip a` no any sign of vmnet devices

## how to fix
under root
```
vmware-modconfig --console --install-all
systemctl daemon-reload
systemctl restart vmware
```
