# Модуль 1
### ISP (root toor)
```
ip -c a
vim /etc/net/ifaces/ens18/options (выход ESC, q!)
apt-get update
systemctl status iptables
iptables -t nat -L
sysctl -a | grep ip_forward
timedatectl (проверить время)
```
### HQ-RTR (admin admin)
```
enable
show ip interface brief
show ip route
ping 8.8.8.8 c4
show ntp status
show ntp date
ping 172.16.100.2 c4
show ip ospf neighbor
ping 192.168.2.2 c4
show run (скрин портов где vlan) 
show ip nat translations
```
### BR-RTR (admin admin)
```
enable
show ip interface brief
show ip route
ping 8.8.8.8 c4
show ntp status
show ntp date
ping 172.16.100.1 c4
show ip ospf neighbor
ping 192.168.1.2 c4
show run (скрин портов где vlan)
show ip nat translations
```
### HQ-SRV (root toor)
```
hostname
ip -c a
apt-get update
su - sshuser (проверить sudo без пароля)
sudo -i
exit
ssh -p 2024 192.168.2.2 (P@ssw0rd, проверить 2 попытки и баннер)
exit
exit
systemctl status bind
timedatectl (проверить время)
```
### BR-SRV (root toor)
```
hostname
ip -c a
apt-get update
su - sshuser
sudo -i (проверить sudo без пароля)
exit
ssh -p 2024 192.168.1.2 (P@ssw0rd, проверить 2 попытки и баннер)
exit
exit
timedatectl (проверить время)
```
### HQ-CLI (user resu)
```
hostname
apt-get update
timedatectl (проверить время)
ping hq-rtr -c4
ping hq-srv -c4
ping hq-cli -c4
ping br-rtr -c4
ping br-srv -c4
ping wiki -c4
ping moodle -c4
```
# Модуль 2
### HQ-RTR (admin admin)
```
enable
ping 8.8.8.8 c4
show ntp status
show ntp date
show run
show ip nat translations
```
### BR-RTR (admin admin)
```
enable
ping 8.8.8.8 c4
show ntp status
show ntp date
show run
show ip nat translations
```
### HQ-SRV (root toor)
```
apt-get update
df -h (внизу должен быть /dev/md0 /raid0)
systemctl status nfs-server
vim /etc/chrony.conf (выход ESC, q!)
systemctl status chrony
chronyc clients
timedatectl 
```
### BR-SRV (root toor)
```
apt-get update
timedatectl 
cat /etc/ansible/ansible.cfg | less (выход q или ctrl + c)
chronyc sources (должно вывести сервер, главное чтобы не пусто)
ansible -m ping all (на всех должно быть pong)
```
### HQ-CLI (user resu)
```
apt-get update
df -h (внизу должен быть /mnt/nfs)
chronyc sources (должно вывести сервер, главное чтобы не пусто)
Запустить Яндекс Браузер и добавить его скрин в отчет
Через проводник создать файл с текстом в папке /mnt/nfs
Зайти на HQ-SRV и проверить появился ли файл:
ls /raid0/nfs
cat /raid0/nfs/<название файла>
```
