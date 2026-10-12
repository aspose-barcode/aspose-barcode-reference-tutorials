---
category: general
date: 2026-09-29
description: 如何在 C# 中使用 Aspose.BarCode 解碼 PDF417 條碼。了解一個條碼讀取範例，展示如何讀取條碼圖像並提取宏資料。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: zh-hant
lastmod: 2026-09-29
og_description: 如何使用 Aspose.BarCode 在 C# 中解碼 PDF417 條碼。本指南展示了一個可直接執行的條碼閱讀器範例，用於讀取條碼圖像。
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: 如何在 C# 中解碼 PDF417 條碼 – 完整的條碼讀取範例
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: 如何在 C# 中解碼 PDF417 條碼 – 逐步指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中解碼 PDF417 條碼 – 步驟指南

如果您需要在 C# 中 **解碼 PDF417** 條碼，本教學提供完整、可執行的解決方案。您將看到一個 **條碼閱讀器範例**，示範 **如何讀取條碼** 圖片、提取宏資訊，並將結果輸出到主控台。

在處理運送標籤、票券或政府身分證時，解碼 PDF417 是常見需求。完成本指南後，您將能讀取 PDF417 條碼圖像、存取其宏欄位，並處理常見的例外情況。無需額外文件——所有內容皆已包含。

## 您將學會

- 安裝 Aspose.BarCode for .NET 套件  
- 建立一個 `BarCodeReader`，從 PNG 或 JPEG 檔案 **讀取 PDF417 條碼** 資料  
- 迭代 `BarCodeResult` 物件並取得 macro‑PDF417 屬性  
- 疑難排解常見問題，例如不支援的影像格式或缺少宏資料  

## 前置條件

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK 或更新版本 | 提供 C# 專案的執行環境 |
| Visual Studio 2022（或任何支援 .NET 的 IDE） | 方便建立與除錯專案 |
| NuGet 套件 **Aspose.BarCode** | 提供範例中使用的 `BarCodeReader` 類別 |
| PDF417 宏圖像（例如 `ExtPDF417Meta.png`） | 讀取器將要解碼的來源檔案 |

> **Pro tip:** 若您沒有 PDF417 圖片，可使用免費的 Aspose.BarCode 線上示範產生，或直接掃描實體標籤。

## 步驟 1：透過 NuGet 安裝 Aspose.BarCode

在解決方案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新穩定版的 Aspose.BarCode 加入專案，並更新 `.csproj` 檔案。此函式庫實作了 **read barcode image C#** 功能，支援包括 PDF417 在內的多種條碼類型。

## 步驟 2：建立 BarCodeReader 以 **解碼 PDF417**

**how to read barcode** 流程的核心是 `BarCodeReader`。您必須同時提供檔案路徑與預期的條碼類型 (`DecodeType.MacroPdf417`)。正確設定 `DecodeType` 可提升偵測速度與準確度。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**為什麼這很重要：**  
- `DecodeType.MacroPdf417` 告訴引擎搜尋 macro‑PDF417 欄位（檔案 ID、段落 ID 等）。  
- 使用 `using` 可確保底層影像串流在使用完畢後關閉，避免 Windows 上的檔案鎖定問題。

## 步驟 3：迭代偵測到的條碼

單一影像可能包含多個條碼。`ReadBarCodes()` 方法會回傳 `IEnumerable<BarCodeResult>`，您可以使用迴圈逐一處理。

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

如果影像中沒有任何 PDF417 符號，迴圈本體將不會執行，您可以在迴圈結束後處理此情況（請參考「錯誤處理」章節）。

## 步驟 4：存取 PDF417 宏欄位

每個 `BarCodeResult` 都會公開一個 `Extended` 屬性，內含 `Pdf417` 子物件。最常用的宏欄位如下：

| Property | Meaning |
|----------|---------|
| `MacroPdf417FileID` | 整個 macro PDF417 檔案的識別碼 |
| `MacroPdf417SegmentID` | 目前段落的序號 |
| `MacroPdf417FileName` | 宏中儲存的可選檔名 |

以下程式碼會將這些值印出：

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### 預期的主控台輸出

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

若宏欄位不存在，輸出會顯示空白行，因為屬性值為 `null`。這在非宏 PDF417 條碼中屬於正常現象。

## 步驟 5：處理常見陷阱（錯誤處理與邊緣案例）

### 未偵測到條碼

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### 不支援的影像格式

Aspose.BarCode 支援 PNG、JPEG、BMP、TIFF 與 GIF。若嘗試讀取 RAW 或 WebP 檔案，會拋出 `ArgumentException`。請先將影像轉換為支援的格式，再交給閱讀器。

### 大型宏檔案

Macro‑PDF417 可能跨多個段落。若要還原原始檔案，必須收集所有段落（依 `MacroPdf417SegmentID` 排序）並串接其內容。上述範例僅列印單一段落的中繼資料；實務上應將每個段落存入字典，待全部讀取完畢後再組合。

### 效能小技巧

若需處理上千張影像，建議使用 `SetImage` 方法重複使用同一個 `BarCodeReader` 實例，而非為每個檔案建立新物件。這可減少記憶體配置並加速解碼。

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## 完整可執行範例

將下列程式碼複製到新的 Console App 專案（`dotnet new console`）。範例已包含所有步驟、錯誤處理與註解。

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**執行程式**

```bash
dotnet run
```

您應該會在主控台看到宏欄位的輸出，與前述預期結果相符。

## 結論

在本教學中，您學會了 **解碼 PDF417** 條碼的完整 **條碼閱讀器範例**。透過安裝 Aspose.BarCode、建立針對 `MacroPdf417` 的 `BarCodeReader`、迭代結果並存取 `Extended.Pdf417` 宏屬性，即可可靠地 **讀取 PDF417 條碼** 資料，無論來源影像為何。

接下來您可以：

- 實作段落聚合，以重建多段 macro 檔案。  
- 使用相同的 `BarCodeReader` 模式探索其他條碼類型（QR、Code128）。  
- 將解碼器整合至處理上傳影像的 Web API（在服務情境下的 `read barcode image C#`）。  

歡迎嘗試不同的影像來源、錯誤處理策略與效能優化。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並提供其他實作方式的範例。

- [如何在 C# 中讀取 PDF417 – 完整條碼閱讀器指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [如何使用 Aspose 產生 PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [如何使用 Aspose 建立 PDF417 條碼 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}