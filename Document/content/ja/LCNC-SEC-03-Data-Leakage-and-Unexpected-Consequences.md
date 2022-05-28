# LCNC-SEC-03: データ漏洩と予期せぬ事態

## リスク評価 [*](https://owasp.org/www-project-top-ten/2017/Note_About_Risks)

| 普及度 | 検出難易度 | 悪用難易度 | 技術的影響 |
| --- | --- | --- | --- |
| 3 | 2 | 3 | 3 |

## 要旨

ノーコード/ローコードアプリケーションは複数のシステム間でデータの同期や操作のトリガーを行うことが多いため、データが組織の境界外へ出てしまう道筋を作り出してしまいます。これはあるシステムでの操作が別のシステムで予期せぬ事態を招く可能性があること意味します。

## 説明

ノーコード/ローコードアプリケーションは複数のシステム間でデータを同期したり、あるシステムの変更に伴って別のシステムで操作をトリガーするためによく使用されます。
データの移動装置として、ノーコード/ローコードアプリケーションはデータを組織の境界外、別の組織、または個人アカウントに移動することで、簡単にデータ漏洩を引き起こす可能性があります。
操作のトリガーとして、ノーコード/ローコードアプリケーションはあるシステム内での操作と別のシステムの変更を暗黙のうちに結び付けることで、予期せぬ事態を招く可能性があります。
さらに、複数のアプリケーションが一つのデータソースに接続してトリガーできるため、データの移動や操作のトリガーが連鎖的に発生し、予測することも完全なマッピングも困難になります。

## 攻撃シナリオの例

Coming soon

## 防止方法

- プラットフォームコネクタを承認済みサービスリストに制限する。
- カスタムコネクタの作成を専任の担当者に制限する。
- マルチホップパスなど、組織の境界外のデータフローについてプラットフォームを監視する。

## 参考資料

- [Low-Code Security and Business Email Compromise via Email Auto-Forwarding](https://www.zenity.io/blog/low-code-security-and-business-email-compromise-via-email-auto-forwarding/)
- [Hackers Abuse Low-Code Platforms And Turn Them Against Their Owners](https://www.zenity.io/blog/hackers-abuse-low-code-platforms-and-turn-them-against-their-owners/)
