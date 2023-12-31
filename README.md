プログラマ退職時のお仕事
==========================

- 残る人々を困らせないようにするために、これくらいはしておきたいというリスト
- ソロプロジェクトが多かった人間が例なので、偏っている可能性が高い
- ちょっとした一大プロジェクトなので、 WBS や DBS を書こうな！

やるタイミング
--------------

タスクを列挙して、いつ行うかを明確にする。

- すぐやってよい
    - 時間がかかったり、漏れチェックもしないといけないので、着手は早め早めで
- 最終出社日のタイミング
    - やってしまうと業務が止まるのでギリギリで
- 最終出社の後
    - 事務書類の郵送とか。GitHub のアカウントの始末なども含まれるかも

具体的にすべきこと例
---------------------

### 引き継ぎ系

- 案件ごとの資料を作成
    - 関係者リスト
        - 顧客
        - 営業担当者
        - 開発メンバー
        - パートナー企業の窓口
    - ミドルウェア
        - ライセンス情報
        - サポート窓口への問合せ手続き
        - 公式ドキュメントのありか
    - 場所
        - ソースレポジトリの URL
        - ドキュメント置き場の場所
            - ファイルサーバ or クラウドストレージ(DropBox…)
        - issue システムの URL
        - Wiki などオンラインドキュメントの URL
            - TeamsWiki, GitHubWiki …
    - ソースや既存文書だけ読んで分からない情報
        - ソースの説明はキリがないので、基本的に書かない。
        - なぜ、そのような仕様となったかの経緯などを書く  
          ( 合理的な理由でないため、なぜそうかなのか推測しづらい話が特に必要 )
- 管理しているサーバーの情報
    - OS,DB のログイン情報
    - (クラウドでない場合) 物理的にどこに筐体あるか？
    - バックアップ・リストアなどの手順
- 自分しか知らない運用手順など  
    - (例) 納品用インストーラの作成の仕方
    - (例) 顧客に報告するための工期記録などの作成方法
    - (例) サーバー証明書を入手する手順
- 説明会
    - **時間がないので、必須ではない**。資料の場所を関係者にアナウンスして「必要であれば言っていただければ説明する場を設けます」とだけ通告して、残る側の人々に主導してもらう形でよい
- 近しい人に退職後の連絡先をお知らせしておく (方がいいと思うが、職場にもよる)
- 不特定多数向けの「お世話になりました」メール (は勝手に出すと怒られる会社もある)

### 端末あけ渡し[^snf]

- 個人情報の削除
    - **ssh鍵(重要)の削除**
    - 私用ファイルの削除
    - **Chromeなどブラウザに記憶されているアカウント情報・キャッシュの削除**
    - **Chrome Remote Desktop の「サービス」のアンインストール**[^crds]
    - 自宅で使っていた場合は、無線LAN情報など削除
    - **パスワード管理ソフトウェアとデータの削除(重要)**
    - OneDrive, DropBox などのクラウドストレージとのリンク状態を解除
    - %APPDATA%, %LOCALAPPDATA%, %USERPROFILE%\\.?\* [^dotfiles] 以下の情報
        - ただし、アプリそのものをアンインストールしてからの方が安全
        - %TEMP% 以下については「ローカルディスクのプロパティ」→「ディスクのクリーンアップ」を使った方が安全
    - VM内に入っている、以上と同様な情報
- 個人的に入れたアプリケーションのアンインストール
    - プログラムの追加と削除
    - C:\Go もね
- 勝手にやった設定を元に戻す
    - (例) タスク(cron)解除 - 常時起動しているPCだったので毎晩自動的にリブートするようタスクなどを登録していた
        - (例) Teams からのカメラ利用禁止の解除[^camera]
- 外付けディスクや機器
    - それがどこに接続されるどういう機器か分かるように、付箋かテプラでも貼っておこう。ケーブルの根本にも貼っておくとなおよい

[^snf]: ストレージをフォーマットしない場合
[^crds]: これが残ってるとスパイできてしまうので、ものすごく怒られる可能性がある
[^camera]: 監視されるような気がいたので、必要時だけ明示的にONにしてたw (あきらかに被害妄想)
[^dotfiles]: いわゆる dotfiles

### その他

- 業務作業用のGitHub アカウントの削除、もしくは [organization化] [^github2account]
- 会社に貸与されたものの返却
    - 社員証、名刺、入館証、PC端末、ヘッドセット、健康保険証
- 事務の人からいろいろ説明してもらう  
    (ちゃんとした会社なら待ちでよい)
    - 退職金 (退職金の管理を委託している団体に退職金の支払いの申請が必要な場合がある)
    - 年金 (確定拠出年金)
    - 健康保険 [^ninikeizoku]
    - 住民税 (最後の給料から天引きして、先払いしてもらえる場合があり、納税の手間が省ける)

[^github2account]: GitHubの規約で、個人が二つ無償アカウントを持つことはできない。私用アカウントを別途持っている場合、業務アカウントが会社の organization から解除されると無償扱いになってしまうので、規約違反状態になってしまう。そのため、削除するか organization化 する必要がある。organization化すると、個々のレポジトリの URL が変わらず維持される

[organization化]: https://docs.github.com/ja/account-and-profile/setting-up-and-managing-your-personal-account-on-github/managing-your-personal-account/converting-a-user-into-an-organization

[^ninikeizoku]: すぐに就職しない場合、国民健康保険のほかの選択肢として今の健康保険を2年間延長する「任意継続」というものがある(会社負担分を自分で払うし、国民年金より安いかというと…微妙)。申し込み締切がシビア
