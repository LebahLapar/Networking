-SWITCH<br>
Switch#conf t<br>
Switch(config)#interface range FastEthernet0/1-5<br>
Switch(config-if-range)#ex<br>
Switch(config)#vlan 10<br>
Switch(config-vlan)#name karyawan<br>
Switch(config-vlan)#ex<br>
Switch(config)#vlan 20<br>
Switch(config-vlan)#name HRD<br>
Switch(config-vlan)#ex<br>
Switch(config)#interface range FastEthernet0/1-5<br>
Switch(config-if-range)#switchport mode access<br>
Switch(config-if-range)#switchport access vlan 10<br>
Switch(config-if-range)#ex<br>
Switch(config)#interface range FastEthernet0/6-10<br>
Switch(config-if-range)#switchport mode access<br>
Switch(config-if-range)#switchport access vlan 20<br>
Switch(config-if-range)#ex<br>
Switch(config)#interface FastEthernet0/11<br>
Switch(config-if)#switchport mode trunk<br>
Switch(config-if)#ex<br>
Switch(config)#ex<br>
Switch#<br>
%SYS-5-CONFIG_I: Configured from console by console<br>
Switch#copy running-config startup-config<br>
Destination filename [startup-config]? <br>
Building configuration...<br>
[OK]<br>


-ROUTER<br>
Router>en<br>
Router#conf t<br>
Router(config)#interface GigabitEthernet0/0/0<br>
Router(config-if)#ip address 192.168.1.1 255.255.255.0<br>
Router(config-if)#no shutdown<br>
Router(config-if)#ex<br>
Router(config)#interface GigabitEthernet0/0/0.10<br>
Router(config-subif)#encapsulation dot1Q 10<br>
Router(config-subif)#ip address 192.168.10.1 255.255.255.0<br>
Router(config-subif)#ex<br>
Router(config)#interface GigabitEthernet0/0/0.20<br>
Router(config-subif)#encapsulation dot1Q 20<br>
Router(config-subif)#ip address 192.168.20.1 255.255.255.0<br>
Router(config-subif)#ex<br>
Router(config)#ip dhcp pool vlan10<br>
Router(dhcp-config)#network 192.168.10.0 255.255.255.0<br>
Router(dhcp-config)#default-router 192.168.10.1<br>
Router(dhcp-config)#dns-server 8.8.8.8<br>
Router(dhcp-config)#ex<br>
Router(config)#ip dhcp pool vlan20<br>
Router(dhcp-config)#network 192.168.20.0 255.255.255.0<br>
Router(dhcp-config)#default-router 192.168.20.1<br>
Router(dhcp-config)#dns-server 8.8.8.8<br>
Router(dhcp-config)#ex<br>
Router(config)#ex<br>
Router#<br>
%SYS-5-CONFIG_I: Configured from console by console<br>
Router#copy running-config startup-config<br>
Destination filename [startup-config]? <br>
Building configuration...<br>
[OK]<br>
