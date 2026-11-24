---
category: general
date: 2026-11-23
description: 學習如何在 C# 中使用 Aspose.BarCode for .NET 產生帶有 MacroPdf417 中繼資料的條碼圖像，請遵循完整的逐步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode image
- MacroPdf417 barcode
- Aspose.BarCode for .NET
- set barcode metadata
- barcode image format
- C# barcode generation
language: zh-hant
lastmod: 2026-11-23
og_description: 如何使用 Aspose.BarCode for .NET 產生條碼圖像。本教學展示 MacroPdf417 元資料設定與 C# 條碼產生。
og_image_alt: Barcode image generated with MacroPdf417 using C#
og_title: 如何在 C# 中使用 MacroPdf417 產生條碼圖像
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  headline: How to generate barcode image with MacroPdf417 in C#
  type: TechArticle
- description: Learn how to generate barcode image using Aspose.BarCode for .NET with
    MacroPdf417 metadata in C#. Follow the complete step‑by‑step guide.
  name: How to generate barcode image with MacroPdf417 in C#
  steps:
  - name: Open a terminal or the Package Manager Console in Visual Studio.
    text: Open a terminal or the Package Manager Console in Visual Studio.
  - name: 'Run the following command:'
    text: 'Run the following command:'
  - name: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
    text: '**Visual inspection** – The barcode should display a series of stacked
      columns with a quiet zone (white margin) around it.'
  - name: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
    text: '**Decoding test** – Use a barcode scanner app or the Aspose.BarCode `BarCodeReader`
      class to read the image back and confirm that all metadata fields are correctly
      embedded.'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- PDF417
title: 如何在 C# 中使用 MacroPdf417 產生條碼圖像
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-barcode-image-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 MacroPdf417 產生條碼影像

如果您需要在 .NET 應用程式中 **產生條碼影像**，本指南將示範如何使用 **Aspose.BarCode for .NET** 完成。 我們將一步步建立 **MacroPdf417 條碼**、設定其中繼資料，並將結果儲存為 PNG 檔案。

本教學涵蓋從安裝函式庫到撰寫完整可執行的主控台程式。 完成後，您將擁有可直接使用的程式碼範例，能產生高品質的條碼影像，並了解如何 **設定條碼中繼資料**、選擇 **條碼影像格式**，以及排除常見問題。 不需要事先使用過 Aspose，只要具備基本的 C# 知識即可。

## 安裝 Aspose.BarCode for .NET

在 **產生條碼影像** 之前，您必須先取得 Aspose.BarCode NuGet 套件。

1. 在 Visual Studio 的終端機或套件管理員主控台開啟。  
2. 執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode.Generation` 命名空間，內含用於 **C# 條碼產生** 的 `BarcodeGenerator` 類別。

> **小技巧：** 使用最新的穩定版（截至 2026 年 11 月目前版本為 24.11），即可取得最新功能與錯誤修正。

## 建立 BarcodeGenerator 實例

第一段程式碼會建立一個針對 **MacroPdf417 條碼** 類型設定好的 `BarcodeGenerator`，並提供您想要編碼的資料字串。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a BarcodeGenerator for MacroPdf417 with the desired text
            using (BarcodeGenerator barcodeGenerator =
                   new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Subsequent configuration goes here...
```

`using` 區塊可確保產生器正確釋放，釋放任何非受控資源。

## 設定基本外觀

可讀的條碼必須有合理的尺寸。 這裡我們設定每個模組的像素寬度（`XDimension`）以及 PDF417 矩陣的欄位數。

```csharp
                // Step 2: Set basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // pixel width of a module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

*為什麼要這樣設定？*  
- **XDimension** 控制每條條紋的粗細；2 像素在螢幕顯示與大多數印表機上都表現良好。  
- **Columns** 影響整體寬度；較少的欄位數可讓條碼保持緊湊，同時仍保有錯誤更正能力。

## 設定條碼中繼資料（MacroPdf417 專屬）

MacroPdf417 允許您直接在條碼中嵌入檔案層級資訊。 這裡就是 **設定條碼中繼資料** 的地方，例如檔案 ID、段落 ID 與時間戳記等。

```csharp
                // Step 3: Configure MacroPdf417 specific metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### 各屬性說明

| Property | Purpose |
|----------|---------|
| **MacroPdf417FileID** | 條碼所屬邏輯檔案的唯一識別碼。 |
| **MacroPdf417SegmentID** | 目前段落的索引（從 0 開始）。 |
| **MacroPdf417SegmentsCount** | 組成完整檔案的總段落數。 |
| **MacroPdf417FileName** | 原始檔案的可讀名稱。 |
| **MacroPdf417Checksum** | 用於資料完整性驗證的可選 CCITT‑16 檢查碼。 |
| **MacroPdf417FileSize** | 原始檔案的預期大小（單位：位元組）。 |
| **MacroPdf417TimeStamp** | 條碼產生的日期與時間——有助於版本追蹤。 |
| **MacroPdf417Addressee / Sender** | 可自訂的字串，用於存放路由資訊。 |
| **MacroPdf417Terminator** | 指示此段是否為最後一段（`Set`）或非最後段（`Unset`）。 |

> **邊緣案例：** 若您打算將大型文件切割成多個段落，請確保所有產生的條碼之 `SegmentsCount` 保持一致。 數量不符會導致解碼失敗。

## 選擇條碼影像格式並儲存

Aspose 支援多種 **條碼影像格式**（PNG、JPEG、BMP、TIFF 等）。 PNG 為無損格式，適用於大多數網頁與列印情境。

```csharp
                // Step 4: Save the generated barcode image
                string outputPath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode image saved to: {outputPath}");
            } // end using
        }
    }
}
```

將 `YOUR_DIRECTORY` 替換為應用程式具有寫入權限的絕對或相對資料夾路徑。

程式執行後，您會在主控台看到確認檔案位置的訊息。 用任何影像檢視器開啟 PNG 檔，即可看到清晰的 **MacroPdf417 條碼**，其中已編碼您提供的文字與先前設定的中繼資料。

### 預期輸出

```
Barcode image saved to: C:\Projects\BarcodeDemo\ExtPDF417Meta.png
```

影像檔案大小大約在 30‑40 KB 左右，具體取決於所選的 `XDimension` 與欄位數。

## 驗證條碼與除錯

1. **目視檢查** – 條碼應呈現一系列堆疊的欄位，且四周有安靜區（白色邊緣）。  
2. **解碼測試** – 使用條碼掃描應用程式或 Aspose.BarCode 的 `BarCodeReader` 類別讀取影像，確認所有中繼資料欄位均正確嵌入。  



## 接下來您可以學習什麼？

以下教學與本指南的技術緊密相關，能進一步深化您對 API 功能的掌握，並探索在專案中實作的其他方式。

- [Generate PDF417 barcode image with Aspose.BarCode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/)
- [How to generate barcode with custom text using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/)
- [How to read barcodes from image using C# with Aspose.BarCode – step‑by‑step guide](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}