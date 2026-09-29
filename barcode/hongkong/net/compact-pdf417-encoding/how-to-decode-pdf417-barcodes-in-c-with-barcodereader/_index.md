---
category: general
date: 2026-09-07
description: 學習如何在 C# 中使用 BarCodeReader 解碼 PDF417 條碼。本逐步指南亦說明如何有效讀取 PDF417 資料。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read pdf417
- PDF417 barcode decoding C#
- MacroPdf417 extraction C#
- barcode reader BarCodeReader
- GroupDocs.Barcode tutorial
language: zh-hant
lastmod: 2026-09-07
og_description: 如何在 C# 中使用 BarCodeReader 解碼 PDF417 條碼。跟隨本教學學習如何讀取 PDF417 資料並提取 MacroPdf417
  欄位。
og_image_alt: Screenshot of C# code reading PDF417 barcode fields in the console
og_title: 在 C# 中解碼 PDF417 條碼的完整指南
schemas:
- author: GroupDocs
  dateModified: '2026-09-07'
  description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  headline: How to decode PDF417 barcodes in C# with BarCodeReader
  type: TechArticle
- description: Learn how to decode PDF417 barcodes in C# using BarCodeReader. This
    step‑by‑step guide also explains how to read PDF417 data efficiently.
  name: How to decode PDF417 barcodes in C# with BarCodeReader
  steps:
  - name: Prepare the project and import namespaces
    text: '```csharp using System; using GroupDocs.Barcode; using GroupDocs.Barcode.Common;
      ```'
  - name: Define the image path
    text: '```csharp // Replace with the absolute or relative path to your barcode
      image string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png"; ```'
  - name: Initialize the barcode reader for MacroPdf417 decoding
    text: '```csharp using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
      { // Step 4 runs inside this block } ```'
  - name: Read every barcode found in the image
    text: '```csharp foreach (BarCodeResult result in reader.ReadBarCodes()) { //
      Step 5 extracts the MacroPdf417 fields } ```'
  - name: Retrieve and display Macro PDF417 specific data
    text: '```csharp Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
      Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
      Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
      Console.WriteLine'
  - name: Full runnable example
    text: 'Combine the snippets above into a single `Program.cs` file:'
  type: HowTo
tags:
- PDF417
- C#
- barcode decoding
title: 如何使用 BarCodeReader 在 C# 中解碼 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-with-barcodereader/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 BarCodeReader 解碼 PDF417 條碼

如果您需要在 .NET 應用程式中 **解碼 PDF417** 條碼，本指南將帶您一步步完成整個過程。您還將了解 **如何讀取 PDF417** 資料，例如 MacroPdf417 檔案和段落識別碼，只需幾行 C# 程式碼。

在處理交通票證、駕照或運輸標籤時，解碼 PDF417 是常見需求。完成本教學後，您將擁有一個可執行的主控台程式，能列印出 GroupDocs.Barcode SDK 所提供的每個 MacroPdf417 欄位。

## 前置條件

* .NET 6.0 SDK 或更新版本（程式碼可在 .NET Core 與 .NET Framework 上編譯）
* Visual Studio 2022 或任何支援 C# 的 IDE
* **GroupDocs.Barcode** NuGet 套件（`GroupDocs.Barcode` ≥ 23.3）
* 包含 Macro PDF417 條碼的影像檔（例如 `ExtPDF417Meta.png`）

> **專業提示：** 透過 CLI 安裝套件：  
> `dotnet add package GroupDocs.Barcode --version 23.3`

## 如何在 C# 中解碼 PDF417 條碼

以下各節將解決方案分解為邏輯步驟。每個步驟都包含您需要的完整程式碼，並簡要說明其重要性。

### 步驟 1：準備專案並匯入命名空間

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;
```

*為什麼？*  
`GroupDocs.Barcode` 提供 `BarCodeReader` 類別，而 `GroupDocs.Barcode.Common` 包含 PDF417 解碼所需的 `DecodeType` 列舉。

### 步驟 2：定義影像路徑

```csharp
// Replace with the absolute or relative path to your barcode image
string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
```

*為什麼？*  
讀取器支援 .NET 所支援的任何影像格式（`.png`、`.jpg`、`.bmp`）。提供正確的路徑可確保 SDK 能找到檔案。

### 步驟 3：初始化條碼讀取器以解碼 MacroPdf417

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 4 runs inside this block
}
```

*為什麼？*  
`DecodeType.MacroPdf417` 告訴 SDK 尋找擴充的 Macro PDF417 格式，該格式攜帶檔案與段落 ID 等額外中繼資料。使用 `using` 陳述式可確保及時釋放非受控資源。

### 步驟 4：讀取影像中所有找到的條碼

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Step 5 extracts the MacroPdf417 fields
}
```

*為什麼？*  
一張影像可能包含多個條碼。`ReadBarCodes()` 方法會回傳集合，讓您能逐一處理每個條碼。

### 步驟 5：取得並顯示 Macro PDF417 專屬資料

```csharp
Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
```

*為什麼？*  
`Extended.Pdf417` 物件會公開規範中定義的所有 Macro PDF417 欄位。列印它們可讓您驗證解碼是否成功，並取得後續處理所需的資料。

### 完整可執行範例

將上述程式碼片段合併成單一的 `Program.cs` 檔案：

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Common;

class Program
{
    static void Main()
    {
        // 1️⃣ Path to the image that contains the Macro PDF417 barcode
        string imagePath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

        // 2️⃣ Create a reader configured for MacroPdf417 decoding
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // 3️⃣ Iterate over all detected barcodes
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // 4️⃣ Output Macro PDF417 metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentCount: {result.Extended.Pdf417.MacroPdf417SegmentCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroTimestamp: {result.Extended.Pdf417.MacroPdf417Timestamp}");
                Console.WriteLine(); // Blank line for readability
            }
        }
    }
}
```

**預期的主控台輸出**（值會依條碼內容而異）：

```
Pdf417MacroFileID: 12345
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentCount: 3
Pdf417MacroFileName: shipment_data
Pdf417MacroTimestamp: 2024-07-15T10:23:45Z
```

如果影像未包含 Macro PDF417 條碼，`ReadBarCodes()` 集合將為空，且不會印出任何內容。

## 常見變體與邊緣情況

| Situation | How to adapt the code |
|-----------|----------------------|
| **標準（非 Macro）PDF417** | 將 `DecodeType.MacroPdf417` 改為 `DecodeType.Pdf417`。`Extended.Pdf417` 物件將為 `null`，因此需防止空參考。 |
| **多張影像** | 將讀取器初始化包在 `foreach (var path in imagePaths)` 迴圈中。 |
| **大型影像** | 設定 `reader.Options.ImageProcessingOptions.MaxImageDimension = 2000;` 以限制記憶體使用量。 |
| **效能關鍵批次** | 重複使用單一 `BarCodeReader` 實例，透過 `reader.SetImage(path)` 設定影像，而非為每個檔案建立新物件。 |

## 疑難排解清單

* **無輸出：** 請確認 `imagePath` 指向有效檔案，且影像確實包含 PDF417 條碼。 |
* **`Extended.Pdf417` 為 null：** 您可能使用了 `DecodeType.Pdf417` 而非 `MacroPdf417`。 |
* **例外 `FileNotFoundException`：** 請確保工作目錄與路徑相符，或使用絕對路徑。 |
* **信心分數低：** 提升影像品質或調整 `reader.Options.Quality` 設定。

## 結論

您現在已了解如何在 C# 中 **解碼 PDF417** 條碼，以及如何 **讀取 PDF417** 中的中繼資料，如 Macro 檔案 ID、段落 ID 與時間戳記。完整範例示範了如何初始化 `BarCodeReader`、選擇正確的解碼類型、遍歷結果，並擷取所有可用的 MacroPdf417 欄位。

從此您可以：

* 將擷取的資料整合至物流或票證驗證系統。
* 將主控台應用程式擴充為寫入資料庫或 JSON 檔案。
* 透過切換 `DecodeType` 列舉，探索 GroupDocs.Barcode 支援的其他條碼格式（QR、DataMatrix、Code128 等）。

祝開發順利，歡迎嘗試不同的影像與條碼設定，以精通 .NET 專案中的 PDF417 解碼！

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中讀取 PDF417 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-step-by-step-guide/)
- [如何在 C# 中讀取 PDF417 – 完整條碼讀取器範例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [如何產生 PDF417 條碼 – 完整程式設計指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}