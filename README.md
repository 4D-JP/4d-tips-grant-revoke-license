# 4d-tips-grant-revoke-license
4D Write/4D Write Proのライセンス管理について

## 概要

[4D Write Pro](http://doc.4d.com/4Dv16/4D/16/Presentation.200-3048089.ja.html)は，4Dに組み込まれており，プラグインではありませんが，使用には4D Write（プラグイン）の追加ライセンスが必要です（Webサーバー・SOAPサーバーと同じ扱い）。4D Writeのライセンスは，4D Developer Proおよび4D Unlimited Desktopに含まれているので，デスクトップ版（シングルユーザー）であれば，無条件で使用することができます。クライアント/サーバー版の場合，同時接続ユーザー（4D Client）と同じ数の4D Writeのライセンスをインストールする必要はありませんが，その場合，[ユーザー/グループ](http://doc.4d.com/4Dv16/4D/16/Access-system-overview.300-3049059.ja.html)の仕組みを活用して4D Writeのライセンスを特定のユーザーに割り当てる必要があります。
