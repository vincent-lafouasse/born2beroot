# notes

## signature 

generate with _____________________
check with `diff`

## apparmor

= restreindre les acces des process/programmes
monitor with `sudo aa-status`

## ssh

package `openssh-server`
status `sudo systemctl status ssh` or `service` instead of `systemctl`
ports/config at `/etc/ssh/sshd_config`
restart `sudo service ssh restart` or `service` instead of `systemctl`
connect `ssh USER@localhost -p 4141`

## ufw = uncomplicated firewall

fw = surveiller les ports et les connections eg seulement port ssh

package `ufw`
`sudo ufw`:
- enable
- status numbered
- allow ssh
- allow PORT
- delete RULE
- delete allow PORT

## users/groups

`usermod` is at `/usr/sbin` or run as su

create user `sudo adduser USER` et pas useradd
create group `sudo groupadd GROUP`
delete group `groupdel [OPTIONS] GROUP`
add user to group `usermod -aG GROUP USER` (-append -groups)

get groups of user `groups USER`
get group info `getent group GROUP`
check local users `cat /etc/passwd | awk -F ':' '{print $1}'`

## hostname

monitor with `hostnamectl`
change with `hostnamectl set-hostname HOSTNAME`  + reboot

## LVM = Logical Volume Manager

monitor with `lsblk`

## sudo log

at `/var/log/sudo/sudo.log`
config at `/etc/sudoers` access via `visudo`

## packages

show packages with `dpkg -l`

## port forwarding

VM > Sttings > Network > Adapter 1 > Advanced > Port forwarding
VM = guest
guest port 4242
host port 4141

## password policy

package `libpam-pwquality`
passwrd strength config at `/etc/pam.d/common-password`
difok = difference with old password
passwrd age config at `/etc/login.defs`
change manually with `sudo chage -M/m/W` max, min, warn expiration
monitor with `sudo chage -l USER`

## crontab

package `net-tools`
edit with `sudo crontab -e root -e`

## monitoring script 

in `/usr/local/bin`
