---

layout: col-sidebar
title: "LCNC-SEC-09: 資産管理の不備"

---

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 2 |

## 要旨

ノーコード/ローコードアプリケーションは簡単に作成でき、メンテナンスコストも比較的低いため、アクティブな状態でありながら放置されがちです。
さらに、内部アプリケーションはビジネス継続性の懸念に対処することなく、急速に普及する可能性があります。

## 説明

ノーコード/ローコードアプリケーションはアクティブな状態でありながら放置されがちです。
新しいアプリケーションの作成が簡単であること、メンテナンスコストが比較的低いこと、SaaS サービスで管理されることが多いことなどが要因として挙げられます。
このため、組織内のアクティブなアプリケーションの数は急激に増加する傾向にあり、人気のあるビジネスアプリケーションが所有者不在の状態になることがよくあります。

さらに、大規模な組織では有用な内部のビジネスアプリケーションのバイラルな性質により、一人のビジネスユーザーが開発したアプリケーションが組織全体で多くのユーザーによって信頼されることになります。
ノーコード/ローコードアプリケーションは重要なビジネスアプリケーションに期待されるビジネス継続性の対策、例えば、複数の所有者がいる、IT によって監視されている、SLA を提供しているなど、を欠いている可能性があります。

## 攻撃シナリオの例

### シナリオ #1

ある開発者が作成したアプリケーションが社内ツールとして普及しました。
その開発者が組織を去ったり、別の役職に移ったりします。
API の変更によりアプリケーションが動かなくなり、業務に支障をきたすようになりました。
IT 部門はそのアプリに気づいておらず、修正を手助けできません。

### シナリオ #2

ある開発者はそのプラットフォームのマーケットプレイスを閲覧し、アプリテンプレートを探します。
クリックするたびに外部向け URL を伴うアプリが作成されます。
これらのアプリはビジネスデータを公開する可能性があるにもかかわらず、ユーザーはそのことを忘れてしまいます。
このシナリオは開発者数の増加に伴い、古くなったアプリの数は増え続けていきます。

## 防止方法

- アプリケーション、コンポーネント、ユーザーをリストアップした包括的なインベントリを保守する。
- 未使用の依存関係、不要な機能、コンポーネント、ファイル、ドキュメントを削除または無効にする。

## 参考資料

- [Why So Many Security Experts Are Concerned About Low-Code/No-Code Apps](https://www.darkreading.com/dr-tech/why-so-many-security-experts-are-concerned-about-low-code-no-code-apps)