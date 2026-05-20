# ぴかりんご / Shiny Apple — Vlogサイト制作プロジェクト

## プロジェクト概要

埼玉在住の主婦「ぴかりんご（英語名：Shiny Apple）」による日英バイリンガルVlogサイト。
赤毛のアンをテーマにした素朴で温かみのあるデザイン。
将来的な収益化（アフィリエイト・Googleアドセンス）を見据えた構成。

## サイトの基本情報

- サイト名（日本語）：ぴかりんごの小部屋
- サイト名（英語）：Shiny Apple's little room
- サブタイトル（日本語）：〜 新しい私と出会う旅 〜
- サブタイトル（英語）：~ A journey to meet a new me ~
- ヒーロータグライン（日本語）：人生は一度きり。自分らしく生きることをテーマに、新しい挑戦や日常のささやかなできごとなどを気のおもむくままにつづります。
- 運営者：ぴかりんご / Shiny Apple
- 拠点：埼玉県
- 公開URL：https://shinyapple.pages.dev
- GitHubリポジトリ：https://github.com/hermione1971-prog/shinyapple
- ホスティング：Cloudflare Pages（wranglerでデプロイ）
- お問い合わせフォーム：Formspree（ID: mzdwpaqz）

## デザインの方向性

- 赤毛のアン（Anne of Green Gables）の世界観
- カラーパレット：クリーム×ラベンダー×パープル系
- フォント：Playfair Display（見出し）＋ EB Garamond（本文英語）＋ Yu Mincho/游明朝（本文日本語）＋ Zen Kurenaido（装飾）
- 素朴で温かみのある雰囲気。過度な装飾は避ける。
- プロフィールイラスト：images/profile-illustration.png（ChatGPTで作成したアニメ風イラスト）

## コンテンツカテゴリ

| カテゴリ（日本語） | カテゴリ（英語） | 内容 |
|---|---|---|
| 日常 | Daily life | 暮らし・季節・手作り |
| 家計・リベ活 | Finances | 家計管理・節約・投資（日本語記事のみ） |
| おしごと | Work | データアノテーション・在宅ワーク |
| 日本の文化 | Japanese culture | 季節行事・食・100均・コンビニ等 |

## 公開済み記事（全7記事）

| # | ファイル名 | タイトル（日本語） | カテゴリ | 日付 |
|---|---|---|---|---|
| 1 | posts/work-remote-decision.html | 50代主婦が在宅ワークを目指すことにした理由 | おしごと | 2026.05.07 |
| 2 | posts/work-02-money-vs-time.html | お金より大切なこと | 日常 | 2026.05.16 |
| 3 | posts/work-03-hellowork-resolve.html | 失業申請と強い決意 | おしごと | 2026.05.10 |
| 4 | posts/life-01-poikatsu-loss.html | ポイ活でお金を失った話 | 日常 | 2026.05.18 |
| 5 | posts/money-01-libekatsu.html | 主婦歴２６年目の初家計簿 | 家計・リベ活 | 2026.05.19 |
| 6 | posts/work-04-remote-first-payment.html | 海外リモートワークと初めての支払い | おしごと | 2026.05.17 |
| 7 | posts/life-02-work-caregiving.html | 仕事と介護 | 日常 | 2026.05.20 |

## トップページ（index.html）の構成

- 「✦ はじめにお読みください」特別枠（固定）→ 記事1（work-remote-decision.html）へリンク
- 記事グリッド：記事7から順に新しい記事が上に来るよう手動で並べる
- サイドバー「新着記事」：最新3記事を表示（記事7・6・5）
- サイドバー「ぴかりんごのお気に入り」（日本語のみ）：お金の大学の本のアフィリエイトリンク

## サイドバーのルール

### 新着記事（全記事ページ共通）
新しい記事を追加するたびに、**全ページ**のサイドバーを更新する必要がある。
現在の表示（最新3記事）：
1. 仕事と介護 → posts/life-02-work-caregiving.html
2. 海外リモートワークと初めての支払い → posts/work-04-remote-first-payment.html
3. 主婦歴２６年目の初家計簿 → posts/money-01-libekatsu.html

### おすすめの本（money-01-libekatsu.html のみ）
日本語版サイドバーに「おすすめの本」セクションあり。
- 書籍：お金の大学（著：両@リベ大学長）
- 画像URL：https://m.media-amazon.com/images/I/71LAm5mfnuL._SY425_.jpg
- アフィリエイトリンク：https://amzn.to/49aEmCJ
- ストアID：shinyapple-22

## アフィリエイト情報

- Amazonアソシエイト：登録済み（ストアID: shinyapple-22）
- Googleサーチコンソール：登録済み
- 現在の設置箇所：
  - posts/money-01-libekatsu.html（本文内＋サイドバー、日本語のみ）
  - index.html サイドバー（日本語のみ）
- 英語版にはアフィリエイトリンクを設置しない（英語圏の読者は日本語書籍を読めないため）

## ファイル構成

```
shinyapple/
├── index.html                         # トップページ
├── about.html                         # プロフィールページ
├── privacy.html                       # プライバシーポリシー
├── contact.html                       # お問い合わせ（Formspree連携）
├── style.css                          # 共通スタイルシート
├── CLAUDE.md                          # このファイル
├── posts/
│   ├── post-template.html             # 記事テンプレート
│   ├── work-remote-decision.html      # 記事1
│   ├── work-02-money-vs-time.html     # 記事2
│   ├── work-03-hellowork-resolve.html # 記事3
│   ├── life-01-poikatsu-loss.html     # 記事4
│   ├── money-01-libekatsu.html        # 記事5
│   ├── work-04-remote-first-payment.html # 記事6
│   └── life-02-work-caregiving.html   # 記事7
└── images/
    ├── profile-illustration.png       # プロフィールイラスト（about・サイドバー）
    └── .gitkeep
```

## 多言語対応のルール

- 日本語・英語の切り替えボタンをヘッダーに設置
- `.lj` クラス = 日本語コンテンツ（デフォルト表示）
- `.le` クラス = 英語コンテンツ（`style="display:none"` でデフォルト非表示）
- `setLang('ja')` / `setLang('en')` 関数で切り替え
- 「家計・リベ活」カテゴリは日本語ページのみに表示
- アフィリエイトリンク・日本語書籍の紹介は日本語版のみ

## デプロイ方法

PowerShellで実行（&&は使えないので ; で区切る）：

```powershell
cd C:\Users\hermi\shinyapple
git add ファイル名
git commit -m "コミットメッセージ"
git push origin master
npx wrangler pages deploy . --project-name=shinyapple --commit-dirty=true
```

## 新記事追加の手順

1. `posts/post-template.html` を参考に新しいHTMLファイルを作成
2. ファイル名の命名規則：`カテゴリ略称-連番-内容.html`（例：life-03-xxx.html）
3. タイトル・カテゴリ・日付・本文を日英両方で書く
4. `index.html` の記事グリッドに新しいカードを先頭に追加
5. **全ページ**のサイドバー「新着記事」を最新3記事に更新
6. GitHubにプッシュ＆Cloudflare Pagesにデプロイ

## 今後書く予定の記事

| タイトル（予定） | カテゴリ | 状況 |
|---|---|---|
| 初めてのデータアノテーション体験記 | おしごと | 未着手 |
| 草むしりビフォーアフター | 日常 | 写真が撮れたら |
| ある日の晩ごはん（料理苦手な主婦版） | 日常 | 写真が撮れたら |
| 元100均店員が選ぶお気に入り | 日本の文化 | 100均に行ったら |
| 庭の草花 | 日常 | 未着手 |

## 作業上の注意

- ファイルはすべて UTF-8 で保存する
- 写真は images/ フォルダに入れてから参照する
- 写真のaltテキストは日英両方で書く（SEO対策）
- リンクはすべて相対パスで記述する
- 編集前に必ずReadツールでファイルを読み込む
- PowerShellでは `&&` が使えない。コマンドは `;` で区切る
