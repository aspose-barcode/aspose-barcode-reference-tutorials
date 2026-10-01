---
category: general
date: 2026-08-12
description: 使用 Aspose.BarCode 產生條碼，並在簡單的幾個步驟中學會如何產生帶自訂文字的 PDF417。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode aspose
- how to generate pdf417
- create barcode custom text
- Aspose.BarCode macro pdf417
- barcode metadata Aspose
language: zh-hant
lastmod: 2026-08-12
og_description: 使用 Aspose.BarCode 產生條碼。本教學示範如何產生帶有自訂文字、巨集元資料的 PDF417，並將結果儲存為 PNG。
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: 生成條碼 aspose – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Generate barcode aspose with Aspose.BarCode and learn how to generate
    pdf417 with custom text in a few easy steps.
  headline: Generate barcode aspose – complete C# guide
  type: TechArticle
tags:
- Aspose
- barcode
- pdf417
title: 生成條碼 Aspose – 完整 C# 指南
url: /zh-hant/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生條碼 aspose – 完整 C# 指南

如果您需要 **generate barcode aspose** 用於 MacroPdf417 符號，本教學將帶您完整步驟。您將看到如何設定宏特定選項、嵌入自訂文字，並將條碼儲存為 PNG 圖片。

使用 Aspose.BarCode 產生條碼可免除手動計算，並保證符合 PDF417 規範。以下步驟中，您還會學習 **how to generate pdf417**，以及如何加入檔案 ID、段落計數與時間戳記等自訂中繼資料。完成本指南後，您將擁有可直接放入任何 .NET 專案使用的程式碼範例。

## 前置條件

* .NET 6.0 或更新版本（程式碼亦相容 .NET Framework 4.7+）
* 有效的 Aspose.BarCode for .NET 授權（免費評估版可用於測試）
* Visual Studio 2022 或您偏好的任何 C# IDE
* 基本熟悉 C# 語法與物件導向概念

除了 **Aspose.BarCode** 之外，無需其他 NuGet 套件。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在 Visual Studio 中開啟您的專案，然後在套件管理員主控台執行以下指令：

```powershell
Install-Package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode` 命名空間，內含本教學中多次使用的 `BarcodeGenerator` 類別。

## 步驟 2：建立 MacroPdf417 的條碼產生器

第一行會建立一個 `BarcodeGenerator` 實例，目標為 **MacroPdf417** 符號，並嵌入您想要編碼的自訂文字。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

*Why this matters*：`EncodeTypes.MacroPdf417` 列舉告訴 Aspose 將條碼視為支援宏的 PDF417 符號，能將大量資料分割成多個段落。字串 `"Åspóse.Barcóde©"` 示範了產生器正確處理 Unicode 字元。

## 步驟 3：定義基本模組大小

模組大小決定條碼的視覺密度。像素值為 `2` 時，可產生清晰的圖像，適合在一般標籤印表機上列印。

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

增大此值會使條碼變大，降低則可能在低解析度裝置上造成掃描問題。

## 步驟 4：設定 PDF417 宏特定的版面配置選項

MacroPdf417 需要多項額外參數。這些設定可讓您將資料分割成多個檔案、辨識每個段落，並驗證完整性。

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

*Why this matters*：`Columns` 屬性會影響條碼寬度，而宏欄位（`FileID`、`SegmentID`、`SegmentsCount`、`FileName`）則讓下游系統能正確重組原始資料。

## 步驟 5：加入額外的宏中繼資料

Aspose.BarCode 允許您嵌入可選的宏欄位，如檢查碼、檔案大小、時間戳記以及發送者/接收者資訊。這些欄位對於稽核追蹤與錯誤偵測很有幫助。

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

*Why this matters*：檢查碼可防止傳輸錯誤，時間戳記與發送者欄位則為下游處理提供上下文。將 `MacroPdf417Terminator` 設為 `Set` 表示此段為宏系列的最後一段。

## 步驟 6：將條碼儲存為 PNG 圖片

最後，將產生的條碼寫入磁碟。PNG 保留無損品質，最適合掃描使用。

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

程式執行完畢後，檔案 `ExtPDF417Meta.png` 會包含高解析度的 MacroPdf417 條碼，內含自訂文字與所有宏中繼資料。

### 預期輸出

開啟 `ExtPDF417Meta.png` 會看到垂直排列的條碼，列與欄清晰可見。使用任何 PDF417 讀取器掃描此圖像，會回傳原始字串 **Åspóse.Barcóde©** 以及您設定的宏欄位（檔案 ID、段落 ID、檢查碼等）。

## 如何在不使用宏選項的情況下產生 pdf417（替代情境）

如果您只需要標準的 PDF417 條碼，請省略宏屬性，僅保留基本設定：

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

此程式碼片段示範了在不需要宏功能時，如何快速 **how to generate pdf417**。

## 常見陷阱與專業技巧

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| 條碼太小無法掃描 | X‑dimension 設為 1 像素或欄位數過高 | 將 `XDimension` 設為至少 `2` 像素，且欄位數保持在 `3` 到 `9` 之間，以符合一般標籤尺寸 |
| Unicode 字元顯示為 � | 專案檔案的編碼不匹配 | 確保專案檔案儲存為 UTF‑8，且來源檔案包含正確的 BOM |
| 掃描器忽略宏欄位 | `MacroPdf417Terminator` 未在最後一段設定 | 在最後一段設定 `MacroPdf417Terminator = Pdf417MacroTerminator.Set` |
| 影像檔案損毀 | 輸出串流未正確關閉 | 使用 `using` 陳述式（如範例所示）以確保產生器正確釋放 |

## 完整、可執行範例

將以下程式碼複製到新的主控台應用程式中並執行。程式會產生條碼、儲存檔案，並在主控台印出輸出路徑。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

執行程式後會印出類似以下的行：

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

開啟該檔案以驗證視覺輸出。

## 結論

現在您已了解如何 **generate barcode aspose** 用於 MacroPdf417 符號、嵌入自訂 Unicode 文字、設定宏中繼資料，並將結果匯出為 PNG 圖片。同樣的模式也可讓您 **how to generate pdf417** 在不使用宏選項的情況下，且可將程式碼套用至 Aspose.BarCode 支援的其他條碼格式。

接下來，您可以探索相關主題，例如 QR Code 的 **create barcode custom text**、使用 `Color` 參數加入顏色濾鏡，或使用 Aspose.PDF 將條碼直接嵌入 PDF 文件。嘗試不同的 `XDimension` 值與欄位數，以微調條碼以符合您的印表機或掃描器。

祝開發順利，並體驗 Aspose.BarCode 為您的 .NET 條碼解決方案帶來的可靠性！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，建立在所示技巧之上。每個資源皆提供完整可運作的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [產生條碼 Java - 使用 Aspose.BarCode 設定程式碼文字](/barcode/english/java/text-and-styling/setting-code-text/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}