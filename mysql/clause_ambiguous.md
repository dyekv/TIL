error:`Column \'isDelete\' in where clause is ambiguous`

where区のisDeleteがあいまいですという内容のエラー

テーブルのリレーションを追加した際に発生した

リレーション先のテーブルにもisDeleteフィールドが存在したため特定できずに発生していた

`'TableName'.isDelete`とすることで解決（シングルクォートは`記号）

TableNameはクオートで囲まなくても動いた、というかそうしないと動かなかった、よく分からない
