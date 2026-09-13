---
category: general
date: 2026-09-13
description: 使用 Aspose.Barcode 在 C# 中快速建立 DataBar 堆疊條碼 – 學習設定欄位、列以及儲存圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- Databar Expanded Stacked
- barcode columns
- barcode rows
- Aspose.Barcode for .NET
- C# barcode generator
language: zh-hant
lastmod: 2026-09-13
og_description: 使用 Aspose.Barcode 在 C# 中建立 DataBar 堆疊條碼。本指南說明如何設定欄位、列，並匯出 PNG 圖像。
og_image_alt: Screenshot of a generated Databar stacked barcode saved as PNG
og_title: 在 C# 中建立 Databar 堆疊條碼 – 完整逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  headline: How to create databar stacked barcode in C# with Aspose.Barcode
  type: TechArticle
- description: Create databar stacked barcode in C# quickly using Aspose.Barcode –
    learn to set columns, rows, and save images.
  name: How to create databar stacked barcode in C# with Aspose.Barcode
  steps:
  - name: 'Create a new Console App project:'
    text: 'Create a new Console App project:'
  - name: 'Add the Aspose.Barcode package:'
    text: 'Add the Aspose.Barcode package:'
  - name: 'Open **Program.cs** and add the required `using` statements:'
    text: 'Open **Program.cs** and add the required `using` statements:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
- Databar
title: 如何在 C# 中使用 Aspose.Barcode 建立堆疊式 DataBar 條碼
url: /zh-hant/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.Barcode 建立 Databar Stacked 條碼

如果您需要在 .NET 應用程式中 **建立 Databar Stacked 條碼**，本教學提供完整、可直接執行的解決方案。您將會看到如何設定欄位數量、調整列數，並將結果儲存為 PNG 檔案——全部使用 Aspose.Barcode for .NET 函式庫。

只要了解三步工作流程：建立產生器、設定所需尺寸、將影像寫入磁碟，產生 **Databar Expanded Stacked** 條碼就不再是謎。以下各節將逐步說明每個部分、解釋設定背後的原因，並即時展示最終輸出供您驗證。

## 前置條件

開始之前，請確保您已具備：

- **Visual Studio 2022**（或任何 C# IDE）且已安裝 .NET 6 以上版本。
- **Aspose.Barcode for .NET** NuGet 套件（`Install-Package Aspose.Barcode`）。
- 對將要儲存 PNG 檔案的資料夾具有寫入權限。

不需要其他相依性。

## 步驟 1：建立專案並加入 Aspose.Barcode

1. 建立一個新的 Console App 專案：

   ```bash
   dotnet new console -n DatabarStackedDemo
   cd DatabarStackedDemo
   ```

2. 加入 Aspose.Barcode 套件：

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. 開啟 **Program.cs**，加入必要的 `using` 陳述式：

   ```csharp
   using Aspose.BarCode;
   using Aspose.BarCode.Generation;
   using System;
   ```

以上步驟確保 **C# 條碼產生器** 類別可在程式中使用。

## 步驟 2：建立 Databar Stacked 條碼的產生器

第一個需要的物件是 `BarcodeGenerator`，並以 **Databar Expanded Stacked** 符號設定。此物件是所有條碼相關操作的入口點。

```csharp
// Step 2: Initialize a generator for Databar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, // Symbology
    "Databar Expanded Stacked long");   // Human‑readable text (optional)
```

**為什麼這很重要：**  
`EncodeTypes.DatabarExpandedStacked` 告訴 Aspose.Barcode 使用 DataBar 系列的堆疊版，適合收據等高度受限的空間。第二個參數提供條碼要編碼的資料；您可以自行替換為符合 DataBar 標準的任意數字或字母數字字串。

## 步驟 3：設定條碼欄位並儲存影像

堆疊式 DataBar 可透過可設定的 **欄位 (Columns)** 數量來顯示。預設為三欄，但較長的資料字串可能需要四欄。請在儲存前調整 `Columns` 屬性。

```csharp
// Step 3: Set the barcode to use 4 columns (default rows) and save the image
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Choose an output folder that exists on your machine
string outputPathCols = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(outputPathCols, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {outputPathCols}");
```

**說明：**  
- `Parameters.Barcode.DataBar.Columns` 直接影響條碼的水平分段。欄位越多，影像越寬，但高度保持不變。  
- `Save` 將條碼寫入 PNG 檔案。傳入不同的 `BarCodeImageFormat` 值亦可支援 JPEG、BMP、SVG 等其他格式。

## 步驟 4：建立另一個產生器並設定條碼列數

有時掃描環境需要較高的條碼，這可以透過增加 **列數 (Rows)** 來達成。以下程式碼片段建立第二個產生器實例，設定三列，並儲存結果。

```csharp
// Step 4: Create a new generator for the same data but with 3 rows
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");

// Set the barcode to use 3 rows (default columns)
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the image with rows configured
string outputPathRows = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(outputPathRows, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {outputPathRows}");
```

**為什麼要使用不同的實例？**  
在同一個 `BarcodeGenerator` 之後呼叫 `Save` 後再變更 `Rows` 也是可行的，但建立全新實例可讓每個設定保持獨立，程式碼也更易讀——尤其在您日後擴充教學內容（例如不同資料字串或錯誤更正等級）時。

## 步驟 5：驗證產生的條碼

開啟剛剛產生的兩個 PNG 檔案，您應該會看到：

- **DatabarCols4.png** – 由四個垂直欄位組成的較寬條碼。  
- **DatabarRows3.png** – 由三個水平列組成的較高條碼。

兩張影像皆編碼相同的文字 (`"Databar Expanded Stacked long"`)，但視覺結構不同。使用任何標準 DataBar 掃描器或支援 DataBar 的手機應用程式掃描，確認能正確解碼。

## 常見問題與專業提示

| 問題 | 為什麼會發生 | 如何避免 |
|------|--------------|----------|
| **資料夾路徑不正確** | 若目錄不存在，`Save` 會拋出 `DirectoryNotFoundException`。 | 在呼叫 `Save` 前使用 `Directory.CreateDirectory(Path.GetDirectoryName(outputPath))` 建立目錄。 |
| **欄位/列數過多** | DataBar 規範限制欄位最多 4、列最多 3。 | 嚴守允許範圍；否則 Aspose.Barcode 會拋出 `ArgumentOutOfRangeException`。 |
| **條碼難以辨識** | 影像解析度過低會使條碼模糊。 | 需要更高品質時，透過 `barcodeGenerator.Parameters.ImageResolution` 提升 DPI（例如 300 dpi）。 |
| **資料格式錯誤** | 某些模式下 DataBar 只接受最多 13 位數字字串。 | 在傳入產生器前先驗證輸入字串。 |

## 延伸範例

現在您已能 **建立 Databar Stacked 條碼** 並自訂欄位與列數，接下來可以探索：

- **變更前景/背景顏色** (`barcodeGenerator.Parameters.Barcode.Color = Color.Blue;`)。  
- **加入靜止區** (`barcodeGenerator.Parameters.Barcode.Qz = 2;`)。  
- **匯出為 SVG** 以取得與解析度無關的渲染效果 (`BarCodeImageFormat.Svg`)。

所有這些選項皆在 [Aspose.Barcode for .NET API 參考文件](https://docs.aspose.com/barcode/net/) 中有詳細說明。

## 完整原始碼

以下為完整、可執行的程式碼，涵蓋上述所有步驟。將它複製到 `Program.cs`，將 `YOUR_DIRECTORY` 替換為實際路徑，然後執行 `dotnet run`。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;
using System.IO;

class Program
{
    static void Main()
    {
        // Ensure the output directory exists
        string outputDir = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputDir);

        // -------------------------------------------------
        // Step 1: Generator for 4‑column stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns (default rows = 2)
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        string colsPath = Path.Combine(outputDir, "DatabarCols4.png");
        barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 4‑column barcode to {colsPath}");

        // -------------------------------------------------
        // Step 2: Generator for 3‑row stacked barcode
        // -------------------------------------------------
        BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows (default columns = 2)
        barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

        string rowsPath = Path.Combine(outputDir, "DatabarRows3.png");
        barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved 3‑row barcode to {rowsPath}");
    }
}
```

執行程式後會產生兩個 PNG 檔案，示範 **欄位 (Columns)** 與 **列數 (Rows)** 如何影響 **Databar Expanded Stacked** 符號的視覺版面。

## 結論

您現在已掌握如何在 C# 中使用 Aspose.Barcode for .NET **建立 Databar Stacked 條碼**。透過調整 `Columns` 與 `Rows` 屬性，即可產生符合各種空間限制且資料完整性的條碼。本範例從專案設定到除錯說明，為您進一步的條碼應用奠定堅實基礎。

**後續步驟：**  
- 嘗試不同的資料字串，觀察欄位/列數限制對可讀性的影響。  
- 結合此程式碼於 Web API，實現即時條碼產生。  
- 使用相同的 `BarcodeGenerator` 模式，探索其他符號（例如 QR、Code128）。

祝程式開發順利，掃描永遠成功！

## 接下來您可以學習什麼？

以下教學與本篇內容緊密相關，能進一步深化您對 API 功能的掌握，並提供其他實作方式的範例：

- [Barcode Generator C# – 建立 DataBar Expanded Stacked 圖像](/barcode/english/python-java/general/barcode-generator-c-create-databar-expanded-stacked-images/)
- [databar expanded stacked 條碼指南 – 如何在 C# 中產生與調整尺寸](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [使用 .NET API 產生 Aspose.BarCode Databar 條碼 – 列與欄配置](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}