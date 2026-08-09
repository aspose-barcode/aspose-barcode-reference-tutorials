---
category: general
date: 2026-08-09
description: Generate barcode from text in C# with Aspose.BarCode. Learn how to generate
  barcode, handle special characters, and create PDF417 barcode C# quickly.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode from text
- how to generate barcode
- barcode with special characters
- barcode encode types
- create pdf417 barcode c#
language: zh-hant
lastmod: 2026-08-09
og_description: 使用 Aspose.BarCode 在 C# 中從文字產生條碼。本教學示範如何產生條碼、支援特殊字元，並以完整程式碼建立 PDF417
  條碼（C#）。
og_image_alt: Screenshot of a generated MicroPdf417 barcode saved as PNG
og_title: 使用 C# 從文字生成條碼 – 快速逐步指南
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Generate barcode from text in C# with Aspose.BarCode. Learn how to
    generate barcode, handle special characters, and create PDF417 barcode C# quickly.
  headline: Generate barcode from text in C# – complete step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose
- encoding
title: 在 C# 中從文字產生條碼 – 完整逐步指南
url: /zh-hant/net/compact-pdf417-encoding/generate-barcode-from-text-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 於 C# 產生文字條碼 – 完整步驟指南

如果您需要在 .NET 應用程式中 **從文字產生條碼**，本指南將帶您一步步完成整個流程。您將學會如何產生條碼、處理特殊字元，並建立一個可直接使用的 PDF417 條碼 C# 實作。

從文字產生條碼是庫存系統、票券平台與文件工作流程的常見需求。完成本教學後，您將擁有一個可執行的 C# 主控台應用程式，使用 Aspose.BarCode 產生 MicroPdf417 PNG 圖片。無需外部服務，且程式碼能正確處理如 “Å”、 “©”、 “é” 等 Unicode 字元。

## 前置條件

- .NET 6.0 SDK 或更新版本（程式碼同樣支援 .NET Core 3.1 與 .NET Framework 4.7+）
- Visual Studio 2022（或任何支援 C# 的 IDE）
- **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- 基本的 C# 語法知識

## 從文字產生條碼 – 設定產生器

第一步是建立一個 `BarcodeGenerator` 實例，告訴它您想使用哪種 **條碼編碼類型**。本教學使用 `EncodeTypes.MicroPdf417`，這是 PDF417 的緊湊變種，適合短資料字串。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for MicroPdf417 with the desired text
        // This demonstrates "generate barcode from text" with Unicode characters.
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Continue with configuration (see next sections)
        ConfigureGenerator(generator);
        SaveBarcode(generator);
    }

    // Configuration is split into its own method for clarity.
    static void ConfigureGenerator(BarcodeGenerator generator)
    {
        // Step 2: Define the X dimension of the barcode modules (in pixels)
        // XDimension controls the width of the smallest bar; 2 px gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Step 3: Set the number of columns for the PDF417 layout.
        // Fewer columns produce a taller barcode; 4 columns works well for short strings.
        generator.Parameters.Barcode.Pdf417.Columns = 4;
    }

    static void SaveBarcode(BarcodeGenerator generator)
    {
        // Step 4: Save the generated barcode as a PNG image.
        // You can change BarCodeImageFormat to Jpeg, Gif, etc., if needed.
        string outputPath = Path.Combine(
            Environment.CurrentDirectory,
            "MicroPdf417.png"
        );
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**為什麼這樣寫會有效：**  
- `EncodeTypes.MicroPdf417` 讓函式庫使用 PDF417 系列，滿足 **create pdf417 barcode c#** 的需求。  
- 建構子直接接受原始文字，這正是 **generate barcode from text** 的核心。  
- 內建 Unicode 支援，像 “Å” 與 “©” 之類的字元會正確編碼，解決 **barcode with special characters** 的問題。

## 如何產生含特殊字元的條碼

當資料包含非 ASCII 符號時，必須確保產生器使用 UTF‑8 編碼。Aspose.BarCode 會自動偵測 Unicode，但若遇到問題，可明確設定文字編碼：

```csharp
generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;
```

在呼叫 `ConfigureGenerator` 之前加入此行，可保證 **barcode with special characters** 在任何平台上皆能正確呈現。

### 實用小技巧
如果輸出看起來亂碼，請確認條碼渲染器使用的字型支援所需字形。您可以透過以下方式嵌入自訂 TrueType 字型：

```csharp
generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";
```

## 可選的條碼編碼類型

Aspose.BarCode 支援數十種 **barcode encode types**，每種皆適用於不同情境：

| Encode type                | Typical use case                     |
|----------------------------|--------------------------------------|
| `EncodeTypes.Code128`      | Shipping labels, inventory           |
| `EncodeTypes.QR`           | Mobile payments, URLs                |
| `EncodeTypes.Pdf417`       | Driver’s licenses, boarding passes   |
| `EncodeTypes.MicroPdf417`  | Small data payloads, limited space   |
| `EncodeTypes.DataMatrix`   | Tiny items, high data density        |

只要在建構子中換成其他 enum 值，即可變更編碼類型：

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

此彈性讓您在 IDE 內即可回答 **barcode encode types** 的相關問題。

## 建立 PDF417 條碼 C# – 最後步驟與驗證

完成產生器設定後，**create pdf417 barcode c#** 的最後一步是儲存影像並確認結果。

```csharp
// Save as PNG (lossless, ideal for further processing)
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

執行程式 (`dotnet run`) 後，您應會在主控台看到類似以下訊息：

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\MicroPdf417.png
```

開啟 PNG 檔案，即可看到清晰的 MicroPdf417 條碼，編碼內容為 “Åspóse.Barcóde©”。使用手機條碼掃描器（例如 ZXing）掃描後，會回傳原始文字，證明 **generate barcode from text** 即使含特殊字元亦能正常運作。

### 邊緣案例：極長文字

MicroPdf417 的最大資料容量為 1 KB。若輸入超過此上限，函式庫會拋出 `ArgumentException`。可使用以下方式優雅處理：

```csharp
try
{
    generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Data too long for MicroPdf417: {ex.Message}");
}
```

若需更大負載，請改用完整的 `EncodeTypes.Pdf417` 或 `EncodeTypes.DataMatrix`。

## 常見陷阱與避免方式

| Issue                               | Cause                                   | Fix |
|-------------------------------------|-----------------------------------------|-----|
| 條碼顯示模糊                         | XDimension 設定過低（例如 1 px）        | 將 `XDimension.Pixels` 提升至 2‑3 px |
| Unicode 字元顯示為 `?`               | 預設文字編碼為 ASCII                     | 設定 `TextEncoding = Encoding.UTF8` |
| 圖片檔案未建立                       | 輸出目錄不存在                           | 在 `Save` 前使用 `Directory.CreateDirectory` |
| 掃描器無法讀取條碼                   | 短資料使用過多欄位                         | 減少 `Pdf417.Columns`（例如 3‑4） |

## 完整原始碼（可直接複製）

```csharp
using System;
using System.IO;
using System.Text;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create the generator – this is the core of "generate barcode from text"
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.MicroPdf417,
            "Åspóse.Barcóde©"
        );

        // Ensure Unicode characters are handled correctly
        generator.Parameters.Barcode.TextEncoding = Encoding.UTF8;

        // Optional: set a font that contains the required glyphs
        generator.Parameters.Barcode.Font.FontFamily = "Arial Unicode MS";

        // Configure visual appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;
        generator.Parameters.Barcode.Pdf417.Columns = 4;

        // Prepare output directory
        string outputDir = Path.Combine(Environment.CurrentDirectory, "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "MicroPdf417.png");

        // Save the barcode image
        try
        {
            generator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
        catch (ArgumentException ex)
        {
            Console.Error.WriteLine($"Failed to generate barcode: {ex.Message}");
        }
    }
}
```

**預期輸出：** 在 `output` 資料夾內產生名為 `MicroPdf417.png` 的檔案，內含清晰的 MicroPdf417 條碼，編碼原始含特殊字元的字串。

## 結論

您現在已掌握如何在 C# 使用 Aspose.BarCode **generate barcode from text**、如何處理 **barcode with special characters**，以及如何 **create pdf417 barcode c#**，並能自行調整 **barcode encode types** 以產生 QR Code、Code128、DataMatrix 或其他支援的格式。

接下來，您可以探索以下主題，以深化條碼專業知識：

- **批次產生條碼**（針對數千筆資料，使用 `Parallel.ForEach` 提升速度）
- 自訂顏色與在條碼內加入商標
- 將條碼產生整合至 ASP.NET Core API，實現即時影像傳遞
- 使用其他函式庫（如 ZXing.Net 或 IronBarcode）作為開源替代方案

歡迎嘗試不同的尺寸、欄位設定與編碼類型。祝開發順利，條碼掃描無礙！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索其他實作方式：

- [如何使用 Aspose.BarCode 建立條碼 – 緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode 產生條碼 – Code 39 設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [如何產生條碼 – 一維條碼類型總覽](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}