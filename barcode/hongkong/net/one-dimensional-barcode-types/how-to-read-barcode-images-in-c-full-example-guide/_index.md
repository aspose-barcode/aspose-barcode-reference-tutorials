---
category: general
date: 2026-10-15
description: 如何使用 BarCodeReader 快速在 C# 中讀取條碼圖像。學習讀取多個條碼，並查看一個支援 Macro‑PDF417 的 C#
  條碼讀取範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode
- read multiple barcodes
- c# barcode reader example
- Macro‑PDF417 decoding
- barcode metadata extraction
language: zh-hant
lastmod: 2026-10-15
og_description: 如何在 C# 中使用 BarCodeReader 讀取條碼。本教學展示了一個完整的 C# 條碼閱讀器範例，能處理多個條碼並提取 Macro‑PDF417
  元資料。
og_image_alt: Screenshot showing how to read barcode with C# BarCodeReader
og_title: 如何在 C# 中讀取條碼 – 逐步示例
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  headline: How to read barcode images in C# – full example guide
  type: TechArticle
- description: How to read barcode images in C# quickly using BarCodeReader. Learn
    to read multiple barcodes and see a c# barcode reader example that works with
    Macro‑PDF417.
  name: How to read barcode images in C# – full example guide
  steps:
  - name: Initialise the `BarCodeReader`
    text: '```csharp using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Read all barcodes present in the image
    text: '```csharp // Step 2: Read all barcodes in the image BarCodeResult[] results
      = reader.ReadBarCodes(); ```'
  - name: Display basic barcode details
    text: '```csharp foreach (BarCodeResult result in results) { Console.WriteLine($"CodeType:
      {result.CodeTypeName}"); Console.WriteLine($"CodeText: {result.CodeText}");
      ```'
  - name: Retrieve and show Macro‑PDF417 specific metadata
    text: '```csharp // Macro‑PDF417 extended data Console.WriteLine($"FileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Segment: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Count: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
      Console.WriteLine($"FileName'
  - name: Full runnable program
    text: Below is a self‑contained console application that puts all four steps together.
      Copy the code into a new `.cs` file, adjust the `imagePath`, and run `dotnet
      run`.
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中讀取條碼圖像 – 完整範例指南
url: /zh-hant/net/one-dimensional-barcode-types/how-to-read-barcode-images-in-c-full-example-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取條碼圖像 – 完整範例指南

如果您需要在 .NET 應用程式中 **如何讀取條碼** 資料，這份指南提供即用即跑的解決方案。您將看到一個完整的 **C# 條碼讀取範例**，它支援 Macro‑PDF417 符號，且能 **讀取多個條碼** 於同一張圖片。

讀取條碼是庫存系統、票證驗證與文件處理的常見需求。完成本教學後，您將能夠：

* 初始化任何支援格式的 `BarCodeReader`。  
* 抽取基本資訊，如條碼類型與解碼文字。  
* 取得 Macro‑PDF417 特定的中繼資料（檔案 ID、段落、檢查碼，…）。  
* 處理包含多個條碼的影像，而不需額外程式碼。

## 前置條件

在開始之前，請確保您已具備以下條件：

* 已安裝 .NET 6.0 SDK 或更新版本。  
* 開發環境（Visual Studio 2022、VS Code 或 Rider）。  
* **Aspose.BarCode for .NET** NuGet 套件（`Aspose.BarCode`）— 提供本範例使用的 `BarCodeReader` 類別。  
* 含有 Macro‑PDF417 條碼的影像檔（例如 `MacroPdf417.png`）。  

您可以使用以下指令安裝 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

## 如何使用 BarCodeReader 在 C# 中讀取條碼

此解決方案的核心分為四個簡潔步驟。每個步驟皆以 `using` 區塊包裹，以確保及時釋放非受控資源。

### 步驟 1：初始化 `BarCodeReader`

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Path to the image that contains the Macro‑PDF417 barcode(s)
string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

// Initialise the reader for the specific DecodeType
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The remaining steps are inside this block
}
```

**為什麼這很重要：**  
`BarCodeReader` 接受檔案路徑與 `DecodeType`。指定 `DecodeType.MacroPdf417` 會讓函式庫僅搜尋 Macro‑PDF417 符號，從而提升偵測速度並減少誤報。

### 步驟 2：讀取影像中所有條碼

```csharp
    // Step 2: Read all barcodes in the image
    BarCodeResult[] results = reader.ReadBarCodes();
```

**為什麼這很重要：**  
`ReadBarCodes()` 方法回傳一個陣列，可能包含一個或多個 `BarCodeResult` 物件。這正是 **read multiple barcodes** 功能發揮作用的地方——您不必為每個可能的條碼寫額外的迴圈。

### 步驟 3：顯示基本條碼資訊

```csharp
    foreach (BarCodeResult result in results)
    {
        Console.WriteLine($"CodeType: {result.CodeTypeName}");
        Console.WriteLine($"CodeText: {result.CodeText}");
```

**為什麼這很重要：**  
`CodeTypeName` 告訴您偵測到的符號類型（例如 “MacroPDF417”），而 `CodeText` 則保存解碼後的內容。這兩個欄位在後續邏輯中最常被使用。

### 步驟 4：取得並顯示 Macro‑PDF417 特定的中繼資料

```csharp
        // Macro‑PDF417 extended data
        Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
        Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
        Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
        Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
        Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
        Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
        Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
        Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
        Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
        Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
        Console.WriteLine(new string('-', 40));
    }
}
```

**為什麼這很重要：**  
Macro‑PDF417 在一般 PDF417 格式上加入文件層級的中繼資料。存取 `Extended.Pdf417` 屬性即可取得重建原始檔案、驗證完整性或將資料傳送至正確接收者所需的全部資訊。

### 完整可執行程式

以下是一個獨立的主控台應用程式，將四個步驟整合在一起。將程式碼複製到新的 `.cs` 檔案，調整 `imagePath` 後執行 `dotnet run`。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ------------------------------------------------------------
            // 1️⃣ Initialise the BarCodeReader for Macro‑PDF417 images
            // ------------------------------------------------------------
            string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ------------------------------------------------------------
                // 2️⃣ Read all barcodes present in the image
                // ------------------------------------------------------------
                BarCodeResult[] results = reader.ReadBarCodes();

                if (results.Length == 0)
                {
                    Console.WriteLine("No barcodes were detected.");
                    return;
                }

                // ------------------------------------------------------------
                // 3️⃣ Iterate over each result – this is where we **read multiple barcodes**
                // ------------------------------------------------------------
                foreach (BarCodeResult result in results)
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // ------------------------------------------------------------
                    // 4️⃣ Extract Macro‑PDF417 metadata (c# barcode reader example)
                    // ------------------------------------------------------------
                    Console.WriteLine($"FileID:    {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Segment:   {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Count:     {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"FileName:  {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Checksum:  {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"FileSize:  {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Time:      {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Addressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Sender:    {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"Terminator:{result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

#### 預期的主控台輸出

```
CodeType: MacroPDF417
CodeText: https://example.com/document
FileID:    12
Segment:   3
Count:     5
FileName:  report.pdf
Checksum:  0x1A2B3C4D
FileSize:  1048576
Time:      2024-08-15T14:23:00Z
Addressee: John Doe
Sender:    Acme Corp.
Terminator:END
----------------------------------------
```

若影像包含多於一個 Macro‑PDF417 符號，程式會為每個條碼印出獨立區塊，示範 **read multiple barcodes** 功能在不需額外程式碼的情況下運作。

## 處理常見的邊緣情況

| 情況 | 處理方式 | 原因 |
|-----------|------------|--------|
| **File not found** | 將 `BarCodeReader` 建構包在 `try/catch (FileNotFoundException)` 區塊中，並顯示友善訊息。 | 防止應用程式當機，並告知使用者缺少資源。 |
| **No barcode detected** | 檢查 `results.Length == 0`（如完整程式所示），並妥善處理。 | 當影像未包含任何支援的符號時提供明確回饋。 |
| **Different barcode type** | 將 `DecodeType.MacroPdf417` 改為 `DecodeType.AllSupportedTypes` 或其他特定列舉值。 | 讓相同程式碼可支援 QR、Code128、DataMatrix 等，同時仍支援 **read multiple barcodes**。 |
| **Large images** | 設定 `reader.AutoSize = true` 或在送入讀取器前縮小影像。 | 提升效能並減少 CLR 的記憶體負擔。 |
| **Thread‑safe usage** | 為每個執行緒建立獨立的 `BarCodeReader` 實例；此類別不具備執行緒安全性。 | 防止多執行緒掃描器或 Web 服務中的競爭條件。 |

## 生產環境程式碼的專業提示

* **Dispose early:** `using` 陳述式可確保原生資源（例如影像緩衝）即時釋放。在長時間執行的服務中，於處理完每張影像後立即釋放讀取器。  
* **Batch processing

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [從影像讀取條碼 C# – 完整指南（含 Macro PDF417）](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [如何在 C# 使用 Aspose.BarCode 建立 Macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何在 C# 讀取 PDF417 – 完整條碼讀取範例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}