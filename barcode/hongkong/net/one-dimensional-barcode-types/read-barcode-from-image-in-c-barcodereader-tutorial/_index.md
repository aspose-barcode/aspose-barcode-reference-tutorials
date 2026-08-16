---
category: general
date: 2026-08-15
description: 使用 BarCodeReader 在 C# 中從圖像讀取條碼。了解如何在 C# 中讀取多個條碼、讀取 PDF417 條碼，並查看完整的 C#
  BarCodeReader 範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcode from image
- read multiple barcodes c#
- how to read pdf417 barcode
- c# barcodereader example
language: zh-hant
lastmod: 2026-08-15
og_description: 在 C# 中從圖片讀取條碼，提供逐步指南。了解如何在 C# 中讀取多條碼、解碼 PDF417 符號，並執行完整的 C# BarCodeReader
  範例。
og_image_alt: Screenshot of C# code that reads barcode from image using BarCodeReader
og_title: 在 C# 中從圖像讀取條碼 – BarCodeReader 教學
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Read barcode from image in C# using BarCodeReader. Learn how to read
    multiple barcodes C#, read PDF417 barcode, and see a full C# BarCodeReader example.
  headline: Read barcode from image in C# – BarCodeReader tutorial
  type: TechArticle
tags:
- barcode
- C#
- .NET
- image processing
title: 在 C# 中從圖像讀取條碼 – BarCodeReader 教學
url: /zh-hant/net/one-dimensional-barcode-types/read-barcode-from-image-in-c-barcodereader-tutorial/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 從圖像讀取條碼（C#） – BarCodeReader 教程

如果您需要在 .NET 應用程式中 **從圖像讀取條碼**，本指南將向您展示如何使用 `BarCodeReader` 類別完成此操作。您還會看到如何 **在 C# 中讀取多個條碼**、解碼 PDF417 符號，以及取得一個完整的 **C# BarCodeReader 範例**，可直接複製到您的專案中。

本教程涵蓋每一步——從加入必要的 NuGet 套件到列印擴充的 PDF417 欄位——讓您最終得到可執行的主控台程式。無需外部文件說明；所有程式碼與說明均已包含在內。

## 您需要的條件

在開始之前，請確保您具備：

* .NET 6.0 SDK 或更新版本（此程式碼可於 .NET Core 與 .NET Framework 執行）
* Visual Studio 2022 或任何相容 C# 的編輯器
* `Aspose.BarCode` NuGet 套件（或提供 `BarCodeReader` 的等效函式庫）
* 包含 Macro PDF417 條碼的圖像檔（例如 `ExtPDF417Meta.png`）

具備上述前置條件即可確保範例能順利編譯，無需額外設定。

## 使用 BarCodeReader 從圖像讀取條碼

第一步是建立一個指向圖像檔案的 `BarCodeReader` 實例，並告訴函式庫要搜尋哪種類型的條碼。

```csharp
using System;
using Aspose.BarCode;               // Namespace for BarCodeReader
using Aspose.BarCode.BarCodeRecognition; // DecodeType enum

class Program
{
    static void Main()
    {
        // Path to the image that holds the Macro PDF417 barcode
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Initialize the reader for Macro PDF417 barcodes only
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Read all barcodes present in the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Basic barcode information
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");

                // Extended Macro PDF417 fields (available only for this type)
                Console.WriteLine($"File ID          : {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID       : {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count   : {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name        : {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum         : {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size        : {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Time Stamp       : {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee        : {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender           : {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator Flag  : {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

**為什麼這樣可行：**  
`BarCodeReader` 會開啟圖像，掃描指定的 `DecodeType`，並回傳 `BarCodeResult` 物件的集合。每個結果都包含一般條碼資料（`CodeTypeName`、`CodeText`），而對於 Macro PDF417，則會有 `Extended.Pdf417` 物件，提供標準定義的所有額外欄位。

## 在單一圖像中以 C# 讀取多個條碼

有時圖像中會包含多個條碼（例如 QR code 與 PDF417 並列）。若要處理此情況，只需省略明確的 `DecodeType`，或傳入 `DecodeType.AllSupported`，然後遍歷結果即可。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.AllSupported))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Found {result.CodeTypeName}: {result.CodeText}");
    }
}
```

**為什麼需要這樣做：**  
指定 `AllSupported` 會讓引擎嘗試所有已知的條碼格式，確保能捕捉圖像中的每個符號。當您無法事先預測條碼類型時，這是建議的做法。

## 使用 C# 讀取 PDF417 條碼的方法

如果您只關心傳統的 PDF417（非 macro）格式，只需將 `DecodeType` 改為 `Pdf417`。其餘程式碼保持相同，只是無法取得擴充欄位。

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"PDF417 text: {result.CodeText}");
    }
}
```

**為什麼這很重要：**  
傳統 PDF417 不會顯示 macro 專屬屬性，因此 `Extended.Pdf417` 區塊不是必需的。使用精確的 `DecodeType` 也能加快掃描速度，因為函式庫會跳過不支援的演算法。

## 完整的 C# BarCodeReader 範例，您可以直接複製

以下是結合上述三種情境的完整程式，為單一易於執行的主控台應用程式。請將 `YOUR_DIRECTORY/ExtPDF417Meta.png` 替換為您圖像的實際路徑。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        const string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 1️⃣ Read Macro PDF417 and show extended fields
        Console.WriteLine("=== Macro PDF417 ===");
        ReadMacroPdf417(imagePath);

        // 2️⃣ Read any barcode type present (multiple barcodes)
        Console.WriteLine("\n=== All supported barcodes ===");
        ReadAllBarcodes(imagePath);

        // 3️⃣ Read classic PDF417 only
        Console.WriteLine("\n=== Classic PDF417 ===");
        ReadClassicPdf417(imagePath);
    }

    static void ReadMacroPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.MacroPdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"Code Type : {result.CodeTypeName}");
                Console.WriteLine($"Code Text : {result.CodeText}");
                Console.WriteLine($"File ID   : {result.Extended.Pdf417.MacroPdf417FileID}");
                // ... other extended fields omitted for brevity
                Console.WriteLine(new string('-', 30));
            }
        }
    }

    static void ReadAllBarcodes(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.AllSupported))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"{result.CodeTypeName}: {result.CodeText}");
            }
        }
    }

    static void ReadClassicPdf417(string path)
    {
        using (BarCodeReader reader = new BarCodeReader(path, DecodeType.Pdf417))
        {
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                Console.WriteLine($"PDF417 text: {result.CodeText}");
            }
        }
    }
}
```

### 預期輸出

當範例圖像包含 Macro PDF417 條碼時，主控台會印出類似以下內容：

```
=== Macro PDF417 ===
Code Type : MacroPdf417
Code Text : 1234567890
File ID   : 5
Segment ID       : 2
Segments Count   : 3
File Name        : report.pdf
Checksum         : 0x1A2B
File Size        : 84212
Time Stamp       : 2024-03-15T10:22:31Z
Addressee        : John Doe
Sender           : Acme Corp
Terminator Flag  : True
------------------------------

=== All supported barcodes ===
MacroPdf417: 1234567890
QrCode: https://example.com

=== Classic PDF417 ===
PDF417 text: 0987654321
```

如果圖像僅包含普通的 PDF417，則 “Macro PDF417” 部分會為空，而 “Classic PDF417” 部分會顯示解碼後的文字。

## 結論

現在您已了解如何在 C# 中使用 `BarCodeReader` **從圖像讀取條碼**、如何在單一檔案中 **讀取多個條碼 C#**，以及 **讀取 PDF417 條碼** 的完整步驟——包括 macro 與 classic 兩種變體。完整的 **C# BarCodeReader 範例** 已可直接貼入任何 .NET 專案，您亦可擴充以支援其他格式或整合至更大的影像處理流程中。

**下一步**

* 探索錯誤處理模式，例如在讀取器區塊周圍使用 `try / catch`。  
* 嘗試使用 `ReaderParameters` 物件調整偵測速度與精確度。  
* 將條碼讀取與影像前處理函式庫結合（

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)
- [讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [從圖像讀取條碼 – 精通 Java 中的條碼區域提取（使用 Aspose.BarCode）](/barcode/english/java/advanced-settings-and-optimization/extracting-barcode-region-information/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}