# ChickenJokey---ISP---(корневой доступ)
ip-ca
vim /etc/net/ifaces/ens18 (нужно ESC, q!)
обновление apt-get
systemctl статус iptables
iptables -t nat -L
sysctl -a | grep ip_forward
timedatectl (карта)

---HQ-RTR---(админ админ)
давать возможность
показать краткое описание интерфейса IP
показать ip маршрут
пинг 8.8.8.8 c4
показать статус ntp
показать дату ntp
пинг 172.16.100.2 c4
показать ip ospf соседа
пинг 192.168.2.2 c4
show run (подключенный к сети vlan)
показать переводы ip nat

---BR-RTR---(админ админ)
давать возможность
показать краткое описание интерфейса IP
показать ip маршрут
пинг 8.8.8.8 c4
показать статус ntp
показать дату ntp
пинг 172.16.100.1 c4
показать ip ospf соседа
пинг 192.168.1.2 c4
show run (подключенный к сети vlan)
показать переводы ip nat

---HQ-SRV---(пользователь root или sshuser P@ssw0rd)
имя хоста
ip-ca
обновление apt-get
su - sshuser (команда sudo недоступна)
судо -i
Выход
ssh -P 2024 192.168.2.2 (P@ssw0rd, пароль 2-х адресов)
Выход
Выход
systemctl статус привязки
timedatectl (карта)

---BR-SRV---(пользователь root или sshuser P@ssw0rd)
имя хоста
ip-ca
обновление apt-get
су - сшусер
sudo -i (перевести sudo в режим)
Выход
ssh -P 2024 192.168.1.2 (P@ssw0rd, пароль 2-х мест)
Выход
Выход
timedatectl (карта)

---HQ-CLI---(пользователь resu)
имя хоста
обновление apt-get
timedatectl (карта)
пинг hq-rtr -c4
пинг hq-srv -c4
пинг hq-cli -c4
пинг br-rtr -c4
пинг br-srv -c4
пинг вики -c4
пинг moodle -c4
