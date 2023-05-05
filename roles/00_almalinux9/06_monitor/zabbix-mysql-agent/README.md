zabbix-mysql-agent
=========

## これは何？

Zabbix 用の MySQL ユーザを作成する Playbookです。

- Zabbix ユーザ作成
- /var/lib/zabbix/ 配下に .my.cnf を配置

## 変数

zabbix_dbpass に作成する zabbix ユーザのパスワードを定義  
db_passwd に MySQL の root ユーザのパスワードを定義

```
---
# vars file for zabbix-mysql-agent
zabbix_dbpass:
db_passwd: 
```

Author Information
------------------

- snkk1210
