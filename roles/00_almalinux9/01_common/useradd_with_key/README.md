useradd_with_key
=========

## これは何？

OS ユーザ作成用の Playbook です。

- ユーザ作成
- 公開鍵登録
- sudo 設定
- キーペアを作成して、Ansible 実行 PC の /var/tmp/ 以下(変更可能)に秘密鍵をダウンロード

## 変数

customer に作成するユーザ名を定義して下さい。  
customer_pass にユーザのパスワードを定義して下さい。  
pkey_dir に秘密鍵をダウンロードするディレクトリを指定することも可能です。  

```
---
# vars file for useradd
ex_user:
  - { customer: 'testuser1' ,customer_pass: 'Kc=datum' }
  - { customer: 'testuser2' ,customer_pass: 'uX7HyhiR' }
#  - { customer: 'testuser3' ,customer_pass: 'Mg39PXQx' }
#  - { customer: 'testuser4' ,customer_pass: 'D6ze9jQ4' }
#  - { customer: 'testuser5' ,customer_pass: 's8ud39fm' }
pkey_dir: /tmp
```

Author Information
------------------

- snkk1210
