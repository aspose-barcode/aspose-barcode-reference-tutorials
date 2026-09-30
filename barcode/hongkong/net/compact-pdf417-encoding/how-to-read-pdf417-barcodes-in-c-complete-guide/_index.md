---
category: general
date: 2026-08-22
description: 如何在 C# 中讀取 PDF417 條碼的逐步指南，涵蓋如何從圖像中讀取多個條碼以及提取 MacroPdf417 詳情。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: zh-hant
lastmod: 2026-08-22
og_description: 如何在 C# 中快速讀取 PDF417 條碼。本教學示範如何從圖像中讀取多個條碼並取得 MacroPDF417 的擴充資訊。
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: 如何在 C# 中讀取 PDF417 條碼 – 完整程式教學
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中讀取 PDF417 條碼 – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 條碼 – 完整指南

如果您需要在 .NET 應用程式中 **how to read PDF417** 條碼，本教學提供即時可執行的解決方案。您將學會如何從單一圖像讀取多個條碼、提取完整的 MacroPdf417 資料集，並在主控台顯示。此方法使用 Aspose.BarCode for .NET 函式庫，僅需幾行程式碼。

從圖像中讀取條碼是庫存系統、票證驗證與文件管理中的常見任務。完成本指南後，您將能解碼任何 PDF417 或 MacroPdf417 條碼、在同一張圖片中處理多個條碼，並了解 MacroPdf417 所提供的擴充欄位。

## 先決條件

- .NET 6.0 SDK 或更新版本（程式碼亦可在 .NET Framework 4.7+ 編譯）
- Visual Studio 2022 或您偏好的任何 C# 編輯器
- Aspose.BarCode for .NET NuGet 套件（`Install-Package Aspose.BarCode`）
- 一張包含 MacroPdf417 條碼的範例圖像（例如 `MacroPdf417.png`）

不需要額外的設定；函式庫會在內部處理圖像載入與解碼。

## 如何在 C# 中從圖像讀取 PDF417 條碼

此解決方案的核心是 `BarCodeReader` 類別。它會開啟圖像、偵測所有指定類型的條碼，並回傳 `BarCodeResult` 物件集合。以下程式碼示範完整的主控台程式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 為何每一行都很重要

| Step | Purpose |
|------|---------|
| **1️⃣ Initialize** | 建立一個綁定至圖像檔案的 `BarCodeReader`，並限制偵測為 MacroPdf417 符號，可加快處理速度。 |
| **2️⃣ Iterate** | `ReadBarCodes()` 會回傳 **所有** 符合請求類型的條碼，讓您 **read multiple barcodes** 而不需額外迴圈。 |
| **3️⃣ Basic output** | 顯示通用的 `CodeTypeName` 與可讀的 `CodeText`，方便記錄或快速驗證。 |
| **4️⃣ Extended data** | MacroPdf417 會攜帶額外的中繼資料（檔案 ID、段落數量、時間戳記等）。`Extended.Pdf417` 物件直接公開每個欄位，讓您能儲存或驗證完整的資料封包。 |

執行程式對有效的 MacroPdf417 圖像時，會產生類似以下的主控台輸出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

此輸出證實函式庫成功讀取條碼、擷取文字，並提供所有 MacroPdf417 欄位。

## 從單一圖像讀取多個條碼

許多實務情境會在同一標籤上放置多個 PDF417 符號——例如包含承運人代碼、追蹤號碼與海關申報的運輸清單。上述程式碼區塊已經 **read multiple barcodes**，因為 `ReadBarCodes()` 會回傳所有符合的列舉。無需額外設定，只要如示範般遍歷結果即可。

若您想將讀取器限制為標準 PDF417（非 macro），同時仍能處理多個條碼，只需將 `DecodeType.MacroPdf417` 改為 `DecodeType.Pdf417`。其餘邏輯保持不變。

## 了解 MacroPdf417 擴充資料

MacroPdf417 是一般 PDF417 規範的延伸。它將大型負載切割成多個段落，並加入描述整個檔案的小型標頭。最相關的欄位包括：

- **MacroPdf417FileID** – 同一檔案所有段落共享的唯一識別碼。
- **MacroPdf417SegmentID** – 目前段落的序號。
- **MacroPdf417SegmentsCount** – 預期的總段落數。
- **MacroPdf417FileName** – 隨條碼傳送的可選檔名。
- **MacroPdf417Checksum** – 整個檔案的錯誤檢查值。
- **MacroPdf417FileSize** – 原始二進位負載的大小。
- **MacroPdf417TimeStamp** – 條碼產生時的 ISO‑8601 時間戳記。
- **MacroPdf417Addressee / Sender** – 用於路由的可選文字欄位。
- **MacroPdf417Terminator** – 表示此段是否為最後一段。

當您收到所有段落後，可依 `MacroPdf417SegmentID` 排序，並將 `CodeText` 串接起來，以重建原始檔案。只要取得這些欄位，實作此邏輯相當直接。

## 常見陷阱與專業提示

- **Image quality matters** – 低解析度或高度壓縮的 PNG/JPEG 可能導致偵測遺漏。列印條碼時建議使用至少 300 dpi 的解析度。
- **Mixed symbologies** – 若圖像同時包含 MacroPdf417 與一般 PDF417，請為每個 `DecodeType` 建立兩個讀取器，或使用 `DecodeType.AllSupported` 後依 `result.CodeTypeName` 篩選結果。
- **Memory usage** – `using` 陳述式會即時釋放 `BarCodeReader`，避免大型圖像緩衝區長時間佔用記憶體。
- **Thread safety** – `BarCodeReader` 並非執行緒安全。若平行解碼圖像，請為每個執行緒建立獨立實例。
- **Error handling** – 將 `ReadBarCodes()` 包在 try/catch 中，以捕捉 `BarCodeException` 處理損毀的圖像。

## 完整範例回顧

以下是可直接複製到新主控台專案的完整程式碼。它包含所有 `using` 指示、圖像路徑常數，以及正確的釋放模式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

使用 `dotnet build` 編譯，並以 `dotnet run` 執行。主控台會列印每個條碼的基本資料與完整的 MacroPdf417 負載。

## 後續步驟

- **Reconstruct multipart files** – 收集所有段落，依 `MacroPdf417SegmentID` 排序，並將 `CodeText` 串接至

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Read PDF417 Barcodes with Turkish Characters in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [How to Use Aspose for PDF417 Barcode (Chinese) in Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}