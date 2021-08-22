### adduser 
(preferred option over useradd)
* create new user
` adduser newUserName `

---

### usermod 
(user to modify user after creation )

* add user to sudo group
` usermod -aG sudo newUserName ` 
(-a = add, -G = secondary group)

* check the user groups
` cat /etc/group | grep newUserName `

* To lock user account
` usermod -L newUserName `
(-L = lock)

* To unlock user account
` usermod -U newUserName `
(-U = unlock)

---

### deluser 
(to delete user )

* To check files created by user
` find / -user newUserName `

* To delete user
` deluser --remove-all-files --backup --bacup-to /user-backups/ newUserName `

---

### groups

* add new group
` addgroup `

* Change group
` chgrp `

