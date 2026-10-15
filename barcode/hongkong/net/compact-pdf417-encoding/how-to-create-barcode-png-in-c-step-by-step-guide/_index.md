---
category: general
date: 2026-10-15
description: 在 C# 中使用緊湊的 PDF417 範例建立條碼 PNG – 了解如何設定欄位、調整尺寸以及產生圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- how to set columns
- c# barcode example
language: zh-hant
lastmod: 2026-10-15
og_description: 在 C# 中使用緊湊 PDF417 範例建立條碼 PNG。本指南說明如何設定欄位、調整尺寸，並儲存圖像。
og_image_alt: Screenshot showing a generated barcode PNG created with C#
og_title: 在 C# 中建立條碼 PNG – 完整程式設計教學
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  headline: How to create barcode PNG in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode PNG in C# with a compact PDF417 example – learn how
    to set columns, adjust dimensions, and generate the image.
  name: How to create barcode PNG in C# – step‑by‑step guide
  steps:
  - name: Initialise the barcode generator with the desired text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the module (X) dimension in pixels
    text: '```csharp // Set the width of the smallest bar (module) to 2 pixels generator.Parameters.Barcode.XDimension.Pixels
      = 2; ```'
  - name: Define the number of columns for the PDF417 barcode
    text: '```csharp // Specify that the barcode should use 3 columns generator.Parameters.Barcode.Pdf417.Columns
      = 3; ```'
  - name: Enable the compact layout by truncating the barcode
    text: '```csharp // Truncate removes unnecessary empty rows, making the barcode
      shorter generator.Parameters.Barcode.Pdf417.Truncate = true; ```'
  - name: Save the barcode image as PNG
    text: '```csharp // Choose the output folder and file name string outputPath =
      Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");'
  - name: Full, runnable example
    text: 'Putting everything together, here is a self‑contained program you can copy,
      paste, and run:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: 如何在 C# 中建立條碼 PNG – 逐步指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立條碼 PNG – 步驟指南

如果您需要 **建立條碼 PNG** 檔案（透過 C# 程式碼），本教學只需幾行程式碼即可提供完整解決方案。您將會看到如何設定欄位、調整模組大小，並將緊湊的 PDF417 條碼儲存為 PNG 影像——全部以單一、易讀的範例示範。

以程式方式產生條碼可省去使用圖形編輯器的手動步驟，並且能直接將條碼嵌入發票、票券或庫存標籤中。以下各節將說明 **如何建立條碼** 影像、每項設定為何重要，以及如何依不同使用情境調整程式碼。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.7+）
* 具備支援 PDF417 的條碼函式庫，例如 **Aspose.BarCode for .NET** 或 **IronBarcode**。本範例使用 Aspose.BarCode，可透過 NuGet 安裝：

```bash
dotnet add package Aspose.BarCode
```

* 基本的 C# 語法與 Visual Studio（或您慣用的任何 IDE）知識。

> **專業小技巧：** 若您偏好免費方案，開源的 **ZXing.Net** 函式庫同樣支援 PDF417，但屬性名稱略有不同。此處示範的概念仍然適用。

## 如何在 C# 中建立條碼 PNG（主要步驟）

解決方案的核心是一個已設定為 PDF417 編碼的 `BarcodeGenerator` 物件。以下各節會逐行說明程式碼、解釋 **如何設定欄位**，以及說明設定如何影響最終 PNG 大小。

### 步驟 1：以欲編碼的文字初始化條碼產生器

```csharp
using Aspose.BarCode.Generation;

// The text you want to encode in the barcode
string barcodeText = "Compact example";

// Create a generator for PDF417 barcodes
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
{
    // Subsequent configuration goes here
}
```

*為何重要*：`EncodeTypes.Pdf417` 列舉告訴函式庫產生二維堆疊條碼。建構子同時接受要編碼的資料，省去額外的 `SetData` 呼叫。

### 步驟 2：以像素設定模組（X）尺寸

```csharp
// Set the width of the smallest bar (module) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**X 尺寸** 控制條碼的視覺密度。數值越小，影像越緊湊，適合在行動裝置螢幕或印刷空間受限的情況下使用。

### 步驟 3：為 PDF417 條碼定義欄位數量

```csharp
// Specify that the barcode should use 3 columns
generator.Parameters.Barcode.Pdf417.Columns = 3;
```

此行示範 **如何設定欄位**。PDF417 可自動選擇最佳欄位數，但明確設定可讓寬度更可預測，特別是當 PNG 要嵌入固定尺寸的版面時。

### 步驟 4：啟用緊湊版面（截斷條碼）

```csharp
// Truncate removes unnecessary empty rows, making the barcode shorter
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

當 `Truncate` 為 true 時，函式庫會移除不含資料的尾端列，降低影像總高度而不遺失資訊。

### 步驟 5：將條碼影像儲存為 PNG

```csharp
// Choose the output folder and file name
string outputPath = Path.Combine(Environment.CurrentDirectory, "CompactPdf417.png");

// Save the generated barcode as a PNG file
generator.Save(outputPath, BarCodeImageFormat.Png);
```

`Save` 方法會依指定格式將條碼寫入磁碟。PNG 為無損格式，適合需要精確邊緣偵測的掃描應用。

### 完整、可執行範例

將上述程式碼整合後，即成為一個可直接複製、貼上並執行的自足程式：

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialise the generator with the data to encode
        string barcodeText = "Compact example";

        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, barcodeText))
        {
            // 2️⃣ Set module width to 2 pixels for a tighter image
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Explicitly set the number of columns (how to set columns)
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 4️⃣ Enable compact layout by truncating empty rows
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Define the output path and save as PNG (create barcode PNG)
            string outputPath = Path.Combine(Directory.GetCurrentDirectory(), "CompactPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG saved to: {outputPath}");
        }
    }
}
```

**預期輸出** – 執行程式後，您會在執行目錄中找到 `CompactPdf417.png`。此影像包含三欄的 PDF417 條碼，足夠緊湊以貼合標準 2 × 2 cm 標籤，同時仍具完整可掃描性。

![Create barcode PNG example](placeholder.png){alt="Create barcode PNG using C#"}

## 如何依不同資料大小設定欄位（次要關鍵字）

欄位數量同時影響條碼的寬度與可讀性：

| 欄位數 | 大約寬度 (px) | 常見使用情境 |
|--------|-------------------|------------------|
| 1‑2    | 窄且高            | 小型標籤、類 RFID 印刷 |
| 3‑5    | 均衡              | 通用標籤 |
| 6‑9    | 寬且短            | 大幅海報或包裝 |

若資料字串變長，函式庫可能會自動增加列數以維持欄位上限。然而，若強制設定過低的欄位數，條碼會變得過高，可能無法在收銀機印表機上完整列印。請依實際輸出媒介的物理限制調整欄位數。

## 如何以其他格式建立條碼影像（次要關鍵字）

雖然 PNG 是網頁與行動裝置最常用的格式，您也可能需要 **如何建立條碼** 影像的 JPEG、BMP 或 SVG 版本，以配合特定工作流程：

```csharp
// Save as JPEG with 90 % quality
generator.Save("CompactPdf417.jpg", BarCodeImageFormat.Jpeg, 90);

// Save as SVG (vector, infinite scaling)
generator.Save("CompactPdf417.svg", BarCodeImageFormat.Svg);
```

選擇適當格式取決於下游使用者：

* **PNG** – 無損，最適合掃描器。
* **JPEG** – 檔案較小，容許輕微壓縮雜訊時可使用。
* **SVG** – 高解析度列印或 UI 縮放的理想選擇。

## C# 條碼範例：錯誤處理與邊界情況

一個健全的 **c# 條碼範例** 必須預先處理執行時可能發生的問題：

```csharp
try
{
    // All configuration steps as shown earlier
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode parameter: {ex.Message}");
}
catch (IOException ex)
{
    Console.Error.WriteLine($"Failed to write file: {ex.Message}");
}
```

*為何要使用 `try/catch`？* 文字中若含有無效字元、尺寸不支援，或寫入權限不足，都會拋出例外。妥善捕捉可避免批次處理時程式當機。

## 延伸範例：加入商標或背景

實務上常需要在條碼上疊加商標或設定彩色背景。Aspose.BarCode API 允許您將條碼與位圖結合：

```csharp
// Load a logo image
using (Bitmap logo = (Bitmap)Image.FromFile("logo.png"))
{
    generator.Parameters.Barcode.ImageFormat = BarCodeImageFormat.Png;
    generator.Parameters.Barcode.Pdf417.EnablePdf417CodewordCount = true; // optional

    // Merge the logo with the barcode (centered)
    generator.Save("BarcodeWithLogo.png", BarCodeImageFormat.Png, logo);
}
```

此技巧在保留 **create barcode PNG** 工作流程的同時，為最終影像增添品牌視覺效果。

## 小結

本指南示範了如何使用緊湊的 PDF417 設定，在 C# 中 **建立條碼 PNG** 檔案。您學會了：

* 初始化 `BarcodeGenerator` 所需的完整程式碼。
* **如何設定欄位** 以及欄位數對尺寸與可讀性的影響。
* 調整 X 尺寸與啟用截斷以取得更緊湊的 PNG。
* 以 PNG、JPEG 或 SVG 儲存影像的方式。
* 針對正式環境的 **c# 條碼範例** 的錯誤處理模式。
* 可選的擴充功能，如商標疊加與背景客製化。

現在您已擁有可直接嵌入發票產生器、票務系統或庫存管理工具的即用程式碼。可自行嘗試不同的欄位值、模組大小或條碼類型（例如 QR、Code128），觀察影像的變化。

## 後續步驟

* 探索其他編碼類型（`EncodeTypes.QR`、`EncodeTypes.Code128`），以滿足更多使用情境。
* 結合條碼產生與 PDF 產生函式庫（如 **iTextSharp**），直接將 PNG 嵌入文件。
* 研究動態尺寸調整：根據輸入字串長度與目標標籤尺寸，自動計算最佳欄位數。

祝開發順利，盡情享受以程式方式產生清晰條碼 PNG 的簡便性！

## 接下來該學什麼？

以下教學與本篇內容密切相關，能進一步深化您對 API 功能的掌握，並探索在專案中實作的其他方式。

- [How to create PDF417 barcode and save it as PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)
- [How to create PDF417 barcode and set its size in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-set-its-size-in-c/)
- [How to create PDF417 barcode in C# with compact mode](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}