---
category: general
date: 2026-11-14
description: 學習如何在 C# 中從圖像讀取條碼，完整的條碼閱讀器教學。包括設定、完整程式碼以及處理 Macro PDF417 欄位。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: zh-hant
lastmod: 2026-11-14
og_description: 在 C# 中使用此條碼閱讀器教學從圖像讀取條碼。取得完整可運作的範例，並學習提取 Macro PDF417 資料。
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: 在 C# 中從圖像讀取條碼 – 完整教學
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: 如何使用 C# 從圖像讀取條碼 – 逐步指南
url: /zh-hant/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 從圖像讀取條碼 – 步驟指南

如果您需要在 .NET 應用程式中 **從圖像讀取條碼**，本教學將一步步示範。完成本教學後，您將擁有一個完整、可執行的程式，能同時擷取基本條碼資料與 Macro PDF417 的專屬欄位。

在這篇 **barcode reader tutorial c#** 中，我們會說明專案設定、必須的 NuGet 套件，以及可在最新 .NET 8 SDK 上執行的完整程式碼範例。全程本機執行，無需任何外部服務。

## 您將學會

- 如何將 Aspose.BarCode（或類似）函式庫加入 C# 專案。  
- 如何建立針對特定圖像檔的 `BarCodeReader`。  
- 如何遍歷所有偵測到的條碼，並輸出其類型、文字與 Macro PDF417 中繼資料。  
- 處理含多條碼或不同解碼類型圖像的技巧。

### 前置條件

- 已安裝 .NET 8 SDK（或 .NET 6 以上亦可）。  
- 具備 C# 主控台應用程式的基本概念。  
- 一張包含 Macro PDF417 條碼的圖像檔（例如 `MacroPdf417.png`）。  

---

## 步驟 1：建立新的主控台專案

在終端機中執行：

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

此指令會建立名為 **BarcodeReaderDemo** 的最小主控台應用程式。接下來的步驟會使用此專案檔 (`BarcodeReaderDemo.csproj`)。

## 步驟 2：安裝條碼讀取函式庫

本教學使用 **Aspose.BarCode for .NET**，因為它原生支援 Macro PDF417。透過 NuGet 安裝：

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **為什麼選擇這個函式庫？** 它提供單一的 `BarCodeReader` 類別，支援數十種條碼類型，且可透過 `Extended` 屬性取得 Macro PDF417 欄位。

## 步驟 3：撰寫條碼讀取程式碼（barcode reader tutorial c#）

將 `Program.cs` 內容取代為以下完整範例。此範例示範 **如何從圖像讀取條碼**，並同時印出一般資訊與 Macro PDF417 的專屬資訊。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 各步驟說明

| 步驟 | 為何重要 |
|------|----------|
| **1️⃣** 定義圖像路徑 | 讀取器可接受檔案路徑或串流。使用相對路徑讓範例更易直接複製貼上。 |
| **2️⃣** 建立 BarCodeReader | 傳入 `DecodeType.MacroPdf417` 只掃描此類型，可提升速度並確保 `Extended` 欄位被填入。 |
| **3️⃣** 逐項遍歷結果 | 圖像可能包含多個條碼，`foreach` 迴圈可確保全部捕捉。 |
| **4️⃣** 一般輸出 | `CodeTypeName` 與 `CodeText` 是開發者最常需要的資訊。 |
| **5️⃣** Macro PDF417 欄位 | Macro PDF417 內含額外資料（檔案 ID、段落 ID、段落總數）。存取 `result.Extended.Pdf417` 即可取得，無需自行解析。 |
| **6️⃣** 可選的額外欄位 | 函式庫還提供其他 macro 欄位（例如 `MacroPdf417FileName`），可依需求自行擴充輸出。 |
| **7️⃣** 保持主控台開啟 | 在 Visual Studio 或 `dotnet run` 執行時，讓視窗不會立即關閉，方便檢視輸出。 |

## 步驟 4：執行程式並驗證輸出

將 `MacroPdf417.png` 放置於 `imagePath` 所指的資料夾，然後執行：

```bash
dotnet run
```

典型的主控台輸出如下：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

若圖像內有多個 Macro PDF417 符號，程式會依序列出每組值。

## 常見變化與例外情況

### 讀取其他條碼類型

若要 **從圖像讀取條碼**，但不是 Macro PDF417，可將 `DecodeType.MacroPdf417` 改為以逗號分隔的類型清單，例如：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

對於不提供額外資料的條碼類型，`Extended` 屬性會是 `null`，因此在存取前務必先檢查 `null`。

### 處理大型圖像

大型 PNG 或 JPEG 會佔用較多記憶體。為降低資源消耗，可在傳入 `BarCodeReader` 前先縮小圖像：

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### 使用串流而非檔案路徑

若圖像來源於資料庫或 Web 請求，可傳入 `Stream`：

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## 提升條碼讀取體驗的專業技巧

- **專業提示：** 請盡可能將 `DecodeType` 設為最精確的條碼集合，這樣可減少誤判並加快處理速度。  
- **注意事項：** 低對比度或過度壓縮的圖像可能導致讀取失敗。若偵測率偏低，請先對圖像進行亮度/對比度調整。  
- **小技巧：** `BarCodeReader` 類別實作 `IDisposable`，使用 `using` 區塊可確保原生資源即時釋放。  

---

## 結論

現在您已掌握如何在 C# 中 **從圖像讀取條碼**，並同時取得標準資訊與 Macro PDF417 的專屬欄位。這篇 **barcode reader tutorial c#** 提供一個完整、獨立的解決方案，您可以直接套用於任何 .NET 專案。

接下來您可以：

- 探索其他解碼類型（QR、DataMatrix、Code128）。  
- 將讀取器整合至 ASP.NET Core API，實時處理上傳的圖像。  
- 將擷取的 macro 欄位寫入資料庫，以供日後彙總分析。

祝編程愉快，歡迎自行嘗試不同的圖像來源與條碼格式！

## 接下來該學什麼？

以下教學與本篇內容密切相關，能進一步深化您所學的技巧。每篇皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能或探索其他實作方式。

- [How to decode PDF417 barcodes in C# and read barcode image C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [How to read barcode from image c# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}