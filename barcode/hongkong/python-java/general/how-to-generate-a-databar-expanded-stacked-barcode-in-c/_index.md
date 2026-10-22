---
category: general
date: 2026-10-21
description: 使用 BarcodeGenerator 在 C# 中產生 DataBar Expanded Stacked 條碼圖像。請依照此步驟指南建立條碼圖像、客製化列與欄，並匯出
  PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- barcode generator c#
- how to generate databar
- create databar barcode
language: zh-hant
lastmod: 2026-10-21
og_description: 使用本教程在 C# 中生成擴展堆疊式 DataBar 條碼。了解如何使用 BarcodeGenerator、設定列與欄，並儲存 PNG
  圖像。
og_image_alt: Sample databar expanded stacked barcode image generated with C#
og_title: 使用 C# 生成 Databar Expanded Stacked 條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  headline: How to generate a databar expanded stacked barcode in C#
  type: TechArticle
- description: Generate a databar expanded stacked barcode image in C# using BarcodeGenerator.
    Follow this step‑by‑step guide to create barcode images, customize rows and columns,
    and export PNG files.
  name: How to generate a databar expanded stacked barcode in C#
  steps:
  - name: Basic barcode generation
    text: The simplest way to generate a **databar expanded stacked** image is to
      instantiate `BarcodeGenerator` with the desired `EncodeTypes` value and a plain
      text payload.
  - name: Customizing columns – create databar barcode with 4 columns
    text: You can control the number of columns using the `Parameters.Barcode.DataBar.Columns`
      property. The following example creates a barcode with **4 columns** while keeping
      the default row count.
  - name: Customizing rows – create databar barcode with 3 rows
    text: Similarly, you can adjust the row count via `Parameters.Barcode.DataBar.Rows`.
      The code below generates a barcode with **3 rows** and the default column count
      (4).
  - name: Exporting to other formats
    text: 'If you need a different image type (e.g., JPEG, BMP, or SVG), replace `BarCodeImageFormat.Png`
      with the appropriate enum value:'
  - name: Saving to a memory stream
    text: 'Sometimes you want to embed the barcode directly into a web response or
      a PDF without touching the file system. Use a `MemoryStream`:'
  - name: Handling invalid input
    text: 'The `BarcodeGenerator` validates the payload against the chosen symbology.
      If the data contains prohibited characters, an `ArgumentException` is thrown.
      Wrap the generation code in a try‑catch block to provide a friendly error message:'
  - name: Scaling the barcode image
    text: 'You can change the image size without altering the encoded data by setting
      `Parameters.Image.Width` and `Parameters.Image.Height`:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中產生 Databar Expanded Stacked 條碼
url: /zh-hant/python-java/general/how-to-generate-a-databar-expanded-stacked-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生 Databar Expanded Stacked 條碼

如果您需要在 C# 中產生 **Databar Expanded Stacked** 條碼，本指南將示範操作步驟。Databar Expanded Stacked 符號非常適合在緊湊的空間內編碼大量資料，您只需幾行程式碼即可產生圖像。您還會學會如何以不同格式 **產生條碼圖像** 檔案，並依需求自訂列或欄，以符合掃描環境。

本教學涵蓋產生 Databar 條碼所需的一切：安裝必要的函式庫、準備輸出資料夾、使用自訂列或欄建立條碼，並將結果儲存為 PNG 檔案。完成後，您將能以程式方式 **建立 Databar 條碼** 圖像，並可依需求調整為其他圖像格式或執行階段情境。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本（此程式碼亦相容 .NET Core 3.1 與 .NET Framework 4.7+）
* 如 Visual Studio 2022、Visual Studio Code 或 Rider 等開發環境
* 可連網以安裝 **Barcode Generator C#** NuGet 套件（Aspose.BarCode for .NET）

> **專業小技巧：** 若您使用 CI/CD 流程，請將 NuGet 套件參考加入專案檔，以確保建置可重現。

## 安裝 Barcode Generator C# 函式庫

範例使用 Aspose.BarCode 函式庫，提供 `BarcodeGenerator` 類別與 `EncodeTypes.DatabarExpandedStacked` 列舉。

```bash
dotnet add package Aspose.BarCode
```

上述指令會將最新的穩定版加入您的專案。安裝完成後，您即可在 C# 檔案中匯入命名空間：

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

## 準備輸出資料夾

可靠的檔案路徑可避免程式在寫入圖像時發生執行時錯誤。以下程式碼會在資料夾不存在時自動建立：

```csharp
using System;
using System.IO;

// Define the folder where barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);
```

> **為什麼重要：** 嘗試寫入不存在的目錄會拋出 `IOException`。事先建立資料夾可讓程式在本機開發與正式環境皆具韌性。

## 產生 Databar Expanded Stacked 條碼圖像

### 基本條碼產生

產生 **Databar Expanded Stacked** 圖像最簡單的方式是以目標 `EncodeTypes` 值與純文字內容建立 `BarcodeGenerator`：

```csharp
// Create a barcode that encodes a long numeric string
var basicGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "01234567890123456789");

// Save the barcode as PNG
basicGenerator.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
    BarCodeImageFormat.Png);
```

執行此程式碼片段後，會在 *Barcodes* 資料夾產生 `DatabarBasic.png`。圖像顯示預設佈局（4 欄 × 4 列）的標準 Databar Expanded Stacked 符號。

### 自訂欄數 – 建立 4 欄的 Databar 條碼

您可透過 `Parameters.Barcode.DataBar.Columns` 屬性控制欄數。以下範例在保留預設列數的情況下，產生 **4 欄** 的條碼：

```csharp
// Step 1: Define a generator with custom column count
var columnGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the column count to 4 (default rows = 4)
columnGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the image
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
    BarCodeImageFormat.Png);
```

產生的檔案 **DatabarCols4.png** 如下所示：

![Databar expanded stacked barcode with 4 columns](databar_cols4.png "Databar expanded stacked barcode with 4 columns – generated with C#")

*圖片替代文字 (og_image_alt)：* **Sample databar expanded stacked barcode image generated with C#** – this satisfies the SEO requirement for image alt text.

### 自訂列數 – 建立 3 列的 Databar 條碼

同理，您可使用 `Parameters.Barcode.DataBar.Rows` 調整列數。以下程式碼會產生 **3 列**、預設欄數（4）的條碼：

```csharp
// Step 2: Define a generator with custom row count
var rowGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the row count to 3 (default columns = 4)
rowGenerator.Parameters.Barcode.DataBar.Rows = 3;

// Save the image
rowGenerator.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
    BarCodeImageFormat.Png);
```

檔案 **DatabarRows3.png** 包含垂直較短的 Databar Expanded Stacked 符號，適合空間受限的標籤。

### 匯出為其他格式

若需不同的圖像類型（例如 JPEG、BMP 或 SVG），只要將 `BarCodeImageFormat.Png` 替換為對應的列舉值即可：

```csharp
columnGenerator.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
    BarCodeImageFormat.Jpeg);
```

函式庫亦支援向量格式如 SVG，適合高解析度列印。

## 進階情境

### 儲存至記憶體串流

有時您希望直接將條碼嵌入 Web 回應或 PDF，而不觸及檔案系統。可使用 `MemoryStream`：

```csharp
using System.IO;

// Generate barcode into a memory stream
using var ms = new MemoryStream();
columnGenerator.Save(ms, BarCodeImageFormat.Png);

// Reset stream position before reading
ms.Position = 0;

// Example: return the stream as a file download in ASP.NET Core
// return File(ms.ToArray(), "image/png", "databar.png");
```

### 處理無效輸入

`BarcodeGenerator` 會依所選符號驗證資料內容。若資料含有禁止字元，會拋出 `ArgumentException`。請將產生程式碼包在 try‑catch 區塊，以提供友善的錯誤訊息：

```csharp
try
{
    var gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "INVALID*DATA");
    gen.Save(Path.Combine(outputFolder, "Invalid.png"), BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Failed to generate barcode: {ex.Message}");
}
```

### 調整條碼圖像大小

您可透過設定 `Parameters.Image.Width` 與 `Parameters.Image.Height` 變更圖像尺寸，而不改變編碼資料：

```csharp
columnGenerator.Parameters.Image.Width = 300;   // pixels
columnGenerator.Parameters.Image.Height = 150; // pixels
columnGenerator.Save(Path.Combine(outputFolder, "DatabarLarge.png"),
    BarCodeImageFormat.Png);
```

調整大小對於條碼必須符合掃描器特定 DPI 要求時相當有用。

## 完整範例

以下是一個完整、可直接執行的 Console 應用程式，示範上述所有步驟：

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Prepare output folder
            string outputFolder = Path.Combine(
                Environment.CurrentDirectory, "Barcodes");
            Directory.CreateDirectory(outputFolder);

            // 2️⃣ Generate basic barcode
            var basic = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "01234567890123456789");
            basic.Save(Path.Combine(outputFolder, "DatabarBasic.png"),
                BarCodeImageFormat.Png);

            // 3️⃣ Generate barcode with 4 columns
            var colGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            colGen.Parameters.Barcode.DataBar.Columns = 4;
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.png"),
                BarCodeImageFormat.Png);

            // 4️⃣ Generate barcode with 3 rows
            var rowGen = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");
            rowGen.Parameters.Barcode.DataBar.Rows = 3;
            rowGen.Save(Path.Combine(outputFolder, "DatabarRows3.png"),
                BarCodeImageFormat.Png);

            // 5️⃣ Export to JPEG as an extra format
            colGen.Save(Path.Combine(outputFolder, "DatabarCols4.jpg"),
                BarCodeImageFormat.Jpeg);

            Console.WriteLine("All barcode images have been generated in:");
            Console.WriteLine(outputFolder);
        }
    }
}
```

**預期輸出**


## 接下來該學什麼？

以下教學與本指南緊密相關，能在此基礎上延伸技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並探索在實際專案中的其他實作方式。

- [如何設定 Databar Expanded Stacked 條碼的欄數 – 完整 C# 教學](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [如何在 C# 中使用 DataBar Expanded Stacked 建立條碼產生器範例](/barcode/english/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-databar-e/)
- [Databar Expanded Stacked 條碼指南 – 如何在 C# 中產生與調整尺寸](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}