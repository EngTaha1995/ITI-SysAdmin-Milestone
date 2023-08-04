# Advanced file access permissions:
permissions for certain users/groups

Command | Info
--------|-----
setfacl -x filename u:user_taha:xw g:group_taha:rw | exclude or remove file permissions.
setfacl -m filename u:user:xw g:group:rw | Modify permissions.
setfacl -b filename | remove all permissions

# Scheduling tasks:

Command | Info
--------|-----
at 15:30 | take you to command written to be executed at 3:30 PM.
at -c 1 | print first task to be run in the cache.
at -l | list all tasks.
at now+3hours | after 3 hours from now.
at now+3weeks | after 3 weeks from now.
* check for atd service if running before using the command

# Firewalld:

Command | Info
--------|-----
firewall-cmd --permanent --add-source --add-port --add-service | different setting to be added to firewall list.
firewall-cmd --list-all | list all config.
firewall-cmd --new-zone zoneName | Create new zone for certain subnet in the network for example.

* Default built-in firewall for red-hat based distros.
* check for service status before using.
* Firewall zone available for every connection interface.
* Reload firewall after adding/removing/changing ports or ip`s.
* config files are saved in /etc/firewalld/zones/public.xml
