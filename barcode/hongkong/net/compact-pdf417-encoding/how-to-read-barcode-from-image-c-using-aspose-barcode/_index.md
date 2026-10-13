---
category: general
date: 2026-10-02
description: 學習如何使用 C# 從圖像中讀取條碼，完整範例示範如何使用 Aspose.BarCode 解碼 PDF417 條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image c#
- how to decode pdf417 barcode
language: zh-hant
lastmod: 2026-10-02
og_description: 使用 Aspose.BarCode 在 C# 中從圖像讀取條碼。本教程說明如何解碼 PDF417 條碼並提取擴充的中繼資料。
og_image_alt: Screenshot showing how to read barcode from image c# in Visual Studio
og_title: 從圖像讀取條碼 C# – 步驟說明指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  headline: How to read barcode from image c# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image c# with a complete example that
    shows how to decode PDF417 barcode using Aspose.BarCode.
  name: How to read barcode from image c# using Aspose.BarCode
  steps:
  - name: Create a `BarCodeReader` for a PDF417 image
    text: '```csharp using System; using Aspose.BarCode; using Aspose.BarCode.BarCodeRecognition;'
  - name: Iterate over all detected barcodes
    text: '```csharp // Step 2: Read every barcode found in the image foreach (BarCodeResult
      barcodeResult in barcodeReader.ReadBarCodes()) { // At this point you have successfully
      read barcode from image c#. ```'
  - name: Access the extended PDF417 macro metadata
    text: '```csharp // Step 3: Grab the macro‑PDF417 extended information var macro
      = barcodeResult.Extended.Pdf417;'
  - name: Output the barcode text and macro details
    text: '```csharp // Step 4: Print the basic barcode information Console.WriteLine($"Type:
      {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");'
  - name: Handle errors and clean up resources
    text: 'The `using` statement automatically disposes the `BarCodeReader`. However,
      you should still catch exceptions that may arise from missing files or unsupported
      formats:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 Aspose.BarCode 在 C# 中從圖像讀取條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 使用 Aspose.BarCode 從圖像讀取條碼

如果您需要 **在 C# 中從圖像讀取條碼**，本指南將帶您完成完整且可執行的解決方案。您將學習如何解碼 PDF417 條碼、存取其擴充宏資料，並將結果輸出至主控台。

從圖像讀取條碼是庫存系統、票證驗證與文件處理的常見需求。本教學涵蓋您所需的一切：必要的套件、程式碼說明、邊緣案例處理與預期輸出。無需外部文件說明；此範例可直接使用 Aspose.BarCode .NET 執行。

## 前置條件

* .NET 6.0 SDK 或更新版本已安裝  
* Visual Studio 2022（或任何 C# IDE）  
* NuGet 參考至 **Aspose.BarCode**（版本 23.10 或更新）  
* 包含 PDF417 條碼的圖像檔案，例如 `ExtPDF417Meta.png`

如果缺少上述任何項目，請安裝 .NET SDK，使用 `dotnet add package Aspose.BarCode` 新增 NuGet 套件，並將圖像放置於可於專案中參考的資料夾內。

## 如何在 C# 從圖像讀取條碼 – 步驟說明

以下各節將實作分解為邏輯步驟。每個步驟皆包含程式碼片段、說明 **為何** 此步驟重要，以及可套用於實務專案的技巧。

### 步驟 1：為 PDF417 圖像建立 `BarCodeReader`

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Step 1: Initialise the reader for a Macro PDF417 image
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // The DecodeType enum tells the library which symbology to look for.
        // Using DecodeType.MacroPdf417 restricts the scan to PDF417 macro symbols.
        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // The reader is now ready to read barcode from image c# efficiently.
```

**為何重要** – `BarCodeReader` 建構子接受圖像路徑與預期的條碼類型。指定 `MacroPdf417` 可縮小搜尋範圍，提升效能，並在圖像包含多種符號時減少誤判。

**專業提示**：若不確定條碼類型，可使用 `DecodeType.AllSupportedTypes`，之後再過濾結果。

### 步驟 2：遍歷所有偵測到的條碼

```csharp
            // Step 2: Read every barcode found in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // At this point you have successfully read barcode from image c#.
```

**為何重要** – PDF417 宏圖像可能包含多個段落。`ReadBarCodes()` 方法回傳集合，讓您能逐一處理每個段落。

**邊緣案例**：若圖像未包含任何 PDF417 符號，集合將為空，迴圈本體不會執行。建議在迴圈後加入檢查，以通知使用者。

### 步驟 3：存取擴充 PDF417 宏中繼資料

```csharp
                // Step 3: Grab the macro‑PDF417 extended information
                var macro = barcodeResult.Extended.Pdf417;

                // The macro object holds file‑level data that PDF417 uses for
                // multi‑segment documents such as shipping manifests.
```

**為何重要** – `Extended.Pdf417` 屬性揭露 PDF417 規範定義的欄位，如檔案 ID、段落 ID 與檔名。當您需要從多個條碼掃描重建多頁文件時，此資料相當關鍵。

**專業提示**：在存取 `Pdf417` 前，務必先確認 `barcodeResult.Extended` 不為 null。對於不支援擴充資料的符號，函式庫會回傳 null。

### 步驟 4：輸出條碼文字與宏細節

```csharp
                // Step 4: Print the basic barcode information
                Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                // Print macro‑specific fields
                Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
            }
        }
    }
}
```

**為何重要** – 主控台輸出讓您即時看到解碼文字與宏中繼資料。這對除錯以及後續處理（例如將資訊存入資料庫）相當有用。

**預期輸出**（假設範例圖像包含一個宏段落）：

```
Type: MacroPdf417, Text: https://example.com/document.pdf
Macro File ID: 12, Segment ID: 1
Segments Count: 3, File Name: shipment_manifest.pdf
```

若圖像包含三個段落，迴圈會印出三個區塊，每個都有不同的 `Segment ID`。

### 步驟 5：處理錯誤與清理資源

`using` 陳述式會自動釋放 `BarCodeReader`。然而，仍應捕捉可能因檔案遺失或不支援格式而產生的例外：

```csharp
        try
        {
            // Place the entire reader block here (Steps 1‑4)
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
```

**為何重要** – 穩健的應用程式不會因檔案缺失或圖像損毀而當機。提供清晰的錯誤訊息有助於您或支援團隊快速診斷問題。

## 如何使用 Aspose.BarCode 解碼 PDF417 條碼

次要關鍵字 **how to decode pdf417 barcode** 在本節自然出現。解碼 PDF417 條碼遵循上述相同模式，但若僅需純文字，可省略 `MacroPdf417` 標誌：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Decoded text: {result.CodeText}");
    }
}
```

**為何選擇此變體** – 若條碼不包含宏資訊，使用 `DecodeType.Pdf417` 可降低處理負擔，並簡化結果處理。

**常見問題**：*如果條碼被旋轉了怎麼辦？*  
Aspose.BarCode 會自動偵測旋轉並校正，無需額外的圖像前處理程式碼。

## 完整、可執行的範例

將下方完整程式碼複製到新的主控台專案（`dotnet new console`）中，並將 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替換為實際圖像的路徑。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        try
        {
            using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
                {
                    var macro = barcodeResult.Extended?.Pdf417;

                    Console.WriteLine($"Type: {barcodeResult.CodeTypeName}, Text: {barcodeResult.CodeText}");

                    if (macro != null)
                    {
                        Console.WriteLine($"Macro File ID: {macro.MacroPdf417FileID}, Segment ID: {macro.MacroPdf417SegmentID}");
                        Console.WriteLine($"Segments Count: {macro.MacroPdf417SegmentsCount}, File Name: {macro.MacroPdf417FileName}");
                    }
                    else
                    {
                        Console.WriteLine("No macro PDF417 metadata available.");
                    }
                }
            }
        }
        catch (Exception ex)
        {
            Console.Error.WriteLine($"Error while trying to read barcode from image c#: {ex.Message}");
        }
    }
}
```

執行程式會印出條碼類型、解碼文字以及任何宏中繼資料。若圖像未包含 PDF417 宏，程式會優雅地提示您。

## 結論

現在您已了解如何使用 Aspose.BarCode **在 C# 中從圖像讀取條碼**、如何 **解碼 PDF417 條碼**，以及如何擷取宏‑PDF417 的擴充欄位。此解決方案涵蓋初始化、遍歷、存取中繼資料、錯誤處理，以及純 PDF417 解碼的變體。

從此您可以：

* 將擷取的資料存入 SQL 資料庫以供日後檢索。  
* 結合多個段落以重建原始文件。  
* 探索 Aspose.BarCode 支援的其他符號，...

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，並以完整可執行的程式碼範例與步驟說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [How to Read PDF417 in C# – Complete Barcode Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-example/)
- [How to Read PDF417 in C# – Complete Barcode Reader Example](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}