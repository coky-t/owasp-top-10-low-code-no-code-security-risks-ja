# LCNC-SEC-05: セキュリティの設定ミス

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## 要旨

設定ミスは機密データや操作への匿名ユーザーアクセス、保護されていないパブリックエンドポイント、保護されていないシークレット、オーバーシェアリングにつながることがよくあります。

## 説明

ノーコード/ローコードプラットフォームは幅広い機能を提供しますが、その中にはセキュリティと特定のユースケースのサポートとのバランスを制御するものもあります。
設定ミスは機密データや操作への匿名ユーザーアクセス、保護されていないパブリックエンドポイント、保護されていないシークレット、オーバーシェアリングにつながることがよくあります。
さらに、多くの設定はテナントレベルではなくアプリケーションレベルで設定されます。つまり、管理者ではなくビジネスユーザーによって設定されることがあります。

## 攻撃シナリオの例

探索案 (TBD):
- 監査ログを有効にする
- RBAC
- Power Platform requireUserConsent フラグ
- 動かないアクセス制御
  - 自動トリガーが匿名ユーザーでも利用可能
  - 管理対象データベースが匿名ユーザーに公開されている (Power Platform のデータ漏洩)

### シナリオ #1

TBD

### シナリオ #2

TBD

## 防御方法

- ベンダーのドキュメントとベストプラクティスを読む。
- 設定が業界のベストプラクティスに沿っていることを確認する。
- 設定にドリフトがないか監視する。
- テナントレベルの設定のために変更管理システムを導入する。

## 参考資料

- [By Design: How Default Permissions on Microsoft Power Apps Exposed Millions](https://www.upguard.com/breaches/power-apps)
- [Microsoft Internal Security Best Practices: Secure Power Platform Development](https://www.youtube.com/watch?v=h9FrOEfc81s)
- [Power Platform Landing Zones Reference Implementation](https://github.com/microsoft/industry/blob/main/foundations/powerPlatform/referenceImplementation/readme.md#power-platform-landing-zones-reference-implementation)
