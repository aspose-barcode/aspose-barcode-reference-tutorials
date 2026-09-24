---
category: general
date: 2026-07-18
description: 使用 Aspose.BarCode for .NET 產生微型 PDF417 條碼 – 包含列、行與 PNG 輸出的逐步指南.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate micro pdf417 barcode
- Aspose.BarCode for .NET
- MicroPdf417 columns
- MicroPdf417 rows
- C# barcode generation
language: zh-hant
lastmod: 2026-07-18
og_description: 使用 Aspose.BarCode for .NET 即時產生微型 PDF417 條碼。學習如何控制列與欄，並在數分鐘內儲存為 PNG。
og_image_alt: Screenshot of a generated Micro PDF417 barcode saved as PNG
og_title: 生成微型 PDF417 條碼 – 完整 C# 教學
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  headline: Generate Micro PDF417 Barcode in C# – Complete Guide
  type: TechArticle
- description: Generate micro pdf417 barcode with Aspose.BarCode for .NET – step‑by‑step
    guide covering columns, rows, and PNG output.
  name: Generate Micro PDF417 Barcode in C# – Complete Guide
  steps:
  - name: 4.1 Two Columns, Auto‑Calculated Rows
    text: '```csharp // Force 2 columns, let rows auto‑adjust generator.Parameters.Barcode.Pdf417.Columns
      = 2; generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto generator.Save("MicroPdf417Columns2.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Columns2.png");
      ```'
  - name: 4.2 Six Rows, Auto‑Calculated Columns
    text: '```csharp // Switch to 6 rows, columns auto‑determined generator.Parameters.Barcode.Pdf417.Columns
      = 0; // auto columns generator.Parameters.Barcode.Pdf417.Rows = 6; generator.Save("MicroPdf417Rows6.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows6.png"); ```'
  - name: 4.3 Four Columns × Eight Rows (Fully Specified)
    text: '```csharp // Explicitly set both columns and rows generator.Parameters.Barcode.Pdf417.Columns
      = 4; generator.Parameters.Barcode.Pdf417.Rows = 8; generator.Save("MicroPdf417Rows8Columns4.png",
      BarCodeImageFormat.Png); Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
      ```'
  - name: Expected Output
    text: 'Running the program produces three PNG files:'
  type: HowTo
- questions:
  - answer: Call `Directory.CreateDirectory(path)` before the first `Save` to avoid
      a `DirectoryNotFoundException`.
    question: What if the output folder doesn’t exist?
  - answer: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Gif`
      as needed.
    question: Can I change the image format?
  - answer: MicroPdf417 can encode up to 1 KB of data, but practical limits depend
      on the chosen rows/columns. If you hit an error, increase rows or columns.
    question: Is there a limit to the text length?
  - answer: Use Aspose.Pdf to insert the generated PNG, or switch to `BarCodeImageFormat.Pdf`
      for a direct PDF output.
    question: How do I embed the barcode in a PDF?
  type: FAQPage
tags:
- barcode
- C#
- Aspose
title: 在 C# 中產生 Micro PDF417 條碼 – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/generate-micro-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 Micro PDF417 條碼 – 完整指南

有沒有想過直接在 C# 應用程式中 **產生 micro pdf417 條碼**？你並不是唯一有此需求的人。無論是標記庫存、編碼短網址，或是打造自訂掃描解決方案，掌握這個小巧卻功能強大的 2‑D 條碼，都能為你省下不少麻煩。

在本教學中，我們將透過 **Aspose.BarCode for .NET**，示範如何調整欄位、列數與模組大小，最後將結果輸出為 PNG 檔案。完成後，你將擁有一個可直接執行的主控台應用程式，能產生三種不同的條碼影像——不留任何疑問。

## 需要的環境

- .NET 6 或更新版本（此程式碼亦相容 .NET Framework 4.7+）
- Visual Studio 2022（或任何你慣用的 C# IDE）
- **Aspose.BarCode** NuGet 套件 (`Aspose.BarCode`)
- 一個可寫入的資料夾，用來存放輸出的 PNG

如果上述條件都已備妥，讓我們開始吧。

## 第一步：建立專案並安裝 Aspose.BarCode

首先，建立一個新的主控台專案：

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode
```

> **小技巧：** 加入套件後執行 `dotnet restore`，確保所有相依性都已解決。

接著開啟 `Program.cs`，加入必要的命名空間：

```csharp
using System;
using Aspose.BarCode.Generation;
```

這兩行 `using` 陳述式讓我們可以使用 `BarcodeGenerator`、`EncodeTypes` 以及稍後會用到的影像格式列舉。

## 第二步：初始化 MicroPdf417 產生器

操作的核心是 `BarcodeGenerator` 物件。我們將編碼類型設定為 **MicroPdf417**，並提供要編碼的文字——此例使用「ASPOSE」這個字串。

```csharp
// Initialise generator with MicroPdf417 and sample text
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");
```

為什麼選擇 `MicroPdf417`？相較於完整尺寸的 PDF417，微型版能在更小的空間內容納更多資料，非常適合空間受限的標籤。

## 第三步：調整模組大小（X‑Dimension）

模組大小決定條碼中每個小方格佔用多少像素。設定為 **2 像素** 時，影像既清晰又不會過大。

```csharp
// Set X‑dimension to 2 pixels per module
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **注意：** 若需遠距離掃描，可將此數值提升至 3 或 4。

## 第四步：以不同的欄列組合產生條碼

### 4.1 兩欄、列數自動計算

```csharp
// Force 2 columns, let rows auto‑adjust
generator.Parameters.Barcode.Pdf417.Columns = 2;
generator.Parameters.Barcode.Pdf417.Rows = 0; // 0 = auto
generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Columns2.png");
```

### 4.2 六列、欄位自動計算

```csharp
// Switch to 6 rows, columns auto‑determined
generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
generator.Parameters.Barcode.Pdf417.Rows = 6;
generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows6.png");
```

### 4.3 四欄 × 八列（全部手動指定）

```csharp
// Explicitly set both columns and rows
generator.Parameters.Barcode.Pdf417.Columns = 4;
generator.Parameters.Barcode.Pdf417.Rows = 8;
generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");
```

每一次 `Save` 呼叫都會將 PNG 檔寫入專案的工作目錄。若想改成專屬資料夾，可將路徑（`"YOUR_DIRECTORY/..."`）改為 `Path.Combine(Environment.CurrentDirectory, "output")`。

## 第五步：完整範例程式

以下是可直接複製貼上的完整程式碼：

```csharp
using System;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialise generator with MicroPdf417 and sample text
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "ASPOSE");

            // 2️⃣ Set module size – 2 pixels per module for a sharp image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Create three variants with different column/row settings

            // Variant A – 2 columns, rows auto‑adjust
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // auto rows
            generator.Save("MicroPdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Columns2.png");

            // Variant B – 6 rows, columns auto‑determine
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("MicroPdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows6.png");

            // Variant C – 4 columns × 8 rows (full control)
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 8;
            generator.Save("MicroPdf417Rows8Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: MicroPdf417Rows8Columns4.png");

            Console.WriteLine("All barcodes generated successfully!");
        }
    }
}
```

### 預期輸出

執行程式後會產生三個 PNG 檔案：

| 檔案名稱 | 大約尺寸 (px) | 視覺說明 |
|-----------|----------------|----------|
| `MicroPdf417Columns2.png` | 180 × 120 | 窄而較高的條碼 |
| `MicroPdf417Rows6.png` | 120 × 180 | 寬而較短的條碼 |
| `MicroPdf417Rows8Columns4.png` | 160 × 160 | 接近方形、布局平衡 |

用任何影像檢視器開啟，都能看到清晰的 **Micro PDF417** 條碼，隨時待掃描。

## 常見問題與特殊情況

- **如果輸出資料夾不存在會怎樣？**  
  在第一次 `Save` 前呼叫 `Directory.CreateDirectory(path)`，即可避免 `DirectoryNotFoundException`。

- **可以更換影像格式嗎？**  
  當然可以。只要把 `BarCodeImageFormat.Png` 換成 `Jpeg`、`Bmp` 或 `Gif` 即可。

- **文字長度有上限嗎？**  
  MicroPdf417 最多可編碼 1 KB 資料，但實際上限取決於選擇的列數與欄位。若發生錯誤，請增加列或欄的數量。

- **如何將條碼嵌入 PDF？**  
  可使用 Aspose.Pdf 把產生的 PNG 插入 PDF，或直接將 `BarCodeImageFormat.Pdf` 作為輸出格式。

## C# 條碼產生的進階小技巧

1. **快取產生器**：若需要大量條碼且設定相同，只需變更文字即可，能減少 CPU 開銷。  
2. **微調錯誤更正**：透過 `generator.Parameters.Barcode.Pdf417.ErrorLevel` 調整，適用於噪聲較大的掃描環境。  
3. **提前實機測試**：某些手持掃描器對密集的微型條碼較敏感，調整 `XDimension` 常能顯著改善掃描成功率。

## 結論

現在你已掌握如何使用 **Aspose.BarCode for .NET** 於 **C#** 中 **產生 micro pdf417 條碼**，並能調整 **MicroPdf417 欄位** 與 **列數**，最後以 PNG 檔案儲存——全部都在一個簡潔的主控台應用程式內完成。接下來，你可以嘗試不同的模組大小、錯誤等級，甚至是彩色輸出，以符合專案需求。

未來，你也可以探索 **C# 條碼產生** 的其他符號，如 QR、Code128 或 DataMatrix，或是直接使用 Aspose.Pdf 把影像嵌入 PDF。只要掌握基礎，無所不能。

祝開發順利，掃描永遠無誤！

## 接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步深化你所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你在專案中靈活運用 API 或探索其他實作方式。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [Generate DataMatrix Barcode – Pro Guide with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}