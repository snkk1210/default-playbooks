certificate
=========

## これは何？

証明書の配置ディレクトリを作成する Playbook です。

- /etc/certs/[ドメイン]/[今年] の証明書配置ディレクトリ作成
- /etc/certs/[ドメイン]/current のシンボリックリンク作成

## 変数定義

domain_name に domain を定義する（マッピング）

```
---
# vars file for certificate
domain_name:
   - { domain: 'develop.local' ,customer: 'vagrant' }
   - { domain: 'dev.ease.local' ,customer: 'vagrant' }
```

Author Information
------------------

snkk1210
