---
category: general
date: 2026-09-22
description: 學習如何在 C# 中讀取 PDF417 條碼，並提供完整的條碼閱讀器範例。本教學示範如何快速且可靠地在 C# 讀取條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read barcode image c#
- c# barcode reader example
language: zh-hant
lastmod: 2026-09-22
og_description: 如何在 C# 中使用簡潔的條碼閱讀器範例讀取 PDF417 條碼。跟隨本指南解碼 Macro PDF417 圖像並提取元資料。
og_image_alt: Screenshot of C# code that reads a PDF417 barcode and prints its metadata
og_title: 如何在 C# 中讀取 PDF417 條碼 – 完整條碼閱讀器範例
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  headline: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcodes in C# with a full barcode reader
    example. This tutorial shows you how to read barcode image C# quickly and reliably.
  name: How to read PDF417 barcodes in C# – complete step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '1. **Creating the reader with `DecodeType.MacroPdf417`** – Macro PDF417
      is a special variant that can carry file‑level metadata. Specifying the decode
      type ensures the SDK parses those extra fields instead of treating the code
      as a plain PDF417. 2. **Iterating over `ReadBarCodes()`** – An image can '
  - name: Reading a non‑macro PDF417 barcode
    text: If your source images contain regular PDF417 codes (no macro metadata),
      replace `DecodeType.MacroPdf417` with `DecodeType.Pdf417`. The rest of the code
      stays identical, but the `Extended.Pdf417` block will be empty because those
      fields simply don’t exist.
  - name: Handling multi‑segment PDFs
    text: 'Macro PDF417 can split a large document across several barcode segments.
      To reassemble the original file you must:'
  - name: Dealing with corrupted images
    text: '- **Low contrast** – Increase image preprocessing (e.g., histogram equalization)
      before passing it to `BarCodeReader`. - **Rotation** – Use `barcodeReader.SetRotateAngle(90)`
      or enable auto‑rotate if the SDK supports it. - **Partial scans** – Ensure the
      image resolution is at least 300 dpi; otherwis'
  - name: Next steps
    text: '- Explore **read barcode image C#** techniques for other symbologies (QR,
      DataMatrix) using the same `BarCodeReader` API. - Integrate the barcode decoder
      into an ASP.NET Core service to process uploads on the fly. - Experiment with
      image preprocessing libraries (e.g., `OpenCvSharp`) to boost success'
  type: HowTo
tags:
- barcode
- pdf417
- c#
title: 如何在 C# 中讀取 PDF417 條碼 – 完整逐步指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 條碼 – 完整步驟指南

如果你需要在 .NET 應用程式中 **how to read pdf417**，本指南會提供完整的程式碼與說明。閱讀完前兩句，你就會知道如何使用熱門的 `BarCodeReader` 類別在 C# 中讀取條碼影像，並且擁有一個可直接執行的範例，能夠擷取所有 Macro PDF417 的中繼資料。

在處理運送標籤、登機證或安全文件時，讀取 PDF417 條碼是常見需求。本教學涵蓋從設定讀取器到處理例外情況的全部步驟，讓你能自信地整合條碼掃描功能。

## 你將達成的目標

- 解碼 Macro PDF417 影像檔。
- 列印基本條碼資訊（類型與文字）。
- 取得所有 Macro PDF417 延伸欄位，如檔案 ID、段落數量與時間戳記。
- 了解處理多段 PDF417 代碼時的常見陷阱。

**先決條件**

- .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.7+）。
- 參考提供 `BarCodeReader`、`DecodeType` 與 `BarCodeResult` 的條碼 SDK（例如 Aspose.BarCode、Dynamsoft，或任何具相同 API 的函式庫）。
- 一張包含 Macro PDF417 條碼的影像檔（`ExtPDF417Meta.png`）。

> **專業小技巧：** 將影像放在相對於專案根目錄的資料夾中，並將其 **Copy to Output Directory** 屬性設為 *Copy if newer*，以確保除錯時路徑正確。

![如何使用 C# 讀取 PDF417 條碼](https://example.com/placeholder-image.png)

## 如何在 C# 中讀取 PDF417 條碼 – 完整程式碼

以下是一個可直接貼入主控台應用程式的完整範例。它會建立條碼讀取器、遍歷每個解碼結果，並印出標準與延伸的 Macro PDF417 欄位。

```csharp
using System;
using Aspose.BarCode;          // Replace with the namespace of your barcode SDK
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode reader for a Macro PDF417 image
        // The second argument tells the SDK to look specifically for Macro PDF417 codes.
        using var barcodeReader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417);

        // Step 2: Decode all barcodes present in the image
        foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
        {
            // Step 3: Display the basic barcode information
            Console.WriteLine($"CodeType: {result.CodeTypeName}");
            Console.WriteLine($"CodeText: {result.CodeText}");

            // Step 4: Output Macro PDF417 specific metadata
            // All properties are available through the Extended.Pdf417 object.
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
}
```

### 為什麼每一步都很重要

1. **使用 `DecodeType.MacroPdf417` 建立讀取器** – Macro PDF417 是可攜帶檔案層級中繼資料的特殊變體。指定解碼類型可讓 SDK 解析這些額外欄位，而不是將條碼當作普通 PDF417 處理。
2. **遍歷 `ReadBarCodes()`** – 一張影像可能包含多個條碼（例如 QR Code 與 PDF417 同時出現）。此迴圈確保你捕捉到所有結果。
3. **列印 `CodeTypeName` 與 `CodeText`** – 這兩個屬性最常使用，分別提供符號名稱與可讀的資料內容。
4. **存取 `Extended.Pdf417`** – `Extended` 物件僅在 PDF417 相關的解碼類型時出現。每個屬性直接對應 Macro PDF417 規範，讓你能重建原始檔案或驗證段落順序。

## 常見變化與例外情況

### 讀取非 Macro PDF417 條碼

如果來源影像僅包含普通 PDF417（沒有 macro 中繼資料），請將 `DecodeType.MacroPdf417` 改為 `DecodeType.Pdf417`。其餘程式碼保持不變，但 `Extended.Pdf417` 區塊會是空的，因為那些欄位根本不存在。

### 處理多段 PDF

Macro PDF417 可以將大型文件分割成多個條碼段落。要重新組合原始檔案，你必須：

1. 收集每個段落的 `Pdf417MacroSegmentID`。
2. 依 ID 排序段落。
3. 驗證 `Pdf417MacroSegmentsCount` 與收到的段落數相符。
4. 按順序串接每個段落的 `CodeText`。
5. （可選）驗證 `Pdf417MacroChecksum`。

以下是一段簡潔的程式碼，示範重組邏輯：

```csharp
var segments = new SortedDictionary<int, string>();
int expectedCount = 0;

foreach (var result in barcodeReader.ReadBarCodes())
{
    int segId = result.Extended.Pdf417.MacroPdf417SegmentID;
    int segCount = result.Extended.Pdf417.MacroPdf417SegmentsCount;
    expectedCount = segCount;               // will be the same for every segment
    segments[segId] = result.CodeText;       // store payload by segment ID
}

// Verify we have all parts
if (segments.Count == expectedCount)
{
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine("Reassembled payload:");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Missing segments: expected {expectedCount}, received {segments.Count}");
}
```

### 處理受損影像

- **對比度低** – 在傳入 `BarCodeReader` 前加強影像前處理（例如直方圖均衡化）。
- **旋轉** – 使用 `barcodeReader.SetRotateAngle(90)` 或啟用自動旋轉（若 SDK 支援）。
- **部分掃描** – 確保影像解析度至少 300 dpi，否則 SDK 可能遺漏小段落。

## c# barcode reader example – 最佳實踐

| 實踐 | 原因 |
|------|------|
| **使用 `using` 釋放讀取器** | 確保原生資源即時釋放，防止記憶體泄漏。 |
| **驗證 `result.Extended` 不為 null** | 某些 SDK 於非 macro 條碼會回傳 `null`，檢查可避免 `NullReferenceException`。 |
| **記錄 `Pdf417MacroFileID`** | 此識別碼對每個檔案唯一，對稽核追蹤很有幫助。 |
| **將解碼包在 try/catch 中** | I/O 錯誤（檔案遺失）或不支援的格式會拋出例外，需妥善處理。 |

```csharp
try
{
    // decoding logic here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image not found: {ex.FileName}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode decoding failed: {ex.Message}");
}
```

## 預期輸出

在正確的 `ExtPDF417Meta.png` 上執行完整程式後，會得到類似以下的輸出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-08-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

若影像包含多個段落，迴圈會依序列印每個段落的中繼資料。

## 結論

現在你已掌握 **how to read pdf417** 條碼的 C# 實作，並擁有一個 **c# barcode reader example**，能夠擷取所有 Macro PDF417 欄位。此解決方案涵蓋基本解碼、元資料擷取、多段重組與錯誤處理，為任何文件處理工作流提供可直接投入生產環境的基礎。

### 後續步驟

- 探索 **read barcode image C#** 的其他符號（QR、DataMatrix）使用相同的 `BarCodeReader` API。
- 將條碼解碼器整合至 ASP.NET Core 服務，實時處理上傳檔案。
- 嘗試使用影像前處理函式庫（如 `OpenCvSharp`）提升低品質掃描的成功率。

祝開發順利，歡迎依需求自行調整範例！

## 接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步延伸本指南所示的技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能，並在專案中探索替代實作方式。

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [How to Read PDF417 in C# – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}