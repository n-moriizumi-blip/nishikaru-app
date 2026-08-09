# nishikaru-app

西軽精機の統合Webアプリ(GitHub Pages + GAS API構成)。既存の[勤怠申請アプリ](https://github.com/n-moriizumi-blip/nishikaru-shuusei-app)と同じ構成を踏襲している。

## 現状(2026-08-10)

Phase 1として「品質不具合報告」(検査で見つかった社内不良・差し戻し品の記録)を実装中。

- `index.html`: QRスキャン→自動入力フォームの画面。カメラでのQR読み取り(jsQR)は実装済み。
- 対応するGAS Web App(`doGet`/`doPost`)のコードは `検査不具合報告\品質不具合管理システム\WebApi.gs`(ローカル)に作成済みだが、**まだGASエディタへの貼り付け・デプロイが済んでいない**。デプロイ後、発行されたURLを `index.html` 内の `GAS_URL` 定数に設定するまでは、QR検索・送信ともにモック(ダミーデータ・コンソール出力)で動作する。
- 対応するスプレッドシート・GAS構築スクリプトは `検査不具合報告\品質不具合管理システム\`(ローカル)を参照。

## 今後の予定

- `WebApi.gs` をGASエディタへ貼り付けてWebアプリとしてデプロイし、`index.html` の `GAS_URL` を実URLに差し替える
- Google Identity Servicesでのログイン(勤怠申請アプリと同じ方式)を追加。ログイン後のメールアドレスを `currentUserEmail` に設定し、品証担当者欄に自動反映する
- アプリアイコン(PWA用)の作成
- 将来的に加工ナレッジ等、他の西軽精機向けアプリもこのリポジトリに統合していく想定
