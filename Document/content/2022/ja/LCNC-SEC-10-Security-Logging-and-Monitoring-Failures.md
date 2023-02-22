---

layout: col-sidebar
title: "LCNC-SEC-10: セキュリティログと監視の不備"

---

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 2 | 2 | 3 | 2 |

## 要旨

ノーコード/ローコードアプリケーションは包括的な監査証跡を欠いたり、ログを生成しないか不十分であったり、機密ログへのアクセスが過度に共有されていることがよくあります。

## 説明

ノーコード/ローコードアプリケーションはログ生成やデータ監視をベンダーに依存することがよくあります。
多くの場合、ログは不十分か収集されておらず、セキュリティ調査を妨げ、コンプライアンス要件を満たすことができません。

さらに、アプリケーションには包括的な監査証跡がないことが多く、変更管理プロセスや問い合わせの妨げになります。
誰がその変更を持ち込んだかを見つけるのは、手に負えない課題となります。

## 攻撃シナリオの例

### シナリオ #1

アプリのログはオフになっています。
侵害が試みられた場合、セキュリティチームは誰がアプリにアクセスし、何をしようとしたのかを判断できません。

### シナリオ #2

ビジネスクリティカルなアプリケーションがある変更後に機能しなくなりました。
複数の変更が発生し、それぞれがアプリケーションの更新につながるため、問題の原因となった特定の変更を持ち込んだ開発者を見つけることは困難です。
開発者たちは問題のあるバージョンを見つけるために、各アプリケーションのバージョンを手作業で確認する必要があります。
アプリケーションの「保存」はすべて更新につながるため、更新の数が多ければ多いほど手作業のコストは非常に高くなります。
一部のプラットフォームでは、開発者は現在のバージョンのアプリケーションしか確認できないため、安定したバージョンを見つけたり戻したりすることができません。

## 防止方法

- プラットフォームのビルトイン機能を活用して、ユーザーアクセスやプラットフォームの監査ログを収集する。
- 適用可能であれば、アプリケーションにログ収集のメカニズムを組み込み、可視性を向上させる。
- アプリケーションの生データをログ収集しないようにプラットフォームを設定し、ログが機密データで汚染されないようにする。

## 参考資料

- [A08:2021 – Software and Data Integrity Failures, OWASP Top 10](https://owasp.org/Top10/A08_2021-Software_and_Data_Integrity_Failures/)