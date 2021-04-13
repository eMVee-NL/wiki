Wireshark
=======

__Attention: The articles published on this wiki are for education purpose, to use during a CTF or for an authorized penetrationtest. By using the wiki, you've agreed to use this knowledge in an ethical way and do not evil in any perspective.__




Filter options
---------
| Example 	                                | Description 	                | 
| ------------------------------------------|-------------------------------|
| ip.add == 10.10.10.1 	                    | Wireshark Filter by IP 	    |
| ip.dest == 10.10.10.1	                    | Filter by Destination IP      |
| ip.src == 10.10.50.2 	                    | Filter by Source IP	        |
| tcp.port == 25    	                    | Filter by port                |
| ip.addr == 10.10.10.9 and Tcp.port == 25 	| Filter by ip adress and port  |
| Tcp.flags.syn == 1 	                    | Filter SYN flag               |
| Tcp.flags.syn == 1 and tcp.flags.ack == 0	| Filter SYN flag               |
| eth.dst == ff:ff:ff:ff:ff:ff 	            | Wireshark broadcast filter    |
