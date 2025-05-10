Router>enable<br>
Router#<br>
Router#configure terminal<br>
Enter configuration commands, one per line.  End with CNTL/Z.<br>
Router(config)#interface GigabitEthernet0/0/0<br>
Router(config-if)#ip address 192.168.1.1 255.255.255.0<br>
Router(config-if)#ip address 192.168.1.1 255.255.255.0<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/1<br>
Router(config-if)#ip address 192.168.2.1 255.255.255.0<br>
Router(config-if)#ip address 192.168.2.1 255.255.255.0<br>
Router(config-if)#ex<br>
Router(config)#ip dhcp pool client<br>
Router(dhcp-config)#network 192.168.1.0 255.255.255.0<br>
Router(dhcp-config)#default-router 192.168.1.1<br>
Router(dhcp-config)#dns-server 192.168.2.5<br>
Router(dhcp-config)#ex<br>
Router(config)#<br>
Router(config)#<br>
Router(config)#interface GigabitEthernet0/0/1<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/0<br>
Router(config-if)#no shutdown<br>
Router(config-if)#<br>
