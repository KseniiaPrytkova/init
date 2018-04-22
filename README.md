# init
The part 1 “Network” is done on school’s 42 Mac.  The part 2 and
3, “System” and “Scripting” is done on a Debian virtual machine.

## V.1 Network

### 01
#### Get the list of the network interfaces of the machine without displaying any detail for these interfaces. Only the list of names `[>man ifconfig]`

A `network interface` is the point of interconnection between a computer and a private or public network. A network interface is generally a network interface card (NIC), but does not have to have a physical form. Instead, the network interface can be implemented in software. For example, the loopback interface (127.0.0.1 for IPv4 and ::1 for IPv6) is not a physical device but a piece of software simulating a network interface. The loopback interface is commonly used in test environments
[[took it here]](https://docs.oracle.com/javase/tutorial/networking/nifs/definition.html).

The -l flag may be used to list all available interfaces on the system, with no other additional information.  Use of this flag is mutually exclusive with all other flags and commands, except for -d (only list interfaces that are down) and -u (only list interfaces that are up). [>man ifconfig]

##### links

* [:rocket:](http://xgu.ru/wiki/Сетевой_интерфейс)
* [:rocket:](https://books.google.com.ua/books?id=MIwu0ljbY2gC&pg=PA190&lpg=PA190&dq=сетевой+интерфейс&source=bl&ots=toUU63tNpl&sig=54mSZV-8mcpl9RAwon90U6x1KOM&hl=ru&sa=X&ved=0ahUKEwjC8bCSi7raAhWB2ywKHYbmCE84ChDoAQhgMAk#v=onepage&q=сетевой%20интерфейс&f=false)
* [:rocket:](https://www.computerhope.com/unix/uifconfi.htm)
* [:rocket:](https://superuser.com/questions/267660/can-someone-please-explain-ifconfig-output-in-mac-os-x)

### 02
#### Identify the IP address of the Ethernet interface `[>man ifconfig]`

`Ethernet` is the name of the most commonly used LAN today. A LAN (Local Area Network) is a network of computers that covers a small area like a room, an office, a building or a campus. It is used in contrast with WAN (wide area network) which spans for much larger geographical areas. Ethernet is a network protocol that controls how data is transmitted over a LAN. Technically it is referred to as the IEEE 802.3 protocol.

##### links
* [:rocket:](https://www.cyberciti.biz/faq/how-to-find-out-the-ip-address-assigned-to-eth0-and-display-ip-only/)
* [:rocket:](https://linux.die.net/man/1/grep)
* [:rocket:](https://proft.me/2011/09/17/grep-kollekciya-primerov-ispolzovaniya/)
* [:rocket:](http://onedev.net/post/266)

### 03
#### Identify the MAC address of the Wi-Fi card `[>man ifconfig]`

A media access control address (MAC address) of a device is a unique identifier assigned to network interface controllers for communications at the data link layer of a network segment. **MAC address** is like **social security number** which remains unchanged for a person's life time (here, the device), but **IP address** is like **postal code** which can be changed.

##### links
* [:rocket:](https://ru.wikipedia.org/wiki/MAC-адрес)
* [:rocket:](http://osxdaily.com/2014/09/03/list-all-network-hardware-from-the-command-line-in-os-x/)

### 04
#### Identify the default gateway in the routing table `[>man netstat]`

A `default gateway` is the node in a computer network using the Internet Protocol Suite that serves as the forwarding host (router) to other networks when no other route specification matches the destination IP address of a packet.

In computer networking a `routing table`, or routing information base (RIB), is a data table stored in a router or a networked computer that lists the routes to particular network destinations, and in some cases, metrics (distances) associated with those routes. The routing table contains information about the topology of the network immediately around it. The construction of routing tables is the primary goal of routing protocols. Static routes are entries made in a routing table by non-automatic means and which are fixed rather than being the result of some network topology "discovery" procedure.

`Default route in routing table`: the entry corresponding to the default gateway configuration is a network destination of 0.0.0.0 with a network mask (netmask) of 0.0.0.0. Any destination IP address joined with 0.0.0.0 by a logical AND results in 0.0.0.0. Therefore, for any IP address, the default route produces a match. If the default route is chosen because no better routes were found, the IP packet is forwarded to the IP address in the Gateway column using the interface corresponding to the IP address in the Interface column.

The `netstat` command symbolically displays the contents of various network-related data structures. `-r` : show the routing tables.  Use with -a to show protocol-cloned routes.  When -s is also present, show routing statistics instead.  When -l is also present, netstat assumes more columns are there and the maximum transmission unit (mtu) are also displayed. 

`-n` :show network addresses as numbers (normally netstat interprets addresses and attempts to display them symbolically). This option may be used with any of the display formats.


##### links
* [:rocket:](https://ru.wikipedia.org/wiki/Таблица_маршрутизации)
* [:rocket:](https://docs.microsoft.com/en-us/previous-versions/windows/it-pro/windows-2000-server/cc958823(v=technet.10))
* [:rocket:](http://rus-linux.net/MyLDP/consol/awk.html) - about awk

### 05
#### Identify the IP address of the DNS that responds to the following url: slash16.org `[>man nslookup]`

The Domain Name System (DNS) is a hierarchical decentralized naming system for computers, services, or other resources connected to the Internet or a private network. It associates various information with domain names assigned to each of the participating entities. Most prominently, it translates more readily memorized domain names to the numerical IP addresses needed for locating and identifying computer services and devices with the underlying network protocols.

##### links
* [:rocket:](https://habrahabr.ru/post/303446/)
* [:rocket:](http://jack.kiev.ua/docs/slackbook/basic-network-commands-dns.html)

### 06
#### Get the complete path of the file that contains the IP address of the DNS server you’re using `[>google man->nameserver unix]`

`resolv.conf` is the name of a computer file used in various operating systems to configure the system's Domain Name System (DNS) resolver (the client side of the DNS is called a DNS resolver). The file is a plain-text file usually created by the network administrator or by applications that manage the configuration tasks of the system. The resolvconf program is one such program on FreeBSD or other Unix machines which manages the resolv.conf file.

##### links
* [:rocket:](https://habrahabr.ru/post/303446/) - Давайте уже разберемся в DNS, Хабрахабр
* [:rocket:](https://habrahabr.ru/company/ruvds/blog/328346/) - очень хорошая статья о Bash-скриптах, Хабрахабр
* [:rocket:](https://forums.macrumors.com/threads/how-do-i-find-out-my-dns-server-ip.466158/)

### 07
#### Query an external DNS server on the slash16.org domain name (ie. : google 8.8.8.8) `[>man dig]`

##### links
* [:rocket:](https://habrahabr.ru/post/137587/) - DNS сервер BIND (теория), Хабрахабр
* [:rocket:](https://en.wikipedia.org/wiki/Google_Public_DNS) - Google Public DNS
* [:rocket:](https://developers.google.com/speed/public-dns/docs/using) - Configure your network settings to use Google Public DNS
* [:rocket:](http://droptips.com/using-dig-to-query-a-specific-dns-server-name-server-directly-linux-bsd-osx) - Using dig to Query a Specific DNS Server (Name Server) Directly (Linux, BSD, OSX)

### 08
#### Find the provider of slash16.org `[>man whois]` `[>man dig]`

ohhhh, it's Amazon!

### 09
#### Find the external IP of 42.fr `[>man host]` `[>man dig]`

I have two IP addresses, an Internal IP address (Private) and an external IP address (Public). The `external IP address` or Public IP address is the IP address of the router interface that is connected to the Internet. `Internal Addresses` are also called Private addresses as they are restricted to private networks. [:rocket:](http://www.steves-internet-guide.com/internal-external-ip-addresses/)

### 10
#### Identify the network devices between your computer and the slash16.org domain `[>man traceroute]`

Traceroute is a utility that records the route (the specific gateway computers at each hop) through the Internet between your computer and a specified destination computer. It also calculates and displays the amount of time each hop took. Traceroute is a handy tool both for understanding where problems are in the Internet network and for getting a detailed sense of the Internet itself.

* [:rocket:](https://ru.wikipedia.org/wiki/Канал_связи) - Канал связи

### 11
#### Use the output of the previous command to find the name and IP address of the device that makes the link between you (local network) and the outside world `[>man traceroute]`

this device is a server in my school

### 12
#### Check that the server with the 10.51.1.253 IP address is reachable from your computer. `[>man ping]`

### 13
#### Check that the server with the 10.51.1.253 IP address is reachable from your computer. `[>man ]`

13. man nslookup && google it: server type

### 14
#### Use the Reverse DNS to find out the name of the server linked to the 10.51.1.81 IP address `[>man ]`

14. man dig && man host

### 15
#### What file contains the local DNS entries? `[>man ]`

15. google it: file hosts

### 16
#### Make the intra.42.fr address reroute to 46.19.122.85 `[>man ]`

16. google it: file hosts

## V.2 System

First u should download Debian ISO image from [here](https://cdimage.debian.org/debian-cd/current-live/amd64/iso-hybrid/). I used `debian-live-9.3.0-amd64-cinnamon.iso` version. Then run it on virtualizer, i used VirtualBox. (in case of my school everything should be done in /tmp folder, otherwise there will be problems with memory; also i ran ISO image from flash drive).

### 01
#### In what file can you find the installed version of your Debian?

The answer is [here](https://linuxconfig.org/check-what-debian-version-you-are-running-on-your-linux-system).

### 02
#### What command can you use to rename your system?

To find the current computer name type `$ hostname`. To change the name of the system u need to Become a root user: `sudo -s` or `su -`.[:mag:](https://www.cyberciti.biz/faq/debian-change-hostname-permanently/)

### 03
#### What file has to be modified to make it permanent?

Everything about it [:mag:](https://debianworld.ru/articles/izmenenie-hostname-v-ubuntu-debian/index.html).

### 04
#### What command gives you the time since your system was last booted?

[:mag:](https://www.cyberciti.biz/tips/linux-last-reboot-time-and-date-find-out.html) - Linux Find Out Last System Reboot Time and Date Command

### 05
#### Name the command that determines the state of the SSH service.

SSH stands for Secure Shell and is `a cryptographic network protocol` for secure remote login and other secure network services over an insecure network [:mag:](https://wiki.debian.org/SSH). The best known example application is for remote login to computer systems by users.
* [:mag:](https://en.wikipedia.org/wiki/Secure_Shell) - Secure Shell
* [:mag:](http://help.ubuntu.ru/wiki/ssh) - SSH
* [:mag:](https://linuxhint.com/enable-ssh-server-debian/) - Enable SSH Server on Debian (How to Enable SSH Server for Remote Login on Debian 9).

### 06
#### Name the command that reboots the SSH service.

Exhaustive answer is here: [:mag:](https://www.cyberciti.biz/faq/howto-start-stop-ssh-server/).

[:mag:](https://www.cyberciti.biz/faq/find-linux-distribution-name-version-number/) - HowTo: Find Out My Linux Distribution Name and Version

### 07
#### Figure out the PID of the SSHD service.

`PID` - process ID of a running terminal program.

`SSHD` is the [OpenSSH](https://ru.wikipedia.org/wiki/OpenSSH) server process. It listens to incoming connections using the SSH protocol and acts as the server for the protocol. It handles user authentication, encryption, terminal connections, file transfers, and tunneling.

* [:mag:](https://www.ssh.com/ssh/sshd/) - about SSHD process.
* [:mag:](https://habrahabr.ru/post/331348/) - Магия SSH, Хабрахабр
* [:mag:](https://stackoverflow.com/questions/6867669/getting-pid-of-sshd) - Getting PID of sshd

### 08
#### What file contains the RSA keys that are authorized to connect via SSH?

`RSA key` is a private key based on RSA algorithm [RSA is one of the first public-key cryptosystems and is widely used for secure data transmission.](https://ru.wikipedia.org/wiki/RSA). Private Key is used for authentication and a symmetric key exchange during establishment of an SSL/TLS session. [:mag:](https://www.namecheap.com/support/knowledgebase/article.aspx/798/67/what-is-an-rsa-key-used-for)

[:mag:](https://www.digitalocean.com/community/tutorials/ssh-essentials-working-with-ssh-servers-clients-and-keys) - SSH Essentials: Working with SSH Servers, Clients, and Keys

### 09
#### What command lets you know who is connected to the System?

Here is the answer [:mag:](https://serverfault.com/questions/360296/see-all-logged-in-users-on-debian-server).

* [:mag:](https://www.thegeekstuff.com/2009/03/4-ways-to-identify-who-is-logged-in-on-your-linux-system) - 4 Ways to Identify Who is Logged-In on Your Linux System
* [:mag:](https://www.computerhope.com/unix/uwho.htm) - Linux who command

### 10
#### Name the command that lists the partition tables of external devices?

A partition ([GUID Partition Table](https://ru.wikipedia.org/wiki/Таблица_разделов_GUID)) is a fixed-size subset of a disk drive which is treated as a unit by the operating system.[1] A partition table is a table maintained on disk by the operating system describing the partitions on that disk. Partitions can be created, resized, or deleted. This is called disk partitioning. It is usually done during the installation of an operating system, however it is sometimes possible to make changes to the partitions even after the operating system has been installed.

* [:mag:](http://www.lostsaloon.com/technology/how-to-list-disks-in-linux/) - how to list all hard disks in linux from command line
* [:mag:](https://www.cyberciti.biz/faq/linux-viewing-drive-partitions-with-fdisk-parted/) - Linux View Hard Drive Partitions with fdisk and parted commands

### 11
#### Name the command that displays the available space left on the system?

[Linux Check Disk Space Command](https://www.cyberciti.biz/faq/linux-check-disk-space-command/).

### 12
#### Figure out the exact size of each folder of /var.

The command du "summarizes disk usage of each FILE, recursively for directories," e.g.: `du -hs /path/to/directory`.
* `-h` is to get the numbers "human readable", e.g. get 140M instead of 143260 (size in KBytes);
* `-s` is for summary (otherwise you'll get not only the size of the folder but also for everything in the folder separately).[:mag:](https://askubuntu.com/questions/1224/how-do-i-determine-the-total-size-of-a-directory-folder-from-the-command-line)
