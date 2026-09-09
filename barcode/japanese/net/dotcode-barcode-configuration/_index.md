---
date: 2026-06-14
description: Aspose.BarCode for .NET を使用して DotCode バーコードを生成する方法を学びます。アスペクト比、エンコーディングモード、拡張テキスト、リーダーの初期化について解説します。
keywords:
- how to generate dotcode
- dotcode barcode configuration
- aspose barcode .net
linktitle: DotCode バーコードの生成方法 – 設定ガイド
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to generate DotCode barcodes with Aspose.BarCode for .NET,
    covering aspect ratio, encoding modes, extended text, and reader initialization.
  headline: How to Generate DotCode Barcodes – Configuration Guide
  type: TechArticle
- questions:
  - answer: Yes, set `BarCodeImageFormat = BarCodeImageFormat.Svg` on the generator
      to receive a scalable vector output.
    question: Can I generate DotCode barcodes in SVG format?
  - answer: Aspose.BarCode does not support direct logo embedding for DotCode, but
      you can overlay an image after generation using standard graphics libraries.
    question: Is it possible to embed a logo inside a DotCode symbol?
  - answer: The symbology includes built‑in Reed‑Solomon error correction; increasing
      rows/columns automatically raises the correction level.
    question: How does error correction work for DotCode?
  - answer: No, the same `BarCodeReader` can extract DotCode from PDF pages, images,
      or streams without additional tools.
    question: Do I need a separate library to read DotCode from a PDF?
  - answer: Up to **1 200** numeric or **800** alphanumeric characters, depending
      on the chosen rows/columns configuration.
    question: What is the maximum data size for a single DotCode symbol?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DotCode バーコードの生成方法 – 設定ガイド
url: /ja/net/dotcode-barcode-configuration/
weight: 32
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DotCode バーコードの生成方法 – 設定ガイド

## はじめに
**DotCode の生成方法** バーコードを迅速かつ確実に生成することは、在庫管理、トラッキング、モバイルスキャン ソリューションを構築する開発者にとって一般的な要件です。このチュートリアルでは、Aspose.BarCode for .NET が提供する DotCode シンボル向けのすべての設定オプション—アスペクト比の調整、Auto と Bytes エンコーディングモード、拡張コードテキストの処理、リーダーの初期化、行/列のレイアウト、構造化付加モード—を順に解説します。最後まで読むと、業界標準を満たし、任意の .NET アプリケーションにシームレスに統合できる、サイズが最適で高密度な DotCode 画像を生成できるようになります。

## クイック回答
- **DotCode バーコードを作成するための主要クラスは何ですか？** `BarcodeGenerator` with `EncodeTypes.DotCode`.
- **アスペクト比を制御するプロパティはどれですか？** `BarCodeImageAspectRatio`.
- **Auto と Bytes エンコーディングを切り替えることはできますか？** Yes, via `EncodeMode` property.
- **DotCode 用に別のリーダーが必要ですか？** No, the same `BarcodeGenerator` can decode when `ReadBarcode` is called.
- **.NET のサポートバージョンは何ですか？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.

## Aspose.BarCode for .NET を使用して DotCode バーコードを生成する方法
`BarcodeGenerator` は Aspose.BarCode でバーコード画像を作成するための主要クラスです。`EncodeTypes.DotCode` で `BarcodeGenerator` をロードし、目的のプロパティ（アスペクト比、エンコーディングモード、行/列 など）を設定してから `GenerateBarCodeImage()` を呼び出します—ライブラリはすぐに使用できる `System.Drawing.Image` またはバイト配列を返します。このワンステップのワークフローはすべての低レベルエンコーディング詳細を処理し、PNG、JPEG、SVG などの出力形式をサポートし、過剰なメモリを消費せずに最大 10 000 × 10 000 px の画像をレンダリングできます。

## DotCode バーコードとは何ですか？
DotCode バーコードは、高密度で正方形の 2D シンボルで、最大 1 200 桁の数字または 800 文字の英数字をドットのコンパクトなマトリックスに格納します。小型パッケージのラベリングやモバイルスキャン向けに最適化されており、低解像度カメラでも高速な読み取りが可能です。

## なぜ Aspose.BarCode で DotCode を使用するのか？
Aspose.BarCode は DotCode を含む **20+** の 2D バーコードタイプをサポートし、画像全体をメモリに読み込むことなく **200 MB** を超えるファイルを処理できます。このライブラリは標準的なスマートフォンカメラで **99.9 %** のスキャン精度を保証し、読み取り失敗を最小限に抑える組み込みエラー訂正レベルを提供します。

## 前提条件
- .NET Framework 4.5 以上、または .NET Core 3.1 / .NET 5+。
- Aspose.BarCode for .NET（最新バージョン推奨）。
- 一時的またはフルのライセンスキー（開発にはトライアルで動作）。

## DotCode アスペクト比のカスタマイズ
**aspect‑ratio** は DotCode マトリックスがどれだけ伸びたり圧縮されたりするかを決定します。`BarCodeImageAspectRatio` プロパティを使用して **0.5**（縦長）から **2.0**（横長）までの値を設定します。**1.0** の比率は完全な正方形シンボルを生成し、デフォルトであり、ほとんどのスキャナで最適に機能します。

> **Tip:** 狭いラベルに印刷する場合、**0.75** の比率はデータ容量を犠牲にせず可読性を向上させることがよくあります。

## DotCode エンコーディングモード（Auto）
**Auto** モードでは、ライブラリが入力文字列を解析し、数値、英数字、バイトの中で最も効率的なエンコーディングを自動的に選択します。これによりデータ密度が最大化され、シンボル全体のサイズが縮小されます。

> **Direct answer:** `BarcodeGenerator` の `EncodeMode = EncodeModes.Auto` を設定して、Aspose.BarCode にデータに最適なエンコーディングを判断させ、すべての文字を保持しつつ可能な限り最小の DotCode を生成します。

## DotCode エンコーディングモード（Bytes）
バイナリデータや事前にエンコードされたバイト配列を格納する必要がある場合は、**Bytes** モードを選択します。これにより、ジェネレータは入力を生バイトとして扱い、自動文字セット検出をバイパスします。

> **Direct answer:** `EncodeMode = EncodeModes.Bytes` を使用し、`byte[]` ペイロードを提供して、暗号化された識別子や圧縮ファイルなどのバイナリ情報を DotCode シンボルに直接埋め込みます。

## DotCode 拡張コードテキストの設定
拡張コードテキストを使用すると、メインデータペイロードの一部ではない補足情報を付加でき、レポートや GUI でバーコードと共に表示できます。`ExtendedCodeText` プロパティに任意の文字列（最大 **256** 文字）を設定し、`ExtendedCodeTextFont` でフォントを選択します。

> **Pro tip:** 拡張テキストは小さいフォントサイズ（例：8 pt）と組み合わせて、視覚的な占有面積を抑えつつ、人が読めるコンテキストを提供します。

## DotCode リーダーの初期化
`BarCodeReader` は画像やストリームからバーコードをデコードするために使用されるクラスです。DotCode 画像の読み取りは生成と同様に簡単です。画像ストリームで `BarCodeReader` をインスタンス化し、`EncodeTypes.DotCode` を指定します。`ReadBarCode()` を呼び出してデコードされた文字列を取得します。

> **Direct answer:** `using (var reader = new BarCodeReader(imageStream, DecodeType.DotCode)) { if (reader.ReadBarCode()) { string data = reader.GetCodeText(); } }` – この単一ブロックで外部依存なしにシンボルをデコードします。

## DotCode 行と列の設定
DotCode は行数と列数を明示的に制御でき、シンボルサイズとエラー訂正容量に影響します。`Rows` と `Columns` プロパティを使用して **10** から **144** の範囲で値を設定します。大きなマトリックスはデータ容量と耐久性を向上させます。

> **Best practice:** 粗い取り扱いに耐える必要がある在庫タグの場合、**Rows = 64** と **Columns = 64** を設定して余分な冗長性を追加します。

## DotCode 構造化付加モードの設定
構造化付加（Structured Append）により、大きなペイロードを複数の DotCode シンボルに分割して順次読み取れるようにします。各パーツで `StructuredAppend = true` を設定し、`StructuredAppendCount` と `StructuredAppendIndex` を定義します。

> **Direct answer:** 各 `BarcodeGenerator` で `StructuredAppend` を有効にし、ユニークなインデックス（1 から開始）を割り当て、総数を設定します。ライブラリは必要なリンク情報を自動的に埋め込みます。

## 一般的な問題と解決策
- **低解像度画面でバーコードが読めない場合:** 生成前に `Resolution` プロパティを少なくとも **300 dpi** に上げてください。
- **データ切り捨て警告:** 入力長が選択した行/列の最大値を超えていないか確認し、必要に応じてサイズを調整するか Bytes モードに切り替えてください。
- **開発中のライセンス期限切れ:** Aspose ポータルから取得した一時ライセンスを使用し、本番展開前に永続キーに置き換えてください。

## よくある質問

**Q: SVG 形式で DotCode バーコードを生成できますか？**  
A: はい、ジェネレータで `BarCodeImageFormat = BarCodeImageFormat.Svg` を設定すると、スケーラブルベクタ出力が得られます。

**Q: DotCode シンボル内にロゴを埋め込むことは可能ですか？**  
A: Aspose.BarCode は DotCode に対する直接的なロゴ埋め込みをサポートしていませんが、生成後に標準のグラフィックライブラリを使用して画像をオーバーレイすることは可能です。

**Q: DotCode のエラー訂正はどのように機能しますか？**  
A: このシンボルは組み込みの Reed‑Solomon エラー訂正を含んでおり、行/列を増やすと自動的に訂正レベルが上がります。

**Q: PDF から DotCode を読み取るために別のライブラリが必要ですか？**  
A: いいえ、同じ `BarCodeReader` が PDF ページ、画像、ストリームから DotCode を抽出でき、追加ツールは不要です。

**Q: 単一の DotCode シンボルの最大データサイズはどれくらいですか？**  
A: 選択した行/列構成に応じて、数値は最大 **1 200** 文字、英数字は最大 **800** 文字です。

---

**最終更新日:** 2026-06-14  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose  

## DotCode バーコード設定チュートリアル
### [DotCode アスペクト比のカスタマイズ](./dotcode-aspect-ratio-customization/)
Aspose.BarCode for .NET を使用して DotCode バーコードのアスペクト比をカスタマイズする方法を学びます。アプリケーション向けに簡単にカスタマイズされたバーコードを作成できます。

### [DotCode エンコーディングモード（Auto）](./dotcode-encoding-mode-auto/)
Aspose.BarCode for .NET の DotCode エンコーディングモード（Auto）を探求し、バーコード生成の強力なツールを学びます。DotCode バーコードをステップバイステップで生成する方法を学び、ドキュメントを確認し、ライブラリをダウンロードし、一時ライセンスを取得してください。

### [DotCode エンコーディングモード（Bytes）](./dotcode-encoding-mode-bytes/)
Aspose.BarCode for .NET を使用した DotCode エンコーディングの学習：バーコード生成のステップバイステップガイド。

### [DotCode 拡張コードテキスト設定](./dotcode-extended-code-text-configuration/)
Aspose.BarCode for .NET を使用して DotCode の拡張コードテキスト設定を簡単に生成します。効率的なバーコード作成のためのステップバイステップガイドに従ってください。

### [DotCode リーダーの初期化](./dotcode-reader-initialization/)
Aspose.BarCode for .NET を使用して DotCode リーダーを初期化する方法を学びます。さまざまなアプリケーション向けに DotCode バーコードを簡単に作成できます。

### [DotCode 行と列の設定](./dotcode-rows-columns-configuration/)
Aspose.BarCode for .NET を使用して DotCode の行と列を設定する方法を学びます。正確でカスタマイズ可能な 2D バーコードを簡単に生成できます。

### [DotCode 構造化付加モードの設定](./dotcode-structured-append-mode-configuration/)
Aspose.BarCode for .NET で DotCode の構造化付加モードを設定し、効率的なバーコードを作成する方法を学びます。

## 関連チュートリアル

- [Aspose.BarCode for .NET で DotCode アスペクト比をカスタマイズ](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)
- [Aspose.BarCode for .NET で DotCode 拡張コードテキスト設定](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [Aspose.BarCode for .NET の DotCode エンコーディングモード（Auto）](/barcode/net/dotcode-barcode-configuration/dotcode-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}