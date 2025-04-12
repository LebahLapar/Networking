-SWITCH
Switch#conf t
Switch(config)#interface range FastEthernet0/1-5
Switch(config-if-range)#ex
Switch(config)#vlan 10
Switch(config-vlan)#name karyawan
Switch(config-vlan)#ex
Switch(config)#vlan 20
Switch(config-vlan)#name HRD
Switch(config-vlan)#ex
Switch(config)#interface range FastEthernet0/1-5
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#switchport access vlan 10
Switch(config-if-range)#ex
Switch(config)#interface range FastEthernet0/6-10
Switch(config-if-range)#switchport mode access
Switch(config-if-range)#switchport access vlan 20
Switch(config-if-range)#ex
Switch(config)#interface FastEthernet0/11
Switch(config-if)#switchport mode trunk
Switch(config-if)#ex
Switch(config)#ex
Switch#
%SYS-5-CONFIG_I: Configured from console by console
Switch#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
[OK]


-ROUTER
Router>en
Router#conf t
Router(config)#interface GigabitEthernet0/0/0
Router(config-if)#ip address 192.168.1.1 255.255.255.0
Router(config-if)#no shutdown
Router(config-if)#ex
Router(config)#interface GigabitEthernet0/0/0.10
Router(config-subif)#encapsulation dot1Q 10
Router(config-subif)#ip address 192.168.10.1 255.255.255.0
Router(config-subif)#ex
Router(config)#interface GigabitEthernet0/0/0.20
Router(config-subif)#encapsulation dot1Q 20
Router(config-subif)#ip address 192.168.20.1 255.255.255.0
Router(config-subif)#ex
Router(config)#ip dhcp pool vlan10
Router(dhcp-config)#network 192.168.10.0 255.255.255.0
Router(dhcp-config)#default-router 192.168.10.1
Router(dhcp-config)#dns-server 8.8.8.8
Router(dhcp-config)#ex
Router(config)#ip dhcp pool vlan20
Router(dhcp-config)#network 192.168.20.0 255.255.255.0
Router(dhcp-config)#default-router 192.168.20.1
Router(dhcp-config)#dns-server 8.8.8.8
Router(dhcp-config)#ex
Router(config)#ex
Router#
%SYS-5-CONFIG_I: Configured from console by console
Router#copy running-config startup-config
Destination filename [startup-config]? 
Building configuration...
[OK]
