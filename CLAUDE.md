# ポートフォリオ ライティングルール

このプロジェクトでコンテンツを書く・リライトするときは、**必ずこのルールを適用**すること。

## サイト構成

- `index.html` — 作品一覧（WORKページ）
- `about.html` — プロフィールページ
- `work-01.html` 〜 — 案件詳細ページ

### work-XX.html のセクション順
1. project-header（英語タイトル / 日本語サブタイトル）
2. project-meta（期間 / 体制 / 担当範囲 / 成果）
3. project-hero（ヒーロー画像）
4. Overview
5. Summary（3カラム：😟課題 / 😊貢献 / 🌱結果・学び）
6. Process（3カラム：01リサーチ / 02企画・要件定義 / 03デザイン）
7. Research（詳細）
8. Planning & Requirements（詳細）
9. Design（詳細）
10. You may also like

---

## ライティングトーンルール

ユーザーがラフな日本語でセクションの内容を伝えてきたら、以下のルールに沿ってリライトし、HTMLに反映する。

### 基本スタイル

| ルール | NG例 | OK例 |
|--------|------|------|
| 体言止めを使う | 「〜を担当しました」 | 「〜を担当。」 |
| 冗長表現を避ける | 「〜することができました」「〜に取り組みました」 | 「〜を実現。」「〜を実施。」 |
| 受け身を避ける | 「〜されました」 | 「〜を推進。」 |
| 主語は省略 | 「私はユーザーインタビューを」 | 「ユーザーインタビューを」 |
| 一文は短く | 「〜し、〜して、〜しながら〜した。」 | 「〜を実施。〜を定義した。」 |
| 専門用語は英語 | 「フィグマ」「ユーザーエクスペリエンス」 | 「Figma」「UX」 |
| 数値・具体性を優先 | 「離脱が改善した」 | 「離脱率が15%改善。」 |
| 自画自賛しない | 「素晴らしい成果を出しました」 | 「CVRが12%向上。」（事実ベース） |

### セクション別ルール

#### Overview
**太字見出し＋箇条書き**の3ブロック構成。課題 → 取り組み → 成果の流れで書く。

```html
<p><strong>見出し（課題・取り組み・成果を端的に）</strong></p>
<ul><li>1〜2文の説明。数値があれば入れる。</li></ul>
```

#### Summary（3カラム）
- **😟 課題**：「〇〇が原因で〇〇が起きていた」形式で箇条書き3点
- **😊 貢献**：「〇〇を起点に〇〇を推進」形式で箇条書き3点
- **🌱 結果・学び**：数値成果1〜2点 ＋ 定性的学び1点

#### Process（3カラム — 短い説明）
1カラム2〜3文。「何をしたか」を動詞で始め、体言止めで閉じる。

例：「ステークホルダーヒアリング、ユーザーインタビュー〇名、競合調査を実施。課題の構造を整理し、優先度を定義した。」

#### Research / Planning & Requirements / Design（詳細セクション）
**番号付き太字見出し＋説明文**の構成。各セクション2〜3項目。画像は見出し直後に置く。必要に応じて `■ サブ項目` を追加。

```html
<div class="project-text">
  <p><strong>1. 見出し</strong></p>
  <p>説明文。何をやったか → なぜそれを選んだか → 何がわかったか。</p>
</div>
<div class="project-images ..." style="margin-top:24px;">
  <img ...>
</div>
<div class="project-text" style="margin-top:40px;">
  <p><strong>2. 見出し</strong></p>
  <p>説明文。</p>
  <!-- 必要な場合のみ -->
  <p><strong>■ サブ項目</strong><br>補足説明。</p>
</div>
```

#### about.html（What I Do / Design Philosophy / Background）
1人称的だが主語は省略。Design Philosophy は「〜だと考えています」で終わってよい。

---

## 図解スタイルルール

HTMLで図解（フロー図・ファネル・比較表など）を作るときは、**必ずこのスタイルを適用**すること。

### 基本方針（Material Design参考）

| 要素 | ルール |
|------|--------|
| フォントサイズ | **16px統一**。小さい文字（12–13px）は使わない |
| 強弱 | サイズ差ではなく `font-weight: 700` vs `400` で表現 |
| ノード（通常） | `background: #f5f5f5; border-radius: 8px; padding: 12px 20px;` |
| ノード（問題・強調） | `background: #1a1a1a; color: #fff; font-weight: 700;` |
| カード（callout・仮説） | `background: #fff; box-shadow: 0 2px 8px rgba(0,0,0,0.08); border-radius: 8px; padding: 20px 24px;` |
| 着色背景・左ボーダー | **使わない**（赤背景・グレー背景・ボーダー強調は廃止） |
| 矢印 | `color: #aaa` 統一 |

### クラス構成テンプレート

```html
<div class="flow-diagram">
  <div class="flow-row">
    <div class="flow-node">通常ノード</div>
    <div class="flow-arrow">→</div>
    <div class="flow-node flow-node--problem">① 問題ノード</div>
    <div class="flow-arrow flow-arrow--exit">→ 離脱</div>
  </div>
  <div class="flow-callouts">
    <div class="flow-callout">
      <strong>① 見出し</strong>
      <p>説明文。</p>
    </div>
  </div>
  <div class="flow-hypothesis">
    <p><strong>仮説：</strong>内容。</p>
  </div>
</div>
```

---

## 作業フロー

ユーザーが「〇〇セクションにこういうことを書きたい」と伝えてきたら：

1. 上記トーンルールを全適用してリライト
2. 対象HTMLファイルの該当セクションを Edit ツールで直接更新
3. 変更後テキストを一言で報告（長い説明は不要）

### HTMLの主な編集箇所

| セクション | 対象タグ |
|-----------|---------|
| 英語タイトル | `<h1 class="project-title-en">` |
| 日本語タイトル | `<p class="project-title-ja">` |
| 期間/体制/担当範囲/成果 | `<dd>` 内テキスト |
| Overview | `.project-text` の `<p>` |
| Summary 各カード | `.summary-card-title` と `<li>` |
| Process ステップ説明 | `.process-step-body` |
| Research / Planning / Design 詳細 | `.project-text` の `<p>` |
| about.html 各セクション | `.about-body > p`、`.timeline-body` |
