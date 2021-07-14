# Recon CheatSheet

## ping

ping 10.10.40.72

## nmap

mkdir nmap
nmap -sC -sV -oN nmap/initial 10.10.30.72

## nmap with script example

find /usr/local/Cellar/nmap/7.91/share/nmap/scripts/ -name '*.nse' | grep smb
nmap --script=/usr/local/Cellar/nmap/7.91/share/nmap/scripts//smb-enum-shares.nse 10.10.30.72

## gobuster

gobuster dir -u http://10.10.30.72 -w gobuster/medium.txt > nmap/gobuster
