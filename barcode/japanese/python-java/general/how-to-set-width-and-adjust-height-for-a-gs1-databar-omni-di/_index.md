---
category: general
date: 2026-09-29
description: C# を使用して GS1 DataBar Omni‑Directional バーコードの幅を設定し、高さを変更する方法。フルコード付きのステップバイステップガイドをご覧ください。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set width
- how to change height
language: ja
lastmod: 2026-09-29
og_description: C#でGS1 DataBar Omni‑Directionalバーコードの幅を設定し、高さを変更する方法。正確なAPI呼び出しを学び、完全に実行可能なサンプルを確認できます。
og_image_alt: Screenshot of two GS1 DataBar barcodes with different heights
og_title: GS1 DataBar バーコードの幅の設定方法 – C# ガイド
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  headline: How to set width and adjust height for a GS1 DataBar Omni‑Directional
    barcode in C#
  type: TechArticle
- description: How to set width of a GS1 DataBar Omni‑Directional barcode and how
    to change height using C#. Follow a step‑by‑step guide with full code.
  name: How to set width and adjust height for a GS1 DataBar Omni‑Directional barcode
    in C#
  steps:
  - name: Why the X‑dimension matters
    text: '* **Scanner tolerance** – Most scanners expect a minimum module width;
      too small a value can cause read errors. * **Print resolution** – When printing
      at 300 dpi, a 2 px module translates to ~0.17 mm, which is within the recommended
      range for GS1 DataBar. * **Image size** – Larger X‑dimension values'
  - name: Tips for reliable width settings
    text: '* **Never set XDimension below 1 px** – the library will clamp the value,
      but the resulting barcode may be unreadable. * **Match the target DPI** – if
      you render to a high‑resolution format (e.g., TIFF at 600 dpi), increase XDimension
      proportionally. * **Test with a real scanner** – after changing t'
  - name: Understanding bar height
    text: '* **Visual balance** – Taller bars improve readability on low‑contrast
      backgrounds but increase the image’s vertical footprint. * **Regulatory limits**
      – Some standards (e.g., retail labeling) specify a maximum bar height; adjust
      accordingly. * **Aspect ratio** – Changing height does not affect the '
  - name: Edge‑case handling for height adjustments
    text: '| Situation | Recommended approach | |-----------|----------------------|
      | Height < 10 px | Increase to at least 10 px; very short bars may be ignored
      by scanners. | | Very tall bars (≥ 100 px) | Verify that the output medium (paper,
      label) can accommodate the extra space. | | Need proportional sca'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
- GS1 DataBar
title: C#でGS1 DataBar Omni‑Directionalバーコードの幅を設定し高さを調整する方法
url: /ja/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# で GS1 DataBar Omni‑Directional バーコードの幅を設定し高さを調整する方法

GS1 DataBar Omni‑Directional バーコードの幅を設定することは、スキャン機器に合わせて正確なサイズが必要な場合に頻繁に行われる作業です。このチュートリアルでは、バーコードをレイアウトにぴったり合わせるための **高さの変更方法** も学びます。ガイドでは、プロジェクトのセットアップから完全に実行可能なコードサンプルまで、全工程を順に説明します。

## カバーする内容

* 必要な NuGet パッケージと .NET バージョン。
* バーコードの可読性に影響する X‑dimension（モジュール幅）の重要性。
* **幅の設定方法** と **高さの変更方法** の正確な API 呼び出し。
* 最小モジュール幅や高解像度レンダリングなどのエッジケース処理。
* 異なるバー高さの PNG ファイルを 2 つ生成する、コピー＆ペースト可能な完全例。

## 前提条件

| Requirement | Reason |
|------------|--------|
| .NET 6.0 SDK 以降 | この例は最新の C# 機能を使用し、Windows、Linux、macOS 上で動作します。 |
| Visual Studio 2022（または任意の C# IDE） | Aspose.Barcode API の IntelliSense を提供します。 |
| **Aspose.Barcode for .NET** NuGet パッケージ | `BarcodeGenerator`、`EncodeTypes`、画像フォーマットのサポートが含まれます。`dotnet add package Aspose.Barcode` でインストールします。 |
| PNG ファイルを保存するフォルダーへの書き込み権限 | ジェネレータは出力画像をディスクに書き込みます。 |

## バーコードの幅を設定する方法

**幅の設定方法** のステップは、バーコードパラメータの `XDimension` プロパティを構成することで実行します。`XDimension` はモジュール幅（最小のバーまたはスペース）をピクセル、ポイント、またはミリメートルで表します。正しく設定することで、バーコードがスキャナの仕様を満たすようになります。

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a generator for a GS1 DataBar Omni‑Directional barcode.
            // The value "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ **How to set width**: define the module width (X‑dimension) in pixels.
            // A value of 2 px is a common choice that balances readability and image size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // The remaining steps (height, saving) are shown in the next section.
```

### X‑dimension が重要な理由

* **スキャナ許容範囲** – ほとんどのスキャナは最小モジュール幅を要求します。値が小さすぎると読み取りエラーが発生します。  
* **印刷解像度** – 300 dpi で印刷する場合、2 px のモジュールは約 0.17 mm に相当し、GS1 DataBar の推奨範囲内です。  
* **画像サイズ** – X‑dimension の値が大きいほど全体のバーコード幅が増加し、レイアウト制約に影響します。

### 幅設定を確実に行うためのヒント

* **XDimension を 1 px 未満に設定しない** – ライブラリは値をクランプしますが、結果のバーコードは読めない可能性があります。  
* **対象 DPI に合わせる** – 高解像度形式（例: 600 dpi の TIFF）でレンダリングする場合は、XDimension を比例して増やします。  
* **実機スキャナでテスト** – 幅を変更したら、実際に読み取るデバイスでバーコードを検証します。

## バーコードの高さを変更する方法

幅が定義されたら、`BarHeight` プロパティで垂直サイズを制御できます。以下のコードは **高さの変更方法** を 30 px から 60 px に変更し、2 つの別々の画像として保存する例です。

```csharp
            // 3️⃣ Set the first bar height to 30 pixels and save the image.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 4️⃣ **How to change height**: increase the bar height to 60 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            // The program ends here; two PNG files are written to the execution folder.
        }
    }
}
```

### バー高さの理解

* **視覚的バランス** – 高いバーは低コントラスト背景での可読性を向上させますが、画像の縦方向の占有領域が増えます。  
* **規制上限** – 小売ラベリングなど、一部の規格では最大バー高さが定められています。必要に応じて調整してください。  
* **アスペクト比** – 高さを変更してもモジュール幅には影響しません。両方を独立して微調整できます。

### 高さ調整時のエッジケース処理

| Situation | Recommended approach |
|-----------|----------------------|
| 高さ < 10 px | 少なくとも 10 px に増やすことを推奨します。非常に短いバーはスキャナに無視される可能性があります。 |
| 非常に高いバー（≥ 100 px） | 出力媒体（紙、ラベル）が余分なスペースを確保できるか確認してください。 |
| 比例スケーリングが必要 | `BarHeight = XDimension * desiredRatio` のように計算し、視覚的な一貫性を保ちます。 |

## 完全な実行可能サンプル

以下は **幅の設定方法** と **高さの変更方法** を組み合わせた完全プログラムです。コードを新しいコンソールプロジェクトに貼り付け、Aspose.Barcode NuGet パッケージを復元して実行してください。`bin/Debug/net6.0` フォルダーに 2 つの PNG ファイルが生成されます。

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // Initialize the barcode generator (GS1 DataBar Omni‑Directional)
            // ------------------------------------------------------------
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // ------------------------------------------------------------
            // **How to set width** – define the module width (X‑dimension)
            // ------------------------------------------------------------
            generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px = ~0.17 mm at 300 dpi

            // ------------------------------------------------------------
            // First image: bar height = 30 px
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight30Pixels.png");

            // ------------------------------------------------------------
            // **How to change height** – increase to 60 px and save again
            // ------------------------------------------------------------
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: DatabarBarHeight60Pixels.png");

            // ------------------------------------------------------------
            // End of demo
            // ------------------------------------------------------------
        }
    }
}
```

**期待される出力**

プログラムを実行すると、次の 2 つの PNG ファイルが生成されます。

* `DatabarBarHeight30Pixels.png` – 高さ 30 px、モジュール幅 2 px のバーコード。  
* `DatabarBarHeight60Pixels.png` – 同じバーコードの高さを倍にしたもの。

任意のビューアで画像を開くと、スキャン準備が整ったクリーンな GS1 DataBar Omni‑Directional シンボルが確認できます。

## よくある質問と回答

| Question | Answer |
|----------|--------|
| *Can I use millimetres instead of pixels?* | はい。`generator.Parameters.Barcode.XDimension.Millimeters` と `BarHeight.Millimeters` を設定します。ライブラリは画像の DPI に基づいてデバイスピクセルに変換します。 |
| *What if I need a different barcode type?* | `EncodeTypes.DatabarOmniDirectional` を他の `EncodeTypes` 値（例: `EncodeTypes.QR`）に置き換えます。幅と高さのプロパティは同様に機能します。 |
| *Is there a way to generate SVG instead of PNG?* | `Save` 呼び出しで `BarCodeImageFormat.Svg` を使用します。幅/高さ設定は引き続き適用されます。 |
| *Do I need to call `generator.Dispose()`?* | `BarcodeGenerator` は `IDisposable` を実装しています。コンソールアプリでは `using` ブロックでラップすると安全ですが、短時間のサンプルでは省略可能です。 |

## 結論

これで **幅の設定方法** と **高さの変更方法** を Aspose.Barcode API を使用して C# で実装できました。完全な例では、ジェネレータの作成、`XDimension` と `BarHeight` の設定、そして異なる垂直サイズの PNG ファイルの保存手順を示しています。

ここからは次のことが可能です。

* 他の `EncodeTypes`（例: QR、Code128）を試す。  
* 印刷向けに TIFF など高解像度形式でレンダリングする。  
* バーコードジェネレータを Web API に組み込み、リアルタイムでバーコードを返す。

Happy coding, and may your barcodes always scan cleanly!

## 次に学ぶべきことは？

以下のチュートリアルは、本ガイドで示した手法を応用した関連トピックを扱っています。各リソースには、完全な動作コード例とステップバイステップの解説が含まれており、API の追加機能を習得したり、プロジェクトで代替実装アプローチを探求したりするのに役立ちます。

- [C# でバーコードの高さを変更する方法 – 完全ガイド](/barcode/english/python-java/general/how-to-change-barcode-height-in-c-complete-guide/)
- [C# のバーコードジェネレータ例 – 幅と高さの設定](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [C# でバーコードジェネレータを使用して DataBar Omni‑directional バーコードを作成する方法](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}