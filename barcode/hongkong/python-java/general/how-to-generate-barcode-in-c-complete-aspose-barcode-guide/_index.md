---
category: general
date: 2026-07-21
description: 如何使用 Aspose.BarCode for C# 快速產生條碼。學習使用 Aspose 建立條碼、調整長寬比，並在數分鐘內儲存 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
- Aspose.BarCode example
- DataBar stacked omnidirectional
- barcode aspect ratio C#
language: zh-hant
lastmod: 2026-07-21
og_description: 如何使用 Aspose.BarCode for C# 生成條碼。本分步指南將向您展示如何使用 Aspose 建立條碼、調整設定以及匯出圖像。
og_image_alt: Screenshot of generated DataBar barcode showing different aspect ratios
og_title: 如何在 C# 中生成條碼 – 快速 Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to generate barcode quickly using Aspose.BarCode for C#. Learn
    to create barcode with Aspose, adjust aspect ratios, and save PNGs in minutes.
  headline: How to Generate Barcode in C# – Complete Aspose.BarCode Guide
  type: TechArticle
tags:
- barcode
- Aspose
- C#
- DataBar
title: 如何在 C# 中產生條碼 – 完整 Aspose.BarCode 指南
url: /zh-hant/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生條碼 – 完整 Aspose.BarCode 指南

有沒有想過在 .NET 應用程式中**產生條碼**而不必與低階影像程式碼糾纏？你並非唯一有此疑問的人。在許多企業專案中，我們需要**使用 Aspose 建立條碼**以供發票、運送標籤或庫存追蹤，而這個函式庫讓這個過程出奇地簡單。

在本教學中，我們將逐步示範一個實務範例，建立 DataBar Stacked Omnidirectional 條碼、調整其長寬比，並儲存兩個 PNG 檔案。完成後，你將擁有一個可直接執行的主控台程式，並清楚了解可控制的關鍵屬性。

## 你將學會

- 在 C# 專案中設定 Aspose.BarCode（NuGet、授權基礎）
- 初始化 **DataBar stacked omnidirectional** 產生器
- 調整 X‑dimension（像素大小）與長寬比
- 將條碼儲存為 PNG 圖片
- 將範例延伸至其他條碼類型或輸出格式

不需要任何 Aspose 的先前經驗——只要有可運作的 .NET 6（或更新）SDK 以及你喜愛的 IDE 即可。

## 前置條件

| Requirement | Reason |
|-------------|--------|
| .NET 6 SDK 或更新版本 | 現代語言功能與簡易的專案建立 |
| Visual Studio 2022（或 VS Code） | 用於建置與除錯的 IDE |
| Aspose.BarCode for .NET NuGet 套件 | 執行核心功能的主要函式庫 |
| 有效的 Aspose 授權（或評估版） | 移除評估水印並解鎖全部功能 |

如果尚未安裝 NuGet 套件，請執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

現在環境已備妥，讓我們深入程式碼吧。

## 步驟 1：建立新 Console 專案

首先，建立一個全新的 console 應用程式。開啟終端機並輸入以下指令：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

此指令會產生 `Program.cs` 與 `.csproj` 檔案。於編輯器中開啟專案，並依上述方式加入 Aspose 參考。

## 步驟 2：初始化 BarcodeGenerator

此流程的核心是 `BarcodeGenerator` 類別。我們將指定 **DataBar stacked omnidirectional** 符號，並提供一個範例 GS1‑128 字串。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Choose the barcode type and data
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1-128 example

        // Step 2.2: Set the X‑dimension (pixel size) – controls overall size
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Continue with aspect ratio adjustments...
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        // Placeholder for the rest of the steps
    }
}
```

**為什麼這很重要：** `EncodeTypes.DatabarStackedOmniDirectional` 產生緊湊且高密度的條碼，非常適合小尺寸標籤。資料字串遵循 GS1 應用識別碼 `(01)`，代表 GTIN‑14 值，這是許多供應鏈系統所期待的。

## 步驟 3：調整長寬比並儲存影像

Aspose.BarCode 允許你透過 `Parameters.Barcode.DataBar.AspectRatio` 調整 DataBar 符號的**長寬比**。變更此數值會改變寬高比例，對於將條碼放入固定尺寸的標籤中可能相當關鍵。

```csharp
static void GenerateBarcodes(BarcodeGenerator generator)
{
    string outputPath = "GeneratedBarcodes/"; // Ensure this folder exists
    System.IO.Directory.CreateDirectory(outputPath);

    // ---------- First image: Aspect Ratio 15 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 15;
    string file15 = $"{outputPath}DatabarAspectRatio15.png";
    generator.Save(file15, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

    // ---------- Second image: Aspect Ratio 30 ----------
    generator.Parameters.Barcode.DataBar.AspectRatio = 30;
    string file30 = $"{outputPath}DatabarAspectRatio30.png";
    generator.Save(file30, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
}
```

**每行說明**

- `outputPath` 指向 PNG 檔案將要儲存的資料夾。`Directory.CreateDirectory` 可確保即使在全新機器上也會建立該資料夾。
- `AspectRatio = 15` 產生相對較高的條碼；`AspectRatio = 30` 則水平拉伸。
- `generator.Save(...)` 將影像寫入磁碟。`BarCodeImageFormat.Png` 列舉確保無損品質。
- `Console.WriteLine` 在執行程式時提供即時回饋。

### 預期輸出

執行 `dotnet run` 後，應會看到類似以下的輸出：

```
Saved barcode with aspect ratio 15 to GeneratedBarcodes/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 to GeneratedBarcodes/DatabarAspectRatio30.png
```

開啟兩個 PNG 檔案並排比較；你會發現第二張影像在保持相同高度的同時明顯更寬。兩張影像皆可被標準條碼讀取器掃描。

## 步驟 4：執行完整範例

以下提供**完整且可執行的原始碼**，以單一區塊方便複製貼上：

```csharp
// Program.cs
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Initialise generator with DataBar stacked omnidirectional symbology
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Set pixel size of the X‑dimension (controls overall size)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Generate two barcodes with different aspect ratios
        GenerateBarcodes(generator);
    }

    static void GenerateBarcodes(BarcodeGenerator generator)
    {
        string outputPath = "GeneratedBarcodes/";
        Directory.CreateDirectory(outputPath);

        // Aspect Ratio 15
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        string file15 = Path.Combine(outputPath, "DatabarAspectRatio15.png");
        generator.Save(file15, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 15 to {file15}");

        // Aspect Ratio 30
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        string file30 = Path.Combine(outputPath, "DatabarAspectRatio30.png");
        generator.Save(file30, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with aspect ratio 30 to {file30}");
    }
}
```

編譯並執行：

```bash
dotnet run
```

完成——兩個完美渲染的條碼 PNG 會出現在 `GeneratedBarcodes/` 資料夾中。

## 步驟 5：延伸範例（可選）

既然你已**了解如何使用 Aspose 產生條碼**，或許會想：*還能調整什麼？* 以下提供幾個快速想法：

| Property | What it does | Typical use‑case |
|----------|--------------|------------------|
| `generator.Parameters.Barcode.CodeTextParameters.Font.Size` | 變更可讀文字的字型大小 | 手持掃描器需要較大字體 |
| `generator.Parameters.Barcode.ImageFormat` | 全域輸出格式（PNG、JPEG、BMP 等） | 網頁友好尺寸的 JPEG |
| `generator.Parameters.Barcode.Color` | 設定前景顏色 | 以顏色區分類別 |
| `generator.Save(..., BarCodeImageFormat.Svg)` | 向量輸出，可無限縮放 | 可直接列印的 PDF |

若要試驗，只需在每個 `Save` 呼叫之前加入相應的程式碼行即可。

## 常見陷阱與專業提示

- **授權檔案位置：** 若使用付費授權，請在建立產生器之前呼叫 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`。若遺漏此步驟，影像上會出現水印。
- **資料字串無效：** DataBar 符號需要數字型 GS1 資料。提供字母字元會拋出 `ArgumentException`。
- **執行緒安全性：** `BarcodeGenerator` 實例**不**具備執行緒安全性。若在平行產生條碼，請為每個執行緒建立新實例。
- **影像大小與掃描器能力：** 設定過高的 `XDimension.Pixels` 會產生過大的影像，部分掃描器可能無法讀取。請以目標硬體進行測試。

## 結論

我們剛剛介紹了在 C# 中使用 Aspose.BarCode **產生條碼**的完整流程，從專案設定到以不同長寬比儲存兩張影像。關鍵步驟——初始化產生器、設定 X‑dimension 與長寬比，並呼叫 `Save`——構成一個可重複使用的模式，適用於 Aspose 支援的任何條碼類型。

現在你可以為發票、運送標籤或庫存標籤**使用 Aspose 建立條碼**，並且具備了探索更進階功能（如顏色、客製字型或 SVG 輸出）的堅實基礎。隨意調整程式碼、嘗試其他 `EncodeTypes`，並將產生器整合至現有服務中吧。

有任何問題或想看到特定條碼樣式嗎？在下方留下評論，我們祝你寫程式愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何自訂條碼 - 使用 Aspose.BarCode for .NET 調整 Codablock F 長寬比](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼（ECC 200）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}