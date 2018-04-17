# init
The part 1 “Network” is done on school’s 42 Mac.  The part 2 and
3, “System” and “Scripting” is done on a Debian virtual machine.

## V.1 Network

### 01
#### Get the list of the network interfaces of the machine without displaying any detail for these interfaces. Only the list of names [>man ifconfig]

A network interface is the point of interconnection between a computer and a private or public network. A network interface is generally a network interface card (NIC), but does not have to have a physical form. Instead, the network interface can be implemented in software. For example, the loopback interface (127.0.0.1 for IPv4 and ::1 for IPv6) is not a physical device but a piece of software simulating a network interface. The loopback interface is commonly used in test environments
[[took it here]](https://docs.oracle.com/javase/tutorial/networking/nifs/definition.html).

The -l flag may be used to list all available interfaces on the system, with no other additional information.  Use of this flag is mutually exclusive with all other flags and commands, except for -d (only list interfaces that are down) and -u (only list interfaces that are up). [>man ifconfig]

##### links

* [:rocket:](http://xgu.ru/wiki/Сетевой_интерфейс)
* [..](https://books.google.com.ua/books?id=MIwu0ljbY2gC&pg=PA190&lpg=PA190&dq=сетевой+интерфейс&source=bl&ots=toUU63tNpl&sig=54mSZV-8mcpl9RAwon90U6x1KOM&hl=ru&sa=X&ved=0ahUKEwjC8bCSi7raAhWB2ywKHYbmCE84ChDoAQhgMAk#v=onepage&q=сетевой%20интерфейс&f=false)
* [..](https://www.computerhope.com/unix/uifconfi.htm)
* [..](https://superuser.com/questions/267660/can-someone-please-explain-ifconfig-output-in-mac-os-x)

### 02
#### Identify the IP address of the Ethernet interface [>man ifconfig]

Ethernet is the name of the most commonly used LAN today. A LAN (Local Area Network) is a network of computers that covers a small area like a room, an office, a building or a campus. It is used in contrast with WAN (wide area network) which spans for much larger geographical areas. Ethernet is a network protocol that controls how data is transmitted over a LAN. Technically it is referred to as the IEEE 802.3 protocol.

##### links
* [..](https://www.cyberciti.biz/faq/how-to-find-out-the-ip-address-assigned-to-eth0-and-display-ip-only/)
* [..](https://linux.die.net/man/1/grep)
* [..](https://proft.me/2011/09/17/grep-kollekciya-primerov-ispolzovaniya/)
* [..](http://onedev.net/post/266)

### 03
#### Identify the MAC address of the Wi-Fi card [>man ifconfig]

A media access control address (MAC address) of a device is a unique identifier assigned to network interface controllers for communications at the data link layer of a network segment. MAC address is like social security number which remains unchanged for a person's life time (here, the device), but IP address is like postal code which can be changed.

##### links
* [..](https://ru.wikipedia.org/wiki/MAC-адрес)
* [..](http://osxdaily.com/2014/09/03/list-all-network-hardware-from-the-command-line-in-os-x/)

### 04
#### Identify the default gateway in the routing table [>man netstat]

A default gateway is the node in a computer network using the Internet Protocol Suite that serves as the forwarding host (router) to other networks when no other route specification matches the destination IP address of a packet.

In computer networking a routing table, or routing information base (RIB), is a data table stored in a router or a networked computer that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes. The routing table contains information about the topology of the network immediately around it. The construction of routing tables is the primary goal of routing protocols. Static routes are entries made in a routing table by non-automatic means and which are fixed rather than being the result of some network topology "discovery" procedure.

Default Route in Routing Table: the entry corresponding to the default gateway configuration is a network destination of 0.0.0.0 with a network mask (netmask) of 0.0.0.0. Any destination IP address joined with 0.0.0.0 by a logical AND results in 0.0.0.0. Therefore, for any IP address, the default route produces a match. If the default route is chosen because no better routes were found, the IP packet is forwarded to the IP address in the Gateway column using the interface corresponding to the IP address in the Interface column.

The ~~netstat~~ command symbolically displays the contents of various network-related data structures. -n :show network addresses as numbers (normally netstat interprets addresses and attempts to display them symbolically). This option may be used with any of the display formats. Show the routing tables.  Use with -a to show protocol-cloned routes.  When -s is also present, show routing statistics instead.  When -l is also present, netstat assumes more columns are there and the maximum transmission unit (mtu) are also displayed.

##### links
* [..](https://ru.wikipedia.org/wiki/Таблица_маршрутизации)
* [..](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-2000-server/cc958823(v=technet.10))
