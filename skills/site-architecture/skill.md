# Site Architecture Skill

## 概要
SEOとユーザビリティを最大化するサイト構造を設計し、内部リンク戦略を最適化する

---

## Inputs（入力）

### 必須
- `site_theme`: サイトテーマ
- `keyword_list`: キーワードリスト（/keyword-researchの出力）

### オプション
- `category_count`: カテゴリー数（デフォルト: 3-5個）
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

#### 推奨階層構造 (3階層以内)
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

#### URL設計ルール
```
✅ 良い例:
https://example.com/skincare/moisturizer-ranking/
https://example.com/review/product-name/

❌ 悪い例:
https://example.com/p=123
https://example.com/2026/03/17/article-title/
```

### 2. カテゴリー設計

#### カテゴリー分類の基準
- 検索キーワードのクラスタリング
- ユーザーの検索意図
- 収益記事と集客記事のバランス

#### カテゴリー例 (月2-5万円サイト)
```markdown
## メインカテゴリー (3-5個)

### カテゴリー1: [基礎知識] (集客)
- 記事数: 10-15記事
- 役割: 初心者向け、PV稼ぎ
- キーワード例: 〇〇とは、〇〇始め方

### カテゴリー2: [選び方ガイド] (集客→収益)
- 記事数: 8-12記事
- 役割: 収益記事への橋渡し
- キーワード例: 〇〇選び方、〇〇比較

### カテゴリー3: [おすすめ・ランキング] (収益)
- 記事数: 5-10記事
- 役割: 収益化メイン
- キーワード例: 〇〇おすすめ、〇〇ランキング

### カテゴリー4: [レビュー] (収益)
- 記事数: 5-10記事
- 役割: 商標キーワード
- キーワード例: [商品名] 口コミ、[商品名] 評判
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

## 出力形式

```markdown
# サイト構造設計書

## サイト名
[サイト名] - [キャッチコピー]

## サイト階層図

```
TOPページ
├── カテゴリーA: [名前]
│   ├── 記事A-1: [タイトル] (収益)
│   ├── 記事A-2: [タイトル] (集客)
│   └── ...
├── カテゴリーB: [名前]
│   └── ...
└── カテゴリーC: [名前]
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
| 1 | [記事1] | /url-1/ | 収益 | ★★★ | 未作成 |
| 2 | [記事2] | /url-2/ | 集客 | ★★☆ | 未作成 |

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
