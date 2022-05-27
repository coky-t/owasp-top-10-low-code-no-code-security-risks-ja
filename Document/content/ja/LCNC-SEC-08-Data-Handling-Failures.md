# LCNC-SEC-08: データ処理の不備

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## 要旨

ノーコード/ローコードアプリケーションはデータやシークレットを「コード」の一部として、あるいはプラットフォームが提供するマネージドデータベースに保存することが多く、これらは規制やセキュリティ要件に準拠して適切に保存する必要があります。

## 説明

ノーコード/ローコードアプリケーションはデータやシークレットを「コード」の一部として、あるいはプラットフォームが提供するマネージドデータベースに保存できます。
ノーコード/ローコードベンダーが管理するデータベース上に保存されるデータには、個人情報や金融データなどの機密データが含まれることがよくあります。
アプリケーションの作成者はデータをどのように保存するかを決めることができますが、管理者はマネージドデータベースを見ることができないことがよくあります。
多くの場合、機密データは暗号化されずに保存され、規制要件を考慮することなく地理的位置間でのデータ移動が行われています。

さらに、アプリケーションの作成者にはシークレットを「コード」にハードコードすることが多くあります。
環境変数、コンフィグレーション、コードのいずれであっても、アプリケーションはサービスにアクセスするためにハードコードされたシークレットに依存することがよくあります。
ハードコードされたシークレットはアプリケーションへの書き込み権限を持つすべてのユーザーが利用でき、クライアント側のコードを介してアプリケーションリーダーや匿名ユーザーに漏洩する可能性もあります。

## 攻撃シナリオの例

探索案 (TBD):
- 暗号化されずに保存された機密データ (例: クレジットカード)
- 準拠していない方法で地理的位置間を移動するデータ

### シナリオ #1

TBD

### シナリオ #2

TBD

## 防御方法

- データストレージに関連するコンプライアンス、プライベート、セキュリティリスクについてビジネスユーザーに教育する。
- ノーコード/ローコードベンダーが提供するマネージドデータベース、環境変数、コンフィグレーションに機密データがないか監視する。
- 機密データにアクセスするアプリケーションにはセキュリティチームが関与する。

## 参考資料

- [Establishing a DLP strategy](https://docs.microsoft.com/en-us/power-platform/guidance/adoption/dlp-strategy)