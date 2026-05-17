# ぴかりんご / Shiny Apple — 引き継ぎ資料

## このドキュメントについて

このドキュメントは、ブログサイト「ぴかりんごの小部屋」の記事更新作業を
別のAIアシスタント（Codexなど）に引き継ぐための資料です。

---

## サイト概要

- **サイト名**：ぴかりんごの小部屋 〜新しい私と出会う旅〜
- **運営者**：ぴかりんご（50代主婦・埼玉県在住）
- **公開URL**：https://shinyapple.pages.dev
- **GitHub**：https://github.com/hermione1971-prog/shinyapple
- **ローカルフォルダ**：C:\Users\hermi\shinyapple
- **言語**：日本語・英語バイリンガル
- **ホスティング**：Cloudflare Pages

---

## ファイル構成

```
shinyapple/
├── index.html                         # トップページ
├── about.html                         # プロフィールページ
├── privacy.html                       # プライバシーポリシー
├── contact.html                       # お問い合わせ
├── style.css                          # 全ページ共通CSS
├── CLAUDE.md                          # プロジェクト概要
├── HANDOFF.md                         # この引き継ぎ資料
├── posts/
│   ├── post-template.html             # 新記事作成用テンプレート
│   ├── work-remote-decision.html      # 記事①
│   └── work-02-money-vs-time.html     # 記事②
└── images/
    └── profile-illustration.png       # プロフィールイラスト
```

---

## 多言語の仕組み

日本語と英語をCSSクラスで切り替えています。

| クラス | 役割 |
|---|---|
| `.lj` | 日本語コンテンツ（デフォルト表示） |
| `.le` | 英語コンテンツ（初期値は `style="display:none"`） |

ヘッダーの「日本語 / English」ボタンで切り替わります。
**英語コンテンツには必ず `style="display:none"` を付けてください。**

---

## 新しい記事を追加する手順

### Step 1：ファイルを作成する

`posts/post-template.html` をコピーして、新しいファイル名で保存します。

**ファイル名のルール**：
- 英数字・ハイフンのみ使用
- カテゴリ-番号-内容の順
- 例：`life-01-garden-weeding.html`、`work-03-annotation.html`

### Step 2：テンプレートの書き換え箇所

以下をすべて書き換えてください。

#### ① `<head>` 部分（上から順に）

```html
<meta name="description" content="（100〜120文字の説明文）">
<meta name="keywords" content="（キーワード1, キーワード2, ...）">
<meta property="og:title" content="（記事タイトル） | ぴかりんご / Shiny Apple">
<meta property="og:description" content="（説明文）">
<title>（記事タイトル） | ぴかりんご / Shiny Apple</title>
```

#### ② パンくずリスト

```html
<span class="lj">（カテゴリ名）</span>
<span class="le" style="display:none">（Category）</span>
<span>›</span>
<span class="lj">（記事タイトル）</span>
<span class="le" style="display:none">（Article title）</span>
```

#### ③ 記事ヘッダー

カテゴリタグは `work` / `life` / `money` / `japan` の中から1つ選んでください。

```html
<!-- カテゴリタグの例（lifeの場合） -->
<span class="post-tag life lj">日常</span>
<span class="post-tag life le" style="display:none">Daily life</span>

<!-- 投稿日 -->
<span class="post-date">2026.XX.XX</span>

<!-- タイトル -->
<h1 class="article-title lj">（日本語タイトル）</h1>
<h1 class="article-title le" style="display:none">（English title）</h1>
```

#### ④ 日本語本文（`<div class="lj">` 内）

```html
<p>（導入文）</p>

<h2>（見出し1）</h2>
<p>（本文）</p>

<h2>（見出し2）</h2>
<p>（本文）</p>

<h2>まとめ</h2>
<p>（まとめ文）</p>
```

#### ⑤ 英語本文（`<div class="le" style="display:none">` 内）

```html
<p>(Opening paragraph)</p>

<h2>(Heading 1)</h2>
<p>(Body text)</p>

<h2>(Heading 2)</h2>
<p>(Body text)</p>

<h2>In summary</h2>
<p>(Closing paragraph)</p>
```

#### ⑥ 関連記事

```html
<a class="post-card" href="（関連記事のファイル名）.html">
  <div class="post-img">（絵文字）</div>
  <div class="post-body">
    <div class="post-meta">
      <span class="post-tag life lj">日常</span>
      <span class="post-tag life le" style="display:none">Daily life</span>
      <span class="post-date">2026.XX.XX</span>
    </div>
    <p class="post-title lj">（関連記事タイトル）</p>
    <p class="post-title le" style="display:none">（Related post title）</p>
  </div>
</a>
```

### Step 3：index.html に記事カードを追加する

`index.html` の `<!-- Post grid -->` 内の先頭に追加します。

```html
<a class="post-card" href="posts/（ファイル名）.html">
  <div class="post-img">（絵文字）</div>
  <div class="post-body">
    <div class="post-meta">
      <span class="post-tag life lj">日常</span>
      <span class="post-tag life le" style="display:none">Daily life</span>
      <span class="post-date">2026.XX.XX</span>
    </div>
    <p class="post-title lj">（日本語タイトル）</p>
    <p class="post-title le" style="display:none">（English title）</p>
  </div>
</a>
```

**注意：**
- `index.html` の「はじめにお読みください」特別枠は変更しないでください
- 特別枠は常に `posts/work-remote-decision.html`（1記事目）を指しています

### Step 4：デプロイする

```powershell
cd C:\Users\hermi\shinyapple
git add -A
git commit -m "Add new article: （記事タイトル）"
git push origin master
npx wrangler pages deploy . --project-name=shinyapple --commit-dirty=true
```

---

## 画像を記事に入れる場合

1. 画像を `C:\Users\hermi\shinyapple\images\` に保存
2. ファイル名は英数字・ハイフンのみ（例：`garden-before.jpg`）
3. 記事HTMLに以下を追加：

```html
<img
  src="../images/（ファイル名）.jpg"
  alt="（説明・日本語） / （description in English）">
```

---

## カテゴリと対応するCSSクラス

| カテゴリ（日本語） | カテゴリ（英語） | CSSクラス |
|---|---|---|
| 日常 | Daily life | `life` |
| 家計・リベ活 | Finances | `money` |
| おしごと | Work | `work` |
| 日本の文化 | Japanese culture | `japan` |

---

## 公開済み記事一覧

| ファイル名 | タイトル | カテゴリ | 日付 |
|---|---|---|---|
| work-remote-decision.html | 50代主婦が在宅ワークを目指すことにした理由 | おしごと | 2026.05.07 |
| work-02-money-vs-time.html | お金より大切なこと | 日常 | 2026.05.16 |

---

## 注意事項

- ファイルはすべて **UTF-8** で保存すること
- 編集前に必ずファイルを読み込んでから編集すること
- リンクはすべて**相対パス**で記述すること（`../` など）
- 英語コンテンツには必ず `style="display:none"` を付けること
- 「家計・リベ活」カテゴリは**日本語記事のみ**（英語版は作らない）
