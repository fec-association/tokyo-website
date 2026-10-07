# tokyo-website

フロントエンドカンファレンス東京の特定商取引法に基づく表記ページ（GitHub Pages、カスタムドメイン tokyo.fec.or.jp）。販売事業者は一般社団法人フロントエンドカンファレンスアソシエーション。

## 構成

- `tokushoho/index.html`: 特定商取引法に基づく表記ページ本体（公開URLは `/tokushoho/`）
- `index.html`: ルート用。別サイトへの `meta refresh` リダイレクトのみを置く
- `style.css`: 公式サイトのスタイルのコピー。このページ専用の差分は `.policy .row` のみ

## 関連リポジトリと情報の参照先

法人情報や契約情報は、このリポジトリではなく次のリポジトリで管理している。表記の内容を確認・更新するときは、必ず参照元の最新の記載を確認する。

- backoffice（https://github.com/fec-association/backoffice）
- website（https://github.com/fec-association/website）: 公式サイト。スタイルの元（`style.css`）。変更があったらこのリポジトリの `style.css` も合わせる
- 販売内容（チケット名・価格・販売開始日時）の一次情報: https://fortee.jp/fec-tokyo-2026/ticket-shop/index

## 法令上の確認

表記項目を変更するときは、次の一次情報を確認する。

- 特定商取引に関する法律 第11条（通信販売の広告表示事項）と同法施行規則 第23条〜第25条（e-Gov法令検索）
- 消費者庁 特定商取引法ガイド 通信販売広告Q&A: https://www.no-trouble.caa.go.jp/qa/advertising.html

特に次の点は、実態と表記が食い違わないようにする。

- 販売価格・申込期間・支払方法・返品の扱いは、fortee の販売ページの実態と一致させる
- 電話番号などを請求時開示にする場合、請求への返信が申込みの意思決定に先立って間に合う運用が前提になる
- 所在地は現に活動している住所である必要がある。登記上の住所とバーチャルオフィスの関係は backoffice で未確認の記載がある
- 返品を認めない場合は、その旨を明示する
- 法令の解釈に迷う内容は、専門家に確認する

## ホスティング

- GitHub Pages（mainブランチのルートから配信）。ビルド工程はなく、pushすると反映される
- カスタムドメイン tokyo.fec.or.jp を設定している。ドメインの所有確認用のDNS TXTレコード（`_github-pages-challenge-fec-association.tokyo.fec.or.jp`）は削除しない
- DNSの変更は XServer Domain で行う（手順は backoffice の `xserver-dns.md`）
- Pagesの設定変更（カスタムドメインの削除など）が、GitHub側で500エラーになることがあった。失敗した場合は時間をおいて再試行する

## 編集時の注意

- 日付は西暦表記のみ
- 公式サイトと見た目を揃えるため、`style.css` は website のものをベースにし、このページ専用の変更は最小限にする
