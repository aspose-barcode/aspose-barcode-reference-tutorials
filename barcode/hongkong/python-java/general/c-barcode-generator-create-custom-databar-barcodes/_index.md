---
category: general
date: 2026-08-19
description: C# 條碼產生器教學示範如何產生 DataBar Expanded Stacked 條碼、客製化條碼大小，以及設定列與欄。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- c# barcode generator
- how to generate barcode
- create databar barcode
- customize barcode size
- configure databar parameters
language: zh-hant
lastmod: 2026-08-19
og_description: C# 條碼產生器教學教您如何產生 DataBar 條碼、客製化尺寸，並設定列與欄以獲得精確輸出。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: C# 條碼產生器 – 客製化 DataBar 條碼逐步指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  headline: 'C# barcode generator: create custom DataBar barcodes'
  type: TechArticle
- description: C# barcode generator tutorial shows how to generate DataBar Expanded
    Stacked barcodes, customize barcode size, and configure rows and columns.
  name: 'C# barcode generator: create custom DataBar barcodes'
  steps:
  - name: Initialise the barcode generator with sample text
    text: '```csharp using Aspose.BarCode.Generation;'
  - name: Set the number of columns (default rows are used)
    text: '```csharp // Configure the DataBar to use four columns. barcodeGenerator.Parameters.Barcode.DataBar.Columns
      = 4; ```'
  - name: Save the barcode image that uses four columns
    text: '```csharp // Save the barcode as a PNG file. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png",
      BarCodeImageFormat.Png); ```'
  - name: Re‑initialise the generator for a new configuration
    text: '```csharp // Create a new generator instance for the same symbology and
      text. barcodeGenerator = new BarcodeGenerator( EncodeTypes.DatabarExpandedStacked,
      "Databar Expanded Stacked long"); ```'
  - name: Set the number of rows (default columns are used)
    text: '```csharp // Configure the DataBar to use three rows. barcodeGenerator.Parameters.Barcode.DataBar.Rows
      = 3; ```'
  - name: Save the barcode image that uses three rows
    text: '```csharp // Save the barcode with three rows. barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  type: HowTo
tags:
- barcode
- csharp
- databar
title: C# 條碼產生器：建立自訂 DataBar 條碼
url: /zh-hant/python-java/general/c-barcode-generator-create-custom-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 條碼產生器：建立自訂 DataBar 條碼

如果您需要一個 **c# barcode generator** 能產生 DataBar Expanded Stacked 符號，本指南將完整說明如何使用自訂列與欄產生條碼影像。您將學會設定 databar 參數、調整條碼尺寸，並將結果儲存為 PNG 檔案。

以程式方式產生條碼可省去手動設計步驟，並確保跨平台輸出一致。在本教學中您將：

* 安裝並參考 Aspose.BarCode for .NET 函式庫（或任何相容套件）。
* 建立 DataBar Expanded Stacked 符號的條碼產生器。
* **如何產生條碼** 影像，使用特定的欄與列設定。
* **自訂條碼尺寸**，透過控制 DataBar 的列與欄。
* **設定 databar 參數**，例如文字、格式與影像品質。

## 前置條件

* .NET 6.0 SDK 或更新版本已安裝。
* C# 開發環境（Visual Studio、VS Code、Rider 等）。
* NuGet 套件 `Aspose.BarCode`（或提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的等效函式庫）。

Add the package with the .NET CLI:

```bash
dotnet add package Aspose.BarCode
```

## 使用 C# 條碼產生器建立 DataBar 條碼

以下各節將逐步說明每個步驟。主要聚焦於 **c# barcode generator** API，但相同的模式亦適用於其他提供類似屬性的條碼函式庫。

### 步驟 1：使用範例文字初始化條碼產生器

```csharp
using Aspose.BarCode.Generation;

// Create a generator for DataBar Expanded Stacked with sample text.
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*為何需要此步驟？*  
`BarcodeGenerator` 是所有條碼產生工作的入口點。提供 `EncodeTypes.DatabarExpandedStacked` 列舉可告訴函式庫使用哪種符號，而文字參數則成為符號中編碼的可讀值。

### 步驟 2：設定欄數（使用預設列）

```csharp
// Configure the DataBar to use four columns.
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

*為何需要此步驟？*  
DataBar Expanded Stacked 符號由堆疊的線性元素組成。調整 `Columns` 屬性會改變水平密度，讓您在不增加整體高度的情況下容納較長的資料字串。這直接 **自訂條碼尺寸**。

### 步驟 3：儲存使用四欄的條碼影像

```csharp
// Save the barcode as a PNG file.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

*您看到的：*  
儲存的 `DatabarCols4.png` 影像顯示一個比預設更寬的 DataBar 條碼，因為它包含四個欄位。您可以使用任何影像檢視器開啟檔案以驗證輸出。

### 步驟 4：重新初始化產生器以設定新組態

```csharp
// Create a new generator instance for the same symbology and text.
barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*為何重新初始化？*  
在保留先前欄設定的同時變更 `Rows` 屬性可能會產生意外的組合。從全新實例開始可確保只有預期的參數（`Rows`）會影響下一張影像。

### 步驟 5：設定列數（使用預設欄）

```csharp
// Configure the DataBar to use three rows.
barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

*為何需要此步驟？*  
`Rows` 屬性控制垂直堆疊。增加列數會使條碼變高，當水平空間受限而垂直空間充裕時此方式相當有用。這是另一種 **自訂條碼尺寸** 的方法。

### 步驟 6：儲存使用三列的條碼影像

```csharp
// Save the barcode with three rows.
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

*結果：*  
`DatabarRows3.png` 顯示一個有三個堆疊列的較高條碼，示範 **設定 databar 參數** 如何影響視覺外觀。

## 完整可執行範例

以下是一個完整的程式，您可以直接複製、貼上並執行。它包含所有引用、錯誤處理與說明註解，以便於閱讀。

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder (adjust as needed).
        string outputFolder = @"C:\Barcodes";

        // -----------------------------------------------------------------
        // Create barcode with custom column count.
        // -----------------------------------------------------------------
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 4 columns – this widens the symbol.
        generator.Parameters.Barcode.DataBar.Columns = 4;

        // Save the first image.
        string colsPath = System.IO.Path.Combine(outputFolder, "DatabarCols4.png");
        generator.Save(colsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 4 columns to: {colsPath}");

        // -----------------------------------------------------------------
        // Create barcode with custom row count.
        // -----------------------------------------------------------------
        generator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // Set 3 rows – this makes the symbol taller.
        generator.Parameters.Barcode.DataBar.Rows = 3;

        // Save the second image.
        string rowsPath = System.IO.Path.Combine(outputFolder, "DatabarRows3.png");
        generator.Save(rowsPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Saved barcode with 3 rows to: {rowsPath}");
    }
}
```

**預期輸出**

執行程式會產生兩個 PNG 檔案：

* `DatabarCols4.png` – 具有四個欄位的寬闊 DataBar 條碼。
* `DatabarRows3.png` – 具有三列的高大 DataBar 條碼。

開啟影像以確認條碼尺寸符合設定的參數。

## 常見問題與邊緣案例處理

| 問題 | 答案 |
|----------|--------|
| *如果我同時需要自訂列 **以及** 欄該怎麼辦？* | 在呼叫 `Save` 之前，於同一個 `BarcodeGenerator` 實例上同時設定 `Rows` **以及** `Columns`。函式庫會結合兩個值，產生所需大小的格子。 |
| *我可以更改影像格式嗎？* | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`，以符合您的工作流程。 |
| *當文字長度超過符號可容納的範圍時會發生什麼？* | 產生器會拋出 `ArgumentException`。請縮短文字或增加 `Columns`/`Rows` 以提供更大的容量。 |
| *有沒有方法設定 DPI 或影像解析度？* | 在儲存之前使用 `generator.Parameters.ImageResolution` 來指定所需的 DPI。這可進一步 **自訂條碼尺寸**，以符合高解析度列印需求。 |
| *函式庫是否支援其他 DataBar 變體？* | 支援。將 `EncodeTypes.DatabarExpandedStacked` 替換為 `DatabarExpanded`、`DatabarLimited` 等，同時保留相同的參數結構。 |

## 可靠條碼產生的技巧

* **專業提示：** 在將產生的影像部署至正式環境前，務必使用掃描器或行動應用程式驗證。  
* **注意：** 空的或不存在的輸出目錄——若路徑不存在，`Save` 會拋出例外。必要時可程式化建立資料夾。  
* **效能說明：** 在迴圈中產生大量條碼時，重複使用同一個 `BarcodeGenerator` 實例，僅變更 `Rows` 或 `Columns`，可減少物件建立的開銷。

## 結論

您現在已了解如何使用 **c# barcode generator** 來 **建立 databar 條碼** 影像、**自訂條碼尺寸**，以及 **設定 databar 參數**（如列與欄）。透過調整這些設定，您可以將條碼符合任何版面需求，同時保持掃描可靠性。

接下來，您可以探索相關主題，如 **如何產生條碼** PDF、在報表中嵌入條碼，或切換至其他符號（QR、Code‑128 等）。嘗試不同的 `Rows`、`Columns` 與影像解析度，以找出最適合您使用情境的組態。

---

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [如何產生與調整單維 DataBar 條碼高度（使用 Aspose.BarCode for .NET）](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [使用 Aspose.BarCode .NET API 產生單維 DataBar 2D 條碼](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)
- [使用 .NET API 產生 Aspose.BarCode DataBar 條碼 – 列與欄設定](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}