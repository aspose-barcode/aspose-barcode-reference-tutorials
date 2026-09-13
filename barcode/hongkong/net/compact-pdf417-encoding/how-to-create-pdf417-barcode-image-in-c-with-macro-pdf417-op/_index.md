---
category: general
date: 2026-09-13
description: 學習如何在 C# 中使用 BarcodeGenerator 及 Macro PDF417 選項建立 PDF417 條碼影像。逐步程式碼、技巧與完整範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode image
- macro PDF417 options
- BarcodeGenerator class
- C# barcode generation
- barcode image format
language: zh-hant
lastmod: 2026-09-13
og_description: 使用 BarcodeGenerator 在 C# 中建立 PDF417 條碼圖像。遵循本詳細教學，設定 Macro PDF417 選項並儲存
  PNG 條碼。
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: 在 C# 中建立 PDF417 條碼圖像 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  headline: How to create PDF417 barcode image in C# with Macro PDF417 options
  type: TechArticle
- description: Learn how to create PDF417 barcode image in C# using BarcodeGenerator
    and Macro PDF417 options. Step‑by‑step code, tips, and full example.
  name: How to create PDF417 barcode image in C# with Macro PDF417 options
  steps:
  - name: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
    text: '**Create the generator** – instantiate `BarcodeGenerator` with `EncodeTypes.MacroPdf417`
      and the data you want to encode.'
  - name: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
    text: '**Define the module size** – set `XDimension.Pixels` to control the physical
      width of each barcode element.'
  - name: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
    text: '**Configure Macro PDF417 options** – specify columns, file identifiers,
      segment numbers, and optional checksum.'
  - name: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
    text: '**Save the barcode** – write the generated image to disk using a supported
      **barcode image format** such as PNG.'
  - name: Create a new .NET 6 (or later) console project.
    text: Create a new .NET 6 (or later) console project.
  - name: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
    text: Add the Aspose.BarCode NuGet package (`dotnet add package Aspose.BarCode`).
  - name: Replace the generated `Program.cs` with the code above.
    text: Replace the generated `Program.cs` with the code above.
  - name: Adjust `outputPath` to a folder you have write access to.
    text: Adjust `outputPath` to a folder you have write access to.
  - name: Build and run – the console will confirm the image location.
    text: Build and run – the console will confirm the image location.
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: 如何在 C# 中使用 Macro PDF417 選項建立 PDF417 條碼圖像
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Macro PDF417 選項建立 PDF417 條碼圖像

如果您需要在 C# 中**建立 PDF417 條碼圖像**，本指南將向您展示如何使用**BarcodeGenerator 類別**完成。無論您是構建文件追蹤系統還是編碼大型檔案，以下逐步說明涵蓋了從設定 Macro PDF417 選項到儲存最終 PNG 的全部內容。

一旦了解關鍵參數，產生條碼就相當簡單。在本教學中您將學會如何：

* 為 **Macro PDF417** 初始化 `BarcodeGenerator`。
* 調整條碼模組大小（`XDimension`）。
* 設定段落特定的參數，如檔案 ID、段落 ID 與校驗碼。
* 將結果儲存為 **條碼圖像格式**（PNG），可在任何 UI 中顯示。

唯一的先決條件是 .NET 開發環境（Visual Studio 2022 或更新版本）以及 Aspose.BarCode for .NET NuGet 套件，該套件提供範例中使用的 `BarcodeGenerator` API。

## 在 C# 中建立 PDF417 條碼圖像 – 概觀

建立 PDF417 條碼圖像包含四個邏輯步驟：

1. **建立產生器** – 使用 `EncodeTypes.MacroPdf417` 以及您想要編碼的資料來實例化 `BarcodeGenerator`。  
2. **定義模組大小** – 設定 `XDimension.Pixels` 以控制每個條碼元素的實際寬度。  
3. **設定 Macro PDF417 選項** – 指定欄位數、檔案識別碼、段落編號以及可選的校驗碼。  
4. **儲存條碼** – 使用支援的 **條碼圖像格式**（如 PNG）將產生的圖像寫入磁碟。  

以下將逐步詳細說明每個步驟，並提供完整可執行的 C# 程式碼。

## 步驟 1：為 Macro PDF417 初始化 BarcodeGenerator

第一行會建立一個 `BarcodeGenerator` 物件，告訴它必須產生 **Macro PDF417** 條碼。建構子接受兩個參數：編碼類型與原始資料字串。

```csharp
using Aspose.BarCode.Generation;   // NuGet: Aspose.BarCode
using System.Drawing.Imaging;      // For ImageFormat if you prefer System.Drawing

// Step 1 – create a barcode generator for Macro PDF417
using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
{
    // Subsequent configuration goes here
}
```

**為什麼這很重要：**  
`EncodeTypes.MacroPdf417` 告訴函式庫將條碼視為多段式容器，當您需要將大型檔案分割成多個符號時此設定必不可少。`BarcodeGenerator` 實例可釋放資源，因此 `using` 區塊可確保圖像儲存後釋放所有非受控資源。

## 步驟 2：設定條碼模組大小 (XDimension)

`XDimension` 控制單一條碼模組（最小的黑白條）的像素寬度。設定為 **2 像素** 可產生緊湊且易讀的圖像。

```csharp
    // Step 2 – define the size of each barcode module (pixel width)
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**實用技巧：**  
如果目標印表機的 DPI 較低，請增加像素數量（例如 `3` 或 `4`）以避免條碼模糊。相反地，若僅在螢幕上顯示，可保持較低值以減少檔案大小。

## 步驟 3：設定 Macro PDF417 專屬選項

Macro PDF417 會加入中繼資料，使掃描器能從多個條碼段重建原始檔案。最常用的選項如下：

| 屬性 | 說明 |
|----------|---------|
| `Columns` | 每個符號的欄位數（影響寬度）。 |
| `MacroPdf417FileID` | 整個檔案的唯一識別碼。 |
| `MacroPdf417SegmentID` | 當前段落的索引（從 1 開始）。 |
| `MacroPdf417SegmentsCount` | 組成檔案的總段落數。 |
| `MacroPdf417FileName` | 原始檔案名稱（可選，用於顯示）。 |
| `MacroPdf417Checksum` | 用於完整性驗證的可選 16 位元校驗碼。 |

```csharp
    // Step 3 – configure Macro PDF417 specific options
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns in the symbol
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf"; // Original file name
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;    // Optional checksum
```

**為什麼這些設定很重要：**  
- **Columns** 影響可讀性與整體圖像尺寸。  
- **FileID** 必須在所有段落中保持相同，讓解碼器知道它們屬於同一檔案。  
- **SegmentID** 與 **SegmentsCount** 讓掃描器正確排序各段。  
- **FileName** 與 **Checksum** 為可選項目，但可提升使用者體驗與資料完整性。

**邊緣情況：** 若產生超過 999 個段落，`SegmentID` 欄位會溢位；此時請將資料分割成多個檔案。

## 步驟 4：將產生的條碼儲存為 PNG 圖像

最後一步將條碼寫入磁碟。`BarCodeImageFormat.Png` 產生無失真的圖像，適用於 Web、桌面與行動平台。

```csharp
    // Step 4 – save the generated barcode as a PNG image
    barcodeGenerator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

**替代格式：**  
若下游系統需要特定格式，可將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。請注意 JPEG 會產生壓縮雜訊，可能降低掃描可靠性。

**預期輸出：**  
檔案 `MacroPdf417.png` 會包含高對比度的多段式 PDF417 條碼。開啟時，應與下方示意圖相似。

![建立 PDF417 條碼圖像範例](image.png){: .align-center alt="由 C# 程式碼產生的 PDF417 條碼圖像範例"}

## 完整原始碼 – 可直接複製執行

以下是完整、獨立的程式。它包含必要的 `using` 指令、`Main` 方法，以及說明每行非顯而易見之處的註解。

```csharp
using System;
using Aspose.BarCode.Generation;   // Install-Package Aspose.BarCode
// No other external dependencies are required.

namespace Pdf417BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Data to encode – can be any UTF‑8 string up to 1,800 characters.
            const string dataToEncode = "Sample data";

            // Output directory – change this to a valid path on your machine.
            const string outputPath = @"C:\Barcodes\MacroPdf417.png";

            // Create a BarcodeGenerator for Macro PDF417.
            using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, dataToEncode))
            {
                // 1️⃣ Define module size (pixel width of each bar).
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // 2️⃣ Configure Macro PDF417 options.
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "report.pdf";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;

                // 3️⃣ Save the barcode as a PNG image.
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            }

            Console.WriteLine($"PDF417 barcode image created at: {outputPath}");
        }
    }
}
```

**執行程式：**  

1. 建立一個新的 .NET 6（或更新）主控台專案。  
2. 新增 Aspose.BarCode NuGet 套件（`dotnet add package Aspose.BarCode`）。  
3. 用上述程式碼取代產生的 `Program.cs`。  
4. 將 `outputPath` 調整為您有寫入權限的資料夾。  
5. 建置並執行 – 主控台會顯示圖像所在位置。

## 常見問題與疑難排解

| 問題 | 答案 |
|----------|--------|
| *如果條碼對我的標籤太寬怎麼辦？* | 減少 `Columns` 或增加 `XDimension.Pixels` 以在寬度與可讀性之間取得平衡。 |
| *我需要設定校驗碼嗎？* | 校驗碼為可選項目 |

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，建立在本教學示範的技術之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [在 C# 中建立 PDF417 條碼 – 完整逐步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [在 C# 中建立 PDF417 條碼中繼資料 – 完整逐步指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [產生帶文字的條碼 – 完整 PDF417 Macro 指南](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}