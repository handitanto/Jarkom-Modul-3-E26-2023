# Jarkom-Modul-3-E26-2023
**Praktikum Jaringan Komputer Modul 2 Tahun 2023**

## Author
| Nama | NRP |
|---------------------------|------------|
|Handitanto Herprasetyo | 5025201077 |

## Topologi
![image](![image](https://github.com/handitanto/Jarkom-Modul-3-E26-2023/assets/94664744/569e3572-71c0-49fd-820a-185d71e68845)

## Config
**Aura**
```
auto eth0
iface eth0 inet dhcp
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.219.0.0/16

auto eth1
iface eth1 inet static
	address 192.219.1.0
	netmask 255.255.255.0

auto eth2
iface eth2 inet static
	address 192.219.2.0
	netmask 255.255.255.0

auto eth3
iface eth3 inet static
	address 192.219.3.0
	netmask 255.255.255.0

auto eth4
iface eth4 inet static
	address 192.219.4.0
	netmask 255.255.255.0
```
**Himmel**
```
auto eth0
iface eth0 inet static
	address 192.219.1.1
	netmask 255.255.255.0
	gateway 192.219.1.0
```
**Heiter**
```
auto eth0
iface eth0 inet static
	address 192.219.1.2
	netmask 255.255.255.0
	gateway 192.219.1.0
```
**Denken**
```
auto eth0
iface eth0 inet static
	address 192.219.2.1
	netmask 255.255.255.0
	gateway 192.219.2.0
```
**Eisen**
```
auto eth0
iface eth0 inet static
	address 192.219.2.2
	netmask 255.255.255.0
	gateway 192.219.2.0
```
**Frieren**

```
auto eth0
iface eth0 inet static
	address 192.219.4.3
	netmask 255.255.255.0
	gateway 192.219.4.0
```
**Flamme**
```
auto eth0
iface eth0 inet static
	address 192.219.4.2
	netmask 255.255.255.0
	gateway 192.219.4.0
```
**Fern**
```
auto eth0
iface eth0 inet static
	address 192.219.4.1
	netmask 255.255.255.0
	gateway 192.219.4.0
```
**Lawine**
```
auto eth0
iface eth0 inet static
	address 192.219.3.3
	netmask 255.255.255.0
	gateway 192.219.3.0
```
**Linie**
```
auto eth0
iface eth0 inet static
	address 192.219.3.2
	netmask 255.255.255.0
	gateway 192.219.3.0
iface eth0 inet static
	address 192.219.3.2
	netmask 255.255.255.0
	gateway 192.219.3.0
```
**Lugner**
```
auto eth0
iface eth0 inet static
	address 192.219.3.1
	netmask 255.255.255.0
	gateway 192.219.3.0
```
**Revolte, Riccher, Sein, Stark**
```
auto eth0
iface eth0 inet dhcp
```

## Script (nano /root/.bashrc)
**Aura (Rooter + DHCP Relay)**
```
iptables -t nat -A POSTROUTING -o eth0 -j MASQUERADE -s 192.219.0.0/16
apt-get update
apt-get install isc-dhcp-relay -y
service isc-dhcp-relay start
```
**Heiter (DNS Server)**
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install bind9 -y
```
**Himmel (DHCP Server)**
```
echo nameserver 192.168.122.1 > /etc/resolv.conf
apt-get update
apt-get install isc-dhcp-server -y
```
**Eisen (Load Balancer)**
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
apt-get update
apt-get install dnsutils -y
apt-get install lynx -y
apt-get install bind9 nginx -y
service nginx start
```
**PHP Worker (Lawine, Linie, Lugner)**
```
echo ‘nameserver 192.168.122.1’ > /etc/resolv.conf
apt-get update
apt-get install nginx -y
apt-get install apache2 -y
apt-get install php -y
service apache2 start
apt-get install wget -y
apt-get install unzip -y
```
**Denken (Database Server)**
```
echo 'nameserver 192.168.122.1' > /etc/resolv.conf
apt-get update
apt-get install mariadb-server -y
service mysql start
```
**Client**
```
echo ‘nameserver 192.168.122.1
search example.org
nameserver 192.219.1.3’ >> /etc/resolv.conf
apt-get update
apt-get install dnsutils -y
apt-get install lynx -y
```
