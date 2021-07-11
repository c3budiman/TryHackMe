#Open Samba
smbutil view -g //anonymous@10.10.64.11

mount_smbfs //anonymous@10.10.64.11

/usr/bin/osascript -e "try" -e "mount volume \"smb://anonymous@${host}\"" -e "end try"
