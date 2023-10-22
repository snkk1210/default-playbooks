zabbix-server60
=========

## これは何？

Zabbix Server 6.0 を導入する Playbook です。

- Zabbix database 作成
- Zabbix db user 作成
- Zabbix インストール

## Dependencies

- 00_almalinux9/01_common/common
- 00_almalinux9/02_web/httpd
- 00_almalinux9/03_app/php-fpm
- 00_almalinux9/04_database/mysql-server80

## 変数

```
mysql_root_password: hogehoge
mysql_zabbix_password: gehogeho
```

Author Information
------------------

- snkk1210