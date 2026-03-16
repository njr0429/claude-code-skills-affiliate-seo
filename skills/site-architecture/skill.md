# Site Architecture Skill

## 概要
SEOとユーザビリティを最大化するサイト構造を設計し、内部リンク戦略を最適化する

---

## Inputs（入力）

### 必須
- `site_theme`: サイトテーマ
- `keyword_list`: キーワードリスト（/keyword-researchの出力）

### オプション
- `platform`: プラットフォーム（`blogger` / `wordpress`、デフォルト: `blogger`）
- `category_count`: カテゴリー/ラベル数（デフォルト: 3-5個）
- `target_article_count`: 目標記事数（デフォルト: 30-50記事）

---

## Outputs（出力）

### 形式
Markdown形式のサイト構造設計書

### 含まれる内容
1. サイト階層図（3階層以内）
2. URL設計ルール
3. カテゴリー詳細（各カテゴリーの記事リスト）
4. 内部リンクマップ（導線設計）
5. グローバルナビゲーション/サイドバー構成

---

## このスキルを使うタイミング
- サイト構築前の設計段階
- カテゴリー構造を見直すとき
- 内部リンク戦略を立案するとき

---

## 実行手順

### 1. サイト構造の基本設計

#### Blogger版（フラット構造）
```
TOPページ (/)
├── 記事A-1 (/2026/03/article-1.html) [ラベル: カテゴリーA]
├── 記事A-2 (/2026/03/article-2.html) [ラベル: カテゴリーA]
├── 記事B-1 (/2026/03/article-3.html) [ラベル: カテゴリーB]
└── 記事B-2 (/2026/03/article-4.html) [ラベル: カテゴリーB]

ラベルページ:
- /search/label/カテゴリーA （該当記事一覧）
- /search/label/カテゴリーB （該当記事一覧）
```

**Blogger URL制御**:
- カスタムパーマリンク設定可（記事ごとに手動）
- 階層URLは不可（フラット構造のみ）
- ラベルで擬似的にカテゴリー分け

#### WordPress版（階層構造）
```
TOPページ (/)
├── カテゴリーA (/category-a/)
│   ├── 記事A-1 (/category-a/article-1/)
│   ├── 記事A-2 (/category-a/article-2/)
│   └── 記事A-3 (/category-a/article-3/)
├── カテゴリーB (/category-b/)
│   ├── 記事B-1 (/category-b/article-1/)
│   └── 記事B-2 (/category-b/article-2/)
└── カテゴリーC (/category-c/)
    ├── 記事C-1 (/category-c/article-1/)
    └── 記事C-2 (/category-c/article-2/)
```

#### Blogger: URL最適化より重要なこと

**現実的なBlogger URL構造:**
```
https://example.blogspot.com/2026/03/skincare-ranking.html
https://example.blogspot.com/2026/03/product-review.html

制約:
- 日付部分は基本固定（/2026/03/）
- 階層URLは不可（category/article/ のような形式は無理）
- カスタムパーマリンクで .html 前の部分のみ変更可能
```

**Bloggerで代わりに重視すること:**

1. **記事タイトル最適化**
   - URLより記事タイトル（H1）にキーワード含める
   - メタディスクリプションを丁寧に設定

2. **ラベル設計の統一**
   - 3-5個のメインラベルに絞る
   - ラベル名はキーワード意識（例: 「基礎知識」「選び方」「おすすめ」）
   - ラベルページ（/search/label/XXX）を活用

3. **内部リンク設計**
   - 記事内に関連記事リンクを手動で3-5箇所配置
   - 収益記事への導線を明確に
   - ラベルページへのリンクも活用

4. **ナビゲーション設計**
   - メニューバーにラベル別ページへのリンク
   - サイドバーに「人気記事」「カテゴリ（ラベル）」
   - 各記事にラベル表示（Blogger標準機能）

#### WordPress: URL設計ルール

```
✅ 良い例:
https://example.com/skincare/moisturizer-ranking/
https://example.com/review/product-name/

❌ 悪い例:
https://example.com/p=123
https://example.com/2026/03/17/article-title/
```

**WordPressの優位性:**
- 階層URL自由に設定可能
- カテゴリー名をパーマリンクに反映
- プラグインで細かい制御可能

### 2. カテゴリー/ラベル設計

#### 分類の基準（共通）
- 検索キーワードのクラスタリング
- ユーザーの検索意図
- 収益記事と集客記事のバランス

#### Blogger: ラベル設計（3-5個）
```markdown
## メインラベル (3-5個)

### ラベル1: 基礎知識 (集客)
- 記事数: 10-15記事
- 役割: 初心者向け、PV稼ぎ
- キーワード例: 〇〇とは、〇〇始め方

### ラベル2: 選び方ガイド (集客→収益)
- 記事数: 8-12記事
- 役割: 収益記事への橋渡し
- キーワード例: 〇〇選び方、〇〇比較

### ラベル3: おすすめ・ランキング (収益)
- 記事数: 5-10記事
- 役割: 収益化メイン
- キーワード例: 〇〇おすすめ、〇〇ランキング

### ラベル4: レビュー (収益)
- 記事数: 5-10記事
- 役割: 商標キーワード
- キーワード例: [商品名] 口コミ、[商品名] 評判
```

**Bloggerラベルの特徴**:
- 1記事に複数ラベル付与可能
- `/search/label/ラベル名` でラベル別記事一覧表示
- 階層構造は不可（フラットのみ）

**Bloggerナビゲーション設計例:**
```html
<!-- ヘッダーメニュー -->
<nav>
  <a href="/">ホーム</a> |
  <a href="/search/label/基礎知識">基礎知識</a> |
  <a href="/search/label/選び方">選び方ガイド</a> |
  <a href="/search/label/おすすめ">おすすめランキング</a> |
  <a href="/search/label/レビュー">レビュー</a>
</nav>

<!-- サイドバー -->
<div class="sidebar">
  <h3>カテゴリー</h3>
  <ul>
    <li><a href="/search/label/基礎知識">基礎知識 (15)</a></li>
    <li><a href="/search/label/選び方">選び方ガイド (10)</a></li>
    <li><a href="/search/label/おすすめ">おすすめランキング (8)</a></li>
    <li><a href="/search/label/レビュー">レビュー (7)</a></li>
  </ul>

  <h3>人気記事</h3>
  <!-- Blogger標準ウィジェット使用 -->
</div>
```

**Blogger内部リンク戦略（重要）:**
```markdown
URLが自由にならない分、内部リンクを手動で丁寧に配置:

1. 集客記事 → 収益記事へのリンクを本文中に3箇所
2. 記事下部に「あわせて読みたい」セクション（手動）
3. ラベルページ（/search/label/XXX）活用
4. TOPページに主要収益記事へのリンク配置

例:
「詳しくは[スキンケアおすすめランキング](記事URL)をご覧ください。」
```

#### WordPress: カテゴリー設計（3-5個）
```markdown
## メインカテゴリー (3-5個)

### カテゴリー1: [基礎知識] (集客)
- 記事数: 10-15記事
- 役割: 初心者向け、PV稼ぎ
- キーワード例: 〇〇とは、〇〇始め方
- URL: /basics/

### カテゴリー2: [選び方ガイド] (集客→収益)
- 記事数: 8-12記事
- 役割: 収益記事への橋渡し
- キーワード例: 〇〇選び方、〇〇比較
- URL: /how-to-choose/

### カテゴリー3: [おすすめ・ランキング] (収益)
- 記事数: 5-10記事
- 役割: 収益化メイン
- キーワード例: 〇〇おすすめ、〇〇ランキング
- URL: /ranking/

### カテゴリー4: [レビュー] (収益)
- 記事数: 5-10記事
- 役割: 商標キーワード
- キーワード例: [商品名] 口コミ、[商品名] 評判
- URL: /review/
```

**WordPressカテゴリーの特徴**:
- 1記事1カテゴリー推奨（複数可）
- 階層構造可能（親・子カテゴリー）
- パーマリンクにカテゴリー名反映可能
```

### 3. 内部リンク戦略

#### ピラミッド構造
```
         TOPページ
             |
    ┌────────┼────────┐
    |        |        |
カテゴリーA カテゴリーB カテゴリーC
    |        |        |
  ┌─┼─┐  ┌─┼─┐  ┌─┼─┐
  | | |  | | |  | | |
 収益記事 収益記事 収益記事
  ↑ ↑ ↑  ↑ ↑ ↑  ↑ ↑ ↑
 集客記事 集客記事 集客記事
```

#### リンク設計ルール
1. **集客記事 → 収益記事**: 自然な文脈で3-5箇所リンク
2. **収益記事 → 関連収益記事**: 比較・代替案として1-2箇所
3. **全記事 → TOPページ**: パンくずリスト
4. **関連記事**: サイドバー・記事下に3-5個表示

#### アンカーテキスト最適化
```markdown
❌ 悪い例:
「詳しくはこちら」
「クリック」

✅ 良い例:
「[商品名]の口コミ・評判を見る」
「初心者向け〇〇の選び方ガイド」
```

### 4. パンくずリスト設計

#### Blogger版
```html
<!-- シンプルなパンくずリスト -->
<nav class="breadcrumb">
  <a href="/">ホーム</a> &gt;
  <a href="/search/label/基礎知識">基礎知識</a> &gt;
  <span>記事タイトル</span>
</nav>
```

**Bloggerの制約:**
- 階層URLがないため、パンくずは「ホーム > ラベル > 記事」の3階層が限界
- 構造化データは手動で追加可能だが、必須ではない
- Bloggerテーマによっては自動生成されることもある

#### WordPress版
```html
<!-- 構造化データ対応 -->
<nav aria-label="breadcrumb">
  <ol class="breadcrumb" itemscope itemtype="https://schema.org/BreadcrumbList">
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a itemprop="item" href="/"><span itemprop="name">ホーム</span></a>
      <meta itemprop="position" content="1" />
    </li>
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <a itemprop="item" href="/category-a/"><span itemprop="name">カテゴリーA</span></a>
      <meta itemprop="position" content="2" />
    </li>
    <li itemprop="itemListElement" itemscope itemtype="https://schema.org/ListItem">
      <span itemprop="name">記事タイトル</span>
      <meta itemprop="position" content="3" />
    </li>
  </ol>
</nav>
```

### 5. XMLサイトマップ設計

#### Blogger版
**自動生成されるサイトマップ:**
```
https://example.blogspot.com/sitemap.xml （自動生成）
https://example.blogspot.com/atom.xml?redirect=false （Atomフィード）
```

**特徴:**
- Bloggerが自動でサイトマップ生成
- Google Search Consoleに自動登録される
- 手動編集は不可
- カスタマイズ不要（自動で最適化）

**やるべきこと:**
- Google Search Console で sitemap.xml を確認するのみ
- 特に追加作業なし

#### WordPress版
```xml
<?xml version="1.0" encoding="UTF-8"?>
<urlset xmlns="http://www.sitemaps.org/schemas/sitemap/0.9">
  <!-- TOPページ: 最優先 -->
  <url>
    <loc>https://example.com/</loc>
    <priority>1.0</priority>
    <changefreq>weekly</changefreq>
  </url>

  <!-- カテゴリーページ: 高優先 -->
  <url>
    <loc>https://example.com/category-a/</loc>
    <priority>0.8</priority>
    <changefreq>weekly</changefreq>
  </url>

  <!-- 収益記事: 中優先 -->
  <url>
    <loc>https://example.com/category-a/monetize-article/</loc>
    <priority>0.7</priority>
    <changefreq>monthly</changefreq>
  </url>

  <!-- 集客記事: 通常優先 -->
  <url>
    <loc>https://example.com/category-a/traffic-article/</loc>
    <priority>0.6</priority>
    <changefreq>monthly</changefreq>
  </url>
</urlset>
```

**WordPressの利点:**
- Yoast SEOなどプラグインで細かい制御可能
- priority、changefreq を記事ごとに設定
- 除外ページ設定可能

## 出力形式

### Blogger版（デフォルト）

```markdown
# サイト構造設計書（Blogger）

## サイト名
[サイト名] - [キャッチコピー]
URL: https://[サイト名].blogspot.com

## サイト階層図（フラット構造）

```
TOPページ (/)
├── 記事A-1: [タイトル] (収益) [ラベル: おすすめ]
├── 記事A-2: [タイトル] (集客) [ラベル: 基礎知識]
├── 記事B-1: [タイトル] (収益) [ラベル: レビュー]
└── ...

ラベルページ:
├── /search/label/基礎知識 （集客記事10-15記事）
├── /search/label/選び方 （集客記事8-12記事）
├── /search/label/おすすめ （収益記事5-10記事）
└── /search/label/レビュー （収益記事5-10記事）
```

## ラベル詳細

### ラベル1: 基礎知識 (集客)
- **ラベルページURL**: /search/label/基礎知識
- **目的**: 初心者向け情報提供、PV獲得
- **ターゲットKW**: 〇〇とは、〇〇始め方
- **記事数**: 10-15記事
- **収益/集客比**: 0:10（純粋な集客）

#### 記事リスト
| # | タイトル | パーマリンク | タイプ | 優先度 | ステータス |
|---|---------|-------------|--------|--------|-----------|
| 1 | [記事1] | /2026/03/keyword-based-url.html | 集客 | ★★★ | 未作成 |
| 2 | [記事2] | /2026/03/another-url.html | 集客 | ★★☆ | 未作成 |

### ラベル2: おすすめ (収益)
- **ラベルページURL**: /search/label/おすすめ
- **目的**: 収益化メイン
- **ターゲットKW**: 〇〇おすすめ、〇〇ランキング
- **記事数**: 5-10記事
- **収益/集客比**: 5:0（純粋な収益）

## 内部リンクマップ

### 収益記事への導線

```
集客記事A（基礎知識） → 収益記事1（おすすめ） (本文3箇所 + 記事下2箇所)
集客記事B（選び方） → 収益記事1（おすすめ） (本文2箇所 + 記事下1箇所)
集客記事C（基礎知識） → 収益記事2（レビュー） (本文3箇所)
```

### ハブページ設定
- TOPページ: 主要収益記事3-5個へのリンク配置
- 各ラベルページ: 該当記事の自動一覧
- 総合ランキング記事: 全収益記事にリンク

## グローバルナビゲーション

```html
<nav>
  <a href="/">ホーム</a> |
  <a href="/search/label/基礎知識">基礎知識</a> |
  <a href="/search/label/選び方">選び方ガイド</a> |
  <a href="/search/label/おすすめ">おすすめランキング</a> |
  <a href="/search/label/レビュー">レビュー</a>
</nav>
```

## パーマリンク設定ルール

**各記事で手動設定:**
- 英語小文字
- ハイフン区切り
- キーワード含む
- 例: `skincare-ranking`, `product-name-review`

❌ 避けるべき: 自動生成（`blog-post.html`）
✅ 推奨: キーワードベース（`skincare-ranking.html`）
```

### WordPress版

```markdown
# サイト構造設計書（WordPress）

## サイト名
[サイト名] - [キャッチコピー]
URL: https://example.com

## サイト階層図（階層構造）

```
TOPページ (/)
├── カテゴリーA: [名前] (/category-a/)
│   ├── 記事A-1: [タイトル] (収益) (/category-a/article-1/)
│   ├── 記事A-2: [タイトル] (集客) (/category-a/article-2/)
│   └── ...
├── カテゴリーB: [名前] (/category-b/)
│   └── ...
└── カテゴリーC: [名前] (/category-c/)
    └── ...
```

## カテゴリー詳細

### カテゴリーA: [名前]
- **URL**: /category-a/
- **目的**: [目的]
- **ターゲットKW**: [キーワード]
- **記事数**: 10記事
- **収益/集客比**: 3:7

#### 記事リスト
| # | タイトル | URL | タイプ | 優先度 | ステータス |
|---|---------|-----|--------|--------|-----------|
| 1 | [記事1] | /category-a/url-1/ | 収益 | ★★★ | 未作成 |
| 2 | [記事2] | /category-a/url-2/ | 集客 | ★★☆ | 未作成 |

## 内部リンクマップ

### 収益記事への導線

```
集客記事A → 収益記事1 (3箇所)
集客記事B → 収益記事1 (2箇所)
集客記事C → 収益記事2 (3箇所)
```

### ハブページ設定
- カテゴリーAトップ: 全記事への入り口
- 総合ランキング記事: 全収益記事にリンク

## URL命名規則

### カテゴリー
- 英語小文字
- ハイフン区切り
- 例: /skin-care/, /hair-care/

### 記事
- カテゴリー配下
- 日本語でもOK (自動エンコード)
- 例: /skin-care/moisturizer-ranking/

## グローバルナビゲーション

```
[ロゴ] カテゴリーA | カテゴリーB | カテゴリーC | ランキング | お問い合わせ
```

## サイドバー構成

1. 検索ボックス
2. 人気記事TOP5
3. カテゴリー一覧
4. プロフィール
5. SNSリンク

## フッター構成

```
カテゴリーA          運営情報
├ 記事1             ├ プライバシーポリシー
├ 記事2             ├ お問い合わせ
└ 記事3             └ サイトマップ
```

## 技術仕様

- CMS: [WordPress / Hugo / Next.js]
- テーマ: [テーマ名]
- プラグイン: Yoast SEO, EWWW Image Optimizer, など
- ホスティング: [サービス名]
```

## 成功のポイント
- ✅ 3クリック以内で全ページにアクセス可能
- ✅ 孤立ページ (内部リンクゼロ) を作らない
- ✅ 収益記事への自然な導線を複数用意
- ✅ カテゴリーは3-5個に絞る (多すぎない)

## 次のステップ
1. `/content-calendar` - コンテンツカレンダー作成
2. `/seo-article-generator` - 記事作成開始
