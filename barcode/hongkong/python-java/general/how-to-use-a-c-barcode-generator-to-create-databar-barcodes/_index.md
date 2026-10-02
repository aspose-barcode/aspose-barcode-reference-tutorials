---
category: general
date: 2026-10-02
description: 學習如何在 C# 條碼產生器中設定欄與列，以產生 DataBar 條碼。逐步指南，附完整程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to set columns
- how to set rows
- create databar barcode
language: zh-hant
lastmod: 2026-10-02
og_description: C# 條碼產生器指南 – 學習如何設定欄與列以產生 DataBar 條碼，並附完整程式碼範例。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with a C#
  barcode generator
og_title: C# 條碼產生器：設定 DataBar 條碼的欄與列
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Learn how to set columns and rows in a C# barcode generator to create
    DataBar barcodes. Step‑by‑step guide with complete code.
  headline: How to use a C# barcode generator to create DataBar barcodes with custom
    columns and rows
  type: TechArticle
tags:
- barcode
- c#
- databar
title: 如何使用 C# 條碼產生器建立具有自訂欄與列的 DataBar 條碼
url: /zh-hant/python-java/general/how-to-use-a-c-barcode-generator-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 條碼產生器建立具有自訂欄與列的 DataBar 條碼

如果您需要一個 **c# barcode generator** 能夠產生具備精確欄與列設定的 DataBar 條碼，本教學將完整說明操作步驟。您將了解調整欄與列的重要性，並取得一個完整、可直接執行的範例，該範例會同時產生 4 欄與 3 列的 DataBar Expanded Stacked 條碼。

在以下章節中，我們將說明：

* 使用 Aspose.BarCode for .NET 函式庫的先決條件。
* 如何在 DataBar 條碼上設定欄位 (`how to set columns`) 與列 (`how to set rows`)。
* 完整的 C# 主控台程式，您可以複製、編譯並執行。
* 預期的輸出檔案以及除錯技巧。

完成本指南後，您將能夠 **create databar barcode** 圖片，依照您的版面需求進行客製化。

## 前置條件

在開始之前，請確保您已具備：

| 需求 | 原因 |
|------|------|
| .NET 6.0 SDK or later | 提供執行 C# 程式碼的執行環境。 |
| Visual Studio 2022 (or any IDE that supports .NET) | 讓專案建立與除錯更為簡便。 |
| Aspose.BarCode for .NET NuGet package | 提供範例中使用的 `BarcodeGenerator` 類別。 |
| Write permission to a folder for the output PNG files | 產生器會將條碼影像寫入磁碟。 |

使用以下指令安裝 Aspose.BarCode 套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立基本的 DataBar Expanded Stacked 條碼

第一步是以 `EncodeTypes.DatabarExpandedStacked` 格式實例化一個 **c# barcode generator**。此格式為二維 DataBar 條碼，最多可編碼 74 個數字字元。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// ...

// Create a generator for a DataBar Expanded Stacked barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

建構子接受兩個參數：

* `EncodeTypes.DatabarExpandedStacked` – 告訴函式庫使用哪種符號系統。
* `"Databar Expanded Stacked long"` – 將被編碼的文字。

## 步驟 2：如何設定欄位

欄位會影響 DataBar 條碼的水平密度。增加欄位數會使條碼變寬，從而提升低解析度印表機上的掃描可靠性。

```csharp
// Set the number of columns to 4
generator.Parameters.Barcode.DataBar.Columns = 4;
```

**為什麼是 4 欄？**  
四欄在大多數零售應用中提供了尺寸與可讀性之間的良好平衡。您可以嘗試 1 到 8 的值；函式庫會自動調整模組寬度。

## 步驟 3：儲存已設定欄位的條碼

```csharp
// Save the image that uses the column setting
generator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
```

影像會以 PNG 檔案儲存，保留條碼掃描器所需的清晰邊緣。

## 步驟 4：為列設定建立獨立的產生器

列設定的運作方式相同，但會影響垂直密度。為避免欄位與列設定混合，我們會建立一個新的產生器實例。

```csharp
var generatorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## 步驟 5：如何設定列

```csharp
// Set the number of rows to 3
generatorRows.Parameters.Barcode.DataBar.Rows = 3;
```

**何時使用更多列？**  
增加列會使條碼變高，當水平印刷空間受限而垂直空間充足時（例如，產品標籤較高於寬）會很有用。

## 步驟 6：儲存已設定列的條碼

```csharp
// Save the image that uses the row setting
generatorRows.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
```

兩個 PNG 檔案（`DatabarCols4.png` 與 `DatabarRows3.png`）將會出現在 `C:\Barcodes` 資料夾中。

## 完整、可執行範例

以下是一個獨立的主控台應用程式，包含上述所有步驟。將程式碼複製到新的 .NET 主控台專案中並執行。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarDemo
{
    class Program
    {
        static void Main()
        {
            // Output directory – change to a folder that exists on your machine
            const string outputDir = @"C:\Barcodes";

            // -------------------------------------------------
            // 1️⃣ Create a barcode generator for column testing
            // -------------------------------------------------
            var colGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of columns (how to set columns)
            colGenerator.Parameters.Barcode.DataBar.Columns = 4;

            // Save the column‑based barcode
            string colPath = System.IO.Path.Combine(outputDir, "DatabarCols4.png");
            colGenerator.Save(colPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Column barcode saved to: {colPath}");

            // -------------------------------------------------
            // 2️⃣ Create a barcode generator for row testing
            // -------------------------------------------------
            var rowGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Set the number of rows (how to set rows)
            rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

            // Save the row‑based barcode
            string rowPath = System.IO.Path.Combine(outputDir, "DatabarRows3.png");
            rowGenerator.Save(rowPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Row barcode saved to: {rowPath}");

            // -------------------------------------------------
            // 3️⃣ Confirmation message
            // -------------------------------------------------
            Console.WriteLine("Both DataBar barcodes have been generated successfully.");
        }
    }
}
```

### 程式碼功能說明

| 區段 | 目的 |
|------|------|
| **命名空間匯入** | 引入 `Aspose.BarCode` 與 `Aspose.BarCode.Generation`。 |
| **輸出目錄** | 集中管理路徑，若搬移資料夾只需修改一行程式碼。 |
| **欄位產生器** | 示範在 `c# barcode generator` 上 **how to set columns**。 |
| **列產生器** | 示範在 `c# barcode generator` 上 **how to set rows**。 |
| **儲存呼叫** | 將 PNG 檔寫入磁碟，使其可供掃描或納入報告。 |
| **主控台輸出** | 提供即時回饋，於開發階段相當有用。 |

## 預期輸出

執行程式後，您應該會看到兩個 PNG 檔案：

* **DatabarCols4.png** – 代表四欄的較寬條碼。  
* **DatabarRows3.png** – 代表三列的較高條碼。

兩張影像皆以 DataBar Expanded Stacked 符號編碼文字 *“Databar Expanded Stacked long”*。您可以使用任何影像檢視器開啟，或將其送入條碼掃描器以驗證可讀性。

## 常見陷阱與避免方法

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **File‑access exception** | 輸出資料夾不存在或缺乏寫入權限。 | 手動建立資料夾或以提升權限執行程式。 |
| **Incorrect column/row values** | 函式庫僅接受欄位 1‑8 與列 1‑4 的值。 | 在指派前驗證值，例如 `if (value < 1 || value > 8) throw new ArgumentOutOfRangeException();`。 |
| **Barcode not scanning** | 產生的影像對掃描器的解析度而言太小。 | 使用 `generator.Parameters.Image.Height` 或 `...Width` 增加 `ImageHeight` 或 `ImageWidth`。 |
| **Text truncation** | 編碼文字超過所選 DataBar 變體的最大長度。 | 使用較短的字串，或若需要更大容量則改用 `EncodeTypes.DatabarExpanded`。 |

## 專業技巧

* **Cache the generator** – 若需大量產生相同欄位/列設定的條碼，請重複使用同一個 `BarcodeGenerator` 實例，僅變更 `CodeText` 屬性。  
* **Batch processing** – 迭代產品識別碼集合，在迴圈內設定 `generator.CodeText`，並於每次迭代以唯一檔名呼叫 `Save`。  
* **Performance** – 在高產量情境下，關閉抗鋸齒 (`generator.Parameters.Image.AntiAlias = false`) 可加速影像產生，且不會影響掃描品質。  

## 往後步驟

既然您已了解如何使用 **c# barcode generator** **how to set columns** 與 **how to set rows**，接下來可以探索以下主題：

* **在條碼下方加入可讀文字** (`generator.Parameters.Barcode.CodeTextLocation`)。  
* **變更顏色** (`generator.Parameters.Image.ForegroundColor` 與 `BackgroundColor`)。  
* **產生其他 DataBar 變體**，例如 `DatabarLimited` 或 `DatabarExpanded`。  
* **在 PDF 報告中嵌入條碼**，使用 Aspose.PDF。  

每個主題皆以本指南為基礎，協助您打造更豐富、可投入生產的條碼解決方案。

---

*祝程式開發順利！若遇到任何問題，歡迎留下評論或查閱 Aspose.BarCode 文件以取得更深入的 API 細節。*

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 C# BarcodeGenerator 設定條碼欄位與列](/barcode/english/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/)
- [C# 條碼產生器範例 – 設定欄位、列與匯出影像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [如何使用 C# 條碼產生器建立 DataBar 條碼](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}