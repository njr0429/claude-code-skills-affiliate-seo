# Conversion Optimizer Skill

## 概要
アフィリエイトリンクのクリック率とコンバージョン率を最大化し、収益を向上させる

---

## Inputs（入力）

### 必須
- `article_url`: 対象記事URL（収益記事）

### オプション
- `platform`: プラットフォーム（`blogger` / `wordpress`、デフォルト: `blogger`）
- `current_cvr`: 現在のCVR（%）
- `monthly_pv`: 月間PV数
- `analytics_data`: GA4データ（ヒートマップ、離脱率など）

---

## Outputs（出力）

### 形式
Markdown形式のCVR最適化レポート

### 含まれる内容
1. 現状分析（CVファネル、問題点）
2. 改善施策（優先度別）
3. CTAボタン改善案（コード例）
4. 商品比較表サンプル
5. KPI目標（1ヶ月後の目標値）

---

## このスキルを使うタイミング

### ✅ 使うべきとき
- **収益記事公開後1ヶ月（データがたまった段階）**
- CVRが1%未満のとき（業界平均を下回る）
- PVはあるが収益が伸びないとき（導線に問題がある）
- **月次の収益改善施策として（定期実施推奨）**
- アフィリエイトリンクのクリック率が低いとき
- 新しい収益記事を公開した後（CTA設計の最適化）

### ❌ 使わない方がいいとき
- 収益記事がまだ公開されていない段階
- PVが月100未満でデータが少なすぎる段階
- CVRより先に記事数を増やすべき段階（まずは10記事以上）

### 📍 ワークフロー上の位置
```
/seo-audit → このスキル → 改善実施 → 効果測定（1ヶ月後）
```

---

## 実行手順

### 1. 現状分析

#### CVファネル分析
```
ページビュー: 1,000
   ↓ 離脱率60%
記事読了: 400
   ↓ リンク非表示70%
リンク表示: 120
   ↓ クリック率5%
リンククリック: 6
   ↓ CV率20%
成果発生: 1-2件

**問題点を特定**:
- 離脱率が高い → 導入文改善
- リンクまで到達しない → 構成見直し
- クリックされない → CTAボタン改善
- CVしない → 案件のマッチング見直し
```

#### ヒートマップ分析
```bash
# Microsoft Clarity (無料) で確認
- クリック箇所
- スクロール深度
- 離脱ポイント
- 滞在時間

→ ユーザーの行動パターンを把握
```

### 2. CVR向上テクニック

#### ① CTAボタン最適化

**❌ 弱いCTA（避けるべき）**
```html
<a href="...">こちら</a>
<a href="...">詳細を見る</a>
```

**✅ シンプルCTA（Blogger初心者向け）**
```html
<p style="text-align: center; padding: 15px; background: #f0f8ff; border: 2px solid #0066cc; border-radius: 5px; margin: 20px 0;">
  <strong>今すぐチェック！</strong><br>
  <a href="[アフィリエイトリンク]" target="_blank" rel="nofollow" style="display: inline-block; margin-top: 10px; padding: 12px 30px; background: #0066cc; color: white; text-decoration: none; border-radius: 5px; font-weight: bold;">
    公式サイトで詳細を見る
  </a><br>
  <small style="color: #666;">送料無料・30日間返品保証</small>
</p>
```

**✅ 装飾CTA（Blogger上級者向け）**
```html
<div style="background: linear-gradient(135deg, #667eea 0%, #764ba2 100%); padding: 20px; border-radius: 10px; text-align: center; margin: 30px 0;">
  <p style="color: #fff; font-size: 16px; margin: 0 0 10px 0; font-weight: bold;">今だけ30%オフ!</p>
  <a href="[アフィリエイトリンク]" target="_blank" rel="nofollow" style="display: inline-block; background: #ff6b6b; color: white; padding: 15px 40px; font-size: 18px; font-weight: bold; border-radius: 50px; text-decoration: none; margin: 10px 0;">
    公式サイトで最安値をチェック
  </a>
  <p style="color: #fff; font-size: 14px; margin: 10px 0 0 0;">送料無料・30日間返品保証</p>
</div>
```

**✅ 強いCTA（WordPress版：カスタムCSS）**
```html
<div class="cta-button primary">
  <p class="benefit">今だけ30%オフ!</p>
  <a href="..." class="btn">
    公式サイトで最安値をチェック
  </a>
  <p class="guarantee">送料無料・30日間返品保証</p>
</div>

<style>
.cta-button {
  background: linear-gradient(135deg, #667eea 0%, #764ba2 100%);
  padding: 20px;
  border-radius: 10px;
  text-align: center;
  margin: 30px 0;
}
.btn {
  display: inline-block;
  background: #ff6b6b;
  color: white;
  padding: 15px 40px;
  font-size: 18px;
  font-weight: bold;
  border-radius: 50px;
  text-decoration: none;
  transition: transform 0.2s;
}
.btn:hover {
  transform: scale(1.05);
}
</style>
```

**CTAの3要素**:
1. **ベネフィット**: 得られる価値を明示
2. **行動指示**: 具体的な行動を促す
3. **安心要素**: 保証・無料などリスク軽減

#### ② ボタン配置の最適化

```markdown
## ボタン配置ルール

### 必須配置箇所 (3箇所)
1. **導入直後** (記事上部20%)
   - 「結論だけ知りたい人向け」として配置

2. **比較表・ランキングの直後** (記事中盤50%)
   - ユーザーの意思決定直後に配置

3. **まとめの直後** (記事下部90%)
   - 最後の一押し

### 追加配置 (任意)
- 各商品レビューの後
- 口コミセクションの後
- FAQの後
```

#### ③ 商品比較表の最適化

```html
<!-- ✅ CVRが高い比較表 -->
<table class="comparison-table">
  <thead>
    <tr>
      <th>商品名</th>
      <th>価格</th>
      <th>評価</th>
      <th>特徴</th>
      <th></th>
    </tr>
  </thead>
  <tbody>
    <tr class="recommended">
      <td>
        <img src="..." alt="商品1">
        <strong>商品名1</strong>
        <span class="badge">🏆 1位</span>
      </td>
      <td><strong>¥9,800</strong></td>
      <td>⭐⭐⭐⭐⭐ 4.8</td>
      <td>
        ✅ 初心者向け<br>
        ✅ コスパ最強<br>
        ✅ サポート充実
      </td>
      <td>
        <a href="..." class="btn-small">公式サイト</a>
      </td>
    </tr>
    ...
  </tbody>
</table>

<style>
.recommended {
  background-color: #fff9e6;
  border: 2px solid #ffd700;
}
.badge {
  background: #ffd700;
  padding: 2px 8px;
  border-radius: 3px;
  font-size: 12px;
}
</style>
```

#### ④ 緊急性・希少性の演出

**Blogger版（静的表現）**
```html
<div style="background: #fff3cd; border-left: 4px solid #ffc107; padding: 15px; margin: 20px 0;">
  <p style="margin: 5px 0;">⏰ キャンペーン期間: 2026年3月31日まで</p>
  <p style="margin: 5px 0;">🔥 在庫残りわずか!</p>
  <p style="margin: 5px 0;">✨ 今なら期間限定30%オフ</p>
</div>

<!-- 限定感 -->
<div style="background: #f8f9fa; border: 1px solid #dee2e6; padding: 15px; margin: 20px 0;">
  <p style="margin: 5px 0;">👥 過去30日間で327人が購入</p>
  <p style="margin: 5px 0;">⭐ 満足度98%</p>
</div>
```

**WordPress版（JavaScriptカウントダウン可）**
```html
<!-- カウントダウンタイマー -->
<div class="urgency-box">
  <p>⏰ このキャンペーンは残り<span id="timer"></span>で終了</p>
  <p>🔥 在庫残りわずか!</p>
  <p>✨ 今なら期間限定30%オフ</p>
</div>
<script>
  // JavaScriptカウントダウン実装
</script>
```

**注意**: 嘘の情報は厳禁。本当のキャンペーン情報のみ掲載

#### ⑤ 口コミ・レビューの活用

```markdown
## [商品名]の口コミ・評判

### ⭐⭐⭐⭐⭐ 良い口コミ

> 使い始めて1週間ですが、すでに効果を実感しています!
> **30代女性・購入者**

> コスパが良く初心者にもおすすめです。
> **20代男性・購入者**

### ⭐⭐⭐☆☆ イマイチな口コミ

> 値段が少し高いと感じました。
> **40代女性・購入者**

**総評**: 価格は平均的だが、効果への満足度が高い
```

**ポイント**: 良い口コミだけでなく、悪い口コミも掲載して信頼性UP

### 3. 導入文の最適化

```markdown
## ❌ 弱い導入文
「今回は〇〇について解説します。」

## ✅ 強い導入文 (PREP法)

【Point: 結論】
〇〇で悩んでいるなら、**[商品A]**が最もおすすめです。

【Reason: 理由】
なぜなら、△△という特徴があり、◇◇な人に最適だからです。

【Example: 具体例】
実際に私も使用したところ、1週間で□□という効果がありました。

【Point: 再度結論】
この記事では、〇〇の選び方とおすすめTOP5を紹介します。
```

### 4. 内部リンク導線の最適化

```markdown
## 記事間の導線設計

### パターン1: 集客記事 → 収益記事
```
記事: 「〇〇の始め方」(集客)
   ↓
内部リンク: 「初心者におすすめの〇〇はこちら」
   ↓
記事: 「〇〇おすすめランキング」(収益)
```

### パターン2: 比較記事 → 個別レビュー
```
記事: 「〇〇比較ランキング」(収益)
   ↓
内部リンク: 「1位の[商品名]の詳細レビューはこちら」
   ↓
記事: 「[商品名]口コミレビュー」(収益)
```

### リンクテキスト例
- ❌ 「こちらの記事」「詳細はこちら」
- ✅ 「初心者向け〇〇の選び方ガイド」
- ✅ 「[商品名]の実際の口コミ・評判を見る」
```

### 5. A/Bテスト項目

```markdown
## テストすべき要素

### タイトル
- バージョンA: 「〇〇おすすめ10選」
- バージョンB: 「【2026年最新】〇〇おすすめランキングTOP10」
→ CTR比較

### CTAボタン
- バージョンA: 緑色ボタン「公式サイトへ」
- バージョンB: 赤色ボタン「最安値をチェック」
→ クリック率比較

### ボタン配置
- バージョンA: 記事上部・中部・下部の3箇所
- バージョンB: 記事中部・下部の2箇所
→ CV数比較

### 価格表示
- バージョンA: 「¥9,800」
- バージョンB: 「通常¥14,800 → 今だけ¥9,800 (33%オフ)」
→ CV率比較
```

## 出力形式

```markdown
# CVR最適化レポート

## 対象記事
[記事タイトル] - [URL]

## 現状分析

### CV率
- 先月: 0.8% (5件/625PV)
- 今月: 0.5% (3件/600PV) ⬇ -37.5%

### 問題点
1. ❌ CTAボタンが1箇所のみ
2. ❌ 比較表がない
3. ❌ 口コミが少ない (2件)
4. ❌ 導入文が弱い

---

## 改善施策

### 優先度★★★ (即実施)

#### 1. CTAボタン追加
**現状**: 記事下部1箇所のみ
**改善**: 導入直後、比較表後、まとめ後の3箇所に配置

```html
[ボタンコード例]
```

**期待効果**: CVR +0.3-0.5%

#### 2. 商品比較表作成
**現状**: テキストのみの商品紹介
**改善**: 視覚的な比較表を挿入

| 商品名 | 価格 | 評価 | 特徴 | |
|--------|------|------|------|---|
| ... | ... | ... | ... | [ボタン] |

**期待効果**: CVR +0.2-0.4%

---

### 優先度★★☆ (今週中)

#### 3. 口コミ追加
**現状**: 口コミ2件
**改善**: 良い口コミ5件 + 悪い口コミ2件追加

**期待効果**: 信頼性向上、CVR +0.1-0.2%

#### 4. 導入文リライト
**現状**: 結論が不明瞭
**改善**: PREP法で結論先出し

**期待効果**: 離脱率 -10%

---

### 優先度★☆☆ (来月)

#### 5. A/Bテスト実施
- CTAボタンの色 (緑 vs 赤)
- ボタンテキスト (「公式サイト」vs「最安値をチェック」)

---

## KPI目標

| 指標 | 現状 | 目標 (1ヶ月後) |
|------|------|----------------|
| 月間PV | 600 | 700 |
| CV数 | 3件 | 7件 |
| CVR | 0.5% | 1.0% |
| 収益 | ¥3,000 | ¥7,000 |

---

## 次回レビュー
2026年4月17日 (1ヶ月後)
```

## 成功のポイント
- ✅ ボタンは最低3箇所配置
- ✅ 比較表で視覚的にわかりやすく
- ✅ 口コミで信頼性を担保
- ✅ 緊急性・希少性を適度に演出
- ✅ A/Bテストで継続改善

## 次のステップ
1. 改善実施後、1週間でヒートマップ確認
2. 1ヶ月後に `/seo-audit` で効果測定
