---
date: 2026-06-09
description: Aspose.BarCode for .NET を使用して DataMatrix バーコードを生成する方法を学び、アスペクト比、ECC モード、DataMatrix
  C40 エンコーディングをカスタマイズして効率的なバーコード作成を実現します。
keywords:
- generate datamatrix barcode
- datamatrix c40 encoding
- aspose barcode .net
- datamatrix ecc modes
- barcode aspect ratio
linktitle: DataMatrix バーコード設定
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  headline: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate datamatrix barcode with Aspose.BarCode for .NET,
    customize aspect ratios, ECC modes, and datamatrix c40 encoding for efficient
    barcode creation.
  name: Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode
  steps:
  - name: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
    text: '**Instantiate** `BarCodeGenerator` with `EncodeTypes.DataMatrix`.'
  - name: '**Adjust** `AspectRatio` to your desired value.'
    text: '**Adjust** `AspectRatio` to your desired value.'
  - name: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
    text: '**Generate** the image and verify with a scanner or Aspose’s built‑in reader.'
  type: HowTo
- questions:
  - answer: Choose ECC 000‑140 for small data sets with limited error correction,
      or ECC 200 for larger data and higher reliability. Macro mode adds an extra
      data layer for linking.
    question: How do I decide which ECC mode to use?
  - answer: Yes, set the `CodeText` property to your custom string, then select the
      appropriate encoding mode (ASCII, C40, etc.) to control size.
    question: Can I embed custom text in a DataMatrix barcode?
  - answer: Set `EncodeMode` to `Auto`; Aspose.BarCode evaluates the payload and picks
      the most space‑efficient mode automatically.
    question: Is there a way to automatically select the best encoding mode?
  - answer: Reuse a single `BarCodeGenerator` instance, enable multi‑threading, and
      generate PNG images for lossless quality or JPEG for smaller file size. Processing
      10 000 symbols typically completes in under 30 seconds on a standard 8‑core
      server.
    question: What are the performance considerations for large barcode batches?
  - answer: Absolutely – the library is fully compatible with .NET Framework, .NET
      Core, and the latest .NET releases, offering the same feature set across all
      platforms.
    question: Does Aspose.BarCode support .NET Core and .NET 5/6?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: DataMatrixバーコード生成 – Aspose.BarCode プロガイド
url: /ja/net/datamatrix-barcode-configuration/
weight: 30
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# DataMatrixバーコード生成 – Aspose.BarCodeによるプロガイド

**generate datamatrix barcode** を使用した Aspose.BarCode for .NET の包括的なチュートリアルシリーズへようこそ。経験豊富な開発者でバーコード出力を微調整したい方でも、基礎を理解したい新人でも、このガイドは基本設定から高度なエンコーディング手法まで、すべてのステップを案内し、任意の .NET アプリケーションで信頼性の高いスキャン可能なバーコードを提供できるようにします。

## クイック回答
- **主な目的は何ですか？** DataMatrixバーコードをプログラムで作成およびカスタマイズするためです。  
- **使用されているライブラリは何ですか？** Aspose.BarCode for .NET。  
- **ライセンスは必要ですか？** 無料トライアルが利用可能です。商用利用には商用ライセンスが必要です。  
- **サポートされている .NET バージョンは？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7。  
- **アスペクト比をカスタマイズできますか？** はい – “How to customize DataMatrix aspect ratio” セクションをご覧ください。

## generate datamatrix barcode とは何ですか？
DataMatrixバーコードは、黒と白のセルからなる二次元マトリックスで、最大2 300文字の英数字を格納できます。Aspose.BarCode を使用すると、.NET コードから直接 **generate datamatrix barcode** 画像、PDF、または SVG を生成でき、サイズ、誤り訂正レベル、エンコーディングモードを制御して任意の業界標準に合わせることができます。

## DataMatrix に Aspose.BarCode を使用する理由は？
Aspose.BarCode は DataMatrix シンボルを最大 **600 dpi** で描画し、ピクセル化せずに高解像度プリンターでも鮮明なスキャンを保証します。**50 以上の ECC およびマクロモード**（ECC 000‑140、ECC 200、Macro 05/06 など）をサポートしており、データサイズに最適な誤り訂正レベルを選択できます。API は **ASCII、C40、Text、X12、Bytes** のエンコーディングオプションを提供し、データを効率的にパックできます。統合は単一の NuGet パッケージだけで、外部のネイティブライブラリは不要です。

## DataMatrix のアスペクト比をカスタマイズする方法
`BarCodeGenerator` の `AspectRatio` プロパティは、生成される DataMatrix シンボルの幅と高さの比率を制御します。`BarCodeGenerator` は Aspose.BarCode でバーコード画像を作成するための主要クラスです。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.AspectRatio = 1.2`（または 0.5 から 2.0 の任意の値）を `GenerateBarCodeImage()` を呼び出す前に設定します。ライブラリはモジュールサイズを自動的に再計算し、要求された比率を尊重しつつスキャンの信頼性を維持します。

### ステップバイステップ
1. **インスタンス化** `BarCodeGenerator` を `EncodeTypes.DataMatrix` と共に使用します。  
2. **調整** `AspectRatio` を希望の値に設定します。  
3. **生成** 画像を作成し、スキャナーまたは Aspose の組み込みリーダーで確認します。

## DataMatrix ECC 000‑140 バーコードを生成する方法
ECC 000‑140 は、コンパクトなシンボルが必要な短いデータ文字列に最適で、最大 140 の誤り訂正コードワードを提供します。`DataMatrixEccMode.Ecc000140` は DataMatrix 用の ECC 000‑140 誤り訂正方式を選択します。

**直接的な回答:** 描画前に `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc000140` を使用します。これによりエンコーダが ECC 000‑140 アルゴリズムに切り替わり、データに対して可能な限り小さなマトリックスを生成しつつ、堅牢な誤り訂正を提供します。

**実用的なヒント:** 20 文字未満の数値データをエンコードする場合、ECC 000‑140 はしばしば 10 × 10 のマトリックスを生成し、ラベルスペースを有効に活用できます。

## DataMatrix ECC 200 バーコードを生成する方法
ECC 200 は最も広く採用されている DataMatrix モードで、最大 2 335 の英数字文字をサポートし、優れた誤り訂正を提供します。`DataMatrixEccMode.Ecc200` は DataMatrix 用の ECC 200 誤り訂正方式を選択します。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.EccMode = DataMatrixEccMode.Ecc200` を設定し、`CodeText` でペイロードを指定します。ライブラリは自動的に最適なマトリックスサイズを選択します。

**ECC 200 を選択すべきとき:** 長い文字列、混合タイプのデータ、または最高の耐久性が必要な場合に使用します—シンボルの最大 **30 %** が損傷しても復元可能です。

## DataMatrix の ASCII エンコーディングをマスターする方法
ASCII モードは文字を 1 バイトでエンコードし、プレーンテキストに対して最もスペース効率が高いです。`DataMatrixEncodeMode.Ascii` はジェネレータに DataMatrix シンボルで ASCII エンコーディングを使用させます。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Ascii` を割り当て、`CodeText` に ASCII 文字列を設定します。エンジンは余分なオーバーヘッドなしにデータをパックし、純粋な ASCII コンテンツに対して可能な限り小さなマトリックスを生成します。

**例シナリオ:** 大文字の英字と数字からなる倉庫 SKU（例: “AB1234”）は ASCII モードに最適で、しばしば 12 × 12 のマトリックスになります。

## DataMatrix モード（Auto）を生成する方法
Auto モードは Aspose.BarCode に入力を解析させ、最も効率的なエンコーディング（ASCII、C40、Text、X12、または Bytes）を自動的に選択させます。`DataMatrixEncodeMode.Auto` はこの自動選択機能を有効にします。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Auto` を設定します。ライブラリはペイロードを評価し、最適なモードを選択して単一ステップでバーコードを描画します。

**メリット:** Auto モードは開発工数を削減し、混合タイプのデータに対して可能な限り小さなシンボルを保証し、スキャン速度を向上させます。

## DataMatrix エンコーディングモード（Bytes）を使用する方法
Bytes モードは暗号化ペイロードや圧縮ファイルなどのバイナリデータ用に設計されています。`DataMatrixEncodeMode.Bytes` はジェネレータに各バイトを生データとして扱わせます。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.Bytes` を使用し、`CodeText` に Base64 エンコードされた文字列を提供します。エンコーダは各バイトを生データとして扱い、正確なバイナリ表現を保持します。

**使用例:** 128 ビット GUID や小さな暗号化トークンを直接 DataMatrix シンボルに埋め込む場合。

## DataMatrix エンコーディングモード（C40）をマスターする方法
C40 モードは大文字の英数字データを圧縮し、ASCII と比較して最大 **40 %** のサイズ削減を実現します。`DataMatrixEncodeMode.C40` はこの圧縮アルゴリズムを有効にします。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.EncodeMode = DataMatrixEncodeMode.C40` を設定し、大文字の文字列（例: “HELLO WORLD”）を提供します。エンジンは 3 文字を 2 コードワードにパックし、最終的なマトリックスを縮小します。

**プロのコツ:** C40 は主に大文字の文字、数字、スペースで構成されたペイロードに最適です。混在ケースの場合は Auto モードを検討してください。

## DataMatrix コードテキストを構成する方法
`CodeText` プロパティはバーコードに格納される正確なデータを定義します。プレーンテキスト、数値文字列、XML ペイロードなどを含めることができます。`CodeText` は `BarCodeGenerator` の主要な文字列プロパティで、バーコードペイロードを保持します。

**直接的な回答:** 描画前に `generator.Parameters.Barcode.CodeText = "YourDataHere"` を割り当てます。このプロパティは選択した ECC モードがサポートする最大長までの任意の UTF‑8 文字列を受け入れます。

**高度なヒント:** `CodeText` と `ExtendedDataMatrix` を組み合わせて、可視マトリックスサイズを増やさずに追加メタデータを埋め込むことができます。

## DataMatrix マクロ構成をマスターする方法
マクロモード（Macro 05 と Macro 06）は、プライマリシンボル内にセカンダリ DataMatrix シンボルを埋め込むことを可能にし、外部データソースへのリンクに便利です。`DataMatrixMacroMode.Macro05` と `DataMatrixMacroMode.Macro06` がこれらのマクロ機能を有効にします。

**直接的な回答:** `generator.Parameters.Barcode.DataMatrix.MacroMode = DataMatrixMacroMode.Macro05`（または `Macro06`）でマクロモードを有効にし、セカンダリペイロード用に `MacroPdf417` プロパティを設定します。ジェネレータはスキャナーが 2 つのリンクされたコードとして解釈できる複合シンボルを作成します。

**実世界の例:** マクロ部分に URL を埋め込み、プライマリマトリックスに製品識別子を保持することで、シームレスな Web‑to‑Barcode 統合を実現します。

*Aspose.BarCode for .NET のチュートリアル一覧*

## DataMatrix バーコード構成チュートリアル
### [DataMatrix アスペクト比のカスタマイズ](./datamatrix-aspect-ratio-customization/)
Aspose.BarCode for .NET を使用して DataMatrix バーコードのアスペクト比をカスタマイズする方法を学びます。バーコード生成のステップバイステップガイドです。

### [DataMatrix ECC 000-140 バーコードの生成](./datamatrix-ecc-000-140-configuration/)
Aspose.BarCode for .NET を使用して DataMatrix ECC 000-140 バーコードを簡単に作成します。在庫管理などの効率を向上させます。

### [DataMatrix ECC 200 バーコードの生成](./datamatrix-ecc-200-configuration/)
Aspose.BarCode を使用して .NET で DataMatrix ECC 200 バーコードを生成する方法を学びます。効率的なバーコード作成で業務を合理化します。

### [ASCII での DataMatrix エンコーディングをマスターする](./datamatrix-encoding-mode-ascii/)
Aspose.BarCode for .NET を使用して ASCII モードで DataMatrix バーコードを作成する方法を学びます。開発者向けのステップバイステップガイドです。

### [DataMatrix モード（Auto）の生成](./datamatrix-encoding-mode-auto/)
Aspose.BarCode for .NET を使用して DataMatrix モード（Auto）を生成する方法を学びます。このステップバイステップガイドは、前提条件からバーコードの読み取りまで網羅しています。

### [DataMatrix エンコーディングモード（Bytes）](./datamatrix-encoding-mode-bytes/)
Aspose.BarCode for .NET を使用して Bytes モードで DataMatrix 形式にデータをエンコードする方法を学びます。バーコード生成と認識のステップバイステップガイドに従ってください。

### [DataMatrix エンコーディングモード（C40）をマスターする](./datamatrix-encoding-mode-c40/)
Aspose.BarCode for .NET で DataMatrix エンコーディングモード（C40）を学びます。カスタムバーコードを効率的に作成し、ステップバイステップガイドを探求してください。

### [DataMatrix コードテキストの構成](./datamatrix-extended-code-text-configuration/)
Aspose.BarCode for .NET を使用して DataMatrix の拡張コードテキストを構成する方法を学びます。バーコードの生成、認識、.NET アプリケーションへの統合が可能です。

### [DataMatrix マクロ構成をマスターする](./datamatrix-macro-configuration/)
Aspose.BarCode for .NET を使用して DataMatrix マクロバーコードを構成する方法を学びます。.NET アプリケーションで DataMatrix バーコードを生成、カスタマイズ、認識できます。

## よくある質問

**Q: どの ECC モードを使用すべきかはどう判断しますか？**  
A: ECC 000‑140 は小規模データで限られた誤り訂正が必要な場合に、ECC 200 は大きなデータと高い信頼性が必要な場合に選択します。マクロモードはリンク用に追加のデータ層を提供します。

**Q: DataMatrix バーコードにカスタムテキストを埋め込めますか？**  
A: はい、`CodeText` プロパティにカスタム文字列を設定し、適切なエンコーディングモード（ASCII、C40 など）を選択してサイズを制御します。

**Q: 最適なエンコーディングモードを自動的に選択する方法はありますか？**  
A: `EncodeMode` を `Auto` に設定します。Aspose.BarCode がペイロードを評価し、最もスペース効率の良いモードを自動的に選択します。

**Q: 大量のバーコードバッチを処理する際のパフォーマンス考慮点は何ですか？**  
A: 単一の `BarCodeGenerator` インスタンスを再利用し、マルチスレッド化を有効にし、ロスレス品質の PNG 画像またはサイズが小さい JPEG を生成します。標準的な 8 コアサーバー上で 10 000 個のシンボルを処理する場合、通常 30 秒未満で完了します。

**Q: Aspose.BarCode は .NET Core および .NET 5/6 をサポートしていますか？**  
A: はい、ライブラリは .NET Framework、.NET Core、最新の .NET リリースすべてと完全に互換性があり、すべてのプラットフォームで同じ機能セットを提供します。

**最終更新日:** 2026-06-09  
**テスト環境:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose

## 関連チュートリアル
- [Aspose.BarCode for .NET を使用した DataMatrix バーコード（ECC 200）の生成方法](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Aspose.BarCode for .NET で ASCII の DataMatrix エンコーディングをマスターする](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [バーコード PNG の作成 – DataMatrix アスペクト比 – Aspose.BarCode](/barcode/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}