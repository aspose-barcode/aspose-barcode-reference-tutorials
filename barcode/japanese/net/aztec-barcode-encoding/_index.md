---
date: 2026-05-19
description: Aspose.BarCode for .NET を使用して Aztec バーコードを作成する方法を学び、アスペクト比をカスタマイズし、バイトまたはテキストをエンコードし、マスターシンボルモードを使用します。
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec バーコード エンコーディング
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Aspose.BarCode for .NET を使用した Aztec バーコードの作成方法
url: /ja/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aztec バーコードエンコーディング

Aztec バーコードエンコーディングの世界に飛び込み、Aspose.BarCode for .NET を使用して **Aztec バーコード** 画像を作成する方法を学ぶ準備はできていますか？このライブラリはサイズ、エラー訂正、データ表現をフルコントロールでき、モバイルチケット発行から在庫管理まであらゆる用途に最適です。

## クイック回答
- **Aztec バーコードをサポートしているライブラリは？** Aspose.BarCode for .NET  
- **アスペクト比を変更できますか？** はい、`AspectRatio` プロパティで変更できます  
- **バイトレベルのエンコードは可能ですか？** もちろんです – `EncodeBytes` メソッドを使用してください  
- **利用可能なエラー訂正レベルは？** レベル 0 から 4（数値が大きいほど冗長性が高くなります）  
- **本番環境でライセンスが必要ですか？** はい、商用ライセンスを取得すると評価版の制限が解除されます  

## Aztec バーコードとは？
Aztec バーコードは、最大で 3,000 桁の数字または 2,300 桁の英数字をエンコードできる 2 次元マトリックスコードです。中央にファインダーパターンを持ち、低解像度で印刷されたシンボルでも高速スキャンが可能です。パターンが中央にあるため、どの方向からでもコードを読み取ることができ、モバイルや産業用途での信頼性が非常に高くなります。

## Aztec バーコードのアスペクト比をカスタマイズする方法
`BarcodeGenerator` は Aspose.BarCode でバーコードを作成するための主要クラスです。`BarcodeGenerator` オブジェクトの `AspectRatio` プロパティに希望する幅‑高さ比を設定し、画像を生成します。アスペクト比を調整することで、スキャン信頼性を損なうことなく、制限された UI スペースやラベルレイアウトにバーコードを収めることができ、ブランドガイドラインや特定のプリンター要件にも合わせられます。

### アスペクト比をカスタマイズする手順
1. `EncodeTypes.Aztec` を使用して `BarcodeGenerator` インスタンスを作成します。  
2. データ（テキスト、バイト、または数値文字列）を割り当てます。  
3. `AspectRatio` を設定します – 例として、幅を広くする場合は `1.5` を使用します。  
4. `Save` または `GetBarCodeImage` を使用して画像を生成します。  

## Aztec バーコードに生バイトをエンコードする方法
`EncodeBytes` はバイト配列を受け取り、Aztec マトリックスに変換するメソッドです。バイト配列を `BarcodeGenerator` の `EncodeBytes` メソッドに渡します。API はバイナリデータを自動的にコンパクトな Aztec マトリックスに変換し、すべてのビットを保持します。暗号化ペイロードやバイナリ識別子、圧縮ファイルなどをバーコードに直接埋め込むのに最適です。

### バイトをエンコードする手順
1. バイト配列を用意します（例: `byte[] data = Encoding.UTF8.GetBytes("Hello")`）。  
2. `EncodeTypes.Aztec` を使用して `BarcodeGenerator` をインスタンス化します。  
3. `EncodeBytes(data)` を呼び出してバイナリコンテンツをロードします。  
4. `Save` または `GetBarCodeImage` でバーコードを描画します。  

## Aztec バーコードにテキストをエンコードする方法
`CodeText` はエンコードするプレーンテキストデータを保持するプロパティです。`BarcodeGenerator` の `CodeText` プロパティにプレーンテキストデータを設定します。ライブラリは自動的に最適なエンコードモード（数値、英数字、バイト）を選択し、適切なエラー訂正レベルを適用します。これにより、URL、製品 ID、任意の可読文字列を簡単に埋め込むことができます。

### テキストをエンコードする手順
1. `EncodeTypes.Aztec` でジェネレータを作成します。  
2. エンコードしたい文字列を `CodeText` に設定します。  
3. 必要に応じて `ErrorLevel` を調整し、耐久性を高めます。  
4. `Save` または `GetBarCodeImage` を使用して画像を生成します。  

## 異なるエラー訂正レベルで Aztec バーコードを生成する方法
`ErrorLevel` はバーコードに追加される冗長データ量を制御するプロパティです。描画前に `ErrorLevel` プロパティ（0‑4）を調整します。レベルが高いほど冗長データが増え、シンボルの最大 30 % が損傷していても読み取れるようになります。産業用ラベリングや屋外サイネージなど過酷な環境での使用に不可欠です。

### エラー訂正を設定する手順
1. Aztec 用に `BarcodeGenerator` をインスタンス化します。  
2. データ（テキストまたはバイト）を割り当てます。  
3. `ErrorLevel` を設定します – 例: `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`。  
4. 好みの出力形式でバーコードを描画します。  

## Aztec シンボルモードの種類と使用方法
`SymbolMode` は生成される Aztec コードのマトリックスサイズとデータ容量を決定する設定です。ライブラリは 4 つのモードを提供します：**Auto**、**FullRange**、**Compact**、**Rune**。

- **Auto** – ジェネレータが可能な限り最小のサイズを自動選択します。  
- **FullRange** – 非常に大きなデータセット向けに最大マトリックスサイズを許可します。  
- **Compact** – 限られたスペースに最適な、より小さく密度の高いシンボルを作成します。  
- **Rune** – Unicode ルーンをエンコードするための特殊モードです。  

`Generator.Parameters.Barcode.Aztec.SymbolMode` でモードを選択します。各モードはサイズ、可読性、データ容量のバランスを取り、アプリケーションの制約に合わせてバーコードを調整できます。

## Aztec バーコードエンコーディングチュートリアル
以下は、上記の各トピックをさらに詳しく解説するステップバイステップのガイドです。リンクをクリックすると、完全なコードサンプル、前提条件、ベストプラクティスのヒントをご覧いただけます。

### [Aztec バーコードのアスペクト比をカスタマイズ](./aztec-aspect-ratio-customization/)
Aspose.BarCode for .NET を使用して Aztec バーコードのアスペクト比をカスタマイズする方法を学びます。 .NET アプリケーション向けにユニークで柔軟なバーコードを作成できます。

### [Aztec バイトエンコーディング](./aztec-bytes-encoding/)
Aspose.BarCode for .NET を使用した Aztec バイトエンコーディングの実装方法を学びます。ステップバイステップのガイド、前提条件、コード例が含まれています。

### [Aztec コードテキストエンコーディング](./aztec-code-text-encoding/)
Aspose.BarCode for .NET による Aztec コードテキストエンコーディングの活用方法を発見します。 .NET アプリケーションで Aztec コードを作成および認識する方法を学べます。

### [Aztec エラーバーコードの生成](./aztec-error-level-example/)
Aspose.BarCode for .NET を使用して、異なるエラーレベルの Aztec エラーバーコードを生成する方法を学びます。バーコード作成に関する包括的なガイドです。

### [Aztec シンボルモードのマスター](./aztec-symbol-mode-example/)
Aspose.BarCode for .NET の Aztec シンボルモードを探求し、さまざまなバーコードを簡単に生成する方法を学びます。この包括的なチュートリアルで Auto、FullRange、Compact、Rune モードを実践的に体験できます。

## よくある質問

**Q: Aspose.BarCode の Aztec エンコーディングはどの .NET バージョンをサポートしていますか？**  
A: ライブラリは .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5、.NET 6 以降で動作します。

**Q: 印刷用に高解像度の Aztec バーコードを作成できますか？**  
A: はい、画像を保存する前に `Resolution` プロパティ（例: 300 dpi）を設定すれば、印刷用の高品質が得られます。

**Q: Aztec バーコードはどれくらいのデータ量を保持できますか？**  
A: 最大で 3,000 桁の数字または 2,300 桁の英数字、Compact モードでは約 1,800 バイトの生データを保持できます。

**Q: 回転した Aztec バーコードを読み取ることは可能ですか？**  
A: もちろんです。Aspose.BarCode のデコーダは自動的に向きを検出し、読み取り時に補正します。

**Q: 開発およびテスト用にライセンスは必要ですか？**  
A: テスト用には無料の評価ライセンスが利用可能ですが、本番環境での展開には商用ライセンスが必要です。

**最終更新日:** 2026-05-19  
**テスト環境:** Aspose.BarCode 24.12 for .NET  
**作者:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 関連チュートリアル

- [Aspose.BarCode for .NET を使用してカスタムアスペクト比の Aztec バーコードを生成する方法](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Aztec バイトエンコーディング（barcode generator .net 使用）](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [.NET でエラー訂正付き Aztec バーコードを作成する方法](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}