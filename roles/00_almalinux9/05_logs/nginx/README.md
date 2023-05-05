logs/nginx
=========

## これは何？

Nginx ログのローテート設定を行う playbook です。

- Nginx のログローテートを調整

## Dependencies

- nginx

## 変数

interval_web に Nginx のログローテーション間隔を定義  
rotate_num_web に Nginx のログ保持期間を定義  
※ 変数を設定しなければ、デフォルト (下記) の設定になります。

```
interval_sys: daily
rotate_num_sys: 90
```

Author Information
------------------

- snkk1210 
