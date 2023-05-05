logs/httpd
=========

## これは何？

Apache ログのローテート設定を行う Playbook です。

- Apache のログローテートを調整

## Dependencies

- httpd

## 変数

interval_web に Apache のログローテーション間隔を定義  
rotate_num_web に Apache のログ保持期間を定義  
※ 変数を設定しなければ、デフォルト (下記) の設定になります。

```
interval_sys: daily
rotate_num_sys: 90
```

Author Information
------------------

- snkk1210
