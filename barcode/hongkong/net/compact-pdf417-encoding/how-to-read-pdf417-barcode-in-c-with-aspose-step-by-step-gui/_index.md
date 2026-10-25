---
category: general
date: 2026-10-24
description: 學習如何在 C# 中使用 Aspose.BarCode 讀取 PDF417 條碼。本教程涵蓋讀取條碼圖像、提取 Macro PDF417
  欄位以及處理常見情況。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode image c#
- read barcode with aspose
language: zh-hant
lastmod: 2026-10-24
og_description: 如何在 C# 中使用 Aspose.BarCode 讀取 PDF417 條碼。跟隨本完整教學解碼圖像、取得宏 PDF417 元資料，並避免常見陷阱。
og_image_alt: Screenshot showing how to read PDF417 barcode results in a C# console
  application
og_title: 如何在 C# 中使用 Aspose 讀取 PDF417 條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-24'
  description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  headline: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Learn how to read PDF417 barcode in C# using Aspose.BarCode. This tutorial
    covers reading a barcode image, extracting Macro PDF417 fields, and handling common
    scenarios.
  name: How to read PDF417 barcode in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why use `DecodeType.MacroPdf417`?
    text: '* **Macro PDF417** stores additional fields (file ID, segment count, timestamps,
      etc.) that are not present in standard PDF417. * The `Extended` property of
      `BarCodeResult` is populated only when you request the macro type, saving you
      a separate parsing step.'
  - name: What each property means
    text: '| Property | Description | |----------|-------------| | **MacroPdf417FileID**
      | Unique identifier for the whole multi‑segment document. | | **MacroPdf417SegmentID**
      | Index of the current segment (starting at 0). | | **MacroPdf417SegmentsCount**
      | Total number of segments that belong to the file. | '
  - name: Missing macro fields
    text: 'Sometimes a PDF417 barcode is generated without the optional macro fields.
      Accessing a missing property returns `null` or `0`. Guard against this if you
      plan to store the values:'
  - name: Corrupted or low‑quality images
    text: 'If the image is blurry, you can improve detection by enabling the `BarCodeReader`
      quality options:'
  - name: Multiple barcode formats in one image
    text: 'If you suspect other barcode types might be present, use `DecodeType.AllSupported`
      and filter results:'
  type: HowTo
- questions:
  - answer: Yes. Change `DecodeType.MacroPdf417` to `DecodeType.Pdf417`. The `Extended`
      property will be empty, but `CodeText` and `CodeTypeName` remain available.
    question: Can I read a standard PDF417 (non‑macro) with the same code?
  - answer: Absolutely. Use the overload `new BarCodeReader(Stream, DecodeType)` and
      pass a `FileStream` or `MemoryStream`. This is useful when the image comes from
      a web API.
    question: Does Aspose.BarCode support reading from a stream instead of a file
      path?
  - answer: 'The `MacroPdf417Checksum` field contains the raw CRC‑16 value. You can
      recompute the checksum on the reconstructed file and compare it to ensure data
      integrity. ## Next steps and related topics * **Write PDF417 barcodes** – explore
      `BarCodeGenerator` to create macro barcodes for testing. * **Combine'
    question: How do I validate the checksum?
  type: FAQPage
tags:
- barcode
- Aspose.BarCode
- C#
title: 如何在 C# 中使用 Aspose 讀取 PDF417 條碼 – 步驟教學
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-with-aspose-step-by-step-gui/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose 讀取 PDF417 條碼 – 步驟指南

如果您需要 **如何讀取 PDF417 條碼** 在 .NET 應用程式中，本指南將向您展示如何使用 Aspose.BarCode 函式庫在 C# 中讀取 PDF417 條碼。無論您是處理掃描文件、行動裝置捕獲，或批次匯入的影像，以下程式碼皆可解碼條碼並提取您可能需要的所有 Macro PDF417 屬性。

在 C# 中讀取條碼影像可能會感到困難，尤其是當條碼包含擴充的中繼資料時。本教學透過提供完整、可執行的範例，說明每一行程式碼，並涵蓋缺少 macro 段落或影像損壞等邊緣情況。完成後，您即可自信地將 PDF417 解碼整合至任何 C# 專案。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本已安裝  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* Aspose.BarCode for .NET 的授權或免費評估版 – 您可從 Aspose 官方網站取得臨時金鑰  
* 包含 Macro PDF417 條碼的影像檔（例如 `ExtPDF417Meta.png`）

> **專業提示：** 若僅想試驗，Aspose 提供 30 天試用，可完整使用條碼讀取功能。

## 第一步：安裝 Aspose.BarCode NuGet 套件

在終端機中開啟您的專案資料夾，執行：

```bash
dotnet add package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode.ReadRecognition` 命名空間，內含用於解碼影像的 `BarCodeReader` 類別。

## 第二步：為 PDF417 影像建立 BarCodeReader

`BarCodeReader` 建構子接受兩個參數：影像檔案路徑以及您想要偵測的 `DecodeType`。指定 `DecodeType.MacroPdf417` 會讓 Aspose 尋找 Macro PDF417 符號，並自動填充延伸屬性。

```csharp
using Aspose.BarCode.ReadRecognition;

// Replace with the actual path to your barcode image
string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image
```

### 為何使用 `DecodeType.MacroPdf417`？

* **Macro PDF417** 會儲存額外欄位（檔案 ID、段落數量、時間戳記等），這些在標準 PDF417 中不存在。  
* `BarCodeResult` 的 `Extended` 屬性僅在您請求 macro 類型時才會被填充，省去額外的解析步驟。

## 第三步：遍歷所有偵測到的條碼

單張影像可能包含多個 PDF417 符號（例如文件被分割成多頁）。`ReadBarCodes()` 方法會回傳 `IEnumerable<BarCodeResult>`，您可以使用迴圈逐一處理。

```csharp
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        // Basic information
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

如果影像中不含任何條碼，迴圈根本不會執行，程式會平順結束。此行為讓程式在批次處理時，即使有檔案沒有條碼，也不會發生錯誤。

## 第四步：輸出 Macro PDF417 延伸屬性

`Extended.Pdf417` 屬性彙總了所有 macro 專屬欄位。每個欄位皆直接對應 PDF417 規範，您可以將它們寫入資料庫、記錄日誌，或用於後續驗證。

```csharp
        // Macro PDF417 extended properties
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

### 各屬性說明

| 屬性 | 說明 |
|----------|-------------|
| **MacroPdf417FileID** | 整個多段文件的唯一識別碼。 |
| **MacroPdf417SegmentID** | 目前段落的索引（從 0 開始）。 |
| **MacroPdf417SegmentsCount** | 屬於該檔案的段落總數。 |
| **MacroPdf417FileName** | 條碼中嵌入的可選檔名。 |
| **MacroPdf417Checksum** | macro 資料區塊的 CRC‑16 檢查碼。 |
| **MacroPdf417FileSize** | 原始檔案大小（位元組）。 |
| **MacroPdf417TimeStamp** | 產生 macro 條碼的時間戳記。 |
| **MacroPdf417Addressee** | 文件的預定收件人。 |
| **MacroPdf417Sender** | 文件的發件人。 |
| **MacroPdf417Terminator** | 指示 macro 序列結束的終止旗標。 |

這些欄位在您需要將大型 PDF 或影像（因低解析度媒介而被切割成多個 PDF417 符號）重新組合時特別有用。

## 第五步：處理常見的邊緣情況

### 缺少 macro 欄位

有時 PDF417 條碼會在未包含可選 macro 欄位的情況下產生。存取不存在的屬性會回傳 `null` 或 `0`。若要將值寫入資料庫，請先做好防護：

```csharp
string fileName = result.Extended.Pdf417.MacroPdf417FileName ?? "Unnamed";
long fileSize = result.Extended.Pdf417.MacroPdf417FileSize;
```

### 損壞或低品質的影像

若影像模糊，可透過啟用 `BarCodeReader` 的品質選項提升偵測率：

```csharp
reader.BarcodeSettings.ImageQuality = 90; // value between 0‑100
reader.BarcodeSettings.PureBarcode = false; // allow detection in noisy backgrounds
```

這些設定為選用項目，但對掃描文件的成功率提升相當顯著。

### 單張影像中多種條碼格式

若懷疑影像中可能同時存在其他條碼類型，使用 `DecodeType.AllSupported` 並自行過濾結果：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        if (result.CodeType == DecodeType.MacroPdf417)
        {
            // Process macro PDF417 as shown above
        }
    }
}
```

## 完整可執行範例

將下列程式碼複製到新建的主控台專案（`dotnet new console`）中執行。將 `imagePath` 變數替換為您自己的 Macro PDF417 影像所在路徑。

```csharp
using System;
using Aspose.BarCode.ReadRecognition;

class Program
{
    static void Main()
    {
        // Path to the barcode image
        string imagePath = @"C:\Barcodes\ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Optional: improve detection on low‑quality scans
            reader.BarcodeSettings.ImageQuality = 90;
            reader.BarcodeSettings.PureBarcode = false;

            // Iterate through every barcode found in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Output extended Macro PDF417 fields
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee ?? \"N/A\"}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender ?? \"N/A\"}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**預期輸出**（數值會依您的影像而異）：

```
CodeType: MacroPdf417
CodeText: 1234567890ABCDEFGHIJ
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: Invoice_2026_10.pdf
Pdf417MacroChecksum: 32768
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2026-10-24T14:32:10Z
Pdf417MacroAddressee: AccountingDept
Pdf417MacroSender: SalesTeam
MacroPdf417Terminator: True
----------------------------------------
```

若影像未包含任何 Macro PDF417 符號，程式將不會輸出任何內容並靜默結束——非常適合大量檔案的批次作業。

## 常見問題

**Q: 可以使用相同程式碼讀取標準 PDF417（非 macro）嗎？**  
A: 可以。將 `DecodeType.MacroPdf417` 改為 `DecodeType.Pdf417`。`Extended` 屬性將為空，但仍可取得 `CodeText` 與 `CodeTypeName`。

**Q: Aspose.BarCode 是否支援從串流而非檔案路徑讀取？**  
A: 當然支援。使用 `new BarCodeReader(Stream, DecodeType)` 的重載，傳入 `FileStream` 或 `MemoryStream`。當影像來自 Web API 時特別有用。

**Q: 要如何驗證檢查碼？**  
A: `MacroPdf417Checksum` 欄位包含原始 CRC‑16 值。您可以在重建檔案後重新計算檢查碼，並與此值比對，以確保資料完整性。

## 下一步與相關主題

* **寫入 PDF417 條碼** – 探索 `BarCodeGenerator` 以產生測試用的 macro 條碼。  
* **合併多個段落** – 讀取所有段落後，依 `MacroPdf417SegmentID` 排序，並串接 `CodeText` 以重建原始資料。  
* **效能調校** – 在高吞吐量情境下，重複使用單一 `BarCodeReader` 實例於多張影像上，並

## 接下來該學什麼？

以下教學與本指南所示技術密切相關，提供完整的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何在 C# 中讀取 PDF417 – 完整條碼範例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [如何使用 Aspose.BarCode 在 C# 中建立 macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [從影像讀取條碼 C# – 含 Macro PDF417 的完整指南](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}