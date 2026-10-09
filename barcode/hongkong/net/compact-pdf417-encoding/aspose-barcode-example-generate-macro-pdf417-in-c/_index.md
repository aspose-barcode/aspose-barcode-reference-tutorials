---
category: general
date: 2026-10-09
description: 了解如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼 – 產生具備完整 metadata 支援的 Macro
  PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- macro pdf417 c#
- aspose barcode c#
- barcode generator c#
lastmod: 2026-10-09
og_description: 了解如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼 – 產生具備完整 metadata 支援的 Macro
  PDF417，包含 file ID、segment data、timestamp 等資訊。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with Aspose.BarCode in
  C#
og_title: 如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼
schemas:
- author: Aspose
  dateModified: '2026-10-09'
  description: Aspose barcode example showing how to use a barcode generator C# to
    create a Macro PDF417 with full metadata support.
  headline: 'Aspose barcode example: generate Macro PDF417 in C#'
  type: TechArticle
tags:
- aspose barcode
- pdf417 barcode
- c# barcode generation
- macro pdf417
title: 如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼

如果您需要快速且可靠地 **建立 PDF417 條碼 C#**，本教學將帶您使用 Aspose.BarCode 完整完成整個流程。您將看到所有必須的設定，從基本尺寸到完整的 Macro PDF417 中繼資料欄位，最後產出可供後續處理的 PNG 影像。

## 快速答案

- **哪個函式庫可產生 PDF417 條碼？** Aspose.BarCode for .NET。  
- **範例輸出什麼格式？** 無失真 PNG 圖片。  
- **是否需要授權？** 免費試用版可用於範例；正式環境需購買商業授權。  
- **支援哪個 .NET 版本？** .NET 6.0 或更新版本。  
- **我可以在條碼中加入中繼資料嗎？** 可以 – Macro PDF417 支援檔案 ID、段落數量、時間戳記等。

## 什麼是 PDF417 條碼？

PDF417 條碼是一種堆疊式線性符號，可在每個符號中編碼約 1 KB 的資料，並支援可選的宏中繼資料以處理多段檔案。它由多列堆疊的線性圖案組成，提供高資料容量，同時仍能被標準 2‑D 掃描器讀取。此格式亦包含錯誤更正等級以提升可靠性，且可選的宏功能允許將大型檔案分割成多個條碼，並透過中繼資料協助重新組合。

## 為何使用 Aspose.BarCode 產生 PDF417？

Aspose.BarCode 支援 **超過 50 種條碼符號**，且可產生最多 **2 000 欄** 的 Macro PDF417 條碼，處理超過 **10 MB** 的檔案而不必將整個負載載入記憶體。此量化能力確保高吞吐量企業情境順暢執行，並提供廣泛的自訂選項。

## 前置條件

開始之前，請確保您已安裝：

- .NET 6.0（或更新版本）  
- Visual Studio 2022 或任何相容 C# 的 IDE  
- 有效的 **Aspose.BarCode for .NET** 授權（免費試用版可用於本範例）  

將 Aspose.BarCode NuGet 套件加入您的專案：

```bash
dotnet add package Aspose.BarCode
```

## 如何在 C# 中建立 PDF417 條碼？

`BarcodeGenerator` 是建立條碼影像的主要類別。  
`EncodeTypes.MacroPdf417` 用於選取 Macro PDF417 符號以產生條碼。  
`Save` 將產生的條碼寫入影像檔案。

以 `EncodeTypes.MacroPdf417` 列舉值與目標文字載入 `BarcodeGenerator`，然後呼叫 `Save` —— 這就是三行完成的完整建立流程。產生器會自動處理 Unicode，且 `using` 陳述式確保影像儲存後釋放非受控資源。

### 步驟 1：建立條碼產生器 C# 實例

`BarcodeGenerator` 類別負責建立與設定條碼影像。

使用 `EncodeTypes.MacroPdf417` 列舉值與欲編碼的文字實例化 `BarcodeGenerator`。文字可包含 Unicode 字元，函式庫會自動處理。

```csharp
using Aspose.BarCode.Generation;
using System;

using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // Subsequent steps are performed inside this using block.
```

*為何重要*：`EncodeTypes.MacroPdf417` 告訴引擎產生 Macro PDF417 符號，支援分段資料與額外的檔案層級中繼資料。`using` 陳述式確保影像儲存後釋放非受控資源。

### 步驟 2：定義條碼基本外觀

`XDimension.Pixels` 設定每個條碼模組的像素大小。

Macro PDF417 條碼由方形模組組成。控制模組大小與欄位數會同時影響可讀性與檔案大小。

```csharp
    // Pixel size of a single module (X dimension)
    generator.Parameters.Barcode.XDimension.Pixels = 2;

    // Number of columns in the symbol; fewer columns produce a taller barcode
    generator.Parameters.Barcode.Pdf417.Columns = 5;
```

*為何重要*：`XDimension.Pixels` 決定視覺密度；2 像素的設定在螢幕顯示時效果良好且保持影像小巧。依需求調整欄位數以符合版面限制——欄位越多條碼越寬、越短。

### 步驟 3：設定 Macro PDF417 專屬中繼資料

`MacroPdf417FileID` 用於識別所有條碼段屬於同一檔案。

Macro PDF417 在標準 PDF417 基礎上加入欄位，使得可從多個條碼段重建大型檔案。每個欄位皆為選用，但設定它們即可展示 API 的完整功能。

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

*為何重要*：  
- `MacroPdf417FileID` 連結屬於同一邏輯檔案的所有段落。  
- `MacroPdf417SegmentID` 與 `MacroPdf417SegmentsCount` 讓解碼器能正確重新排序片段。  
- `MacroPdf417Checksum` 提供快速完整性檢查，無需解碼整個負載。  
- `MacroPdf417FileSize` 與 `MacroPdf417TimeStamp` 讓下游系統驗證重建檔案是否與原始檔案相符。  
- `MacroPdf417Addressee` / `MacroPdf417Sender` 在物流或文件交換情境中相當有用。  
- 將 `MacroPdf417Terminator` 設為 `Set` 表示此條碼為最後一段，簡化重建演算法。

### 步驟 4：儲存產生的條碼影像

`Save` 將條碼影像寫入指定的檔案路徑。

最後，將條碼寫入 PNG 檔案。您也可以選擇任何支援的格式（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。

```csharp
    // Save the barcode image to the specified path
    generator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*為何重要*：PNG 保留無失真的像素資料，確保掃描器讀取您設定的模組圖樣。變更格式可能會影響視覺品質與檔案大小。

#### 預期輸出

執行完整程式會產生名為 **ExtPDF417Meta.png** 的檔案。開啟影像可見一個矩形的 Macro PDF417 條碼，編碼文字為 “Åspóse.Barcóde©”，且視覺密度符合您設定的 2 像素 XDimension。使用相容 PDF417 讀取器掃描此影像，即可取得第 3 步設定的所有中繼資料欄位。

## 完整範例

將下列程式碼複製到新的主控台專案（`dotnet new console`），並將 `YOUR_DIRECTORY` 替換為您機器上實際存在的絕對或相對路徑。

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

執行程式（`dotnet run`）。執行完畢後，請確認 PNG 檔案出現在您指定的位置。使用任何支援 Macro PDF417 的條碼讀取應用程式，驗證中繼資料是否正確嵌入。

## 常見變形與邊緣情況

- **不同影像格式**：若下游系統偏好其他格式，可將 `BarCodeImageFormat.Png` 改為 `Jpeg`、`Bmp` 或 `Tiff`。  
- **變更模組大小**：較大的 `XDimension.Pixels` 數值可提升低解析度掃描器的掃描可靠性，但會增加影像檔案大小。  
- **多段條碼**：若要產生多段檔案，請產生一系列條碼，為每個條碼遞增 `MacroPdf417SegmentID`，且保持 `MacroPdf417FileID` 不變。最後一段須將 `MacroPdf417Terminator` 設為 `Set`。  
- **Unicode 支援**：產生器會自動編碼 Unicode 字元；若從外部檔案讀取字串，請確保使用 UTF‑8 編碼。  
- **錯誤處理**：將 `using` 區塊包在 try‑catch 中，以捕捉 `BarCodeException`，處理參數錯誤（例如欄位數超出範圍）。

## 專業提示

- **效能**：在大量產生條碼且設定相同的情況下，重複使用同一個 `BarcodeGenerator` 實例；只在每次儲存前變更 `CodeText` 屬性。  
- **檔案大小估算**：`MacroPdf417FileSize` 欄位應與原始負載的位元組數相符；不符可能導致下游驗證失敗。  
- **測試**：同時使用 Aspose 內建的解碼器（`BarCodeReader`）與第三方掃描器驗證產生的條碼，確保相容性。

## 結論

本 **Aspose.BarCode** 範例示範了如何使用 **C#** 建立具備完整 Macro 中繼資料的 PDF417 條碼，為建構穩健的條碼資料交換管線奠定了堅實基礎。

## 接下來該學什麼？

以下教學與本指南所示技術緊密相關，提供完整的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何建立條碼 – 緊湊型 PDF417（使用 Aspose.BarCode）](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 為 ITF-14 建立條碼靜區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

---

**最後更新：** 2026-10-09  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何在 C 中使用 Aspose 產生 Pdf417 條碼影像](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [如何建立條碼 – 緊湊型 PDF417（使用 Aspose.BarCode）](/barcode/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [條碼產生器教學：如何產生 Pdf417 條碼](/barcode/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}