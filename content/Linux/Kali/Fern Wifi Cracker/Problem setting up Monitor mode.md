When fern is open, sometimes when selecting an interface, the following message will show:
**"problem occurred while setting up the monitor mode of selected"

![[Pasted image 20241108222037.png]]

If there is no interface to select, see [[Enable Wifi adapter]]

1. First, close Fern Wifi Cracker
2. Open a terminal as root
3. Enter the commands:
	
	*Ip link set wlan0 down
	
	*Ip link set wlan0 name wlan0mon
	
	*ip link set wlan0mon up
	
![[Pasted image 20241108222950.png]]

Open fern again and should now see the name has changed and monitor mode now enabled

![[Pasted image 20241108223041.png]]

