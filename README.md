# 4d-tips-grant-revoke-license
4D Write/4D Write Proのライセンス管理について

## 概要

[4D Write Pro](http://doc.4d.com/4Dv16/4D/16/Presentation.200-3048089.ja.html)は，4Dに組み込まれており，プラグインではありませんが，使用には4D Write（プラグイン）の追加ライセンスが必要です（Webサーバー・SOAPサーバーと同じ扱い）。4D Writeのライセンスは，4D Developer Proおよび4D Unlimited Desktopに含まれているので，デスクトップ版（シングルユーザー）であれば，無条件で使用することができます。クライアント/サーバー版の場合，同時接続ユーザー（4D Client）と同じ数の4D Writeのライセンスをインストールする必要はありませんが，その場合，[ユーザー/グループ](http://doc.4d.com/4Dv16/4D/16/Access-system-overview.300-3049059.ja.html)の仕組みを活用して4D Writeのライセンスを特定のユーザーに割り当てる必要があります。

### 基本

ユーザー/グループは，特定のフォーム・メニュー・プラグイン等に対するアクセス権を管理するための仕組みです。（**注記**：特定のテーブルに対するアクセスを管理するためにはSQLの[スキーマ](http://doc.4d.com/4Dv16/4D/16/CREATE-SCHEMA.300-3201309.ja.html)を使用します。）

ユーザー/グループは，デフォルトで無効となっています。[Designerにパスワードを設定する](http://doc.4d.com/4Dv16/4D/16/Activating-access-control.300-3049054.ja.html)ことにより，これを有効にすることができます。

4D Write Proに対するアクセス権を管理するためには，まず，グループを作成し，そのグループに4D Writeライセンスを与えます。この例では，グループ「書ける」に4D Writeライセンスが与えられています。グループ「書けない」には，4D Writeライセンスが与えられていません。次に，ユーザーを作成し，グループに所属させます。この例では，ユーザー「書ける人」がグループ「書ける」に所属し，ユーザー「書けない人」はグループ「書けない」に所属しています。

![group](group.png | width=400)

最小限のアクセス権を有する標準のユーザーを[デフォルトユーザー](http://doc.4d.com/4Dv16/4D/16/Setting-a-Default-User.300-3049055.ja.html)に指定することにより，ログイン画面を省略することもできます。この例では，「書けない人」がデフォルトユーザーに設定されています。

![default](default.png | width=400)

Designer/Administrator以外のユーザーは，ユーザー/グループを管理することができません。アクセス権をDesigner/Administratorに「昇格」するためには，[CHANGE CURRENT USER](http://doc.4d.com/4Dv16/4D/16/CHANGE-CURRENT-USER.301-3036847.ja.html)コマンドを使用するか，``Shift``キーを押しながら再度アプリケーションを開き，ログイン画面からDesigner/Administratorとしてログインします。

![login](login.png | width=400)
