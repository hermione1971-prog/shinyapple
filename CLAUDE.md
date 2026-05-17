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

## 公開済み記事

| ファイル名 | タイトル（日本語） | カテゴリ | 日付 |
|---|---|---|---|
| posts/work-remote-decision.html | 50代主婦が在宅ワークを目指すことにした理由 | おしごと | 2026.05.07 |
| posts/work-02-money-vs-time.html | お金より大切なこと | 日常 | 2026.05.16 |
| posts/work-03-hellowork-resolve.html | 失業申請と強い決意 | おしごと | 2026.05.17 |

## トップページの構成

- 「✦ はじめにお読みください」特別枠（固定）→ 1記事目へリンク
- 記事グリッド（新しい記事から順に追加）

## 今後書く予定の記事

| タイトル（予定） | カテゴリ | 状況 |
|---|---|---|
| ハローワークで失業申請をした話 | おしごと | 完成（work-03-hellowork-resolve.html） |
| ポイ活で逆に損した話 | 日常 | 未着手 |
| 初めてのデータアノテーション体験記 | おしごと | 未着手 |
| リベ活で気づいたこと・家計管理を始めた話 | 家計・リベ活 | 未着手 |
| 草むしりビフォーアフター | 日常 | 写真が撮れたら |
| ある日の晩ごはん（料理苦手な主婦版） | 日常 | 写真が撮れたら |
| 元100均店員が選ぶお気に入り | 日本の文化 | 100均に行ったら |
| 庭の草花 | 日常 | 未着手 |

## ファイル構成

```
shinyapple/
├── index.html            # トップページ
├── about.html            # プロフィールページ
├── privacy.html          # プライバシーポリシー
├── contact.html          # お問い合わせ（Formspree連携）
├── style.css             # 共通スタイルシート
├── CLAUDE.md             # このファイル
├── posts/
│   ├── post-template.html             # 記事テンプレート
│   ├── work-remote-decision.html      # 1記事目
│   └── work-02-money-vs-time.html     # 2記事目
└── images/
    ├── profile-illustration.png       # プロフィールイラスト（about・サイドバー）
    └── .gitkeep
```

## 多言語対応のルール

- 日本語・英語の切り替えボタンをヘッダーに設置
- `.lj` クラス = 日本語コンテンツ
- `.le` クラス = 英語コンテンツ
- `setLang('ja')` / `setLang('en')` 関数で切り替え
- 「家計・リベ活」カテゴリは日本語ページのみに表示

## デプロイ方法

```
cd C:\Users\hermi\shinyapple
git add -A
git commit -m "コミットメッセージ"
git push origin master
npx wrangler pages deploy . --project-name=shinyapple --commit-dirty=true
```

## 新記事追加の手順

1. `posts/post-template.html` をコピーして新しいファイル名で保存
2. タイトル・カテゴリ・日付・本文を書き換える
3. `index.html` の記事グリッドに新しいカードを追加
4. 関連記事のリンクを更新
5. GitHubにプッシュ＆Cloudflare Pagesにデプロイ

## 作業上の注意

- ファイルはすべて UTF-8 で保存する
- 写真は images/ フォルダに入れてから参照する
- 写真のaltテキストは日英両方で書く（SEO対策）
- リンクはすべて相対パスで記述する
- 編集前に必ずReadツールでファイルを読み込む
