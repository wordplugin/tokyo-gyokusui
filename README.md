# 東京玉翠会ウェブサイト

香川県立高松高校、旧制高松中学校、旧制高松高等女学校の東京地区同窓会「東京玉翠会」のウェブサイトです。
従来の [www.gyokusui.com](https://www.gyokusui.com/) の内容を GitHub Pages に移したものです。

- 公開URL: https://wordplugin.github.io/tokyo-gyokusui/
- 移行元: https://www.gyokusui.com/ （2026年10月8日時点の内容）

## フォルダ構成

| 場所 | 内容 |
|---|---|
| `index.html` | トップページ（お知らせ、各ページへのリンク） |
| `data/` | 東京玉翠会の歴史、過去の総会データ・報告 |
| `program/` | 過去の総会プログラム（PDF） |
| `dokokai/` | 各同好会のページ（ゴルフ、麻雀、俳句、連歌、合唱、野球部OB会など） |
| `kandakai/` | 高高神田会の開催記録 |
| `katuyaku/` | 卒業生を応援するページ |
| `map/` | 東京さぬきマップ（卒業生のお店） |
| `rekishi/` | 高高の歴史探訪 |
| `shashin/` | 校舎の写真集、復元模型 |
| `kouka/` | 校歌（高高、高中、高女、校友会の歌） |
| `yakuin/`、`kaisoku/` | 役員名簿、会則 |
| `kakuchi/` | 各地の玉翠会総会の開催予定 |
| 直下の画像・PDF | トップページで使うバナー、お知らせ用の写真や案内 |

ビルド工程はなく、置いてあるHTMLがそのまま公開されます。

## 更新のしかた

1. 該当するHTMLファイルを編集し、写真やPDFは近くのフォルダに追加する
2. `main` ブランチにコミットしてpushする（GitHubの画面上で直接編集・アップロードしても構いません）
3. 数分後に公開サイトへ反映される

注意点:

- **文字コードは UTF-8 で保存してください。** 元サイトの一部は Shift_JIS でしたが、移行時にすべて UTF-8 に変換しています。Shift_JIS のまま保存すると文字化けします。
- **リンクは相対パスで書いてください**（例: `dokokai/golf/golf-top.html`、`../index.html`）。公開URLが `/tokyo-gyokusui/` の下にあるため、`/` から始まるリンクは切れます。
- **容量に気をつけてください。** GitHub Pages はサイト全体で約1GB、1ファイル100MBが上限で、移行時点で約960MBを使っています。写真は長辺1600px程度に縮小し、大きなPDFや動画は追加前にサイズを確認してください。
- **一度pushしたファイルは履歴に残ります。** 公開リポジトリなので、あとからファイルを削除しても過去のコミットから取り出せます。個人の写真や名簿などは、掲載の了承を得てから追加してください。

## 移行時に行った変更

- Shift_JIS のページ（56ファイル）を UTF-8 に変換し、文字コード指定も UTF-8 に統一
- 自サイトを指す絶対URL（`http://www.gyokusui.com/...`）を相対リンクに変更
- `.nojekyll` を追加（Jekyllによる加工を止め、ファイルをそのまま配信するため）
- 容量削減のため、以下を軽量化（ファイル名と置き場所は変えていないので、リンクはそのまま有効）
  - PDF: 編集ソフトのメタデータを除去（ページの見た目は変わらない）
  - 動画（神田会の4本）: 解像度はそのままで再エンコード
  - 写真: 長辺1600pxを超えるものを1600pxに縮小

## 既知のリンク切れ

次のリンク先は、移行元のサイトにも存在しませんでした。

- `data/soukai-houkoku/soukai15kai/15soukai.html` から `data/index.html`、`data/hometaka.gif`
- `data/soukai-houkoku/soukai14kai/14kai.html` から `taka-3.jpg`
- `dokokai/internet/internet-top.html` から `data/program/program.html`
- `dokokai/golf/golf-top.html` から `golf33kai.html`
- `dokokai/tbb-ob/tbb-ob-top.html` から `tbb-28kai.pdf` 〜 `tbb-31kai.pdf`
- `kandakai/kanda-index.html` から `53kai/53kai-annai.pdf`
- `katuyaku/katuyaku.html` から `31kimura/31kimura.html`
- `katuyaku/sotsugyosei.html` から `../index.html`（サイトの外を指しているリンク）

ファイルが見つかれば、該当の場所に置くだけで復旧します。

## 独自ドメインについて

`www.gyokusui.com` のままこのサイトを公開する場合は、リポジトリの Settings → Pages の「Custom domain」に `www.gyokusui.com` を設定し、ドメインのDNSで `www` を `wordplugin.github.io` へ向ける CNAME レコードを追加します。
