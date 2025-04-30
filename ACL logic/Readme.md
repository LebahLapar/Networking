<h1>What is ACL (Access Control List)?</h1><br>
An Access Control List (ACL) is a security feature used on routers and switches to control the flow of network traffic.
It works by filtering packets based on rules such as source IP, destination IP, protocol (TCP/UDP/ICMP), and port numbers.
Think of ACLs like firewall rules that allow or deny traffic through a network device.<br>
<h2>ACL Direction Rules: in vs out</h2><br>
IN = PC(client) > Router<br>
OUT = Router > PC(client)<br>
<h2>Configuration Example : </h2><br>
Router>enable<br>
Router#<br>
Router#configure terminal<br>
Router(config)#interface GigabitEthernet0/0/1<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/0<br>
Router(config-if)#ip address 192.168.1.1 255.255.255.0<br>
Router(config-if)#ip address 192.168.1.1 255.255.255.0<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/1<br>
Router(config-if)#ip address 192.168.2.1 255.255.255.0<br>
Router(config-if)#ip address 192.168.2.1 255.255.255.0<br>
Router(config-if)#<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/1<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/0<br>
Router(config-if)#no shutdown<br>
Router(config-if)#<br>
Router(config-if)#exit<br>
Router(config)#interface GigabitEthernet0/0/1<br>
Router(config-if)#no shutdown<br>
Router(config-if)#<br>
Router(config-if)#ex<br>
Router(config)#access-list 100 deny tcp host 192.168.1.3 host 192.168.2.2 eq 80<br>
Router(config)#access-list 100 deny tcp host 192.168.1.2 host 192.168.2.3 eq 80<br>
Router(config)#access-list 100 permit ip any any<br>
Router(config)#interface GigabitEthernet0/0/0<br>
Router(config-if)#ip access-group 100 in<br>
Router(config-if)#ex<br>
Router(config)#ex<br>
Router#<br>
Router#copy running-config startup-config<br>
