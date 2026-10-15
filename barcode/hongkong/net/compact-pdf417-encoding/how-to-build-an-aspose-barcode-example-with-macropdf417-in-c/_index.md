---
category: general
date: 2026-10-12
description: 學習如何在 C# 中建立 Aspose 條碼範例，生成帶有完整元資料的 MacroPdf417 條碼，並使用 BarCodeReader
  讀取它。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- macroPdf417 barcode
- barcode metadata
- c# barcode generation
- BarCodeReader
language: zh-hant
lastmod: 2026-10-12
og_description: Aspose 條碼範例（C#）示範如何產生帶有嵌入式中繼資料的 MacroPdf417 條碼，並使用 BarCodeReader 讀回。
og_image_alt: Screenshot of an Aspose barcode example displaying a MacroPdf417 barcode
  with metadata
og_title: 在 C# 中建立使用 MacroPdf417 的 Aspose 條碼範例
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: Learn how to create an Aspose barcode example in C# that generates
    a MacroPdf417 barcode with full metadata and reads it back using BarCodeReader.
  headline: How to build an Aspose barcode example with MacroPdf417 in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Barcode
title: 如何在 C# 中使用 MacroPdf417 建立 Aspose 條碼範例
url: /zh-hant/net/compact-pdf417-encoding/how-to-build-an-aspose-barcode-example-with-macropdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 MacroPdf417 建立 Aspose 條碼範例

如果您需要一個 **aspose barcode example** 來建立 MacroPdf417 條碼並讀取其嵌入的中繼資料，本指南將展示完整的工作流程。您將會看到如何設定產生器、嵌入檔案層級資訊、儲存影像，然後使用 `BarCodeReader` 進行解碼。

本教學涵蓋了使用 Aspose.BarCode 進行 **C# barcode generation** 所需的全部知識，包含常見的陷阱與處理大型檔案 ID 或自訂時間戳記的技巧。

## 您需要的條件

* .NET 6.0 SDK 或更新版本（此程式碼可在 .NET Core 與 .NET Framework 上執行）
* Visual Studio 2022 或任何支援 C# 的 IDE
* 有效的 Aspose.BarCode 授權（免費試用可用於開發）
* 已在專案中安裝 NuGet 套件 `Aspose.BarCode`

上述前置條件可確保範例在不需額外設定的情況下執行。

## 步驟 1：設定 Aspose 條碼範例專案

建立一個新的主控台應用程式，並加入 Aspose.BarCode 函式庫：

```bash
dotnet new console -n AsposeMacroPdf417Demo
cd AsposeMacroPdf417Demo
dotnet add package Aspose.BarCode
```

`Aspose.BarCode` 套件提供 `BarcodeGenerator`、`BarCodeReader` 以及處理 MacroPdf417 所需的所有型別。

### 為何此步驟重要

加入 NuGet 套件可解決稍後使用的 `EncodeTypes`、`DecodeType` 與 `BarCodeImageFormat` 列舉。若未安裝套件，編譯器將無法辨識這些符號，導致範例在建置時失敗。

## 步驟 2：建立 MacroPdf417 條碼產生器

開啟 **Program.cs**，將範本程式碼替換為以下區塊。此區塊會建立一個針對 MacroPdf417 符號配置的 `BarcodeGenerator`，並設定基本的外觀參數。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Enums;
using System;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator with source text.
        using (BarcodeGenerator barcodeGenerator =
               new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample data"))
        {
            // Adjust the module size – 2 pixels per X‑dimension.
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Reduce the number of columns to keep the barcode compact.
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

            // Step 2.2: Embed MacroPdf417 metadata.
            // ---------------------------------------------------------
            // The following properties are optional but illustrate
            // how a full‑featured barcode can carry file‑level data.
            // ---------------------------------------------------------
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp =
                new DateTime(2024, 9, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator =
                Pdf417MacroTerminator.Set;

            // Step 2.3: Save the barcode image.
            const string outPath = "ExtPDF417Meta.png";
            barcodeGenerator.Save(outPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outPath}");
        }
```

#### 主要屬性說明

| Property | 目的 | 常見範圍 / 備註 |
|----------|------|----------------|
| `MacroPdf417FileID` | 整個檔案的唯一識別碼 | 必須 ≤ 2³¹‑1 |
| `MacroPdf417SegmentID` | 目前段落的索引 | 從 0 開始 |
| `MacroPdf417SegmentsCount` | 檔案中段落的總數 | 必須 ≥ SegmentID |
| `MacroPdf417FileName` | 檔案的可讀名稱 | 最多 255 個字元 |
| `MacroPdf417Checksum` | 原始檔案的 CCITT‑16 檢查碼 | 如有需要可由外部工具計算 |
| `MacroPdf417FileSize` | 原始檔案的位元組大小 | 有助於驗證 |
| `MacroPdf417TimeStamp` | 檔案建立的日期/時間 | 使用 UTC 以保持一致 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 可選的路由資訊 | 任意字串，最多 255 個字元 |
| `MacroPdf417Terminator` | 標示最後一個段落 | 最後段落使用 `Set` |

這些欄位構成 **barcode metadata**，讀取器之後可將其擷取。

## 步驟 3：解碼條碼並顯示中繼資料

儲存影像後，同一程式會使用 `BarCodeReader` 開啟檔案。請在先前的 `using` 區塊之後，於 `Main` 方法內加入以下程式碼：

```csharp
        // Step 3: Open the saved image with a MacroPdf417 reader.
        using (BarCodeReader barcodeReader =
               new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
        {
            // Step 3.1: Iterate through all decoded results.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // The Extended property holds the MacroPdf417 specific fields.
                var meta = result.Extended.Pdf417;
                Console.WriteLine($"FileID: {meta.MacroPdf417FileID}");
                Console.WriteLine($"SegmentID: {meta.MacroPdf417SegmentID}");
                Console.WriteLine($"SegmentsCount: {meta.MacroPdf417SegmentsCount}");
                Console.WriteLine($"FileName: {meta.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {meta.MacroPdf417Checksum}");
                Console.WriteLine($"FileSize: {meta.MacroPdf417FileSize}");
                Console.WriteLine($"Timestamp: {meta.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {meta.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {meta.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {meta.MacroPdf417Terminator}");
            }
        }
    }
}
```

### 為何回讀很重要

`BarCodeReader` 會驗證您嵌入的中繼資料是否正確編碼。若任何屬性缺失或超出範圍，讀取器會回傳 `null`，讓您能優雅地處理錯誤。

## 步驟 4：執行並驗證輸出

執行程式：

```bash
dotnet run
```

您應該會看到類似以下的主控台輸出：

```
Barcode saved to ExtPDF417Meta.png
FileID: 12345678
SegmentID: 12
SegmentsCount: 20
FileName: file01
Checksum: 1234
FileSize: 400000
Timestamp: 9/1/2024 12:00:00 AM
Addressee: street
Sender: aspose
Terminator: Set
```

若輸出的值與第 2 步設定的相符，則 **aspose barcode example** 如預期般運作。

## 邊緣情況與最佳實踐提示

| 情況 | 需留意的事項 | 推薦處理方式 |
|------|--------------|--------------|
| **FileID 超過 32 位元範圍** | Aspose 會拋出 `ArgumentOutOfRangeException`。 | 將 ID 保持 ≤ 2 147 483 647，或將檔案拆分為多個 MacroPdf417 區塊。 |
| **本地時間的時間戳記** | 其他時區的讀取器可能會誤解此值。 | 將時間戳記儲存為 UTC (`DateTime.UtcNow`)，必要時再於顯示時轉換。 |
| **檔案過大** | `MacroPdf417FileSize` 為 `int`；超過 2 GB 的值會發生溢位。 | 使用自訂欄位或將檔案拆分為較小的段落。 |
| **缺少段落** | 若 `SegmentID` 不連續，重建將失敗。 | 在編碼前驗證段落順序，或使用錯誤更正設定。 |
| **不支援的影像格式** | 儲存為 BMP 可能會大幅增加檔案大小。 | PNG 是不錯的預設；若接受有損壓縮，可使用 JPEG。 |

**專業提示：** 若批次產生大量條碼，請重複使用同一個 `BarcodeGenerator` 實例，僅變更 `EncodeTypes` 與來源文字。這可減少記憶體配置並提升處理速度。

## 您可能感興趣的相關主題

* **其他宏符號** – Aspose 亦支援具錯誤更正等級的 MacroPdf417。  
* **在 PDF 中嵌入條碼** – 結合 `Aspose.PDF` 與條碼產生器，以產生可列印的文件。  
* **ASP.NET Core 整合** – 從 Web API 直接提供產生的條碼。  
* **使用行動裝置掃描** – 使用 `Aspose.BarCode.Cloud` SDK 進行跨平台解碼。  

這些後續主題自然延伸 **aspose barcode example**，並加深您在 **C# barcode generation** 方面的專業知識。

## 結論

您現在已擁有一個完整功能的 **aspose barcode example**，可建立 MacroPdf417 條碼、嵌入豐富的 **barcode metadata**、儲存影像，並使用 `BarCodeReader` 讀回資料。依循上述步驟，即可將程式碼套用至不同的檔案 ID、時間戳記，甚至其他 Aspose 支援的條碼類型。

歡迎嘗試加入其他中繼資料欄位、變更影像格式，或將產生器整合至更大型的應用程式。祝開發愉快！

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}