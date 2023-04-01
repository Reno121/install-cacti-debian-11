# install-cacti-debian-11


```
apt update && apt upgrade
```
```
apt install sudo unzip
```
```
apt-get install cacti cacti-spine
```
```
dpkg-reconfigure tzdata
```
```
cd /usr/share/cacti/site/plugins
```
```
wget https://github.com/Cacti/plugin_monitor/archive/refs/tags/v2.5.zip
```
```
unzip v2.5.zip
```
```
mv plugin_monitor-2.5 monitor
```
```
wget https://github.com/Cacti/plugin_thold/archive/refs/tags/v1.5.2.zip
```
```
unzip v1.5.2.zip
```
```
mv v1.5.2.zip thold
```

***Aktif kan plugin di***
```
Configuration -> Plugins
```
***Rubah Poler tipe ke spine***
```
Console -> Configuration -> Settings -> Poller -> Poller Type -> Ganti jadi spine -> SAVE
```

***Tambahkan Mikrotik***
Aktifkan SNPM DI Mikrotik, kasih akses read aja ya

Di Cacti
Create -> New Device
Description : Isi Bebas
Hostname : Isi IP Public Mikrotik
Device Template : Net-SNMP Device
Monitori Device : Enabel
Ping Warning : 400
Ping Alert : 400

di SNMP Options sesuaikan dengan yang ada dimikrotik

Downed Device Detection bisa piling Ping ICMP, Ping UDP, Ping TCP, atau SNMP Uptime
Lalu save
