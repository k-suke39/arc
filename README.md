![currentuser](/assets/currentuser.png 'currentuser')

# サービス概要

## サービス名

https://current-user.vercel.app/

※ レスポンシブ未対応です。Google Chrome での利用を推奨しています。

## サービス概要

環境構築不要の`Ruby on Rails`の O/R マッパーである`ActiveRecord`の学習サービス

# サービスを作成した背景

スクールに入ってから勉強会を開催したり、初学者同士で勉強を教え合う機会が何度もありました。
その際、`Ruby on Rails`を学習する中で初学者がつまずきやすいポイントがあることがわかりました。

- MVC の Model に関して、どのような役割があるかわからない
- `ActiveRecord`が何かわかっていない = 内部で`O/Rマッパー`の仕組みにより**SQL に変換されていることがわかっていない**
- `User.all`や`Post.find_by`を**暗記のように書いている人が多い**

`Rails`には良くも悪くも**ブラックボックスな部分**が多く、`ActiveRecord`の理解が浅くてもアプリを作れてしまうという点があります。

そのため、学習が進む中で複数テーブルの結合でレコードを取得する際に、つまずいてしまう状況を多く見かけました。

そのような中で SQL の学習サービスは複数存在しますが、**ActiveRecord の学習サービスは現状存在しなかった為**、今回開発することに挑戦してみました。

# 使い方

シンプルです！
問題集一覧からチャプターと好きな問題を選択すると、練習ページで問題を解くことができます。

[![Image from Gyazo](https://i.gyazo.com/94827f3d8c32a092b761381b14420c55.gif)](https://gyazo.com/94827f3d8c32a092b761381b14420c55)

# 練習問題について

| 問題         | 問題数       | 概要                                                     |
| :----------- | :----------- | :------------------------------------------------------- |
| トライアル編 | 5 問         | 基本的な操作方法について練習できます。                   |
| 初級編       | 10 問        | 一対多の基本的なリレーションを練習できます。             |
| 中級編       | 3 問         | メソッドを用いて少し複雑なレコードの取得を練習できます。 |
| 上級編       | 準備中です。 |                                                          |

# 主要機能

| SQL 変換機能                                                                                                                        | コード判定機能                                                                                                                      |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [![Image from Gyazo](https://i.gyazo.com/6811fa702258324ff713273bd3f50119.gif)](https://gyazo.com/6811fa702258324ff713273bd3f50119) | [![Image from Gyazo](https://i.gyazo.com/3bf91e296642baf2aafe6fbf29d18164.gif)](https://gyazo.com/3bf91e296642baf2aafe6fbf29d18164) |
| コードを実行することで、ActiveRecord の SQL への変換と実行結果を確認することができます。                                            | 書いたコードを任意のタイミングで判定することができます。                                                                            |

| 学習記事閲覧機能                                                                                                                    | メソッド検索機能                                                                                                                    |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [![Image from Gyazo](https://i.gyazo.com/0690ccde96bca8a0f564fecb9a167f25.gif)](https://gyazo.com/0690ccde96bca8a0f564fecb9a167f25) | [![Image from Gyazo](https://i.gyazo.com/09215f7156663f09ba24327daf8700a2.gif)](https://gyazo.com/09215f7156663f09ba24327daf8700a2) |
| QiitaAPI を用いて、 学習参考記事を表示しています。                                                                                  | 取得系メソッドをオートコンプリート検索で確認することができます。                                                                    |

| Twitter シェア機能                                                                                                                  | ログイン/ログアウト機能                                                                                                             |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [![Image from Gyazo](https://i.gyazo.com/7f40129ab51ba226d9344a7b7aac0ce7.gif)](https://gyazo.com/7f40129ab51ba226d9344a7b7aac0ce7) | [![Image from Gyazo](https://i.gyazo.com/08890496d42bf718de523db31c4abc8f.gif)](https://gyazo.com/08890496d42bf718de523db31c4abc8f) |
| OGP を設定しています。                                                                                                              | NextAuth.js を採用し、手軽な認証体験を実現しています。                                                                              |

| コード実行時に結果タブがアクティブに遷移                                                                                            | Active Record の説明用モーダル                                                                                                      |
| ----------------------------------------------------------------------------------------------------------------------------------- | ----------------------------------------------------------------------------------------------------------------------------------- |
| [![Image from Gyazo](https://i.gyazo.com/8a06fa20c7de5f92dd0b818e4cc70b0b.gif)](https://gyazo.com/8a06fa20c7de5f92dd0b818e4cc70b0b) | [![Image from Gyazo](https://i.gyazo.com/dcf5471f0f40a4b58736e490161ae365.gif)](https://gyazo.com/dcf5471f0f40a4b58736e490161ae365) |
| UX を考慮しての実装です。                                                                                                           | ActiveRecord の基礎を説明することで理解しやすくしています。                                                                         |

# 使用技術

| カテゴリ       | 技術                                                                        |
| :------------- | :-------------------------------------------------------------------------- |
| フロントエンド | TypeScript 5.2.2 / React 18.2 / Next.js 13.4                                |
| バックエンド   | Ruby 3.2.2 / Ruby on Rails 7.0.8（API モード）                              |
| データベース   | PostgreSQL                                                                  |
| 認証           | NextAuth.js                                                                 |
| 環境構築       | Docker / docker-compose                                                     |
| CI/CD          | Github Actions                                                              |
| インフラ       | Vercel / Render                                                             |
| API            | Qiita API                                                                   |
| その他         | SWR / MUI / monaco-editor / Prettier / ESLint / rack-cors / rspec / rubocop |

# 選定理由

開発期間が 3 週間ほどしかありませんでした。その為、①**実装スピード**と ②**ユーザの離脱率を下げるような UI/UX にしたい**という 2 点から技術選定を行いました。

### 開発環境

環境ごとの差異をなくしたいこと、また`Docker`での環境構築に慣れていた為、`Docker` / `docker-compose`をベースの技術として選びました。

### バックエンド

バックエンドにはカリキュラムで多く学んできた`Ruby on Rails`を採用する事でキャッチアップコストを最小限にしました。

### フロントエンド

フロント側には Rails7 系の`Hotwire`という選択肢もありましたが、

- 本番環境だと動作があまり速くないことを体感した。(個人開発のアプリ作成時)
- CSS のデザインを１から構築するには時間がなかった、自信がなかった。
- UI/UX、実装スピード、認証セキュリティの面などを考慮し、`Next.js`の`NextAuth.js`を採用したかった。

以上の 3 点から、あまり触れた事がない技術ではありましたが、全体的な工数を考えたときに`Next.js`を採用しました。

### インフラ

デプロイ先である`Render`、`Github Actions`等は導入コストが低かったため、`Vercel`に関しては`Next.js`とのデプロイ時の相性が良いこと、ブランチごとに新しいドメインでデプロイも行ってくれる為、`build`時のエラーがわかりやすいことからも今回採用に至りました。

# インフラ構成

[![Image from Gyazo](https://i.gyazo.com/21e3ebb19efd67bb5a6cba49d93685b1.png)](https://gyazo.com/21e3ebb19efd67bb5a6cba49d93685b1)

# 工夫したポイント

## 1.パフォーマンス

キャッシュ管理ライブラリの 1 つである**SWR**を採用し、レコード取得のパフォーマンスを意識しました。**SWR** は、まずキャッシュからデータを返し（stale）、次にフェッチリクエストを送り（revalidate）、最後に最新のデータを持ってくるという**Stale While Revalidate**の略称です。

`axios`や`fetch`に比べて処理速度が速く、キャッシュを再利用することによりデータを即時反映できることから、サクサクとしたページ表示を実現する事ができます。問題がトライアル編、初級編、中級編とそれぞれありますが、**一度のリクエストで該当の問題群を全て取得してくること**で、**2 回目以降は全てキャッシュからデータを表示させる**ように設計しました。

```javascript
const fetcher = (url: string) => axios.get(url).then((res) => res.data);
const { data, error } = useSWR(
	`https://xxxx.xxx.com/api/v1/practices?slug=${slug}`,
	fetcher
);
```

[![Image from Gyazo](https://i.gyazo.com/ece0f895b9ccbcfc86daedb425c00875.gif)](https://gyazo.com/ece0f895b9ccbcfc86daedb425c00875)

## 2.快適な UI/UX

### 2-1.視覚的な導線

導線がわかりやすいように`アイコン`を多めにすること、`Tooltip(アイコンhover時に説明の吹き出しが出る仕様)`を配置することで次のアクションを行いやすい設計にしました。
配色も意識し、落ち着いた配色のみを採用する事で**視覚的な印象を最小限にする** = **利用者を絞らせない、幅広い方に使ってもらえる**ように意識しました。

[![Image from Gyazo](https://i.gyazo.com/53bb70bd3ca8a5f58b0b80c7b3f3691c.gif)](https://gyazo.com/53bb70bd3ca8a5f58b0b80c7b3f3691c)

### 2-2.手軽で快適な認証

今回、UI/UX、セキュリティ面を考慮し、`NextAuth.js`でのログイン機能を実装しました。
`OAuth`ベースの`Next.js`向けに作られたライブラリで、`Google`や`Twitter`、`GitHub`など、認証やセッション管理を手軽に行うことができます。

`PagesRouter`向けに作られたドキュメントなので、`AppRouter`向けのドキュメントがなく調査に少し苦戦しました。

```javascript:app/api/auth/[...nextauth]/route.ts
import NextAuth from 'next-auth';
import GithubProvider from 'next-auth/providers/github';

const handler = NextAuth({
	providers: [
		GithubProvider({
			clientId: process.env.NEXT_PUBLIC_GITHUB_CLIENT_ID || '',
			clientSecret: process.env.NEXT_PUBLIC_GITHUB_CLIENT_SECRET || '',
		}),
	],
	secret: process.env.NEXTAUTH_SECRET || '',
});
export { handler as GET, handler as POST };

```

```javascript:src/providers/NextAuth.tsx
'use client';

import { SessionProvider } from 'next-auth/react';
import { ReactNode } from 'react';

const NextAuthProvider = ({ children }: { children: ReactNode }) => {
	return <SessionProvider>{children}</SessionProvider>;
};

export default NextAuthProvider;
```

[![Image from Gyazo](https://i.gyazo.com/08890496d42bf718de523db31c4abc8f.gif)](https://gyazo.com/08890496d42bf718de523db31c4abc8f)

とはいえ、セキュリティ周りが`OAuth`ベースで保証されており、ユーザ側としても手軽にログインすることができ、**離脱率を下げる上で効果的な選択**だと感じました。

## 3.SQL 変換機能について

当初の設計では、to_sql を使用して、実行結果の文字列を返すような考えでした。実際に調査したところ、戻り値のクラスによって使えない仕様であったため、別の方法を考えました。ActiveSupport::Nortifications のイベントトリガーを用いて、ActiveRecord の実行されたタイミングで、ログを検知できるようにしています。

とはいえ、綺麗に SQL が吐かれるのではなく、schema のバージョンを確認する内部クエリなども出力される為、実行時のクエリのみが取得できるようにロジックを組みました。プレースホルダの部分を実際の値で置換したり、即座にクエリが吐かれないメソッドもあるので、配列にすることで、イベントが発火されるようにするなど、かなり泥臭く仮説検証を繰り返し、シンプルに表示させることができました。

```ruby
  ActiveSupport::Notifications.subscribe "sql.active_record" do |*args|
    event = ActiveSupport::Notifications::Event.new(*args)
    sql = event.payload[:sql]
    binds = event.payload[:binds].map(&:value)

    log_entry = {
      sql: sql,
    }

    unless logs.map { |log| log[:sql] }.include?(log_entry[:sql])
      logs << log_entry
      logger.debug(log_entry.to_json)
    end
  end
```

```ruby
# ActiveRecordの内部クエリを無視
  next unless sql.start_with?("SELECT \"") || sql.start_with?("SELECT COUNT")

# プレースホルダを実際の値で置換
  binds.each_with_index do |value, i|
    placeholder = "$#{i + 1}"
    sql = sql.gsub(placeholder, value.to_s)
  end
# クエリを即時発行するように調整
  result = result.to_a if result.is_a?(ActiveRecord::Relation)
```

[![Image from Gyazo](https://i.gyazo.com/6513e3501a3720d1f6abf8fe51bc61e7.gif)](https://gyazo.com/6513e3501a3720d1f6abf8fe51bc61e7)

# 今後の開発について

**1.問題数を増やす**
現状のテーブル構成から作り直しを行い、より実践的な問題を増やしていきたいと考えています。
現状が 15 問なので、50 問近くに増やしたいです。

**2.管理画面の作成**
現状 seed のみでマスタデータを管理しているため、管理画面を作成し円滑に運用していきたいです。

**3.ダッシュボード画面の作成**
ユーザの滞在率、利用率を上げるためにダッシュボード機能の作成と関連機能の拡張を考えています。

**4.テスト**
テストがほとんど書けていないので、フロント、バック合わせて書いていきたいです。
