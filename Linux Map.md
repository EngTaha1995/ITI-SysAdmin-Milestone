# advanced file access permissions:
permissions for certain users/groups

Command | Info
--------|-----
setfacl -x filename u:user_taha:xw g:group_taha:rw | exclude or remove file permissions.
setfacl -m filename u:user:xw g:group:rw | Modify permissions.
setfacl -b filename | remove all permissions

# Scheduling tasks:
Command | Info
--------|-----
