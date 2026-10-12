---
category: general
date: 2026-09-19
description: 如何在 C# 中解碼 PDF417 – 透過簡潔的條碼讀取範例，學習從圖像讀取條碼，並提取完整的 Macro PDF417 資料。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcodes from image
- decode pdf417 barcode
- c# barcode reader example
language: zh-hant
lastmod: 2026-09-19
og_description: 如何在 C# 中使用一步一步的條碼閱讀器範例解碼 PDF417。只需數秒即可從圖像中提取所有 Macro PDF417 欄位。
og_image_alt: Screenshot showing how to decode PDF417 in C# using a barcode reader
og_title: 如何在 C# 中解碼 PDF417 – 完整條碼閱讀器指南
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to decode PDF417 in C# – learn to read barcodes from image using
    a concise barcode reader example that extracts full Macro PDF417 data.
  headline: How to decode PDF417 in C# with a barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: 如何在 C# 中使用條碼閱讀器範例解碼 PDF417
url: /zh-hant/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼閱讀器範例解碼 PDF417

如果您需要在 C# 中解碼 PDF417，本指南將逐步說明如何從影像檔案中解碼 PDF417。您將學會從影像讀取條碼、存取擴充的 Macro PDF417 欄位，並將此解決方案整合至任何 .NET 專案中。

在物流、票務與身份驗證等領域，解碼 PDF417 條碼相當常見。本教學涵蓋了生產環境所需的全部內容，包括前置套件、完整原始碼，以及處理例外情況的技巧。

## 前置條件

- .NET 6.0 或更新版本已安裝  
- Visual Studio 2022（或任何支援 C# 的 IDE）  
- Aspose.BarCode for .NET NuGet 套件（版本 23.11 或更新）

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

`BarCodeReader` 類別支援 `MacroPdf417` 解碼類型，可用於完整的 PDF417 抽取。

## 步驟 1：如何在 C# 中解碼 PDF417 – 初始化閱讀器

第一步會建立針對 Macro PDF417 影像的 `BarCodeReader` 實例。`DecodeType.MacroPdf417` 旗標告訴函式庫解析擴充的 Macro 欄位。

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // Reader and result types

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for Macro PDF417 decoding
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Continue with step 2...
```

**為何重要：** 使用 `MacroPdf417` 初始化後，每個 `BarCodeResult` 皆會啟用 `Extended.Pdf417` 屬性，讓您取得檔案層級的中繼資料，例如段落 ID 與時間戳記。

## 步驟 2：從影像讀取條碼

PDF417 影像可能包含多個 macro 段落。`ReadBarCodes()` 方法會回傳所有偵測到的條碼集合，您可以安全地遍歷它們。

```csharp
    // Step 2: Read every barcode present in the image
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Continue with step 3...
```

**提示：** 若您只預期單一條碼，可在第一次迭代後即跳出，但遍歷所有結果可確保在多頁文件中捕捉到每個段落。

## 步驟 3：解碼 PDF417 條碼 – 抽取基本與擴充資料

在迴圈內，同時輸出一般條碼資訊與 Macro 專屬欄位。`Extended.Pdf417` 物件包含 PDF417 標準定義的所有中繼資料。

```csharp
        // Basic barcode information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");

        // Macro PDF417 extended data
        Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
    }
}
```

**關鍵欄位說明**

| 欄位 | 說明 |
|-------|----------|
| `MacroPdf417FileID` | 將屬於同一邏輯檔案的所有段落分組的識別碼 |
| `MacroPdf417SegmentID` | 目前段落的索引（從 0 開始） |
| `MacroPdf417SegmentsCount` | 檔案預期的總段落數 |
| `MacroPdf417FileName` | 嵌入於 macro 中的可選檔名 |
| `MacroPdf417Checksum` | 用於資料完整性的 CRC‑16 檢查碼 |
| `MacroPdf417FileSize` | 原始檔案大小（位元組） |
| `MacroPdf417TimeStamp` | macro 產生的時間戳記 |
| `MacroPdf417Addressee` | macro 資料的預期收件人 |
| `MacroPdf417Sender` | macro 資料的發送者 |
| `MacroPdf417Terminator` | 指示最後段落的布林旗標 |

取得這些欄位後，您即可重建原始文件、驗證完整性，或依據發送者/收件者資訊進行資料路由。

## 步驟 4：完整 C# 條碼閱讀器範例 – 整合所有步驟

以下為完整可執行的程式。請將 `YOUR_DIRECTORY` 替換為存放 `MacroPdf417.png` 檔案的資料夾路徑。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417Decoder
{
    class Program
    {
        static void Main()
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // Initialise the reader for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate through all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic information
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Extended Macro PDF417 data
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete.");
        }
    }
}
```

**預期的主控台輸出（範例）**

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 452312
Pdf417MacroTimeStamp: 2024-03-15T14:27:00Z
Pdf417MacroAddressee: LogisticsDept
Pdf417MacroSender: Warehouse01
MacroPdf417Terminator: False
----------------------------------------
Decoding complete.
```

實際數值會依您的 Macro PDF417 條碼內容而異。

## 處理常見例外情況

| 情況 | 建議做法 |
|-----------|----------------------|
| **未偵測到條碼** | 確認影像路徑、確保檔案未損毀，並檢查條碼是否清晰可見（對比度足夠）。 |
| **部分 macro 段落缺失** | 利用 `MacroPdf417SegmentsCount` 偵測缺少的段落。可向來源系統請求剩餘段落，然後重新執行解碼器。 |
| **大型影像導致記憶體壓力** | 在傳入 `BarCodeReader` 前，先以較低解析度載入影像至 `System.Drawing.Bitmap`。 |
| **非 Macro PDF417** | 若僅需純條碼文字，將 `DecodeType.MacroPdf417` 改為 `DecodeType.Pdf417`。 |

## 專業技巧

- **批次處理：** 將閱讀器邏輯封裝於接受檔案路徑清單的方法中。每個執行緒重複使用同一個 `BarCodeReader` 實例，以降低配置開銷。  
- **效能：** 在高吞吐量情境下，啟用 `ReaderOptions` 的 `ReadQuality` 屬性，以在速度與準確度之間取得平衡。  
- **安全性：** 在將 `CodeText` 用於檔案系統操作前先進行驗證，以防止路徑穿越攻擊。

## 結論

在本教學中，您學會了如何在 C# 中透過讀取影像條碼、抽取所有 Macro PDF417 欄位，並建立完整的 C# 條碼閱讀器範例來解碼 PDF417。此解決方案相容最新的 Aspose.BarCode 函式庫，能處理多段 macro，並提供實務上專案的實用指引。

接下來，您可以探索相關主題，例如 **讀取 QR Code**、**批次條碼處理** 與 **產生 PDF417 條碼**，以擴充文件自動化工具箱。歡迎嘗試不同的影像來源、將程式碼整合至 ASP.NET 服務，或延伸至將抽取的中繼資料儲存至資料庫。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何在 C# 中讀取 PDF417 – 完整條碼閱讀器範例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [如何使用 Aspose 在 C# 中產生 PDF417 條碼影像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [從影像讀取條碼 – C# 條碼閱讀器範例](/barcode/english/net/one-dimensional-barcode-types/read-barcode-from-image-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}