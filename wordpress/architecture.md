# page.php

固定ページを組み立てるphpファイル

`header.php`と`footer.php`をくっつけている

`the_content();`が固定ページの中身を表示させているところ

# single.php

投稿ページを組み立てるphpファイル

投稿フォーマットに応じて、`post-formats`ディレクトリ内のphpファイルを読み取る

デフォルトは`format.php`が読み込まれる

# front-page.php

TOPページを開いた際に読み込まれるテンプレートphpファイル

管理画面でフロントページを指定している場合に読み込まれる？

TOPページが投稿の一覧ではないサイト（コーポレートサイト）の場合はこれを作成するのが吉

[参考](https://blog.maromaro.co.jp/archives/2791)
