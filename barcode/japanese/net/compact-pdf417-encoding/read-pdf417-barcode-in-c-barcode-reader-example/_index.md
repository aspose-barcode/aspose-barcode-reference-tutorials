---
category: general
date: 2026-10-14
description: C#で console barcode scanner を作成し、PDF417 バーコードを読み取り、macro PDF417 に対応し、1枚の画像から複数のバーコードをデコードします。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create console barcode scanner
- read barcodes from picture
- c# barcode reader example
lastmod: 2026-10-14
og_description: C#で console barcode scanner を作成し、画像から PDF417 および macro PDF417 バーコードを迅速に読み取ります。このステップバイステップガイドでは、1枚の画像で複数のバーコードをデコードする方法を示します。
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: C#で console barcode scanner を作成 – 完全ガイド
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  headline: Create console barcode scanner in C# – barcode reader example
  type: TechArticle
- description: Create a console barcode scanner in C# that reads PDF417 barcodes,
    handles macro PDF417, and decodes multiple barcodes from a single image.
  name: Create console barcode scanner in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
- console application
title: C#で console barcode scanner を作成 – PDF417 バーコード読み取り例
url: /ja/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# でコンソールバーコードスキャナーを作成 – PDF417 バーコードの読み取り例

`BarCodeReader` は Aspose.BarCode のコアクラスで、画像からバーコードをデコードし、詳細なメタデータを返します。画像から PDF417 バーコードデータを読み取る必要がある場合、このガイドでは C# の **BarCodeReader** クラスを使用する方法を示します。**コンソールバーコードスキャナーの作成** の例を学び、マクロ PDF417 を処理し、単一画像内の複数バーコードを読み取ることができます。

バーコードを扱う際は、さまざまな画像ソースや照明条件、場合によってはマクロ PDF417 セグメントなどの複合データに対応する必要があります。このチュートリアルでは、PDF417 バーコードをデコードし、拡張フィールドを抽出し、同じ画像から複数のバーコードを処理するために必要なすべてをカバーします。最後まで実行すれば、画像ファイルからバーコードを読み取り、コンソールに詳細情報を出力する実行可能なコンソールプログラムが手に入ります。

## クイック回答
- **例は何をしますか？** 画像から PDF417 およびマクロ PDF417 バーコードを読み取り、すべてのデコードされたフィールドを出力するコンソールバーコードスキャナーを作成します。  
- **どのライブラリが必要ですか？** Aspose.BarCode for .NET (NuGet)。  
- **複数のバーコードを同時に読み取れますか？** はい – リーダーは画像内で検出されたすべてのバーコードを順に処理します。  
- **インターネット接続は必要ですか？** いいえ、ライブラリは完全にオフラインで動作します。  
- **サポートされている .NET バージョンは？** .NET 6.0 以降。

## 必要なもの

* .NET 6.0 SDK 以降がインストールされていること  
* **Aspose.BarCode for .NET** の最新バージョンの NuGet パッケージ（または `BarCodeReader` と `DecodeType.MacroPdf417` を提供する互換ライブラリ）  
* PDF417 またはマクロ PDF417 バーコードを含む画像ファイル（サンプルは `ExtPDF417Meta.png` を使用）  
* Visual Studio 2022 などのコードエディタまたは IDE  

追加のサービスや外部 API は不要です。

## バーコード読み取り用プロジェクトの設定

1. **新しいコンソールプロジェクトを作成する**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **バーコードライブラリを追加する**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **バーコード画像をコピーする**  

   `ExtPDF417Meta.png`（または PDF417 バーコードを含む任意の画像）をプロジェクトフォルダーに配置します。  
   本チュートリアルではファイルが `YOUR_DIRECTORY/ExtPDF417Meta.png` にあると想定しています。

プロジェクトはこれでコンパイルと実行の準備が整いました。

## C# でコンソールバーコードスキャナーを作成する方法

`BarCodeReader` は Aspose.BarCode が提供するクラスで、画像からバーコードを読み取り、デコードされたデータを返します。  
`BarCodeReader` で画像を読み込み、デコードタイプを `MacroPdf417` に設定し、結果を反復処理するだけでコンソールバーコードスキャナーを作成できます。`using` 文のおかげでリーダーはネイティブリソースを自動的に解放するため、メモリ管理を手動で行う必要はありません。このアプローチは PNG、JPEG、BMP など .NET がサポートするすべての画像形式で動作します。

### 手順ごとのウォークスルー

ソリューションの核心は、`using` ブロックで `BarCodeReader` インスタンスを作成し、`DecodeType.MacroPdf417` を指定して検出されたすべてのバーコードを反復処理することです。以下のコードは `Program.cs` に貼り付けて使用できる、完全かつ自己完結型のプログラムです。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**この動作の理由**:  

* `DecodeType.MacroPdf417` はリーダーに PDF417 のマクロ拡張を検索させ、ファイル ID、セグメント数、タイムスタンプなどの追加メタデータを取得できるようにします。  
* `using` 文は、ファイルハンドルやネイティブデコードバッファなどのアンマネージドリソースが速やかに解放されることを保証します。  
* `foreach` ループは画像に含まれる **すべて** のバーコードを自動的に処理し、*複数バーコードの読み取り* 要件を満たします。  

プログラムを実行すると（`dotnet run`）、以下のような出力が表示されます。

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

画像に複数の PDF417 バーコードが含まれている場合、ループは各バーコードごとに別々のブロックを出力し、単一画像から **複数バーコードを読み取る** 方法を実証します。

## 画像から複数のバーコードを読み取る方法

単一の `BarCodeReader` インスタンスを使用し、`DecodeType` フラグに検出したいすべてのフォーマットを含めます。ビット単位の OR 演算子でフラグを組み合わせることで、PDF417、QR、Code‑128 など多数のシンボルを一度に検索させることができます。これにより別々のリーダーを用意する必要がなくなり、処理時間が短縮されます。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

*`DecodeType`* はビットマスクなので、サポートされている任意の数のフォーマットを組み合わせられます。Aspose.BarCode は **30 以上のバーコードシンボル**（QR、DataMatrix、Code‑128、UPC‑A など）をサポートしており、製品ラベリング、チケット検証、身分証明など多様なユースケースに単一スキャナーで対応できます。

## マクロ PDF417 とは何か、そしてそのフィールドに安全にアクセスする方法

マクロ PDF417 は PDF417 シンボルの拡張で、大容量データを複数のバーコードシンボルに分割して格納できるようにします。  
マクロ PDF417 には豊富な拡張プロパティが追加されますが、すべてのバーコードがすべてのフィールドを持つわけではありません。存在しないプロパティにアクセスしようとすると `NullReferenceException` がスローされる可能性があります。安全な方法は、各プロパティを出力する前に null かどうかを確認することで、マクロデータが欠如していてもアプリケーションが安定したまま動作するようにします。

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*このチェックが重要な理由*: 実運用ではマクロデータを含まない普通の PDF417 バーコードが届くことがあります。防御的チェックにより、アプリケーションがクラッシュせずに実行し続けられます。

## よくある落とし穴とベストプラクティス

| 問題 | 発生原因 | 推奨される対策 |
|------|----------|----------------|
| 画像パスが正しくない | `BarCodeReader` がデコード前にファイルが見つからない例外をスローします | `Path.Combine` を使用し、`File.Exists` でファイルの存在を確認してください |
| 低解像度画像 | デコーダがバーコードのエッジを検出できず、検出数がゼロになります | 信頼性のある結果のために最低 300 dpi の解像度を提供してください |
| バーコードが 45° 超で回転している | 多くのライブラリは正立姿勢を前提としています | 画像が回転している可能性がある場合は `reader.RecognitionOptions.RotateImage = true` を有効にしてください |
| マクロフィールドが欠如 | null プロパティを読み取ろうとするとクラッシュします | マクロプロパティにアクセスする前に必ず `null` かどうか確認してください |
| 大量バッチ処理 | 各ファイルごとにリーダーを再作成するとオーバーヘッドが増えます | 多数の画像を処理する際は、異なるストリームで単一の `BarCodeReader` インスタンスを再利用してください |

## コンソールバーコードスキャナーに Aspose.BarCode を使用する理由

Aspose.BarCode は **30 以上のバーコードタイプ** をデコードでき、最大 **200 MP** の画像をメモリ全体にロードせずに処理し、典型的な 3.2 GHz CPU で **150 フレーム/秒** のスループットを実現します。これらの数値化された性能は、レイテンシと精度が重要な高ボリューム・オンプレミスのスキャンソリューションにおいて、信頼できる選択肢となります。

## 次に学ぶべきこと

以下のチュートリアルは、本ガイドで示した手法を基にした、密接に関連するトピックをカバーしています。各リソースには、ステップバイステップの解説付きの完全なコード例が含まれており、追加の API 機能を習得したり、独自プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [Aspose.BarCode for .NET で DataMatrix バーコードを読み取る方法](/barcode/english/net/datamatrix-barcode-reading/)
- [DataMatrix バーコード C# 読み取り – DataMatrix モード（自動）を生成](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [画像からバーコードを読み取る – Aspose.BarCode を使用した Java のバーコード領域抽出マスター](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

## よくある質問

**Q: このスキャナーを本番環境で使用できますか？**  
A: はい。評価用ウォーターマークを除去し、フルサポートを受けるには商用の Aspose.BarCode ライセンスを購入してください。

**Q: ライブラリは Linux と macOS でも動作しますか？**  
A: 完全に対応しています。Aspose.BarCode for .NET はクロスプラットフォームで、Windows、Linux、macOS 上の .NET 6+ で動作します。

**Q: 非常に大きな画像をメモリ不足なく処理するには？**  
A: `LoadOptions` コンストラクタでストリーミングモードを有効にし、画像をチャンク単位で処理することで RAM への全体ロードを回避できます。

**Q: 暗号化またはパスワード保護された画像をデコードできますか？**  
A: 標準的な PNG/JPEG のパスワード方式で暗号化された画像を処理できます。`reader.ImagePassword` にパスワードを渡すだけです。

**Q: バーコードが部分的に損傷している場合は？**  
A: `reader.RecognitionOptions.CorrectErrors = true` などのエラー訂正オプションを有効にすると、損傷やノイズに対する耐性が向上します。

**最終更新日:** 2026-10-14  
**テスト環境:** Aspose.BarCode 24.11 for .NET  
**作者:** Aspose

## 関連チュートリアル

- [C で Pdf417 を読む方法 – 完全なバーコードリーダー例](/barcode/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [Pdf417 を使用した C の複数バーコード読み取り完全ガイド](/barcode/net/compact-pdf417-encoding/read-multiple-barcodes-c-complete-guide-with-pdf417/)
- [画像からバーコードをデコード – C バーコードリーダー例](/barcode/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}