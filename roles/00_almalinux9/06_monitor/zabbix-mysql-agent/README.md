zabbix-mysql-agent
=========

## これは何？

Zabbix 用の MySQL ユーザを作成する Playbookです。

- Zabbix ユーザ作成
- /var/lib/zabbix/ 配下に .my.cnf を配置

## 変数

mysql_zabbix_password に作成する zabbix ユーザのパスワードを定義  
mysql_root_password に MySQL の root ユーザのパスワードを定義

```
---
# vars file for zabbix-mysql-agent
mysql_zabbix_password:
mysql_root_password: 
```

Author Information
------------------

- snkk1210
