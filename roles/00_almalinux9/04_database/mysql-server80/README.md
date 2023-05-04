mysql-server80
=========

## これは何？

MySQL サーバ 8.0 を導入する Playbook です。

- リポジトリ追加
- my.cnf 設定
- MySQL インストール
- expect インストール
- MySQL 初期設定 ( mysql_secure_installation )
- mysql_config_editor 登録

## 変数定義

MySQL のパラメータと root ユーザのパスワードを定義して下さい。

```
---
# vars file for db_backup
innodb_buffer_pool_size: 256M
key_buffer_size: 128M
db_passwd: OP:Ts7ajsu98J
```

※ db_passwd に 「# (シャープ)」 の文字を含めないで下さい。  

Author Information
------------------

snkk1210
