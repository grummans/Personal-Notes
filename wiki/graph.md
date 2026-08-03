# Graph — quan hệ giữa các trang

Nginx architecture -> part_of -> Nginx
Nginx architecture -> uses -> Nginx event loop
Nginx architecture -> depends_on -> TCP
Nginx architecture -> depends_on -> IP
Nginx architecture -> related_to -> Nginx configuration
Nginx configuration -> related_to -> Nginx
Nginx configuration -> related_to -> Nginx reverse proxy headers
Nginx configuration -> related_to -> Nginx architecture
Nginx configuration -> related_to -> Tomcat
Nginx configuration -> related_to -> Tomcat architecture
Nginx reverse proxy headers -> related_to -> Nginx
Nginx reverse proxy headers -> related_to -> Tomcat
Nginx reverse proxy headers -> depends_on -> TCP
Nginx reverse proxy headers -> related_to -> OSI Model
Nginx reverse proxy headers -> related_to -> Tomcat architecture
Tomcat architecture -> part_of -> Tomcat
Tomcat architecture -> related_to -> Nginx
Tomcat -> related_to -> Nginx configuration
Tomcat -> related_to -> Nginx
Keepalived -> uses -> VRRP
Keepalived failover flow -> depends_on -> VRRP
Keepalived failover flow -> part_of -> Keepalived
Keepalived -> related_to -> Nginx
VRRP -> depends_on -> IP
Keepalived failover flow -> depends_on -> IP
Keepalived failover flow -> related_to -> Nginx
OSI Model -> related_to -> TCP/IP
Protocol -> related_to -> TCP
Protocol -> related_to -> UDP
Protocol -> related_to -> IP
Protocol -> related_to -> TCP/IP
TCP/IP -> depends_on -> Protocol
TCP -> part_of -> TCP/IP
UDP -> part_of -> TCP/IP
IP -> part_of -> TCP/IP
TCP/IP -> related_to -> TCP vs UDP
TCP -> related_to -> UDP
TCP -> depends_on -> IP
TCP -> part_of -> Protocol
TCP -> related_to -> TCP vs UDP
UDP -> depends_on -> IP
UDP -> part_of -> Protocol
UDP -> related_to -> TCP vs UDP
IP -> part_of -> Protocol
IP -> related_to -> OSI Model
Subnetting -> depends_on -> IP
Subnetting -> related_to -> Routing
Routing -> depends_on -> IP
Routing -> related_to -> OSI Model
Routing -> related_to -> VPN
VPN -> related_to -> Routing
VPN -> related_to -> IP
Port -> part_of -> OSI Model
Port -> related_to -> TCP
Port -> related_to -> UDP
Port -> related_to -> DNS
Port -> related_to -> Nginx configuration
Connection-Oriented -> related_to -> TCP
Connection-Oriented -> related_to -> Connectionless
Connectionless -> related_to -> UDP
Connectionless -> related_to -> Connection-Oriented
DNS -> depends_on -> IP
DNS -> part_of -> Protocol
DNS -> part_of -> TCP/IP
DNS -> related_to -> Port
