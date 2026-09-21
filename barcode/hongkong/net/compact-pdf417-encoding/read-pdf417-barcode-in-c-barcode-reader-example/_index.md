---
category: general
date: 2026-08-03
description: 使用 C# BarCodeReader 從圖像讀取 PDF417 條碼 – 完整的條碼閱讀器範例，同時示範如何讀取多個條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read PDF417 barcode
- barcode reader example
- read multiple barcodes
- read barcodes image
language: zh-hant
lastmod: 2026-08-03
og_description: 使用 C# BarCodeReader 範例快速讀取 PDF417 條碼。跟隨此一步一步的指南解碼宏 PDF417，並從圖像中讀取多個條碼。
og_image_alt: Console output of a read PDF417 barcode example in C#
og_title: 在 C# 中讀取 PDF417 條碼 – 完整的條碼閱讀器範例
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  headline: Read PDF417 barcode in C# – barcode reader example
  type: TechArticle
- description: Read PDF417 barcode from an image using C# BarCodeReader – a complete
    barcode reader example that also shows how to read multiple barcodes.
  name: Read PDF417 barcode in C# – barcode reader example
  steps:
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the barcode library**'
    text: '**Add the barcode library**'
  - name: '**Copy the barcode image**'
    text: '**Copy the barcode image**'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- .NET
title: 在 C# 中讀取 PDF417 條碼 – 條碼讀取範例
url: /zh-hant/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中讀取 PDF417 條碼 – 條碼閱讀器範例

如果您需要從圖像中讀取 PDF417 條碼資料，本指南將示範如何使用 C# 中的 **BarCodeReader** 類別來完成。您將學習一個條碼閱讀器範例，該範例同時支援 macro PDF417，且能在單張圖像中讀取多個條碼。

處理條碼時常常需要面對不同的圖像來源、變化的光線條件，有時還會遇到如 macro PDF417 這類的複合資料段。本教學涵蓋了解碼 PDF417 條碼、擷取其擴充欄位，以及從同一張圖片處理多個條碼所需的全部步驟。完成後，您將擁有一個可執行的主控台程式，能從圖像檔讀取條碼並將詳細資訊輸出至主控台。

## 您需要的條件

* .NET 6.0 SDK 或更新版本已安裝  
* 最近版本的 **Aspose.BarCode for .NET** NuGet 套件（或任何提供 `BarCodeReader` 與 `DecodeType.MacroPdf417` 的相容函式庫）  
* 包含 PDF417 或 macro PDF417 條碼的圖像檔（範例使用 `ExtPDF417Meta.png`）  
* 如 Visual Studio 2022 等程式碼編輯器或 IDE  

不需要額外的服務或外部 API。

## 設定條碼讀取專案

1. **建立新的主控台專案**  

   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```

2. **加入條碼函式庫**  

   ```bash
   dotnet add package Aspose.BarCode --version 23.12
   ```

3. **複製條碼圖像**  

   將 `ExtPDF417Meta.png`（或任何包含 PDF417 條碼的圖像）放入專案資料夾。  
   本教學假設該檔案位於 `YOUR_DIRECTORY/ExtPDF417Meta.png`。

專案現在已可編譯並執行條碼閱讀器範例。

## 使用 BarCodeReader 讀取 PDF417 條碼

解決方案的核心是一個 `using` 區塊，用於建立 `BarCodeReader` 實例、指定 `DecodeType.MacroPdf417`，並遍歷所有偵測到的條碼。以下程式碼是一個完整、獨立的程式，您可以直接貼到 `Program.cs` 中。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the image that contains one or more PDF417 barcodes
        const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Step 1: Create a BarCodeReader for a macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Output macro PDF417 specific fields
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

            // Pro tip: If no barcodes are found, ReadBarCodes() returns an empty collection.
            // You can check reader.HasBarcodes for a quick boolean test.
            if (!reader.HasBarcodes)
            {
                Console.WriteLine("No barcodes detected in the provided image.");
            }
        }
    }
}
```

**為什麼這樣可行**：  

* `DecodeType.MacroPdf417` 告訴閱讀器尋找 PDF417 的 macro 擴充，該擴充包含檔案 ID、段落數量、時間戳記等額外中繼資料。  
* `using` 陳述式確保非受管理資源（檔案句柄、原生解碼緩衝）能即時釋放。  
* `foreach` 迴圈會自動處理圖像中 **所有** 條碼，滿足 *讀取多條碼* 的需求。  

執行程式 (`dotnet run`) 後，您應該會看到類似以下的輸出：

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 204800
Pdf417MacroTimeStamp: 2024-07-15T10:25:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp
MacroPdf417Terminator: True
----------------------------------------
```

如果圖像包含多於一個 PDF417 條碼，迴圈會為每個條碼印出獨立的區塊，從而示範如何從單張圖片 **讀取多條碼**。

## 從圖像中讀取多條碼

相同的 `BarCodeReader` 實例可一次解碼多種條碼類型。若要將範圍從僅 macro PDF417 擴展至任何 PDF417（甚至 QR、Code128 等），請調整 `DecodeType` 旗標：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
       DecodeType.Pdf417 | DecodeType.MacroPdf417 | DecodeType.QR | DecodeType.Code128))
{
    // The rest of the code stays unchanged.
}
```

`*DecodeType*` 為位元遮罩，可結合任意數量的支援格式。此彈性使得此程式碼片段成為一個 **條碼閱讀器範例**，可應用於掃描商品標籤、票券或身分證等多種情境。

## 安全存取 macro PDF417 欄位

Macro PDF417 會加入豐富的擴充屬性。然而，並非所有條碼都包含所有欄位。存取不存在的屬性會拋出 `NullReferenceException`。最安全的做法是在列印前先驗證每個屬性是否為 null：

```csharp
var macro = result.Extended?.Pdf417;
if (macro != null)
{
    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID ?? "N/A"}");
    // Repeat for other fields...
}
```

*為什麼這很重要*：在實務部署中，您可能會收到缺少 macro 資料的普通 PDF417 條碼。防禦性檢查可確保應用程式不會因例外而當機。

## 常見陷阱與最佳實踐

| 問題 | 發生原因 | 建議解決方式 |
|-------|----------------|-----------------|
| 圖像路徑不正確 | `BarCodeReader` 會在任何解碼之前拋出檔案未找到例外 | 使用 `Path.Combine` 並以 `File.Exists` 驗證檔案是否存在 |
| 低解析度圖像 | 解碼器無法定位條碼邊緣，導致偵測為零 | 提供至少 300 dpi 的解析度以確保可靠的結果 |
| 條碼旋轉超過 45° | 許多函式庫假設條碼為直立方向 | 若條碼旋轉，請啟用 `reader.RecognitionOptions.RotateImage = true` if the |

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上進一步說明。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)
- [讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [從圖像讀取條碼 – 精通 Java 中使用 Aspose.BarCode 的條碼區域擷取](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}