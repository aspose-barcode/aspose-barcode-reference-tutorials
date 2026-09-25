---
category: general
date: 2026-08-22
description: 學習如何在 C# 中產生郵政條碼，並使用條碼產生器 C# 函式庫控制條碼高度、X 尺寸及圖像格式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- barcode generator c#
- barcode x dimension
- barcode image format
- change barcode width
language: zh-hant
lastmod: 2026-08-22
og_description: 使用 C# 產生郵政條碼，完整控制條碼高度、X 尺寸與圖像格式。按照此逐步教學，打造完美的郵政符號。
og_image_alt: Example of a generated postal barcode with custom bar height in C#
og_title: 在 C# 中生成郵政條碼 – 完整指南與自訂尺寸
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to generate postal barcode in C# and control bar height,
    X dimension, and image format using the barcode generator C# library.
  headline: How to generate postal barcode in C# with custom dimensions
  type: TechArticle
tags:
- barcode
- C#
- image processing
title: 如何在 C# 中生成具有自訂尺寸的郵政條碼
url: /zh-hant/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生自訂尺寸的郵政條碼

如果您需要在 C# 中產生郵政條碼，本指南將展示完整的工作流程。您將看到如何控制條碼高度、調整條碼 X 方向尺寸，並選擇適當的條碼影像格式。

郵政條碼被全球郵件服務廣泛使用，可靠的實作必須在不同符號系統間產生一致的尺寸。在本教學中，您將學會使用 **BarcodeGenerator** 類別、變更條碼寬度，並將結果儲存為 PNG、JPEG 或其他支援的格式。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 .NET 6.0 或更新版本  
* 參考 **Aspose.BarCode** NuGet 套件（或任何相容的 C# 條碼產生器函式庫）  
* 具備 C# 語法與 Visual Studio 或您慣用的 IDE 基本知識  

您不需要任何外部服務；程式碼完全在客戶端機器上執行。

## 第一步：設定專案並匯入命名空間

建立一個新的主控台應用程式並加入條碼函式庫。以下 `using` 陳述式可讓您存取產生器與影像格式列舉。

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator, EncodeTypes, etc.
using Aspose.BarCode;               // Contains BarCodeImageFormat
```

`BarcodeGenerator` 類別是條碼產生器 C# API 的核心。它會建立一個物件，保存所有渲染參數。

## 第二步：使用預設尺寸產生基本郵政條碼

第一個範例使用預設條碼高度建立 Planet 條碼。此範例示範產生郵政條碼所需的最小設定。

```csharp
// Create a Planet barcode with the default bar height
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X dimension) to 4 pixels – this defines the narrow bar size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG using the default bar height
barcodeGenerator.Save("PostalPlanetDefault.png", BarCodeImageFormat.Png);
```

*為什麼會這樣*：當您省略 `BarHeight` 屬性時，函式庫會套用所選符號系統的標準高度。`XDimension` 控制 **barcode X dimension**，直接影響符號的總寬度。

## 第三步：變更條碼寬度並提升條碼高度

通常您需要較高的條碼以符合特定郵寄規範。以下程式碼將條碼高度自訂為 100 像素，同時保留相同的 X 方向尺寸。

```csharp
// Re‑use the generator for a custom height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Increase the bar height to 100 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save using the same PNG format
barcodeGenerator.Save("PostalPlanetHeight100.png", BarCodeImageFormat.Png);
```

*為什麼要調整高度*：`BarHeight` 屬性控制每根條的垂直尺寸。對於要求最小高度的郵政服務，設定此值即可符合規範，同時不影響編碼內容。

## 第四步：使用預設設定產生 RM4SCC 條碼

RM4SCC 是另一種常見的郵政符號系統。以下程式碼與 Planet 範例相同，但切換了 `EncodeTypes` 列舉。

```csharp
// Create an RM4SCC barcode with default bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG; default height is applied automatically
barcodeGenerator.Save("PostalRM4SCCDefault.png", BarCodeImageFormat.Png);
```

由於函式庫會自動為 RM4SCC 選擇適當的預設高度，您只需一行程式碼即可取得符合標準的影像。

## 第五步：為 RM4SCC 條碼變更條碼高度

如果郵寄系統要求較高的條碼，您可以像對 Planet 那樣調整高度。

```csharp
// RM4SCC barcode with a custom 100‑pixel bar height
barcodeGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the result; you may also choose JPEG, BMP, or TIFF
barcodeGenerator.Save("PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
```

*小技巧*：**barcode image format** 列舉包含 `Jpeg`、`Bmp`、`Tiff` 與 `Gif`。選擇最符合下游處理流程的格式即可。

## 第六步：探索其他影像格式並微調尺寸

以下是一段精簡程式碼，示範如何切換輸出格式並嘗試不同的 X 方向尺寸。

```csharp
string[] formats = { "Png", "Jpeg", "Bmp", "Tiff" };
int[] xDims = { 2, 3, 4, 5 };

foreach (var fmt in formats)
{
    foreach (var x in xDims)
    {
        barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = x;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 80; // consistent height

        // Dynamically choose the format enum
        BarCodeImageFormat imageFormat = (BarCodeImageFormat)Enum.Parse(
            typeof(BarCodeImageFormat), fmt, true);

        string fileName = $"Planet_X{x}_{fmt}.png";
        barcodeGenerator.Save(fileName, imageFormat);
    }
}
```

*為什麼要迭代*：此迴圈會產生一組影像矩陣，說明 **change barcode width**（透過 X dimension）如何影響整體外觀。它同時展示同一產生器可在不額外程式碼變更的情況下輸出多種 **barcode image format** 類型。

## 常見陷阱與避免方式

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 條紋過細 | X dimension 設為 1 像素或更小 | 將 `XDimension.Pixels` 設為至少 2，以確保可讀性 |
| 影像模糊 | 以高壓縮率儲存為 JPEG | 使用 `BarCodeImageFormat.Png` 取得無損輸出 |
| 列印尺寸異常 | 未考慮 DPI | 若印表機要求特定 DPI，請設定 `barcodeGenerator.Parameters.ImageResolution.Dpi` |
| 符號系統錯誤 | 為 RM4SCC 資料使用 `EncodeTypes.Planet` | 選擇符合郵政服務規範的正確 `EncodeTypes` 值 |

## 驗證輸出

執行程式後，開啟任一產生的 PNG 檔案。您應該會看到一個清晰、矩形的條碼，垂直條紋高度與您設定的值（例如 100 像素）相符，總寬度則反映您配置的 **barcode X dimension**。

若需在網頁中嵌入影像，PNG 格式可直接在瀏覽器顯示。若要在 PDF 報告中使用，可將 PNG 轉換為位元組陣列，並透過 PDF 函式庫插入。

## 完整範例 – 一個程式內完成所有步驟

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Directory for output files
        const string outDir = @"C:\Barcodes\";

        // 1. Planet barcode – default height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, null, "PlanetDefault.png");

        // 2. Planet barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.Planet, "123456", 4, 100, "PlanetHeight100.png");

        // 3. RM4SCC barcode – default height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, null, "RM4SCCDefault.png");

        // 4. RM4SCC barcode – custom height
        GenerateBarcode(outDir, EncodeTypes.RM4SCC, "123456", 4, 100, "RM4SCCHeight100.png");
    }

    /// <summary>
    /// Creates a barcode image with optional custom height.
    /// </summary>
    static void GenerateBarcode(string folder, EncodeTypes type, string data,
                                int xDim, int? barHeight, string fileName)
    {
        var generator = new BarcodeGenerator(type, data);
        generator.Parameters.Barcode.XDimension.Pixels = xDim;

        if (barHeight.HasValue)
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight.Value;

        generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
    }
}
```

執行此程式會在 `C:\Barcodes\` 產生四個 PNG 檔案。每個檔案示範不同的 **generate postal barcode**、**barcode X dimension** 與 **barcode image format** 組合。

## 結論

現在您已掌握如何在 C# 中產生郵政條碼，並完整控制條碼高度、模組寬度與輸出格式。透過調整 **barcode X dimension** 並使用適當的 **barcode image format**，即可符合任何郵寄規格，並將條碼整合至桌面、網頁或行動應用程式中。

接下來，您可以探索進階功能，例如加入可讀文字、套用顏色調色盤，或將條碼嵌入 PDF 文件。這些主題仍然基於您剛剛掌握的 **barcode generator C#** 概念，讓您能自信地擴展此基礎。

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能並探索其他實作方式。

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – Code 93 with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}