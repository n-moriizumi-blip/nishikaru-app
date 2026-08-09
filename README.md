# nishikaru-app

西軽精機の統合Webアプリ(GitHub Pages + GAS API構成)。既存の[勤怠申請アプリ](https://github.com/n-moriizumi-blip/nishikaru-shuusei-app)と同じ構成を踏襲している。

## 現状(2026-08-10)

Phase 1として「品質不具合報告」(検査で見つかった社内不良・差し戻し品の記録)を実装中。

- `index.html`: QRスキャン→自動入力フォームの画面。**フロントエンドのみ実装済み、GAS Web App側は未実装**のため、QRからの得意先名/品番検索・送信処理はモック(ダミーデータ・コンソール出力)になっている。
- 対応するスプレッドシート・GAS構築スクリプトは `検査不具合報告\品質不具合管理システム\`(ローカル)を参照。

## 今後の予定

- GAS Web App(`doGet`/`doPost`)を新規作成し、`fetchLookup`/`fetchSubmit`をモックから実データに差し替える
- Google Identity Servicesでのログイン(勤怠申請アプリと同じ方式)を追加
- 将来的に加工ナレッジ等、他の西軽精機向けアプリもこのリポジトリに統合していく想定
