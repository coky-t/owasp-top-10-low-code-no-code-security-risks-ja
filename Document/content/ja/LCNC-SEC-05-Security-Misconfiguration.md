---

layout: col-sidebar
title: "LCNC-SEC-05: セキュリティの設定ミス"

---

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## 要旨

設定ミスは機密データや操作への匿名アクセス、保護されていないパブリックエンドポイント、シークレット、オーバーシェアリングにつながることがよくあります。

## 説明

ノーコード/ローコードプラットフォームは幅広い機能を提供しますが、その中にはセキュリティと特定のユースケースのサポートとのバランスを制御するものもあります。
設定ミスは機密データや操作への匿名ユーザーアクセス、保護されていないパブリックエンドポイント、シークレット、オーバーシェアリングにつながることがよくあります。
さらに、多くの設定はテナントレベルではなくアプリケーションレベルで設定されます。つまり、管理者ではなくビジネスユーザーによって設定されることがあります。

## 攻撃シナリオの例

### シナリオ #1

ある開発者は API エンドポイントを公開するアプリケーションを作成しましたが、そのエンドポイントには匿名アクセスを拒否する設定をし忘れてしまいました。
攻撃者はローコード/ノーコードプラットフォームのサブドメインをスキャンして、その基盤となるデータを盗んでしまいます。

### シナリオ #2

ある開発者は webhook によってトリガーされるオートメーションを作成しましたが、その webhook をシークレットで保護することをし忘れてしまいました。
攻撃者は webhook を特定し、今では自由にそのオートメーションをトリガーできます。
そのオートメーションはデータを変更したり削除したりできます。

## 防止方法

- ベンダーのドキュメントを読み、ベストプラクティスガイドに従う。
- 設定が業界のベストプラクティスに沿っていることを確認する。
- 設定にドリフトがないか監視する。
- テナントレベルの設定のために変更管理システムを導入する。

## 参考資料

- [By Design: How Default Permissions on Microsoft Power Apps Exposed Millions](https://www.upguard.com/breaches/power-apps)
- [Microsoft Internal Security Best Practices: Secure Power Platform Development](https://www.youtube.com/watch?v=h9FrOEfc81s)
- [Power Platform Landing Zones Reference Implementation](https://github.com/microsoft/industry/blob/main/foundations/powerPlatform/referenceImplementation/readme.md#power-platform-landing-zones-reference-implementation)
