---
category: general
date: 2026-09-26
description: 學習如何在 C# 中解碼 PDF417，並透過一步一步的條碼閱讀器範例。本指南示範如何使用 Aspose.BarCode 在 C# 讀取條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- read barcode image c#
- c# barcode reader example
language: zh-hant
lastmod: 2026-09-26
og_description: 如何快速在 C# 中解碼 PDF417。跟隨此條碼閱讀器範例，使用 Aspose.BarCode 在 C# 中讀取條碼圖像並提取宏資訊。
og_image_alt: Screenshot showing how to decode PDF417 in C# using Aspose.BarCode
og_title: 如何在 C# 中解碼 PDF417 – 完整條碼閱讀器指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to decode PDF417 in C# with a step‑by‑step barcode reader
    example. This guide shows you how to read barcode image C# using Aspose.BarCode.
  headline: How to decode PDF417 in C# – barcode reader example
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: 如何在 C# 中解碼 PDF417 – 條碼閱讀器範例
url: /zh-hant/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中解碼 PDF417 – 條碼閱讀器範例

如果您需要在 .NET 應用程式中 **how to decode PDF417**，本教學提供完整、可直接執行的解決方案。您將看到如何使用 Aspose.BarCode 函式庫在 C# 中讀取條碼影像、取得擴充的 PDF417 宏資訊，並顯示所有相關欄位。

解碼 PDF417 不僅限於純文字；此格式還能攜帶檔案分段資料、時間戳記與檢查碼。本指南會逐步說明每個步驟，解釋程式碼的結構原因，並指出在實作 C# 條碼閱讀器範例時可能遇到的常見陷阱。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0（或更新版本）SDK 已安裝  
* Visual Studio 2022（或任何相容 C# 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 套件 (`Aspose.BarCode`)  
* 範例 Macro PDF417 圖片（例如 `ExtPDF417Meta.png`）

以上需求可確保程式碼能順利編譯與執行，且不需額外設定。

## 第一步：安裝 Aspose.BarCode NuGet 套件

在任何 **read barcode image C#** 專案中，第一步都是加入條碼函式庫。於解決方案資料夾的終端機執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此套件提供 `BarCodeReader`、`DecodeType` 與 `Extended` 屬性，以存取宏資料。安裝一次即可在整個專案中使用這些類別。

## 第二步：為 Macro PDF417 圖片建立條碼閱讀器

現在您可以使用圖檔路徑實例化 `BarCodeReader`，並指定 `DecodeType.MacroPdf417`。此設定會告訴函式庫尋找包含宏資訊的擴充 PDF417 格式。

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Path to the Macro PDF417 image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// Initialize the reader for Macro PDF417 decoding
using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // The reader is ready – next we will extract barcodes.
}
```

**為何這很重要：**  
`DecodeType.MacroPdf417` 會啟用宏專屬的解析器。若省略此設定，閱讀器僅回傳純文字內容，且會忽略您可能需要用於檔案重建的宏欄位。

## 第三步：讀取影像中所有偵測到的條碼

單一影像可能包含多個 PDF417 符號，特別是當資料被切割成多段時。透過迴圈 `ReadBarCodes()` 可確保捕捉到每個段落。

```csharp
// Step 3: Iterate over each detected barcode
foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
{
    // Inside the loop we will access both basic and macro data.
}
```

**為何需要迴圈：**  
PDF417 宏資料常分散於多個段落。處理每個 `BarCodeResult` 可確保收集完整的宏欄位，如 `MacroPdf417FileID` 與 `MacroPdf417SegmentsCount`。

## 第四步：取得並顯示基本條碼資料

`BarCodeResult` 物件包含類型與解碼後的文字。顯示這些值有助於在深入宏細節前，驗證閱讀器是否正確辨識符號。

```csharp
Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
Console.WriteLine($"CodeText: {barcodeResult.CodeText}");
```

**提示：** 若 `CodeText` 為空，可能是影像受損或解碼模式不正確。請再次確認初始化時使用的 `DecodeType`。

## 第五步：擷取擴充的 PDF417 宏資訊

宏資料位於 `barcodeResult.Extended.Pdf417` 下。每個屬性對應 PDF417 規範中定義的欄位。

```csharp
// Step 5: Access macro-specific fields
var macroInfo = barcodeResult.Extended.Pdf417;

Console.WriteLine($"Pdf417MacroFileID: {macroInfo.MacroPdf417FileID}");
Console.WriteLine($"Pdf417MacroSegmentID: {macroInfo.MacroPdf417SegmentID}");
Console.WriteLine($"Pdf417MacroSegmentsCount: {macroInfo.MacroPdf417SegmentsCount}");
Console.WriteLine($"Pdf417MacroFileName: {macroInfo.MacroPdf417FileName}");
Console.WriteLine($"Pdf417MacroChecksum: {macroInfo.MacroPdf417Checksum}");
Console.WriteLine($"Pdf417MacroFileSize: {macroInfo.MacroPdf417FileSize}");
Console.WriteLine($"Pdf417MacroTimeStamp: {macroInfo.MacroPdf417TimeStamp}");
Console.WriteLine($"Pdf417MacroAddressee: {macroInfo.MacroPdf417Addressee}");
Console.WriteLine($"Pdf417MacroSender: {macroInfo.MacroPdf417Sender}");
Console.WriteLine($"MacroPdf417Terminator: {macroInfo.MacroPdf417Terminator}");
```

**每個欄位的意義**

| 屬性 | 說明 |
|----------|-------------|
| `MacroPdf417FileID` | 用於將屬於同一邏輯檔案的所有段落分組的識別碼。 |
| `MacroPdf417SegmentID` | 當前段落的索引（從 1 開始）。 |
| `MacroPdf417SegmentsCount` | 重建原始檔案所需的總段落數。 |
| `MacroPdf417FileName` | 宏中嵌入的可選檔名。 |
| `MacroPdf417Checksum` | 用於完整性驗證的 CRC‑16 檢查碼。 |
| `MacroPdf417FileSize` | 重建檔案的預期大小（以位元組為單位）。 |
| `MacroPdf417TimeStamp` | 宏產生的日期時間。 |
| `MacroPdf417Addressee` | 可選的收件人識別碼。 |
| `MacroPdf417Sender` | 可選的發件人識別碼。 |
| `MacroPdf417Terminator` | 結束標誌；在最後一段應為 `true`。 |

了解這些欄位後，您即可重建原始檔案、驗證資料完整性，並實作自訂業務邏輯（例如拒絕過期文件）。

## 第六步：處理多段資料並重建原始檔案（進階）

當 `MacroPdf417SegmentsCount` 大於 1 時，必須收集每個段落、依 `MacroPdf417SegmentID` 排序，並串接 `CodeText` 值。以下提供簡潔實作：

```csharp
// Collect segments in a dictionary keyed by SegmentID
var segments = new SortedDictionary<int, string>();

foreach (BarCodeResult result in barcodeReader.ReadBarCodes())
{
    var macro = result.Extended.Pdf417;
    segments[macro.MacroPdf417SegmentID] = result.CodeText;
}

// Verify that we received all expected segments
int expectedCount = segments.First().Value != null
    ? barcodeReader.ReadBarCodes().First().Extended.Pdf417.MacroPdf417SegmentsCount
    : 0;

if (segments.Count == expectedCount)
{
    // Reconstruct the full payload
    string fullPayload = string.Concat(segments.Values);
    Console.WriteLine($"Reconstructed payload ({fullPayload.Length} chars):");
    Console.WriteLine(fullPayload);
}
else
{
    Console.WriteLine($"Warning: Expected {expectedCount} segments but received {segments.Count}.");
}
```

**為何這很重要：**  
若未正確排序與串接，解碼後的資料將不完整或出現錯亂。此程式碼片段亦示範了透過檢查段落數量來實作防禦性程式設計。

## 第七步：加入錯誤處理與最佳實踐

一個可投入生產環境的 **c# barcode reader example** 必須預先考慮 IO 錯誤、不支援的格式與受損影像。

```csharp
try
{
    // Existing barcode reading code goes here
}
catch (FileNotFoundException ex)
{
    Console.Error.WriteLine($"Image file not found: {ex.Message}");
}
catch (BarCodeException ex)
{
    Console.Error.WriteLine($"Barcode processing error: {ex.Message}");
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Unexpected error: {ex.Message}");
}
```

**最佳實踐清單**

* 在建立 `BarCodeReader` 前驗證影像路徑。  
* 使用 `using` 陳述式以確保釋放非受控資源。  
* 記錄宏欄位以作稽核追蹤——尤其是 `MacroPdf417Checksum` 與 `MacroPdf417TimeStamp`。  
* 處理大型檔案時，考慮將串接後的資料串流寫入磁碟，而非全部保留在記憶體中。

## 預期輸出

對有效的 `ExtPDF417Meta.png` 執行完整程式後，會產生類似以下的輸出：

```
CodeType: MacroPdf417
CodeText: <base64‑encoded segment data>
Pdf417MacroFileID: 42
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254312
Pdf417MacroTimeStamp: 2024-03-15T10:23:45Z
Pdf417MacroAddressee: Acme Corp
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: False
...
```

若三個段落皆存在，重建區塊會在驗證訊息之後印出完整的有效負載。

## 結論

您現在已掌握 **how to decode PDF417** 的 C# 實作方式，並擁有一套完整的條碼閱讀器範例。教學涵蓋了安裝 Aspose.BarCode、為 Macro PDF417 初始化 `BarCodeReader`、遍歷多條碼、擷取宏欄位、重建分段資料，以及實作錯誤處理。

接下來您可以：

* 將閱讀器整合到接受上傳影像的 Web API 中。  
* 將宏中繼資料儲存至資料庫以作稽核用途。  
* 透過更換 `DecodeType` 將解決方案擴展至其他 2‑D 符號（例如

## 接下來該學什麼？

以下教學與本指南所示技術密切相關，提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索在專案中的其他實作方式。

- [如何在 C# 中讀取 PDF417 – 完整條碼閱讀器範例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [如何使用 Aspose 建立 PDF417 條碼 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [在 C# 中讀取 PDF417 條碼 – 條碼閱讀器範例](/barcode/english/net/compact-pdf417-encoding/read-pdf417-barcode-in-c-barcode-reader-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}