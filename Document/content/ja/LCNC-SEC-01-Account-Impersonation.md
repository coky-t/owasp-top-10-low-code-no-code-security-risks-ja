# LCNC-SEC-01: アカウントのなりすまし

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## 要旨

ノーコード/ローコードアプリケーションには任意のアプリケーションユーザーが暗黙的に使用するユーザー ID を埋め込むことができます。
これは権限昇格への直接的な経路を作り出し、攻撃者が他のユーザーの ID の後ろに隠れることを可能にし、従来のセキュリティコントロールを回避できてしまいます。

## 説明

ノーコード/ローコードアプリケーションは独自のアプリケーション ID を持つのではなく、既存のユーザー ID を利用できます。
組み込まれた ID はアプリケーションの作成者に属するものであったり、データベース資格情報のようにチームで共有される共通の ID であったりします。

アプリケーションの ID がないため、ノーコード/ローコードプラットフォームの外部にある監視システムに機密データが露出することになります。
外部から見ると、アプリケーションを使用するユーザーはアプリケーションの作成者になりすますことになり、アプリケーションとその作成者を区別することはできません。
アプリケーションが異なる ID を使用してさまざまなプラットフォームで動作する場合、問題はさらに深刻になります。そのようなケースでは、あるユーザーはファイル共有 SaaS にファイルを保存するために使用し、別のユーザーはオンプレミスのデータを取得するために使用することができます。

さらに、ID はアプリケーション内に組み込まれ、複数のユーザーがそのアプリケーションを使用できます。これは権限昇格への直接的な道筋を作り出し、アプリケーションユーザーが本来持つべきではないアクセスレベルを取得できてしまいます。

## 攻撃シナリオの例

### シナリオ #1

ある作成者はデータベースからレコードを閲覧するためのシンプルなアプリケーションを作成しました。
作成者の ID を使用してデータベースにログインし、アプリケーション内に組み込まれた接続を作成します。
このアプリでユーザーが実行するすべてのアクションは作成者の ID を使用してデータベースに問い合わせることになります。
悪意のあるユーザーはこれを利用し、このアプリケーションを使用して、アクセスしてはならないレコードを閲覧、修正、削除します。
データベースのログではすべての問い合わせがアプリ作成者である一人のユーザーによって行われたことが示されています。

### シナリオ #2

ある作成者は企業の従業員が自分の情報をフォームに入力できるようにするビジネスアプリケーションを作成しました。
フォームの回答を保存するために、作成者は個人の電子メールアカウントを使用します。
ユーザーはこのアプリが作成者の個人アカウントにデータを保存していることを知る由もありません。

### シナリオ #3

ある作成者はビジネスアプリケーションを作成して、それを管理者と共有しました。
その作成者は自分のユーザー ID を使用するようにアプリを設定します。
本来の目的から外れて、このアプリは作成者のユーザー ID を使用して、作成者の権限を昇格させることもできます。
管理者がアプリを使用すると、知らぬ間に作成者の権限を昇格してしまいます。

## 防止方法

- 外部サービスへの接続をプロビジョニングする際、最小権限の原則を遵守する。
- アプリケーションではユーザーアカウントではなく専用のサービスアカウントを使用する。
- アプリケーションでは接続ごとに異なる ID ではなく、すべての接続で一貫した単一の ID を使用する。
- 共有接続を通じて実行されるアクションの背後にいるアクターを特定するために、適切な監査証跡が維持されていることを確認する。

## 参考資料

- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)