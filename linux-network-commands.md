# Useful Linux Network Commmands

**Step 1:** Go to the Katacoda Ubuntu Playground

`https://katacoda.com/courses/ubuntu/playground`

**Step 2:** Execute the following commands. Have fun!

**COMMAND: ifconfig**

_ifconfig reports the IP Address and Hardware / MAC address information assigned to the network interface and also the MTU (Maximum transmission unit) size._

Example: `ifconfig`

* To read the manual page type, `man ifconfig`.
* To  get help type, `ifconfig --help`.

You'll get output similar to, but not exactly like the following:

```text
docker0   Link encap:Ethernet  HWaddr 02:42:54:e5:c7:41
          inet addr:172.18.0.1  Bcast:172.18.0.255  Mask:255.255.255.0
          UP BROADCAST MULTICAST  MTU:1500  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:0
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)

ens3      Link encap:Ethernet  HWaddr 02:42:ac:11:00:22
          inet addr:172.17.0.34  Bcast:172.17.255.255  Mask:255.255.0.0
          inet6 addr: fe80::42:acff:fe11:22/64 Scope:Link
          UP BROADCAST RUNNING MULTICAST  MTU:1500  Metric:1
          RX packets:6022 errors:0 dropped:0 overruns:0 frame:0
          TX packets:3171 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1000
          RX bytes:1299791 (1.2 MB)  TX bytes:557177 (557.1 KB)

lo        Link encap:Local Loopback
          inet addr:127.0.0.1  Mask:255.0.0.0
          inet6 addr: ::1/128 Scope:Host
          UP LOOPBACK RUNNING  MTU:65536  Metric:1
          RX packets:0 errors:0 dropped:0 overruns:0 frame:0
          TX packets:0 errors:0 dropped:0 overruns:0 carrier:0
          collisions:0 txqueuelen:1
          RX bytes:0 (0.0 B)  TX bytes:0 (0.0 B)

```

**COMMAND: ping**

_ping (Packet INternet Groper) command tests connectivity between two nodes._

Example: `ping nbc.com`

* To read the manual page type, `man ping `.
* To  get help type, `ping --help`.

You'll get output similar to, but not exactly like the following:

```text
PING nbc.com (2.21.41.34) 56(84) bytes of data.
64 bytes from a2-21-41-34.deploy.static.akamaitechnologies.com (2.21.41.34): icmp_seq=1 ttl=59 time=11.2 ms
64 bytes from a2-21-41-34.deploy.static.akamaitechnologies.com (2.21.41.34): icmp_seq=2 ttl=59 time=11.3 ms
64 bytes from a2-21-41-34.deploy.static.akamaitechnologies.com (2.21.41.34): icmp_seq=3 ttl=59 time=11.5 ms
64 bytes from a2-21-41-34.deploy.static.akamaitechnologies.com (2.21.41.34): icmp_seq=4 ttl=59 time=11.3 ms
64 bytes from a2-21-41-34.deploy.static.akamaitechnologies.com (2.21.41.34): icmp_seq=5 ttl=59 time=11.1 ms
```

**COMMAND: traceroute**

_traceroute is a network utility that shows the number of hops taken to reach destination and also t0 determine packets traveling path_

This command requires that you in install, `traceroute`. To do the installlation, enter the following at the command line:

`apt update && apt install traceroute -y`

Once installed, execute the example.


Example: `traceroute -I nbc.com`

* To read the manual page type, `man traceroute `.
* To  get help type, `ping --traceroute `.

You'll get output similar to, but not exactly like the following:

```text
traceroute to nbc.com (2.22.32.148), 30 hops max, 60 byte packets
 1  172.17.0.1 (172.17.0.1)  0.556 ms  0.535 ms  0.530 ms
 2  static.1.50.202.116.clients.your-server.de (116.202.50.1)  0.645 ms  0.653 ms  0.652 ms
 3  core22.fsn1.hetzner.com (213.239.245.121)  0.741 ms  0.743 ms  0.742 ms
 4  core1.fra.hetzner.com (213.239.245.177)  5.333 ms  5.344 ms  5.343 ms
 5  46.33.77.5 (46.33.77.5)  10.048 ms  10.057 ms  10.057 ms
 6  xe-1-2-1.cr0-mil2.ip4.gtt.net (89.149.186.25)  23.408 ms  19.911 ms  19.858 ms
 7  ip4.gtt.net (213.254.196.202)  21.941 ms  23.573 ms  23.551 ms
 8  a2-22-32-148.deploy.static.akamaitechnologies.com (2.22.32.148)  19.823 ms  19.915 ms  19.912 ms
```

**COMMAND: netstat**

_netstat (Network Statistic) displays connection info, routing table information, etc..._

Example: `netstat -v`

* To read the manual page type, `man netstat `.
* To  get help type, `netstat --help`.

You'll get output similar to, but not exactly like the following:

```text
Active Internet connections (w/o servers)
Proto Recv-Q Send-Q Local Address           Foreign Address         State
tcp        0      0 172.17.0.34:ssh         172.17.0.49:42704       ESTABLISHED
Active UNIX domain sockets (w/o servers)
Proto RefCnt Flags       Type       State         I-Node   Path
unix  2      [ ]         DGRAM                    9543     /run/systemd/journal/syslog
unix  2      [ ]         DGRAM                    50268    /run/user/0/systemd/notify
unix  2      [ ]         DGRAM                    9477     /run/systemd/notify
unix  3      [ ]         STREAM     CONNECTED     73987
unix  3      [ ]         DGRAM                    11564
unix  2      [ ]         DGRAM                    11486
unix  3      [ ]         STREAM     CONNECTED     13830    /run/containerd/containerd.sock
unix  3      [ ]         STREAM     CONNECTED     12841
unix  3      [ ]         STREAM     CONNECTED     12825    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     14537
unix  3      [ ]         STREAM     CONNECTED     12842    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     14538
unix  2      [ ]         STREAM     CONNECTED     11484
unix  3      [ ]         STREAM     CONNECTED     13828    /run/containerd/containerd.sock
unix  3      [ ]         STREAM     CONNECTED     73988
unix  3      [ ]         STREAM     CONNECTED     14502    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     12824
unix  3      [ ]         STREAM     CONNECTED     13815
unix  3      [ ]         STREAM     CONNECTED     12622
unix  3      [ ]         STREAM     CONNECTED     12621
unix  3      [ ]         STREAM     CONNECTED     12623    /var/run/dbus/system_bus_socket
unix  3      [ ]         STREAM     CONNECTED     11075
unix  2      [ ]         STREAM                   50251
unix  3      [ ]         DGRAM                    11563
netstat: no support for `AF IPX' on this system.
netstat: no support for `AF AX25' on this system.
netstat: no support for `AF X25' on this system.
netstat: no support for `AF NETROM' on this system.
```
**COMMAND: dig**

_Dig (domain information groper) query DNS related information like A Record, CNAME, MX Record etc. This command mainly use to troubleshoot DNS related query._

Example: `dig www.github.com`

* To read the manual page type, `man dig `.
* To  get help type, `dig --help`.

You'll get output similar to, but not exactly like the following:

```text
; <<>> DiG 9.10.3-P4-Ubuntu <<>> www.github.com
;; global options: +cmd
;; Got answer:
;; ->>HEADER<<- opcode: QUERY, status: NOERROR, id: 65427
;; flags: qr rd ra; QUERY: 1, ANSWER: 2, AUTHORITY: 0, ADDITIONAL: 1

;; OPT PSEUDOSECTION:
; EDNS: version: 0, flags:; udp: 512
;; QUESTION SECTION:
;www.github.com.                        IN      A

;; ANSWER SECTION:
www.github.com.         3599    IN      CNAME   github.com.
github.com.             59      IN      A       140.82.118.4

;; Query time: 7 msec
;; SERVER: 8.8.8.8#53(8.8.8.8)
;; WHEN: Sat Oct 19 23:18:15 UTC 2019
;; MSG SIZE  rcvd: 73
```

**COMMAND: nslookup**

_nslookup finds out DNS information about domain names and IP addressess known to the machine._

Example `nslookup www.devops.com`

* To read the manual page type, `man nslookup `.
* To  get help type, `nslookup --help`.

You'll get output similar to, but not exactly like the following:

```text
Server:         8.8.8.8
Address:        8.8.8.8#53

Non-authoritative answer:
www.devops.com  canonical name = devops.com.
Name:   devops.com
Address: 35.185.75.107
```


**COMMAND: route**

_route command also displays and manipulates ip routing table information._

Example `route`

* To read the manual page type, `man route `.
* To  get help type, `route --help`.


You'll get output similar to, but not exactly like the following:

```text
Kernel IP routing table
Destination     Gateway         Genmask         Flags Metric Ref    Use Iface
default         172.17.0.1      0.0.0.0         UG    0      0        0 ens3
172.17.0.0      *               255.255.0.0     U     0      0        0 ens3
172.18.0.0      *               255.255.255.0   U     0      0        0 docker0
```

**COMMAND: host**

_host correlates a domain name to an IP address in IPv4 or IPv6 format. You can also use it to query DNS records._

Example `host rollingstone.com`

* To read the manual page type, `man host `.
* To  get help type, `host --help`.

You'll get output similar to, but not exactly like the following:

```text
rollingstone.com has address 151.101.192.69
rollingstone.com has address 151.101.128.69
rollingstone.com has address 151.101.64.69
rollingstone.com has address 151.101.0.69
rollingstone.com mail is handled by 10 us-smtp-inbound-1.mimecast.com.
rollingstone.com mail is handled by 20 us-smtp-inbound-2.mimecast.com.
rollingstone.com mail is handled by 10 us-smtp-inbound-2.mimecast.com.
```

**COMMAND: arp**

_arp (Address Resolution Protocol) views contents of and adds content to the the kernel’s [ARP tables](http://www.pearsonitcertification.com/articles/article.aspx?p=2339639&seqNum=4)._

Example `arp -e`

* To read the manual page type, `man arp `.
* To  get help type, `arp --help`.

You'll get output similar to, but not exactly like the following:

```text
Address                  HWtype  HWaddress           Flags Mask            Iface
172.17.0.1               ether   02:42:2c:a6:1d:f4   C                     ens3
172.16.0.34              ether   06:fe:dd:72:0e:33   C                     ens3
172.17.0.49              ether   02:42:ac:11:00:31   C                     ens3
```

**COMMAND: hostname**

_hostname reports the actual host name of the machine_

Example `hostname `

* To read the manual page type, `man hostname `.
* To  get help type, `hostname --help`.

You'll get output similar to, but not exactly like the following:

`host01`