#VLAN Configuration on Access Switches

##Switch1 (HR VLAN)
Switch1> enable
Switch1# configure terminal
Switch1(config)# vlan 10
Switch1(config-vlan)# name HR
Switch1(config-vlan)# exit

Switch1(config)# interface range FastEthernet0/1 - 2
Switch1(config-if-range)# switchport mode access
Switch1(config-if-range)# switchport access vlan 10
Switch1(config-if-range)# exit

##Switch2 (Finance VLAN)
Switch1(config)# interface GigabitEthernet0/1
Switch1(config-if)# switchport mode trunk
Switch1(config-if)# switchport trunk allowed vlan 10,20,30
Switch1(config-if)# exit

Switch2> enable
Switch2# configure terminal
Switch2(config)# vlan 20
Switch2(config-vlan)# name Finance
Switch2(config-vlan)# exit

Switch2(config)# interface range FastEthernet0/1 - 2
Switch2(config-if-range)# switchport mode access
Switch2(config-if-range)# switchport access vlan 20
Switch2(config-if-range)# exit

Switch2(config)# interface GigabitEthernet0/1
Switch2(config-if)# switchport mode trunk
Switch2(config-if)# switchport trunk allowed vlan 10,20,30
Switch2(config-if)# exit

##Switch3 (IT VLAN)
Switch3> enable
Switch3# configure terminal
Switch3(config)# vlan 30
Switch3(config-vlan)# name IT
Switch3(config-vlan)# exit

Switch3(config)# interface range FastEthernet0/1 - 2
Switch3(config-if-range)# switchport mode access
Switch3(config-if-range)# switchport access vlan 30
Switch3(config-if-range)# exit

Switch3(config)# interface GigabitEthernet0/1
Switch3(config-if)# switchport mode trunk
Switch3(config-if)# switchport trunk allowed vlan 10,20,30
Switch3(config-if)# exit
