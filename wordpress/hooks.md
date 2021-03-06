# フックとは

Wordpressにおけるフックとはイベントハンドラのようなものである

予め処理を挿入できるポイント（フック）が設けられており、そこに任意の処理を記述できる

フックにはアクションフックとフィルターフックがある

アクションフックは処理を実行するイベントトリガのようなイメージで

フィルターフックは値を更新して戻り値を返すイメージ、使われ方は割と曖昧らしい

`add_action(フック名,使用したい関数,優先度（数値）,関数の引数の数)` もしくは、

`add_filter(フック名,使用したい関数,優先度（数値）,関数の引数の数)` のように記述する

フック名は、どの処理に関連して関数を実行したいかを書く（フックに指定できるものは決まっている）

[アクションフック一覧](https://wpdocs.osdn.jp/%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3_API/%E3%82%A2%E3%82%AF%E3%82%B7%E3%83%A7%E3%83%B3%E3%83%95%E3%83%83%E3%82%AF%E4%B8%80%E8%A6%A7)
/ [フィルターフック一覧](https://wpdocs.osdn.jp/%E3%83%97%E3%83%A9%E3%82%B0%E3%82%A4%E3%83%B3_API/%E3%83%95%E3%82%A3%E3%83%AB%E3%82%BF%E3%83%BC%E3%83%95%E3%83%83%E3%82%AF%E4%B8%80%E8%A6%A7)

使用したい関数は別で定義したものを指定する、関数名は`my_フック名`などが多い

優先度は値が小さいほど優先度が高い、初期値は10になる

関数の引数には関数で使用している引数の数を指定する

また、`add_`の代わりに`remove_`とすることで設定したフック処理を取り除くことができる

一部だけフックさせたいときは処理が終わったら取り除くように書けば良い

