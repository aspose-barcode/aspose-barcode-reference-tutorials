---
category: general
date: 2026-08-09
description: Aspose 條碼範例示範如何使用 C# 條碼產生器建立具備完整中繼資料支援的 Macro PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode example
- barcode generator c#
language: zh-hant
lastmod: 2026-08-09
og_description: Aspose 條碼範例示範如何使用 C# 條碼產生器產生包含檔案 ID、段資料、時間戳記及其他中繼資料的 Macro PDF417
  條碼。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: Aspose 條碼範例 – 使用 C# 建立宏式 PDF417
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- Macro PDF417
title: Aspose 條碼範例：在 C# 中產生 Macro PDF417
url: /zh-hant/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose 條碼範例：在 C# 中產生 Macro PDF417

如果您需要一個 **aspose barcode example** 來建立 Macro PDF417 條碼，本指南將示範如何使用 **barcode generator C#** 完成。您將看到所有必需的設定，從基本尺寸到完整的 Macro PDF417 中繼資料欄位，最終會得到一個可供後續處理的 PNG 圖片。

本教學涵蓋完整工作流程，說明每個參數的重要性，並提供可直接執行的程式碼範例。無需外部參考；您只要複製程式碼、調整數值，即可立即執行。

## 前置條件

- .NET 6.0（或更新版本）已安裝  
- Visual Studio 2022 或任何相容 C# 的 IDE  
- 有效的 **Aspose.BarCode for .NET** 授權（此範例可使用免費試用版）  

將 Aspose.BarCode NuGet 套件加入您的專案：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立 barcode generator C# 實例

第一步是使用 `EncodeTypes.MacroPdf417` 列舉值以及您想要編碼的文字來實例化 `BarcodeGenerator`。文字可以包含 Unicode 字元，函式庫會自動處理。

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*為什麼這很重要*：`EncodeTypes.MacroPdf417` 告訴引擎產生 Macro PDF417 符號，支援分段資料與額外的檔案層級中繼資料。`using` 陳述式確保在儲存影像後釋放非受控資源。

## 步驟 2：定義條碼的基本外觀

Macro PDF417 條碼由方形模組組成。控制模組大小與欄位數會影響可讀性與檔案大小。

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*為什麼這很重要*：`XDimension.Pixels` 決定視覺密度；2 像素的值在螢幕顯示時效果良好且保持影像小巧。調整欄位數以符合您的版面限制——欄位越多會產生較寬、較短的條碼。

## 步驟 3：設定 Macro PDF417 專屬中繼資料

Macro PDF417 在標準 PDF417 格式上加入欄位，使得可從多個條碼片段重建大型檔案。每個欄位皆為選填，但設定它們可展示 API 的完整功能。

```csharp
    // Unique identifier for the entire file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (zero‑based)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the file
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Logical name of the source file
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

    // 16‑bit CCITT checksum for error detection
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate size of the original file in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;

    // Timestamp when the file was generated
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields for routing information
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the last segment
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*為什麼這很重要*：  
- `MacroPdf417FileID` 連結屬於同一邏輯檔案的所有片段。  
- `MacroPdf417SegmentID` 與 `MacroPdf417SegmentsCount` 讓解碼器能正確重新排序片段。  
- `MacroPdf417Checksum` 提供快速完整性檢查，無需解碼整個有效負載。  
- `MacroPdf417FileSize` 與 `MacroPdf417TimeStamp` 讓下游系統驗證重建檔案是否與原始檔案相符。  
- `MacroPdf417Addressee` / `MacroPdf417Sender` 在物流或文件交換情境中很有用。  
- 將 `MacroPdf417Terminator` 設為 `Set` 表示此條碼為最後一段，簡化重建演算法。

## 步驟 4：儲存產生的條碼影像

最後，將條碼寫入 PNG 檔案。您可以選擇任何支援的格式（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*為什麼這很重要*：PNG 保留無損像素資料，確保掃描器讀取您設定的精確模組圖樣。變更格式可能會影響視覺品質與檔案大小。

### 預期輸出

執行完整程式會產生名為 **ExtPDF417Meta.png** 的檔案。開啟影像會看到一個矩形的 Macro PDF417 條碼，編碼了文字 “Åspóse.Barcóde©”，且視覺密度符合您設定的 2 像素 X 維度。使用相容 PDF417 的讀取器掃描此影像，可返回第 3 步中定義的所有中繼資料欄位。

## 完整可執行範例

將以下程式碼複製到新的主控台專案（`dotnet new console`），並將 `YOUR_DIRECTORY` 替換為您機器上存在的絕對或相對路徑。

```csharp
using Aspose.BarCode.Generation;
using System;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a barcode generator for Macro PDF417 with the desired text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the basic barcode appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // pixel size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol

                // Step 3: Set Macro PDF417 specific metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the generated barcode image
                generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

執行程式（`dotnet run`）。執行完畢後，確認 PNG 檔案出現在您指定的位置。使用任何支援 Macro PDF417 的條碼讀取應用程式，確認中繼資料已正確嵌入。

## 常見變化與邊緣案例

- **不同的影像格式**：如果下游系統偏好其他格式，將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Tiff`。  
- **變更模組大小**：較大的 `XDimension.Pixels` 數值可提升低解析度掃描器的掃描可靠性，但會增加影像大小。  
- **多段式**：若要產生多段式檔案，產生一系列條碼，為每個條碼遞增 `MacroPdf417SegmentID`，且保持 `MacroPdf417FileID` 不變。只有最後一段應設定 `MacroPdf417Terminator`。  
- **Unicode 支援**：產生器會自動編碼 Unicode 字元；若從外部檔案讀取，請確保來源字串使用 UTF‑8 編碼。  
- **錯誤處理**：將 `using` 區塊包在 try‑catch 中，以捕捉 `BarCodeException`，處理無效參數（例如欄位數超出範圍）。

## 專業提示

- **效能**：在大量產生設定相同的條碼時，重複使用單一 `BarcodeGenerator` 實例；僅在儲存之間變更 `CodeText` 屬性。  
- **檔案大小估算**：`MacroPdf417FileSize` 欄位應與原始有效負載的位元組數相符；不符可能導致下游驗證失敗。  
- **測試**：使用 Aspose 內建的解碼器 (`BarCodeReader`) 以及第三方掃描器驗證產生的條碼，以確保相容性。

## 結論

這個 **aspose barcode example

## 接下來該學什麼？

以下教學涵蓋與本指南示範技術密切相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 建立條碼 – Compact PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 為 ITF-14 建立條碼靜區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}