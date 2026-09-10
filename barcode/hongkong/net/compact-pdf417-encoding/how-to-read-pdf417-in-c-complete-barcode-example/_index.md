---
category: general
date: 2026-07-27
description: 如何在 C# 中快速讀取 PDF417 條碼。學習讀取多個條碼、解碼圖像，並在完整的 C# 條碼範例中取得 Macro PDF417 中繼資料。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- c# barcode example
- read barcode image c#
language: zh-hant
lastmod: 2026-07-27
og_description: 使用此一步一步指南在 C# 中讀取 PDF417 條碼。解碼圖像、處理多條條碼，並在即用範例中提取 Macro PDF417 中繼資料。
og_image_alt: Screenshot showing how to read PDF417 barcode using C# code
og_title: 如何在 C# 中讀取 PDF417 – 完整條碼範例
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  headline: How to Read PDF417 in C# – Complete Barcode Example
  type: TechArticle
- description: How to read PDF417 barcode in C# quickly. Learn to read multiple barcodes,
    decode images, and get Macro PDF417 metadata in a full C# barcode example.
  name: How to Read PDF417 in C# – Complete Barcode Example
  steps:
  - name: Loads a barcode image from disk.
    text: Loads a barcode image from disk.
  - name: Decodes **PDF417** (including Macro PDF417) barcodes.
    text: Decodes **PDF417** (including Macro PDF417) barcodes.
  - name: Prints basic information such as code type and text.
    text: Prints basic information such as code type and text.
  - name: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
    text: Outputs the full set of Macro PDF417 fields (file ID, segment ID, checksum,
      etc.).
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image-processing
- Aspose
title: 如何在 C# 中讀取 PDF417 – 完整條碼範例
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 – 完整條碼範例

有沒有想過 **如何在 C# 應用程式中讀取 PDF417** 條碼而不至於抓狂？你並不是唯一有此困惑的人。無論你是在開發物流掃描器、票券驗證器，或只是需要從 PDF417 編碼的身分證中取得資料，這個過程起初可能會顯得有點神祕。  

在本教學中，我們將逐步說明一個 **c# barcode example**，它會讀取 PDF417 圖片、在有多個條碼時處理 **read multiple barcodes**，並擷取所有可能需要的便利 Macro PDF417 中繼資料。

## 您將建立的內容

完成本指南後，您將擁有一個小型主控台程式，能夠：

1. 從磁碟載入條碼影像。  
2. 解碼 **PDF417**（包括 Macro PDF417）條碼。  
3. 輸出基本資訊，例如條碼類型與文字。  
4. 輸出完整的 Macro PDF417 欄位（檔案 ID、段落 ID、檢查碼等）。  

不需要外部服務，只需一個 NuGet 套件與幾行 C# 程式碼。

## 前置條件 – 開始前您需要的項目

- **.NET 6.0** 或更新版本（此程式碼亦可在 .NET Framework 4.6+ 上執行）。  
- 最新版的 **Aspose.BarCode for .NET** 函式庫 – 透過 NuGet 安裝（`Install-Package Aspose.BarCode`）。  
- 含有 PDF417 條碼的影像檔（示範使用 `ExtPDF417Meta.png`）。  
- 基本的 C# 主控台應用程式概念（只要寫過「Hello World」就沒問題）。

> **Pro tip:** 如果您手頭沒有 PDF417 範例，可在 Aspose 示範網站產生，或使用能建立 PDF417 標籤的手機應用程式。

## 步驟 1：設定專案並安裝函式庫

首先，建立一個新的主控台專案：

```bash
dotnet new console -n Pdf417ReaderDemo
cd Pdf417ReaderDemo
dotnet add package Aspose.BarCode
```

這會將我們需要的 **c# barcode example** 相依性加入。開啟 `Program.cs`，將預設程式碼替換為下方的骨架：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // We'll fill this in in the next steps.
        }
    }
}
```

## 步驟 2：為 PDF417 初始化條碼讀取器

此解決方案的核心是 `BarCodeReader` 類別。我們告訴它要掃描哪個檔案以及關注哪種條碼類型——在本例中為 `DecodeType.Pdf417` 或其宏變體 `DecodeType.MacroPdf417`。使用宏類型可確保我們取得擴充欄位。

```csharp
// Step 2: Create the reader, targeting Macro PDF417 barcodes
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

using (BarCodeReader reader = new BarCodeReader(
           imagePath, DecodeType.MacroPdf417))
{
    // The rest of the logic lives inside this block.
}
```

為什麼要使用 `MacroPdf417` 而非普通的 `Pdf417`？Macro PDF417 含有額外的中繼資料（檔案 ID、段落數量、時間戳記等），許多實務應用都依賴這些資訊——例如跨多頁的貨運清單。

## 步驟 3：讀取影像中所有偵測到的條碼

單一影像可能包含 **read multiple barcodes**——例如 PDF417 旁邊還有 QR Code。`ReadBarCodes()` 方法會回傳 `IEnumerable<BarCodeResult>`，我們可以對其進行迭代。

```csharp
// Step 3: Iterate through every barcode detected
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside we’ll output both generic and macro‑specific data.
}
```

即使影像只包含一個 PDF417，迴圈仍會執行一次，使程式碼在未來需要 **read multiple barcodes** 時仍具彈性。

## 步驟 4：顯示基本條碼資訊

在深入宏欄位之前，先顯示條碼類型與解碼文字會很有幫助。這能讓您確認讀取器真的辨識出 PDF417，而非其他符號。

```csharp
Console.WriteLine($"CodeType : {result.CodeTypeName}");
Console.WriteLine($"CodeText : {result.CodeText}");
```

`CodeTypeName` 會顯示 *MacroPdf417*（若未設定宏旗標則為 *Pdf417*），而 `CodeText` 則包含條碼中編碼的原始資料。

## 步驟 5：擷取 Macro PDF417 中繼資料

`Extended` 屬性讓您深入了解 PDF417 專屬的結構。以下列印的每個欄位皆直接對應 PDF417 宏規格。

```csharp
// Step 5: Macro PDF417 metadata – all optional, but very handy
Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
```

每一行會取得宏負載中的不同資訊：

- **FileID** – 整個文件集的唯一識別碼。  
- **SegmentID** – 多段檔案中的哪一段。  
- **SegmentsCount** – 預期的總段數。  
- **FileName、Checksum、FileSize** – 用於驗證傳輸檔案完整性的資訊。  
- **TimeStamp、Addressee、Sender** – 許多物流系統會嵌入的可選欄位。  

若來源條碼缺少上述任一欄位，函式庫會回傳 `null` 或 `0`，您可依需求自行處理。

## 步驟 6：執行完整範例

將上述所有步驟整合起來，以下是完整、可直接執行的程式碼：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the reader for Macro PDF417 (covers both standard and macro)
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Loop through every barcode detected – handles read multiple barcodes gracefully
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // Basic info
                    Console.WriteLine($"CodeType : {result.CodeTypeName}");
                    Console.WriteLine($"CodeText : {result.CodeText}");

                    // Macro PDF417 specific metadata
                    Console.WriteLine($"Pdf417MacroFileID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName        : {result.Extended.Pdf417.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum        : {result.Extended.Pdf417.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee       : {result.Extended.Pdf417.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender          : {result.Extended.Pdf417.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator      : {result.Extended.Pdf417.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding complete. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### 預期輸出

當您對有效的 `ExtPDF417Meta.png` 執行程式時，應會看到類似以下的輸出：

```
CodeType : MacroPdf417
CodeText : https://example.com/track?order=12345
Pdf417MacroFileID          : 101
Pdf417MacroSegmentID       : 1
Pdf417MacroSegmentsCount   : 3
Pdf417MacroFileName        : order_manifest.pdf
Pdf417MacroChecksum        : 0x1A2B3C4D
Pdf417MacroFileSize        : 45296
Pdf417MacroTimeStamp       : 2024-03-15T10:27:00Z
Pdf417MacroAddressee       : LogisticsDept
Pdf417MacroSender          : WarehouseA
MacroPdf417Terminator      : true
----------------------------------------
Decoding complete. Press any key to exit.
```

如果影像中包含多於一個條碼，

## 接下來您可以學習什麼？

以下教學涵蓋與本指南密切相關的主題，並在此基礎上延伸技術。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [How to Generate PDF417 Barcodes – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Read DataMatrix Barcodes with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-reading/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}