# notes

## users

## groups

usermod -aG GROUP USER (-append -groups)
getent group GROUP

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
