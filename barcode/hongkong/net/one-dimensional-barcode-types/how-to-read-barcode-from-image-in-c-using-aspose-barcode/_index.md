---
category: general
date: 2026-10-18
description: 學習如何在 C# 中使用 Aspose.BarCode 從圖像讀取條碼，涵蓋 Macro PDF417 元資料提取及完整範例程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read barcode from image
- C# barcode reader
- Macro PDF417 metadata
- BarCodeReader class
- DecodeType.MacroPdf417
- barcode metadata extraction
language: zh-hant
lastmod: 2026-10-18
og_description: 如何使用 C# Aspose.BarCode 從圖像中讀取條碼。請按照本分步教學，提取 Macro PDF417 元資料並處理常見情況。
og_image_alt: Screenshot showing output of how to read barcode from image with C#
  Aspose.BarCode
og_title: 如何在 C# 中從圖像讀取條碼 – 完整 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-10-18'
  description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  headline: How to read barcode from image in C# using Aspose.BarCode
  type: TechArticle
- description: Learn how to read barcode from image in C# with Aspose.BarCode, covering
    Macro PDF417 metadata extraction and complete sample code.
  name: How to read barcode from image in C# using Aspose.BarCode
  steps:
  - name: Expected console output
    text: '``` CodeType: MacroPdf417 CodeText: https://example.com/document.pdf MacroFileID:
      12345 MacroSegmentID: 1 MacroSegmentsCount: 3 MacroFileName: document.pdf MacroChecksum:
      0x1A2B3C4D MacroFileSize: 204800 MacroTimeStamp: 2023-07-15T10:23:45Z MacroAddressee:
      Acme Corp MacroSender: Warehouse 7 MacroTer'
  - name: Large images
    text: 'Reading very large images can consume significant memory. Use the `BarcodeReader`
      overload that accepts `ReaderParameters` to limit the maximum image size:'
  - name: Missing or corrupted metadata
    text: If any of the Macro fields are missing, the corresponding property returns
      `null` or `0`. Log these cases and decide whether to treat the barcode as incomplete.
  - name: Multiple barcode types in one image
    text: 'If an image may contain other barcode formats, you can pass an array of
      `DecodeType` values:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Aspose.BarCode 從圖片讀取條碼
url: /zh-hant/net/one-dimensional-barcode-types/how-to-read-barcode-from-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 從圖像讀取條碼

如果您需要在 .NET 應用程式中 **how to read barcode from image**，本指南將展示使用 Aspose.BarCode 的具體步驟。無論您是在處理掃描文件、收據或庫存標籤，您都會看到如何讀取條碼、提取 Macro PDF417 中繼資料，並處理常見的邊緣情況。

從圖像讀取條碼是一項常規任務，但提取擴展的 Macro PDF417 欄位會增加複雜度。本教學涵蓋完整工作流程，從專案設定到可完整執行的範例，讓您可以直接複製貼上程式碼並立即看到結果。

## 您將學習到

- 如何為 C# 專案設定 Aspose.BarCode。  
- 正確的方式來實例化 **C# barcode reader** 以讀取 Macro PDF417 圖像。  
- 如何遍歷每個偵測到的條碼並輸出基本資訊。  
- 如何存取 **Macro PDF417 metadata**，例如檔案 ID、段落 ID 與檢查碼。  
- 處理遺失中繼資料、大圖像以及常見解碼錯誤的技巧。  

**先決條件**

- 已安裝 .NET 6.0（或更新版本）。  
- 具備 C# 與 Visual Studio 的基本知識（任何 IDE 都可）。  
- 包含 Macro PDF417 條碼的圖像檔案（例如 `ExtPDF417Meta.png`）。  

## 步驟 1：安裝 Aspose.BarCode

在專案資料夾中開啟終端機並執行：

```bash
dotnet add package Aspose.BarCode
```

此套件包含 **BarCodeReader class**，實作本教學所需的 **C# barcode reader** 功能。

## 步驟 2：設定開發環境

如果尚未有專案，請建立新的主控台應用程式：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

在 `Program.cs` 頂部加入 `using` 指令：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;
```

這些命名空間會公開 **BarCodeReader class** 與用於 Macro PDF417 解碼的 `DecodeType` 列舉。

## 步驟 3：為 Macro PDF417 初始化 BarCodeReader

**how to read barcode from image** 的核心在於建立針對特定 `DecodeType` 的 `BarCodeReader` 實例。對於 Macro PDF417 必須傳入 `DecodeType.MacroPdf417`：

```csharp
// Step 3: Create a barcode reader for a Macro PDF417 image
using (BarCodeReader reader = new BarCodeReader(
           "YOUR_DIRECTORY/ExtPDF417Meta.png", DecodeType.MacroPdf417))
{
    // The reader is now ready to scan the image.
}
```

**為什麼這很重要：**  
選擇 `DecodeType.MacroPdf417` 會告訴函式庫尋找擴充的 Macro PDF417 格式，該格式包含超出基本條碼資料的額外欄位。如果使用一般的 `DecodeType.Pdf417`，這些額外欄位將被忽略。

## 步驟 4：遍歷偵測到的條碼

單一圖像可能包含多個條碼。`ReadBarCodes()` 方法會回傳 `BarCodeResult` 物件的可列舉集合。迴圈遍歷它們以輸出每個條碼的基本資訊：

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    Console.WriteLine($"CodeType: {result.CodeTypeName}");
    Console.WriteLine($"CodeText: {result.CodeText}");
}
```

`CodeTypeName` 會告訴您確切的條碼符號（例如 “MacroPdf417”），而 `CodeText` 則保存解碼後的字串。

## 步驟 5：提取並顯示 Macro PDF417 中繼資料

當條碼為 Macro PDF417 時，`Extended.Pdf417` 屬性會提供豐富的中繼資料欄位。如下直接存取：

```csharp
Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
```

這些欄位提供您重建原始多段檔案、驗證完整性，以及將條碼與特定文件或發件人關聯所需的全部資訊。

### 預期的主控台輸出

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
MacroFileID: 12345
MacroSegmentID: 1
MacroSegmentsCount: 3
MacroFileName: document.pdf
MacroChecksum: 0x1A2B3C4D
MacroFileSize: 204800
MacroTimeStamp: 2023-07-15T10:23:45Z
MacroAddressee: Acme Corp
MacroSender: Warehouse 7
MacroTerminator: END
```

如果圖像不包含 Macro PDF417 條碼，`Extended.Pdf417` 物件將為 `null`。請做好防護以避免 `NullReferenceException`：

```csharp
if (result.Extended?.Pdf417 != null)
{
    // Safe to read metadata
}
else
{
    Console.WriteLine("No Macro PDF417 metadata found.");
}
```

## 步驟 6：處理常見錯誤與邊緣情況

### 大圖像

讀取非常大的圖像可能會佔用大量記憶體。使用接受 `ReaderParameters` 的 `BarcodeReader` 重載以限制最大圖像尺寸：

```csharp
ReaderParameters parameters = new ReaderParameters
{
    MaxImageSize = 4096 // pixels
};

using (BarCodeReader reader = new BarCodeReader(
           "large_image.png", DecodeType.MacroPdf417, parameters))
{
    // Process as before
}
```

### 遺失或損壞的中繼資料

如果任何 Macro 欄位缺失，對應的屬性會回傳 `null` 或 `0`。請記錄這些情況，並決定是否將條碼視為不完整。

### 單一圖像中多種條碼類型

如果圖像可能包含其他條碼格式，您可以傳入 `DecodeType` 陣列：

```csharp
DecodeType[] types = { DecodeType.MacroPdf417, DecodeType.QR, DecodeType.Code128 };
using (BarCodeReader reader = new BarCodeReader("mixed.png", types))
{
    // Iterate as before
}
```

此方式可讓 **how to read barcode from image** 的邏輯保持彈性，同時不犧牲效能。

## 步驟 7：完整原始碼

以下是完整、可直接執行的程式。請將 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替換為您自己的圖像路徑。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Path to the image containing a Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

            // Initialize the C# barcode reader for Macro PDF417
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // Iterate over all detected barcodes
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // Safely access Macro PDF417 metadata
                    if (result.Extended?.Pdf417 != null)
                    {
                        Console.WriteLine($"MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                        Console.WriteLine($"MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                        Console.WriteLine($"MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                        Console.WriteLine($"MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                        Console.WriteLine($"MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                        Console.WriteLine($"MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                        Console.WriteLine($"MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                        Console.WriteLine($"MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                        Console.WriteLine($"MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                        Console.WriteLine($"MacroTerminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                    }
                    else
                    {
                        Console.WriteLine("No Macro PDF417 metadata found for this barcode.");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Barcode processing completed.");
        }
    }
}
```

使用以下指令執行程式：

```bash
dotnet run
```

您應該會在主控台看到條碼類型、解碼文字以及所有可用的 Macro PDF417 欄位。

## 結論

在本教學中，您學會了使用 Aspose.BarCode for C# 來 **how to read barcode from image**。本指南涵蓋了設定 **C# barcode reader** 的步驟，

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [從圖像讀取條碼 C# – 完整指南（含 Macro PDF417）](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [如何在 C# 使用 Aspose.BarCode 建立 macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何在 C# 讀取 PDF417 條碼 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}