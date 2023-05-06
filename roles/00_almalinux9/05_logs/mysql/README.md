logs/mysql
=========

## これは何？

MySQL ログのローテート設定を行う Playbook です。

- ログ flush ユーザ作成
- /var/log/mysql 配下に認証情報を設置
- error / slowlog のログローテート設定

## Dependencies

- mysql-server[xx]

## 変数

interval_mysql に ログローテーション間隔を定義  
rotate_num_mysql に ログ保持期間を定義  
mysqllogs_dbpass に ログを flush するDBユーザのパスワードを定義  
※ 変数を設定しなければ、デフォルト (下記) の設定となります。

```
interval_mysql: daily
rotate_num_mysql: 4
mysqllogs_dbpass: dwRW2unMF&T
```

※ mysqllogs_dbpass に 「# (シャープ)」 の文字を含めないで下さい。  


Author Information
------------------

- snkk1210 
