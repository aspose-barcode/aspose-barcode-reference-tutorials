---
category: general
date: 2026-09-22
description: 學習如何在 C# 中建立 PDF417 條碼、設定條碼尺寸，並以清晰的逐步程式碼範例產生條碼圖像檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to create PDF417
- set barcode size
- create barcode image c#
language: zh-hant
lastmod: 2026-09-22
og_description: 快速在 C# 中建立 PDF417 條碼。本教學示範如何設定條碼尺寸、啟用緊湊模式，並為任何 .NET 專案輸出 PNG 圖像。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: 在 C# 中建立 PDF417 條碼 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to create PDF417 barcode in C#, set barcode size, and generate
    barcode image files with clear step‑by‑step code examples.
  headline: How to create PDF417 barcode and set its size in C#
  type: TechArticle
tags:
- PDF417
- C#
- Barcode
- Imaging
title: 如何在 C# 中建立 PDF417 條碼並設定其大小
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立 PDF417 條碼並設定其尺寸

如果您需要在 C# 中**建立 PDF417 條碼**，本指南將向您展示如何產生條碼、控制其尺寸，並將結果儲存為影像檔。無論您是在構建票務系統、物流標籤，或是安全憑證，精通 PDF417 格式都能讓您在緊湊的視覺形式中編碼大量資料。

在本教學中您將學會：

* 使用 Aspose.BarCode（或任何相容）函式庫**建立 PDF417 條碼**。  
* 透過調整 X‑dimension 與欄位數**設定條碼尺寸**。  
* 為 PNG、JPEG 或 BMP 輸出**在 C# 中產生條碼影像**。  

範例使用 Aspose.BarCode for .NET 的免費社群版，但相同概念亦適用於其他提供類似屬性的函式庫。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本。  
* C# 開發環境 (Visual Studio、Visual Studio Code、Rider 等)。  
* `Aspose.BarCode` NuGet 套件 (`dotnet add package Aspose.BarCode`)。  

不需要額外設定；此函式庫可在 Windows、Linux 與 macOS 上執行。

## 步驟 1：建立基本的 PDF417 條碼並設定其尺寸

第一步是以 `EncodeTypes.Pdf417` 列舉建立 `BarcodeGenerator`，並提供欲編碼的文字。之後調整 **X‑dimension**（模組寬度）與 **欄位數** 以控制整體尺寸。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Define the text that the barcode will represent.
string data = "Sample text for PDF417 barcode";

// Create a basic PDF417 barcode generator.
var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Set the module width to 2 pixels (controls bar thickness).
basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Set the column count; 3 columns yields a compact visual but still readable.
basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Save the barcode as a PNG image.
string basicPath = Path.Combine("YOUR_DIRECTORY", "Pdf417Basic.png");
basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
```

**為何這些設定很重要**

* `XDimension.Pixels` 決定最窄條的寬度。較小的數值會產生更緊密的條碼，較大的數值則提升低解析度掃描器的可讀性。  
* `Pdf417.Columns` 影響條碼的長寬比。欄位較少會使條碼變高；欄位較多則使條碼變寬。調整欄位是 **設定條碼尺寸** 的主要方式，且不會改變編碼資料。

執行程式後，您會在指定資料夾中找到 `Pdf417Basic.png`。影像與下方截圖相似：

<img src="images/pdf417-basic.png" alt="create PDF417 barcode example showing basic barcode layout">

## 步驟 2：以相同尺寸建立緊湊的 PDF417 條碼（截斷模式）

有時空間受限，需要較短的條碼。PDF417 提供 *truncate*（緊湊）模式，可移除停止圖樣並降低整體高度。`Truncate` 屬性可切換此行為。

```csharp
// Reuse the same data string.
var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);

// Keep the same module width and column count for a fair size comparison.
compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;

// Enable compact (truncate) mode – this removes the stop pattern.
compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;

// Save the compact version.
string compactPath = Path.Combine("YOUR_DIRECTORY", "CompactPdf417.png");
compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
```

**`Truncate = true` 會產生什麼變化？**

* 條碼在垂直方向上大約縮短 15‑20 %，適用於小標籤或行動裝置螢幕。  
* 資料仍可完整還原；大多數現代掃描器會自動支援截斷模式。

產生的 `CompactPdf417.png` 會呈現基本條碼的較纖細版本。

## 步驟 3：建立 Micro PDF417 條碼、調整欄位並儲存

Micro PDF417 是針對極小空間（例如身分證）設計的高密度變體。它僅支援 1‑4 欄，且函式庫同樣提供 `XDimension` 屬性供尺寸控制。

```csharp
// Create a Micro PDF417 generator.
var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);

// Set module width – 2 pixels works well for most printers.
microPdf417.Parameters.Barcode.XDimension.Pixels = 2;

// Micro PDF417 allows only 1 to 4 columns; choose 4 for a more square shape.
microPdf417.Parameters.Barcode.Pdf417.Columns = 4;

// Save the micro barcode.
string microPath = Path.Combine("YOUR_DIRECTORY", "MicroPdf417.png");
microPdf417.Save(microPath, BarCodeImageFormat.Png);
```

**Micro PDF417 的重點說明**

* 使用 `EncodeTypes.MicroPdf417` 列舉即可自動選擇微型變體。  
* 由於符號更密集，建議使用 300 dpi 或更高的印表機，以確保條碼可讀。  
* 調整欄位數是唯一可用的尺寸調整方式；`XDimension` 仍然有效。

## 如何為不同輸出格式設定條碼尺寸

上述範例使用 PNG，但相同的 `Save` 方法亦支援 JPEG、BMP 或 TIFF。若需特定影像尺寸（例如 300 × 150 px），可將 `XDimension` 與 `ResolutionX`/`ResolutionY` 結合使用：

```csharp
basicPdf417.Parameters.ImageResolution = 300; // DPI
basicPdf417.Parameters.Barcode.XDimension.Pixels = 3; // larger modules for higher DPI
basicPdf417.Save("Pdf417HighRes.jpg", BarCodeImageFormat.Jpeg);
```

在提升 `ImageResolution` 的同時調整 `XDimension`，可在高解析度列印時保持視覺品質。

## 常見問題與進階技巧

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| 條碼在螢幕上顯示模糊 | DPI 較低且 `XDimension` 設定過小 | 提升 `ImageResolution` 或 `XDimension.Pixels` |
| 掃描器無法讀取截斷模式 | 舊版掃描器韌體未支援 | 對舊硬體使用完整（未截斷）模式 |
| Micro PDF417 無法辨識 | 列印低於 300 dpi 或對比度不足 | 使用 300 dpi 以上的啞光紙列印，確保前景顏色足夠深 |
| 輸出檔案損毀 | 目標資料夾缺乏寫入權限 | 確認 `YOUR_DIRECTORY` 已存在且可寫入 |

**進階小技巧：** 若需無損品質以供後續處理（例如嵌入 PDF），請始終以 PNG 格式產生條碼。PNG 能保留精確的像素值，而 JPEG 會產生壓縮雜訊，可能影響條碼可讀性。

## 完整可執行範例

以下是一個完整的主控台應用程式，示範一次產生上述三種條碼類型。將程式碼複製到新的 .NET 主控台專案中並執行。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // The text to encode – change this to whatever data you need.
        const string data = "Sample text for PDF417 barcode";

        // Directory where images will be saved.
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // ---------- Basic PDF417 ----------
        var basicPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        basicPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        basicPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        string basicPath = Path.Combine(outputDir, "Pdf417Basic.png");
        basicPdf417.Save(basicPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Basic PDF417 saved to {basicPath}");

        // ---------- Compact (Truncate) PDF417 ----------
        var compactPdf417 = new BarcodeGenerator(EncodeTypes.Pdf417, data);
        compactPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        compactPdf417.Parameters.Barcode.Pdf417.Columns = 3;
        compactPdf417.Parameters.Barcode.Pdf417.Truncate = true;
        string compactPath = Path.Combine(outputDir, "CompactPdf417.png");
        compactPdf417.Save(compactPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Compact PDF417 saved to {compactPath}");

        // ---------- Micro PDF417 ----------
        var microPdf417 = new BarcodeGenerator(EncodeTypes.MicroPdf417, data);
        microPdf417.Parameters.Barcode.XDimension.Pixels = 2;
        microPdf417.Parameters.Barcode.Pdf417.Columns = 4; // 1‑4 allowed
        string microPath = Path.Combine(outputDir, "MicroPdf417.png");
        microPdf417.Save(microPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Micro PDF417 saved to {microPath}");
    }
}
```

**預期輸出**

執行程式後會在 `Barcodes` 資料夾內建立三個 PNG 檔案：

* `Pdf417Basic.png` – 具有三欄的標準 PDF417 條碼。  
* `CompactPdf417.png` – 同樣資料的截斷（緊湊）模式，稍微較短。  
* `MicroPdf417.png` – 具四欄的高密度 Micro PDF417 變體。

使用任何影像檢視器開啟，即可看到具特色的堆疊式條碼外觀。

## 接下來該學什麼？

以下教學與本指南緊密相關，能協助您進一步掌握 API 功能並探索其他實作方式：

- [如何使用 Aspose.BarCode 建立緊湊 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何在 PDF417 條碼中設定錯誤等級 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [在 C# 中建立 PDF417 條碼 Metadata – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}