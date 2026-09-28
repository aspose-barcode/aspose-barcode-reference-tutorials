---
category: general
date: 2026-07-21
description: 如何在 C# 中使用簡潔的條碼讀取範例讀取 PDF417 條碼。快速學會使用逐步程式碼從圖像中讀取條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode from image
- c# barcode reader example
language: zh-hant
lastmod: 2026-07-21
og_description: 如何在 C# 中使用實作範例讀取 PDF417 條碼。了解如何從圖像讀取條碼，並立即整合 C# 條碼讀取器範例。
og_image_alt: Screenshot of a C# console app printing PDF417 barcode details
og_title: 如何在 C# 中讀取 PDF417 – 完整條碼閱讀器教學
schemas:
- author: Aspose
  dateModified: '2026-07-21'
  description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  headline: How to Read PDF417 in C# – Complete Barcode Reader Example
  type: TechArticle
- description: How to read PDF417 barcode in C# using a concise barcode reader example.
    Quickly learn how to read barcode from image with step‑by‑step code.
  name: How to Read PDF417 in C# – Complete Barcode Reader Example
  steps:
  - name: Why This Works
    text: '- **`DecodeType.MacroPdf417`** tells the reader to expect the extended
      Macro PDF417 format, which carries extra metadata (file ID, segment count, timestamps,
      etc.). - The **`Extended.Pdf417`** object is only populated for Macro PDF417
      barcodes, so accessing those properties is safe after the `ReadBa'
  - name: Multiple Barcodes in One Image
    text: Sometimes a single scan contains more than one PDF417 segment (think of
      a multi‑page document encoded across several symbols). The `foreach` loop already
      enumerates *all* detected barcodes, so you don’t need extra logic—just collect
      the segments and reassemble them later if required.
  - name: Missing Extended Data
    text: 'Not every PDF417 carries macro information. In that scenario `result.Extended.Pdf417`
      will be instantiated but its fields will be default values (zero, empty string,
      or `false`). You can guard against it like this:'
  - name: Performance Tips
    text: '- **Batch processing:** If you have a folder of images, wrap the `BarCodeReader`
      creation inside a loop that reuses the same instance with `barcodeReader.SetImage(imagePath)`.
      This reduces allocation overhead. - **Parallelism:** For large workloads, consider
      `Parallel.ForEach` on the file list, but '
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 如何在 C# 中讀取 PDF417 – 完整條碼讀取器範例
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 – 完整條碼讀取範例

有沒有想過在 .NET 專案中 **如何讀取 PDF417**，卻不必翻閱無盡的文件？你並非唯一有此需求的人。無論是掃描駕照、登機證，或是自訂庫存標籤，可靠地提取這些資料都是實務上的需求。  

在本指南中，我們將逐步說明一個 **c# barcode reader example**，從單一圖像檔中提取所有 Macro PDF417 的中繼資料。完成後，你將擁有一個可直接執行的主控台應用程式，能 **reads barcode from image**，並列印出所有可能需要的擴充欄位。

## 需要的條件

- .NET 6.0 SDK 或更新版本（亦可目標 .NET Framework 4.7+ – 程式碼同樣適用）
- Visual Studio 2022、VS Code，或任何你喜歡的 C# 編輯器
- The **Aspose.BarCode for .NET** NuGet 套件（`BarCodeReader` 類別來自此函式庫）
- 包含 Macro PDF417 條碼的圖像檔（示範將使用 `ExtPDF417Meta.png`）

> **Pro tip:** 如果你手頭沒有 PDF417 範例，Aspose 在其 GitHub 倉庫中提供了幾張測試圖像 – 只需下載一張並放入你的專案資料夾。

## 步驟 1：安裝條碼函式庫

在專案資料夾中開啟終端機並執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此套件會加入我們稍後需要的 `BarCodeReader`、`DecodeType` 以及 `Extended` 屬性。無需額外設定；此函式庫即支援大多數圖像格式（PNG、JPEG、BMP 等）。

## 步驟 2：建立最小化主控台應用程式

如果尚未建立，先建立一個新的主控台專案：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
```

將產生的 `Program.cs` 替換為以下程式碼。請注意每個區段都有註解，即使你是條碼處理新手也能跟上邏輯。

```csharp
using System;
using Aspose.BarCode;               // Core barcode classes
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // 👉 1️⃣  Point the reader at the image that holds the Macro PDF417 barcode.
        //    Replace the path with your own image location if needed.
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The BarCodeReader is disposable – using a using‑statement guarantees resources are freed.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 👉 2️⃣  Iterate over every barcode that the reader finds.
            //    Macro PDF417 can embed multiple segments, so we handle them all.
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
            {
                // Basic barcode info – always handy for logging.
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // 👉 3️⃣  Pull out the extended Macro PDF417 fields.
                //    These properties live under result.Extended.Pdf417.
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
                Console.WriteLine(new string('-', 40)); // visual separator
            }
        }

        // Keep the console window open when debugging.
        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

### 為什麼這樣可行

- **`DecodeType.MacroPdf417`** 告訴讀取器預期為擴充的 Macro PDF417 格式，該格式會攜帶額外的中繼資料（檔案 ID、段落數量、時間戳記等）。
- **`Extended.Pdf417`** 物件僅在 Macro PDF417 條碼時會被填充，因此在呼叫 `ReadBarCodes()` 後存取這些屬性是安全的。
- 使用 **`using`** 區塊可確保檔案句柄被釋放，避免在 Windows 上出現檔案鎖定問題。

## 步驟 3：執行應用程式

編譯並執行：

```bash
dotnet run
```

如果圖像包含有效的 Macro PDF417 條碼，應會看到類似以下的輸出：

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: SampleDocument.pdf
Pdf417MacroChecksum: 0xABCD
Pdf417MacroFileSize: 102400
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
Done. Press any key to exit...
```

若沒有任何輸出，請再次確認圖像路徑是否正確，以及條碼是否確實為 Macro PDF417 變體。普通的 PDF417（未含 macro 擴充）仍會被解碼，但 `Extended` 屬性會是空的。

## 處理邊緣情況

### 單張圖像中多條條碼

有時一次掃描會包含多個 PDF417 段（例如跨多個符號編碼的多頁文件）。`foreach` 迴圈已經列舉 *所有* 偵測到的條碼，因此不需要額外的邏輯——只要收集這些段落，必要時再重新組合即可。

### 缺少擴充資料

並非所有 PDF417 都包含 macro 資訊。在此情況下，`result.Extended.Pdf417` 仍會被實例化，但其欄位會是預設值（0、空字串或 `false`）。你可以這樣防護：

```csharp
if (macro.MacroPdf417FileID != 0)
{
    // Process macro data
}
else
{
    Console.WriteLine("No macro information present in this barcode.");
}
```

### 效能建議

- **Batch processing:** 若有大量圖像資料夾，可在迴圈中包裹 `BarCodeReader` 的建立，使用 `barcodeReader.SetImage(imagePath)` 重複使用同一實例。這可減少分配開銷。
- **Parallelism:** 對於大量工作負載，可考慮對檔案清單使用 `Parallel.ForEach`，但需注意 Aspose 讀取器僅在每個執行緒使用各自的 `BarCodeReader` 實例時才是執行緒安全的。

## 完整原始碼清單（可直接複製貼上）

以下是完整程式碼，可直接放入 `Program.cs`。除了圖像檔外不需要其他額外檔案。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
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

        Console.WriteLine("Done. Press any key to exit...");
        Console.ReadKey();
    }
}
```

## 重點回顧：快速在 C# 中讀取 PDF417

- 透過 NuGet 安裝 **Aspose.BarCode**。
- 使用 `DecodeType.MacroPdf417` 將 `BarCodeReader` 指向你的圖像。
- 透過 `ReadBarCodes()` 迴圈取得基本與擴充欄位。
- 優雅地處理缺少的 macro 資料，並針對大量掃描考慮效能調整。

## 往後步驟與相關主題

- 使用其他格式（QR、DataMatrix）**Read barcode from image** – 只需切換 `DecodeType` 列舉值。
- 若需程式化產生條碼，可使用 `BarCodeGenerator` **Encode PDF417**。
- 探索 **error correction levels** 以及它們對掃描可靠性的影響。
- 將此邏輯整合至 ASP.NET Core API，將條碼讀取功能以 Web 服務方式提供。

隨意嘗試：更換圖像、調整 `DecodeType` 旗標，或將 macro 資料寫入資料庫。核心模式不變，現在你的工具箱中已擁有完整的 **c# barcode reader example**。

祝程式開發順利，願你的掃描永遠乾淨！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在本篇示範的技術之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)
- [如何使用 Aspose.BarCode 建立條碼 – Compact PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼安靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}