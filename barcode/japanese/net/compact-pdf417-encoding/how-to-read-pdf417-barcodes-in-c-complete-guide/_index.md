---
category: general
date: 2026-08-22
description: C#でPDF417バーコードを読み取る方法：ステップバイステップのガイドで、画像から複数のバーコードを読み取る方法とMacroPdf417の詳細を抽出する方法をカバーしています。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: ja
lastmod: 2026-08-22
og_description: C#でPDF417バーコードを素早く読み取る方法。このチュートリアルでは、画像から複数のバーコードを読み取り、MacroPdf417の拡張情報を取得する方法を紹介します。
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: C#でPDF417バーコードを読み取る方法 – 完全なプログラミングウォークスルー
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: C#でPDF417バーコードを読み取る方法 – 完全ガイド
url: /ja/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で PDF417 バーコードを読む方法 – 完全ガイド

.NET アプリケーションで **PDF417 の読み取り方法** が必要な場合、このチュートリアルはすぐに実行できるソリューションを提供します。単一画像から複数のバーコードを読み取り、完全な MacroPdf417 データセットを抽出し、コンソールに表示する方法を学びます。このアプローチは Aspose.BarCode for .NET ライブラリで動作し、数行のコードだけで実装できます。

画像からバーコードを読み取ることは、在庫管理システム、チケット検証、文書管理などで一般的なタスクです。本ガイドの最後までに、任意の PDF417 または MacroPdf417 バーコードをデコードし、1 枚の画像内の複数コードを処理し、MacroPdf417 が提供する拡張フィールドを理解できるようになります。

## 前提条件

- .NET 6.0 SDK 以上（コードは .NET Framework 4.7+ でもコンパイル可能）
- Visual Studio 2022 またはお好みの C# エディタ
- Aspose.BarCode for .NET NuGet パッケージ（`Install-Package Aspose.BarCode`）
- MacroPdf417 バーコードを含むサンプル画像（例：`MacroPdf417.png`）

追加の設定は不要です。ライブラリが画像の読み込みとデコードを内部で処理します。

## C# で画像から PDF417 バーコードを読む方法

ソリューションの核心は `BarCodeReader` クラスです。画像を開き、指定したタイプのすべてのバーコードを検出し、`BarCodeResult` オブジェクトのコレクションを返します。以下のコードは完全なコンソールプログラムを示しています。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 各行の重要ポイント

| ステップ | 目的 |
|------|---------|
| **1️⃣ Initialize** | 画像ファイルにバインドされた `BarCodeReader` を作成し、検出を MacroPdf417 シンボルに限定することで処理速度を向上させます。 |
| **2️⃣ Iterate** | `ReadBarCodes()` は要求されたタイプに一致する **すべて** のバーコードを返すため、余分なループなしで **複数のバーコードを読み取る** ことができます。 |
| **3️⃣ Basic output** | 汎用的な `CodeTypeName` と人間が読める `CodeText` を表示します。ログ記録や簡易検証に便利です。 |
| **4️⃣ Extended data** | MacroPdf417 は追加メタデータ（ファイル ID、セグメント数、タイムスタンプ等）を保持します。`Extended.Pdf417` オブジェクトは各フィールドを直接公開するので、データパケット全体を保存または検証できます。 |

有効な MacroPdf417 画像に対してプログラムを実行すると、以下のようなコンソール出力が得られます。

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

この出力により、ライブラリがバーコードを正常に読み取り、テキストを抽出し、すべての MacroPdf417 フィールドを提供したことが確認できます。

## 1 枚の画像から複数のバーコードを読む

実際のシナリオでは、1 つのラベルに複数の PDF417 シンボルが配置されることがよくあります。たとえば、運送業者コード、追跡番号、税関申告書が同じラベルに含まれる場合です。上記のコードブロックは既に `ReadBarCodes()` がすべての一致を列挙するため、**複数のバーコードを読み取ります**。追加設定は不要で、結果をループするだけです（例示参照）。

標準の PDF417（マクロなし）に限定しつつ複数コードを処理したい場合は、`DecodeType.MacroPdf417` を `DecodeType.Pdf417` に置き換えてください。残りのロジックは変更不要です。

## MacroPdf417 拡張データの理解

MacroPdf417 は通常の PDF417 仕様の拡張版です。大容量ペイロードを複数のセグメントに分割し、全体ファイルを記述する小さなヘッダーを付加します。主なフィールドは次のとおりです。

- **MacroPdf417FileID** – 同一ファイルのすべてのセグメントで共有される一意の識別子。
- **MacroPdf417SegmentID** – 現在のセグメントのシーケンス番号。
- **MacroPdf417SegmentsCount** – 期待される総セグメント数。
- **MacroPdf417FileName** – バーコードと共に送信されるオプションのファイル名。
- **MacroPdf417Checksum** – 完全ファイルのエラーチェック値。
- **MacroPdf417FileSize** – 元のバイナリペイロードのサイズ。
- **MacroPdf417TimeStamp** – バーコード生成時の ISO‑8601 タイムスタンプ。
- **MacroPdf417Addressee / Sender** – ルーティング用のオプションテキストフィールド。
- **MacroPdf417Terminator** – このセグメントが最終かどうかを示すフラグ。

すべてのセグメントを受け取ったら、`MacroPdf417SegmentID` で順序付けし、`CodeText` の値を連結して元のファイルを再構築できます。必要なフィールドが取得できれば、このロジックは簡単に実装可能です。

## よくある落とし穴とプロのコツ

- **Image quality matters** – 低解像度または過度に圧縮された PNG/JPEG は検出漏れの原因となります。印刷されたバーコードは最低 300 dpi を使用してください。
- **Mixed symbologies** – 画像に MacroPdf417 と通常の PDF417 の両方が含まれる場合は、`DecodeType` ごとにリーダーを 2 つインスタンス化するか、`DecodeType.AllSupported` を使用して `result.CodeTypeName` で結果をフィルタリングします。
- **Memory usage** – `using` 文で `BarCodeReader` を速やかに破棄し、大きな画像バッファがメモリに残らないようにします。
- **Thread safety** – `BarCodeReader` はスレッドセーフではありません。並列で画像をデコードする場合は、スレッドごとに別インスタンスを作成してください。
- **Error handling** – `ReadBarCodes()` 呼び出しを try/catch で囲み、破損画像に対しては `BarCodeException` を捕捉します。

## 完全動作例のまとめ

以下は新しいコンソールプロジェクトにコピーできる完全プログラムです。`using` ディレクティブ、画像パス用定数、破棄パターンをすべて含んでいます。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

`dotnet build` でコンパイルし、`dotnet run` で実行してください。コンソールは各バーコードの基本データと完全な MacroPdf417 ペイロードを出力します。

## 次のステップ

- **Reconstruct multipart files** – すべてのセグメントを収集し、`MacroPdf417SegmentID` でソートして `CodeText` を連結する

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を基にした密接に関連するトピックをカバーしています。各リソースには完全な動作コード例とステップバイステップの解説が含まれており、追加の API 機能を習得し、独自プロジェクトで代替実装アプローチを探求するのに役立ちます。

- [PDF417 バーコードの生成方法 – コンパクト PDF417 エンコーディング](/barcode/english/net/compact-pdf417-encoding/)
- [Java でトルコ文字を含む PDF417 バーコードを読む方法](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Java で Aspose を使用した PDF417 バーコード（中国語）](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}