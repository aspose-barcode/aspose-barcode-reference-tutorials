---
category: general
date: 2026-10-21
description: 在 C# 中快速生成 PDF417 條碼。了解如何使用自訂布局、欄位、列以及 PNG 輸出生成 PDF417 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- pdf417 barcode layout
- barcode generator C#
- save barcode as PNG
language: zh-hant
lastmod: 2026-10-21
og_description: 在 C# 中產生 PDF417 條碼。跟隨本教學了解如何使用自訂欄位、列數以及 PNG 輸出產生 PDF417 條碼。
og_image_alt: Screenshot showing a generated PDF417 barcode saved as a PNG file
og_title: 在 C# 中產生 PDF417 條碼 – 完整逐步指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  headline: Generate pdf417 barcode in C# with custom columns and rows
  type: TechArticle
- description: Generate pdf417 barcode quickly in C#. Learn how to generate pdf417
    barcode with custom layout, columns, rows, and PNG output.
  name: Generate pdf417 barcode in C# with custom columns and rows
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
    text: Use a free PDF417 scanner app (e.g., ZXing, PDF417 Decoder) to scan the
      image.
  - name: Confirm that the decoded text matches the original input.
    text: Confirm that the decoded text matches the original input.
  type: HowTo
tags:
- barcode
- pdf417
- C#
- image generation
title: 在 C# 中生成自訂欄與列的 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-with-custom-columns-and-rows/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 pdf417 條碼 – 完整程式設計指南

如果您需要在 .NET 應用程式中 **產生 pdf417 條碼**，本指南將示範如何僅用幾行程式碼完成。您將看到一個實作範例，設定欄與列的數量，然後將結果儲存為 PNG 圖片。相同的方法適用於任何想要編碼的文字，您可以將其套用於發票、票券或身分證等。

產生 **pdf417 條碼** 常常感覺與其餘程式碼相互獨立。完成本教學後，您將了解為何版面參數很重要、如何控制影像品質，以及哪些函式庫呼叫是可靠 **產生 pdf417 條碼** 所必需的。

## 您需要的條件

* .NET 6.0 SDK 或更新版本已安裝  
* 支援 C# 的 IDE（Visual Studio、VS Code、Rider 等）  
* **Aspose.BarCode for .NET** NuGet 套件（或任何相容的條碼函式庫）  

您可以使用以下指令加入此函式庫：

```bash
dotnet add package Aspose.BarCode
```

此函式庫提供在本教學中全程使用的 `BarcodeGenerator` 類別。

## 步驟 1：建立條碼產生器實例

第一行會建立一個能夠 **產生 pdf417 條碼** 的物件。您必須指定編碼類型（`EncodeTypes.Pdf417`）以及欲編碼的文字。

```csharp
using Aspose.BarCode.Generation;

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample Text");
```

*此步驟的重要性* – `BarcodeGenerator` 封裝了條碼的所有設定。以正確的 `EncodeTypes` 來實例化它，會告訴引擎使用 PDF417 符號，而非 QR、Code128 或其他格式。

## 步驟 2：設定 PDF417 版面配置

PDF417 允許您控制欄與列的數量，直接影響條碼的尺寸與密度。調整這些數值即是以自訂版面 **產生 pdf417 條碼** 的核心。

```csharp
// Set the number of data columns (valid range: 2‑30)
generator.Parameters.Barcode.Pdf417.Columns = 4;

// Set the number of rows (up to 90 rows)
generator.Parameters.Barcode.Pdf417.Rows = 9;
```

*為何可能需要變更這些數值* – 欄數增加會降低條碼高度，列數增加則會擴寬條碼。請選擇符合目標掃描裝置與可用列印區域的數值。

> **專業提示：** 若省略列設定，函式庫會自動依資料長度計算最佳列數。若需要固定的影像尺寸以配合 UI 版面時，明確設定列數會很有幫助。

## 步驟 3：選擇影像格式並儲存檔案

完成版面配置後，您可以將條碼渲染為影像。以下範例將條碼儲存為 PNG 檔案，您亦可選擇 JPEG、BMP 或 TIFF。

```csharp
using Aspose.BarCode;
using System.IO;

// Define the output path – replace with your actual directory
string outputPath = Path.Combine("C:\\Barcodes", "CustomLayout.png");

// Save the barcode image as PNG
generator.Save(outputPath, BarCodeImageFormat.Png);
```

程式執行後，`CustomLayout.png` 會包含一個清晰的 **pdf417 條碼**，其欄/列設定與您提供的相符。

### 預期輸出

開啟 `CustomLayout.png` 後會看到一個矩形條碼，包含四個資料欄與九列。使用任何 PDF417 讀取器掃描此影像，即可還原原始文字 **「Sample Text」**。

![產生的 PDF417 條碼範例](generated-pdf417.png){: .center-image alt="已儲存為 PNG 檔案的產生 pdf417 條碼"}

## 步驟 4：完整、可執行範例

以下是一個獨立的主控台應用程式，將所有步驟整合在一起。將程式碼複製到新的 `.csproj` 專案中並執行——不需要其他檔案。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Sample Text for PDF417 barcode");

            // 2️⃣ Configure layout – custom columns and rows
            generator.Parameters.Barcode.Pdf417.Columns = 4; // 2‑30
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // up to 90

            // Optional: increase image resolution for sharper output
            generator.Parameters.ImageResolution = 300; // DPI

            // 3️⃣ Define the output location
            string folder = Path.Combine(Environment.CurrentDirectory, "output");
            Directory.CreateDirectory(folder);
            string filePath = Path.Combine(folder, "CustomLayout.png");

            // 4️⃣ Save as PNG
            generator.Save(filePath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode generated at: {filePath}");
        }
    }
}
```

執行程式後會在主控台印出確認訊息，並在 `output` 子資料夾下產生 PNG 檔案。此影像可嵌入報表、列印於標籤，或傳送至行動裝置進行掃描。

## 常見變化與邊緣情況

| 情境 | 要變更的項目 | 為何重要 |
|----------|----------------|----------------|
| **編碼長字串** | 增加 `Rows` 或省略 `Rows` 指定，讓函式庫自動計算 | PDF417 可容納最多 1,850 個字元；列數不足會導致截斷 |
| **更高視覺品質** | 將 `generator.Parameters.ImageResolution` 設為 600 DPI | 適用於高解析度印表機列印 |
| **不同的影像格式** | 將 `BarCodeImageFormat.Png` 替換為 `Jpeg` 或 `Tiff` | JPEG 可減少檔案大小；TIFF 保留無損資料以供存檔 |
| **加入安靜區** | `generator.Parameters.Barcode.XDimension = 2;`（或調整 `Margins`） | 安靜區可提升噪雜環境下掃描器的可靠性 |
| **從使用者輸入的動態文字** | 將硬編碼字串改為 `Console.ReadLine()` | 允許根據使用者資料在執行時產生條碼 |

### 如何在 Web API 中產生 pdf417 條碼

如果您需要透過 ASP.NET Core 端點提供條碼產生功能，請將影像以位元組陣列回傳：

```csharp
[HttpGet("api/barcode/pdf417")]
public IActionResult GetPdf417([FromQuery] string data)
{
    var generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
    generator.Parameters.Barcode.Pdf417.Columns = 5;
    generator.Parameters.Barcode.Pdf417.Rows = 10;

    using var ms = new MemoryStream();
    generator.Save(ms, BarCodeImageFormat.Png);
    return File(ms.ToArray(), "image/png");
}
```

此程式碼片段即時說明如何在不寫入磁碟的情況下 **產生 pdf417 條碼**，非常適合微服務或行動後端使用。

## 測試產生的條碼

1. 在任何影像檢視器中開啟 PNG 檔案。  
2. 使用免費的 PDF417 掃描應用程式（例如 ZXing、PDF417 Decoder）掃描影像。  
3. 確認解碼後的文字與原始輸入相符。  

若掃描器回報錯誤，請再次檢查欄/列設定，並確保影像解析度足以符合您的裝置需求。

## 結論

您現在已了解如何在 C# 中 **產生 pdf417 條碼**，並完整掌控欄、列與輸出格式。完整範例示範了整個工作流程——從建立 `BarcodeGenerator` 到儲存 PNG 檔案——讓您能將條碼產生整合至任何 .NET 專案。

接下來，您可以探索相關主題，例如 **pdf417 條碼版面** 最佳化、在 PDF 報告中嵌入條碼，或在行動裝置上解碼條碼。調整錯誤更正等級並嘗試不同的影像解析度，將有助於為您的特定使用情境微調解決方案。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中產生 PDF417 條碼 – 步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中儲存條碼 – 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [如何產生 PDF417 條碼 – 完整程式設計指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}