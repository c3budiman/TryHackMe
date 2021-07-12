#ping
ping 10.10.40.72

#nmap
mkdir nmap
nmap -sC -sV -oN nmap/initial 10.10.203.64

#nmap with script
find /usr/local/Cellar/nmap/7.91/share/nmap/scripts/ -name '*.nse' | grep smb
nmap --script=smb* 10.10.31.129

#gobuster
gobuster dir -u http://10.10.203.64 -w gobuster/medium.txt
