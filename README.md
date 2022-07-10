# Network Id: 192.168.4.0/24 

In order to divide it to 8 subnets you'll need /27. In each of the networks you''l have 32 total addresses and 30 usable hosts.  

192.168.4.0 /27  

192.168.4.32 /27  

192.168.4.64 /27 

192.168.4.96 /27 

192.168.4.128 /27  

192.168.4.160 /27  

192.168.4.192 /27  

192.168.4.224 /27  

 

# What happens when you go to a website from your computer?  

When you enter a URL, the computer doesn’t know English so it needs to go to the DNS which will resolve the name to an IP.  

First it’ll go to the dns which is your router, and search for a matching IP in his datatbase. If he doesn't find it he will go to the DNS datatbase which is on the ISP’s router.  

Now your computer knows where to forward it and will send an HTTP request to the server from which you want to get the web page. For example, Amazon.  

Your IP source address will be the IP on your computer. You can see it if you type ipconfig (for windows) or ifconfig/ip a (for linux) in your terminal. This is your private IP which the interet doesnt know but your local network does because private addresses are used all over the world in local networks only. The destination IP will be the private IP of the server your’e trying to connect. 

The internet or the public network, uses public addresses. In that way when you go out to the internet, your ISP’s router will translate your private IP to a public IP, using NAT, and forward the packet. 

You also have Mac addresses and when going to your router the destination mac address will be the mac address of your router. When it hits the router, he sees the destination ip address which is Amazon’s but unpackes the mac address of its own and the src and replaces it with the new mac addresses. Source mac: his own, destination mac: next hop router. This happens with every single router all the way to the router at the Amazon’s data center which then forwards it to the switch and the switch to the server...to the desirable port.  

When the amazon server responds, the destination IP will be your public IP and the ISP’s router knows to forward it back to your computer.  


![image](https://user-images.githubusercontent.com/98810962/178142289-1082821b-8d13-47ab-87a2-293465021f2a.png)
