

# 21110025 - Nguyễn Thành Hiếu
# Extra Lab: firewall



*First we setup docker for lab:*

<img width="726" alt="fw1.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw1.jpg" >

<img width="726" alt="fw2.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw2.jpg" >

*check running containers*

<img width="726" alt="fw3.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw3.jpg" >

*You will see a list of running containers, including "router" , "inner" , "outsider" , "iweb" and "badsite".*

*Set up iptables rules on the container router
a. Block all access to the router except ping*

*Check from a subnet to the router
To check the connection from a subnet to the router, you need to know the IP address of the router container. For example, let's say the router's IP address is 172.16.10.100:*
*Block access to the router except for ping:*

<img width="726" alt="fw4.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw4.jpg" >

*Prevent subnet 10.9.0.0/24 from accessing internal web server (iweb):*

<img width="726" alt="fw5.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw5.jpg" >

*Prevent subnet 172.16.10.0/24 from accessing badsite*

<img width="726" alt="fw6.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw6.jpg" >


*check configuration:*

<img width="726" alt="fw7.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw7.jpg" >

*Check from a subnet to the router
The router's IP address is 172.16.10.100: *

*Block access to the router except for ping:*

<img width="726" alt="fw8.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw8.jpg" >

*Prevent subnet 10.9.0.0/24 from accessing the internal web server (iweb):*

<img width="726" alt="fw9.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw9.jpg" >

*Prevent subnet 172.16.10.0/24 from accessing badsite:*

<img width="726" alt="fw10.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw10.jpg" >

*iptables -A: Adds a rule to the specified chain.
INPUT, FORWARD: Chain will process input or forward packets.
-s: Source address.
-d: Destination address.
--dport: Destination port.
ACCEPT, DROP, REJECT: Action will be performed on the packet.*

*Check ping from container outsider to iweb:*

<img width="726" alt="fw111.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw111.jpg" >

*Ping from inner to badsite:*

<img width="726" alt="fw12.jpg" src="https://github.com/NguyenThanhHieu-21110025/InformationSecurity-Lab/blob/main/images/fw12.jpg" >
