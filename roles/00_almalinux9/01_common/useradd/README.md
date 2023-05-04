useradd
=========

## これは何？

OS ユーザ作成用の Playbook です。

- ユーザ作成
- 公開鍵登録
- sudo 設定

## 変数

customer に作成するユーザ名を定義して下さい。  
customer_pass にユーザのパスワードを定義して下さい。  
full_publickey_path にユーザの公開鍵を定義して下さい。  
※ 指定がなければデフォルトの公開鍵を設定します。

```
---
# vars file for useradd
ex_user:
  - { customer: 'testuser1' ,customer_pass: 'Kc=datum' ,full_publickey_path:  '../../../../key/testuser1.pub'}
  - { customer: 'testuser2' ,customer_pass: 'uX7HyhiR' }
#  - { customer: 'testuser3' ,customer_pass: 'Mg39PXQx' }
#  - { customer: 'testuser4' ,customer_pass: 'D6ze9jQ4' }
#  - { customer: 'testuser5' ,customer_pass: 's8ud39fm' }
```

Author Information
------------------

- snkk1210
