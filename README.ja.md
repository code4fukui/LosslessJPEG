# LosslessJPEG

JavaScriptで実装されたJPEG Losslessデコーダーです。

## 機能
- DICOM JPEG Lossless転送構文をサポート:
  - 1.2.840.10008.1.2.4.57 JPEG Lossless, Nonhierarchical (Processes 14)
  - 1.2.840.10008.1.2.4.70 JPEG Lossless, Nonhierarchical (Processes 14 [Selection 1])

### 使い方
[API](https://github.com/rii-mango/JPEGLosslessDecoderJS/wiki/API) および [その他の例](https://github.com/rii-mango/JPEGLosslessDecoderJS/tree/master/tests)

```javascript
var decoder = new jpeg.lossless.Decoder();
var output = decoder.decompress(buffer [, offset [, length]]);

// パラメータ
// {ArrayBuffer} buffer
// {Number} offset バッファ内のオフセット（デフォルト = 0）
// {Number} length バッファの長さ（デフォルト = JPEGブロックの終端）

// 戻り値
// {ArrayBuffer} output（サイズ = cols * rows * bytesPerComponent * numComponents）
```

### インストール
[release フォルダ](https://github.com/rii-mango/JPEGLosslessDecoderJS/tree/master/release)からパッケージ化されたソースファイルを取得します:

* [lossless.js](https://raw.githubusercontent.com/rii-mango/JPEGLosslessDecoderJS/master/release/lossless.js)
* [lossless-min.js](https://raw.githubusercontent.com/rii-mango/JPEGLosslessDecoderJS/master/release/lossless-min.js)

または、[NPM](https://www.npmjs.com/) 経由でインストールします:

```
npm install jpeg-lossless-decoder-js
```

### テスト
```
npm test
```

### ビルド
```
npm run build
```
これにより、`lossless.js` と `lossless-min.js` が、型定義ファイルおよびソースマップとともに `/release` に出力されます。

### 謝辞
このデコーダーは、元々 Helmut Dersch 氏によって Java 向けに作成されたものです。私は選択値（selection values）2〜7のサポートを追加し、バグ修正を行い、JavaScriptへ移植しました。

また、このパッケージを TypeScript にモダナイズしてくれた [@jens-ox](https://github.com/jens-ox) 氏に感謝します。

## ライセンス
MIT License — 詳細は [LICENSE](LICENSE) を参照してください。
