this is a ospf protocol, same as i learn before, but more complex and efficient than before :)
this is my configuration :
router 1
Akbar1(config)#router ospf 1
Akbar1(config-router)#network 192.168.1.0 0.0.0.3 area 0
Akbar1(config-router)#network 10.10.10.0 0.0.0.3 area 0
Akbar1(config-router)#ex
Akbar1(config)#
Akbar1(config)#

router 2
Akbar2(config)#router ospf 1
Akbar2(config-router)#network 10.10.10.0 0.0.0.3 area 0
Akbar2(config-router)#network 10.10.10.4 0.0.0.3 area 0
Akbar2(config-router)#ex
Akbar2(config)#

router 3
Akbar3(config)#router ospf 1
Akbar3(config-router)#network 10.10.10.4 0.0.0.3 area 0
Akbar3(config-router)#network 192.168.1.4 0.0.0.3 area 0
Akbar3(config-router)#ex
