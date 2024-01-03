# notes


## users/groups

`usermod` is at `/usr/sbin` or run as su

create user `sudo adduser USER`
create group `sudo groupadd GROUP`
add user to group `usermod -aG GROUP USER` (-append -groups)

get groups of user `groups USER`
get group info `getent group GROUP`
check local users `cat /etc/passwd | sed 's/:.*$//'`

## ssh

package `openssh-server`
status `sudo systemctl status ssh` or `service` instead of `systemctl`
ports at `/etc/ssh/sshd_config`
restart `sudo service ssh restart` or `service` instead of `systemctl`
connect `ssh USER@localhost -p 4141`

## ufw

package `ufw`
`sudo ufw`:
- enable
- status numbered
- allow ssh
- allow PORT
- delete deny RULE

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
