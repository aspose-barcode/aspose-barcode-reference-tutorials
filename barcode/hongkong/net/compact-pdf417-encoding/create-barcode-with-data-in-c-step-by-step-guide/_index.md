---
category: general
date: 2026-07-27
description: 快速使用 C# 產生條碼。學習如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼、設定尺寸，並儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode with data
- create pdf417 barcode c#
language: zh-hant
lastmod: 2026-07-27
og_description: 使用 Aspose.BarCode 在 C# 中建立含資料的條碼。本指南說明如何在 C# 中使用自訂設定建立 PDF417 條碼，並將其儲存為
  PNG。
og_image_alt: Screenshot of a barcode created with data in a C# application
og_title: 使用 C# 建立含資料的條碼 – 完整程式教學
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  headline: Create barcode with data in C# – Step‑by‑Step Guide
  type: TechArticle
- description: Create barcode with data in C# quickly. Learn how to create PDF417
    barcode c# using Aspose.BarCode, set dimensions, and save as PNG.
  name: Create barcode with data in C# – Step‑by‑Step Guide
  steps:
  - name: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
    text: Initialising `BarcodeGenerator` with MicroPdf417 and a Unicode string.
  - name: Tweaking the X‑dimension for finer resolution.
    text: Tweaking the X‑dimension for finer resolution.
  - name: Limiting columns to keep the barcode compact.
    text: Limiting columns to keep the barcode compact.
  - name: Saving the result as a PNG file.
    text: Saving the result as a PNG file.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 使用 C# 建立帶資料的條碼 — 步驟指南
url: /zh-hant/net/compact-pdf417-encoding/create-barcode-with-data-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立含資料的條碼 – 完整程式教學

是否曾在 .NET 應用程式中需要 **建立含資料的條碼**，卻不確定要使用哪個 API？你並不孤單。無論是為庫存貼標、列印票證，或在行動裝置掃描時嵌入資訊，掌握條碼產生都是每位 C# 開發者的實用技能。

在本教學中，我們將示範一個實務範例，說明如何使用 Aspose.BarCode 套件 **create PDF417 barcode c#**，調整模組寬度、限制欄位數，最後將結果輸出為 PNG 檔案。完成後，你將擁有一個完整、可直接執行的 Console 程式，隨時可以放入任何專案使用。

## 前置需求 — 你需要的環境

- **.NET 6.0** 或更新版本（程式碼同樣支援 .NET Framework 4.7 以上）  
- **Aspose.BarCode for .NET** NuGet 套件（`Install-Package Aspose.BarCode`）  
- 任一程式碼編輯器或 IDE（Visual Studio、VS Code、Rider – 自行挑選）  
- 具寫入權限的資料夾，以便儲存 PNG 檔案  

不需要額外的設定檔；此函式庫為獨立套件。

## 步驟 1：建立專案並匯入命名空間

先建立一個新的 Console 專案（或開啟既有專案），再加入 Aspose.BarCode 的參考。

```csharp
// Program.cs – entry point
using System;
using Aspose.BarCode.Generation;   // Core generator classes
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll place the barcode generation logic here.
        }
    }
}
```

> **為什麼這很重要：** 匯入正確的命名空間即可直接使用 `BarcodeGenerator` 以及相關設定，免除每次都必須寫完整型別名稱，也讓程式碼在未來維護時更為簡潔。

## 步驟 2：以資料初始化條碼產生器

現在正式 **create barcode with data**。`BarcodeGenerator` 建構子接受兩個參數：條碼類型（`EncodeTypes.MicroPdf417`）以及欲編碼的字串。

```csharp
// Inside Main()
string dataToEncode = "Åspóse.Barcóde©";   // Example containing Unicode characters
var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);
```

> **小技巧：** MicroPdf417 是 PDF417 的緊縮版，當你需要較小的圖像但仍想保有高資料容量時非常適合。此函式庫內建 Unicode 支援，像 “Å” 與 “©” 之類的字元都能正確處理。

## 步驟 3：微調 X‑Dimension（模組寬度）

若需要更銳利、解析度更高的圖像，可縮小模組寬度。將其設定為 **2 像素**，即可在不大幅增加檔案大小的前提下取得更細緻的格線。

```csharp
// Adjust the module (X‑dimension) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **為什麼要調整 X‑Dimension？** 較小的 X‑Dimension 會讓每根條紋變窄，提升高解析度掃描器的可讀性，同時保持條碼整體尺寸在合理範圍內。

## 步驟 4：限制 PDF417 欄位數（可選但常見）

PDF417 允許自行指定欄位數量。對於 MicroPdf417，最大值為 **4**，可讓條碼保持短而寬的形狀。

```csharp
// Set the column count to the maximum allowed (4)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

> **邊緣案例：** 若設定的欄位數超過上限，Aspose 會自動將其夾回允許範圍，但最佳實踐仍是遵守文件所列的上限，以免產生意外的縮放效果。

## 步驟 5：將條碼儲存為 PNG 圖片

最後，將產生的圖像寫入磁碟。`Save` 方法接受完整路徑與目標圖像格式。

```csharp
// Define output path – adjust as needed
string outputPath = @"C:\Temp\MicroPdf417.png";

// Save as PNG (lossless, widely supported)
generator.Save(outputPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode saved to {outputPath}");
```

> **專業提示：** PNG 能完整保留像素資訊，對條碼而言相當重要。若需向量格式以便縮放，可將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Svg`。

### 完整範例程式

以下是可直接複製貼上的完整程式碼：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Data we want to encode – includes special characters
            string dataToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Initialise generator with MicroPdf417 symbology
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, dataToEncode);

            // 3️⃣ Fine‑tune resolution – 2‑pixel modules
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Use the maximum of 4 columns for a compact barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 5️⃣ Save the image
            string outputPath = @"C:\Temp\MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode created successfully! Saved at: {outputPath}");
        }
    }
}
```

執行此程式後會產生一個 PNG 檔，外觀大致如下：

![在 C# 中建立含資料的條碼](barcode-sample.png "C# 應用程式產生的條碼截圖")

*上圖僅為示意圖——實際產生的條碼會包含精確字串 “Åspóse.Barcóde©”。*

## 常見問題與邊緣案例

| 問題 | 解答 |
|----------|--------|
| *如果我的資料超過 MicroPdf417 的容量上限怎麼辦？* | 改用 `EncodeTypes.Pdf417`（一般 PDF417），其支援最高 1 800 個字元。 |
| *可以改成 JPEG 格式嗎？* | 可以——將 `BarCodeImageFormat.Png` 換成 `BarCodeImageFormat.Jpeg`。請注意 JPEG 為有損壓縮，可能影響掃描器的可靠度。 |
| *需要自行處理 Unicode 嗎？* | 不需要。Aspose.BarCode 會自動編碼 Unicode 字元，但請確保原始程式檔以 UTF‑8 編碼儲存。 |
| *如果想要透明背景該怎麼做？* | 在儲存前加入 `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;` 即可。 |
| *有沒有辦法在記憶體中產生條碼？* | 呼叫 `generator.GenerateBarCodeImage()` 可取得 `System.Drawing.Image` 物件，直接串流使用。 |

## 重點回顧 – 我們學到了什麼

我們示範了如何在 C# 中 **create barcode with data**，步驟如下：

1. 使用 MicroPdf417 與 Unicode 字串初始化 `BarcodeGenerator`。  
2. 調整 X‑dimension 以取得更細緻的解析度。  
3. 限制欄位數以保持條碼緊湊。  
4. 以 PNG 格式儲存結果。

以上步驟完整回答了「**how to create PDF417 barcode c#**」的核心需求，同時展示了常見參數的客製化方式。

## 後續步驟與相關主題

- 使用 `generator.Parameters.Barcode.CodeTextParameters` 在條碼下方加入**可讀文字**。  
- 透過 `Aspose.Pdf` 將 PNG 嵌入 PDF，製作可列印的報表。  
- 交換 `EncodeTypes` 產生其他條碼類型（QR、Code128、DataMatrix）。  
- **批次處理** – 迭代 CSV 中的商品編號，批量輸出條碼資料夾。

歡迎自行嘗試調整欄位數、錯誤更正等級與配色方案。熟練後，你就能打造完整的標籤解決方案，無縫整合庫存或票務系統。

祝開發順利，掃描永遠零錯誤！

## 接下來該學什麼？

以下教學與本篇內容密切相關，能進一步深化你對 API 功能的掌握，並提供其他實作方式的範例說明。

- [如何使用 Aspose.BarCode 建立緊縮版 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [建立 DotCode 條碼影像 – 設定列與欄 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [建立 DataMatrix 條碼 PNG – 調整長寬比 (Aspose.BarCode)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}