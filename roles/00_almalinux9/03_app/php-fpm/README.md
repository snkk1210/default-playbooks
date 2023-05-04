php-fpm
=========

## これは何？

PHP-FPM をインストールする Playbook です。

- リポジトリの追加
- PHP-FPM インストール
- 各種モジュールインストール
- php.ini 設定
- PHP-FPM 設定

## 変数

php_var に導入する php のバージョンを定義して下さい。  
php_modules に導入するモジュールを定義して下さい。

```
---
  php_var: 8.1
  php_modules:
    - "php"
    - "php-pdo"
    - "php-mbstring"
    - "php-gd"
    - "php-fpm"
#    - "php-curl"
#    - "php-pear"
#    - "php-bcmath"
#    - "php-gmp"
#    - "php-intl"
    - "php-mysqlnd"
```

Author Information
------------------

- snkk1210
