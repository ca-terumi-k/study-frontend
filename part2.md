# CSS の基礎知識

CSS は「Cascading Style Sheets」の略で、HTML で作成した構造に対して見た目やレイアウトを指定するための言語です。

## CSS の基本構造

```css
セレクタ {
  プロパティ: 値;
  プロパティ: 値;
}
```

## part1 で使用されている主要な CSS 概念

### 1. ボックスモデル

HTML の各要素はボックスとして扱われます。

```css
* {
  box-sizing: border-box; /* パディングとボーダーを要素の幅と高さに含める */
  font-family: sans-serif;
}
```

- `content`: 要素の内容
- `padding`: コンテンツの周りの余白
- `border`: パディングの外側の境界線
- `margin`: ボーダーの外側の余白

### 2. Flexbox レイアウト

モダンなレイアウト手法で、要素を柔軟に配置できます。

```css
body {
  display: flex;
  flex-direction: column; /* 縦方向に並べる */
  min-height: 100vh; /* ビューポートの高さ全体を使用 */
}

.container {
  display: flex;
  gap: 1em; /* 子要素間の間隔 */
  height: 100%;
}

.main-content {
  flex: 3; /* 利用可能な空間の3割を占める */
}

.sidebar {
  flex: 1; /* 利用可能な空間の1割を占める */
}
```

### 3. カラーとスタイリング

各セマンティック要素の視覚的区別のために背景色を設定しています。

```css
header {
  background: #f8b400; /* 16進数カラーコード */
  padding: 1em;
}

footer {
  background: #9d8189;
  color: white; /* テキストカラー */
  padding: 1em;
}
```

### 4. マージンとパディング

要素内外の余白を制御します。

```css
section {
  background: #a0e7e5;
  margin: 1em 0; /* 上下のマージン */
  padding: 1em; /* 内側の余白 */
}
```

### 5. 画面全体を使うレイアウト

ページが画面全体を使うよう設定します。

```css
html,
body {
  margin: 0;
  padding: 0;
  height: 100%;
}

main {
  flex: 1; /* 利用可能な空間を埋める */
}

footer {
  margin-top: auto; /* 下部に固定 */
}
```

### 6. CSS の単位

- `px`: ピクセル単位（固定サイズ）
- `em`: 親要素のフォントサイズに対する相対値
- `%`: 親要素に対する割合
- `vh`: ビューポート高さの 1%

## CSS セレクタ

```css
* {
  ...;
} /* 全ての要素に適用 */
body {
  ...;
} /* body要素に適用 */
.container {
  ...;
} /* class="container"の要素に適用 */
header {
  ...;
} /* header要素に適用 */
```

## レスポンシブデザインの基本

より高度なレイアウトには、メディアクエリを使用してデバイスのサイズに応じたスタイル調整が可能です。

```css
@media (max-width: 768px) {
  .container {
    flex-direction: column; /* 画面が小さい時は縦に並べる */
  }
}
```

## CSS 設計の原則

1. **再利用性** - 共通のスタイルを再利用する
2. **保守性** - わかりやすく整理されたスタイル
3. **拡張性** - 将来の変更に対応しやすいように設計

これらの原則を意識することで、保守しやすく拡張性の高い CSS を書くことができます。
