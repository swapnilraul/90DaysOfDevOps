# Hands-On with Networking Commands

# ping (check connectivity) 
The Linux ping command is a network utility used to test a host's reachability on an Internet Protocol (IP) network.
ping sends out ICMP (Internet Control Message Protocol) echo request packets to the target host and waits for echo replies.
=============================================================================================================================

ubuntu@ip-172-31-8-139:~$ ping google.com
PING google.com (172.217.174.238) 56(84) bytes of data.
64 bytes from bom12s03-in-f14.1e100.net (172.217.174.238): icmp_seq=1 ttl=55 time=1.29 ms
64 bytes from bom12s03-in-f14.1e100.net (172.217.174.238): icmp_seq=2 ttl=55 time=1.27 ms
64 bytes from bom12s03-in-f14.1e100.net (172.217.174.238): icmp_seq=3 ttl=55 time=1.56 ms
64 bytes from bom12s03-in-f14.1e100.net (172.217.174.238): icmp_seq=4 ttl=55 time=1.76 ms
64 bytes from bom12s03-in-f14.1e100.net (172.217.174.238): icmp_seq=5 ttl=55 time=1.35 ms

^C--- google.com ping statistics ---
5 packets transmitted, 5 received, 0% packet loss, time 4007ms
rtt min/avg/max/mdev = 1.270/1.448/1.764/0.188 ms
ubuntu@ip-172-31-8-139:~$

===========================================================================================================================


# traceroute / tracert (trace packet routes)
The traceroute command can help diagnose connection issues between different servers and locations.
===========================================================================================================================================================

traceroute to google.com (142.250.66.14), 64 hops max
  1   240.2.196.14  0.932ms  0.902ms  1.194ms
  2   *  *  *
  3   99.82.178.53  1.958ms  2.317ms  2.131ms
  4   *  *  *
  5   72.14.237.138  2.631ms  2.803ms  2.247ms
  6   72.14.236.219  1.706ms  1.841ms  1.772ms
  7   142.250.66.14  1.090ms  1.069ms  1.065ms
ubuntu@ip-172-31-8-139:~$
ubuntu@ip-172-31-8-139:~$

=========================================================================================================================================================



# netstat (network statistics)
The netstat command is a command-line tool for retrieving network statistics. It provides an overview of network activity and displays which ports are open or have established connections. netstat is essential for diagnosing network issues.
=======================================================================================================================================================

ubuntu@ip-172-31-8-139:~$ netstat -tulnp
(No info could be read for "-p": geteuid()=1000 but you should be root.)
Active Internet connections (only servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State       PID/Program name
tcp        0      0 0.0.0.0:80              0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:6010          0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.1:36215         0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.53:53           0.0.0.0:*               LISTEN      -
tcp        0      0 127.0.0.54:53           0.0.0.0:*               LISTEN      -
tcp6       0      0 ::1:6010                :::*                    LISTEN      -
tcp6       0      0 :::22                   :::*                    LISTEN      -
tcp6       0      0 :::80                   :::*                    LISTEN      -
udp        0      0 127.0.0.54:53           0.0.0.0:*                           -
udp        0      0 127.0.0.53:53           0.0.0.0:*                           -
udp        0      0 172.31.8.139:68         0.0.0.0:*                           -
udp        0      0 127.0.0.1:323           0.0.0.0:*                           -
udp6       0      0 ::1:323                 :::*                                -
ubuntu@ip-172-31-8-139:~$

=====================================================================================================================================================================



# curl (make HTTP requests)
Curl (Client URL) is a command-line tool used for transferring data with various protocols, including HTTP, HTTPS, FTP, and many more.
Update the Package Index.
sudo apt install curl
curl http://www.example.com/
=========================================================================================================================================================================


ubuntu@ip-172-31-8-139:~$ curl -I --http2 https://www.ubuntu.com/
HTTP/2 301
server: nginx/1.14.0 (Ubuntu)
date: Sun, 16 Feb 2025 14:13:04 GMT
content-type: text/html
content-length: 162
location: https://ubuntu.com/
strict-transport-security: max-age=15724800
link: <https://assets.ubuntu.com>; rel=preconnect; crossorigin, <https://assets.ubuntu.com>; rel=preconnect, <https://res.cloudinary.com>; rel=preconnect
x-cache-status: HIT from content-cache-il3/0

ubuntu@ip-172-31-8-139:~$

=================================================================================================================================================================



# dig / nslookup (DNS lookup)
The dig command in Linux is used to gather Domain Name System (DNS) information. It stands for domain information groper and helps troubleshoot DNS problems.
=================================================================================================================================================================

ubuntu@ip-172-31-8-139:~$ dig google.com

; <<>> DiG 9.18.30-0ubuntu0.24.04.2-Ubuntu <<>> google.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 42356
;; flags: qr rd ra; QUERY: 1, ANSWER: 1, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 65494
;; QUESTION SECTION:
;google.com.                    IN      A

;; ANSWER SECTION:
google.com.             195     IN      A       172.217.174.238

;; Query time: 2 msec
;; SERVER: 127.0.0.53#53(127.0.0.53) (UDP)
;; WHEN: Sun Feb 16 14:13:51 UTC 2025
;; MSG SIZE  rcvd: 55

ubuntu@ip-172-31-8-139:~$
