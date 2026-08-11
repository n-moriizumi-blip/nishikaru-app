# nishikaru-kensa-app

西軽精機の統合Webアプリ「品質保証課アプリ」(GitHub Pages + GAS API構成)。既存の[勤怠申請アプリ](https://github.com/n-moriizumi-blip/nishikaru-sinsei-app)と同じ構成を踏襲している。

## 構成(2026-08-11)

ルートの `index.html` はアプリ選択画面。ここから3つの機能へ分岐する。

- `defect-report/`: 品質不具合報告(社内不良・差し戻し品のクイック入力)。バックエンドは`検査不具合報告\品質不具合管理システム\WebApi.gs`(ローカル)、デプロイ済み。
- `qr-cleaning/`: 洗浄工程(洗浄待機・洗浄完了のQR受付)。単独アプリ。
- `qr-inspection/`: 検査担当割付・検査開始前保留のQR受付。`?func=assign` または `?func=inspectionHold` を付けて開くと、アプリ内の選択画面を飛ばして直接その機能へ進む(ルートの選択画面はこの形でリンクしている)。

`qr-cleaning`・`qr-inspection`のバックエンドは、`進捗状況照会`スプレッドシートに紐づくGAS(`コード.gs`、ローカルは`進捗状況照会\コード.gs`)。

アイコン(`icon-192.png`・`icon-512.png`)は`勤怠管理システム\資料\品質保証課アプリ.png`(ローカル)を透過処理して書き出したもの。

## 今後の予定

- 将来的に加工ナレッジ等、他の西軽精機向けアプリもこのリポジトリに統合していく想定
