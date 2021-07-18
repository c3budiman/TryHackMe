# Recon CheatSheet

## add host
sudo nano /etc/hosts
sudo killall -HUP mDNSResponder

## ping

ping 10.10.40.72

## nmap

mkdir nmap
nmap -sC -sV -oN nmap/initial 10.10.102.134

## nmap with script example

find /usr/local/Cellar/nmap/7.91/share/nmap/scripts/ -name '*.nse' | grep smb
nmap --script=/usr/local/Cellar/nmap/7.91/share/nmap/scripts/smb-enum-shares.nse 10.10.115.57

## gobuster

gobuster dir -u http://10.10.115.57 -w gobuster/medium.txt > nmap/gobuster
gobuster dir -u http://10.10.115.126 -w gobuster/medium.txt > nmap/gobuster

## wpscan

wpscan --url http://10.10.115.126/blog
wpscan --url http://10.10.115.126/blog -e u
