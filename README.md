# linux-distribution-pkgs
Create a Backup list of all installed software on select Linux distributions

Reference document: 

https://www.cyberciti.biz/tips/linux-get-list-installed-software-reinstallation-restore.html

How to create a backup list of installed packages;

For Debian based systems use the commannd 

    prompt$ dpkg --get-selections > /backup/installed-software.log

For Red Hat based systems use the command

    prompt$ rpm -qa --qf "%{NAME}\n" | sort > /backup/installed-software.log

Restore installed software from a backup List

How to restore using a backup list to installed neccessary packages;

For Debian based systems use the comman

    prompt$ dpkg --set-selections < /backup/installed-software.log && apt-get dselect-upgrade

For Red Hat based systems use the command

    prompt$ yum -y install $(cat /backup/installed-software.log)
