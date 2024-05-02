### Ansible Laravel Nginx Mysql

Modify inventory file :
```
[web]
<your web ip/host>

[db]
<your db ip/host>
```

Modify file : roles/db/vars/main.yml (decrypt using vault) change with : 
```
---
# vars file for db
psroot: <root db>
db_user: <user db>
db_pass: <pass db>
db_name: <db name>
```

roles/laravel/vars/main.yml : 
```
---
# vars file for roles/laravel
db_user: <user db>
db_pass: <pass db>
db_name: <db name>
db_host: localhost <db host>     
```

To check playbook syntax : 
```
ansible-playbook --syntax-check playbook.yml 
```
