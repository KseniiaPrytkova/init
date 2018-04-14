# init
The part 1 “Network” is done on school’s 42 Mac.  The part 2 and
3, “System” and “Scripting” is done on a Debian virtual machine.

## V.1 Network

### 01
#### Get the list of the network interfaces of the machine without displaying any detail for these interfaces. Only the list of names.

A network interface is the point of interconnection between a computer and a private or public network. A network interface is generally a network interface card (NIC), but does not have to have a physical form. Instead, the network interface can be implemented in software. For example, the loopback interface (127.0.0.1 for IPv4 and ::1 for IPv6) is not a physical device but a piece of software simulating a network interface. The loopback interface is commonly used in test environments
[[took it here]](https://docs.oracle.com/javase/tutorial/networking/nifs/definition.html).

The -l flag may be used to list all available interfaces on the system, with no other additional information.  Use of this flag is mutually exclusive with all other flags and commands, except for -d (only list interfaces that are down) and -u (only list interfaces that are up). [>man ifconfig]

##### links

* [good resource](http://xgu.ru/wiki/Сетевой_интерфейс)


