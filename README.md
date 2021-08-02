# Switch

en
config t

hostname AccessSwitch
ip domain-name accesswitch.etechsc.com

crypto key generate rsa  

1024


username admin password etech
username admin privilege 15

line console 0
logging synchronous
login local


line vty 0 4
logging synchronous
login local


interface vlan 1
ip add  192.168.20.2 255.255.255.0
no shutdown

ip default-gateway 192.168.20.1
ip ssh version 2

interface range gigabitEthernet 0/1 - 2
channel-group 1 mode active 
do wr
