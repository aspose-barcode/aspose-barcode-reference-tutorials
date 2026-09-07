---
category: general
date: 2026-09-07
description: 條碼產生器 C# 教學，示範如何產生條碼 PNG 檔案，並建立可自訂列與欄的 DataBar 條碼
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- generate barcode PNG
- create DataBar barcode
language: zh-hant
lastmod: 2026-09-07
og_description: 條碼產生器 C# 教學：學會在短短幾分鐘內產生條碼 PNG 檔案，並以自訂行列建立 DataBar 條碼
og_image_alt: Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator
  C#
og_title: 條碼產生器 C# – 建立 DataBar 條碼與 PNG 圖像
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: barcode generator C# tutorial that shows you how to generate barcode
    PNG files and create DataBar barcodes with customizable rows and columns
  headline: How to use a barcode generator C# to create DataBar barcodes
  type: TechArticle
tags:
- barcode
- C#
- DataBar
title: 如何使用 C# 條碼產生器建立 DataBar 條碼
url: /zh-hant/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 barcode generator C# 產生 DataBar 條碼

如果您需要一個 **barcode generator C#** 來產生高品質條碼，本指南將示範如何 **產生 barcode PNG** 檔案以及 **建立 DataBar 條碼**，並可自訂列與欄。無論您是在建構零售庫存系統或票務平台，以下步驟都能讓您在單一、完整的範例中產生 DataBar Expanded Stacked 條碼。

在本教學中，您將學會：

* 如何實例化 `BarcodeGenerator` 以使用 DataBar Expanded Stacked 符號。  
* 如何調整欄與列的設定以符合 ISO / GS1 規範。  
* 如何將輸出儲存為 PNG 圖像，以便嵌入網頁或列印於標籤上。  

不需要任何外部服務——只需 Aspose.BarCode for .NET 函式庫（或任何相容且遵循相同 API 的函式庫）。程式碼可在 .NET 6+ 上執行，並支援 Visual Studio、Rider 或任何支援 C# 的 IDE。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6 SDK 或更新版本已安裝。  
* 已參考 `Aspose.BarCode` NuGet 套件（或提供 `BarcodeGenerator`、`EncodeTypes`、`BarCodeImageFormat` 的等效函式庫）。  
* 具備 C# 語法與專案結構的基本認識。  

您可以透過指令列加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：初始化 DataBar Expanded Stacked 的 barcode generator C#

第一步是建立一個 `BarcodeGenerator` 實例，目標為 **DataBar Expanded Stacked** 符號。此物件保存所有渲染參數，包括要編碼的文字。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,          // Symbology
    "Databar Expanded Stacked long");            // Data to encode
```

**為何重要：** `EncodeTypes.DatabarExpandedStacked` 列舉值告訴函式庫應套用哪種條碼標準。使用正確的列舉可確保產生的圖像符合 GS1 DataBar 規範。

## 步驟 2：設定欄數（使用預設列）

DataBar Expanded Stacked 可以分割成多個欄。調整欄數會改變視覺密度，並有助於在有限空間內容納較長的資料字串。

```csharp
// Step 2: Set the number of columns (default rows are used)
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;
```

**小技巧：** 預設欄數為 1。將其設定為 4 會產生四個堆疊的欄，適合較長的數字字串，同時保持條碼高度在可接受範圍。

## 步驟 3：依欄設定產生 barcode PNG

現在將條碼儲存為 PNG 圖像。PNG 能保留掃描器所需的清晰邊緣，且在網路與列印媒介上皆表現良好。

```csharp
// Step 3: Save the barcode image with the column setting applied
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

檔案 `DatabarCols4.png` 包含一個 **barcode PNG**，您可以直接嵌入 HTML 中：

```html
<img src="DatabarCols4.png" alt="Sample DataBar Expanded Stacked barcode saved as PNG using barcode generator C#">
```

## 步驟 4：建立獨立的產生器實例以設定列

如果您需要控制列數而非欄數，請實例化新的 `BarcodeGenerator`。在變更尺寸後重複使用同一實例可能會產生意外的版面問題，因此使用全新物件是最安全的做法。

```csharp
// Step 4: Create a new generator instance for the same barcode type
BarcodeGenerator rowBarcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

## 步驟 5：設定列數（使用預設欄）

列會影響條碼模組的垂直堆疊。增加列數會使條碼變高，這在某些標籤尺寸下可能是必要的。

```csharp
// Step 5: Set the number of rows (default columns are used)
rowBarcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;
```

**為何要選擇列或欄：** 欄將條碼水平分割，而列則垂直延伸。請依您的標籤版面選擇最適合的方向。

## 步驟 6：依列設定產生 barcode PNG

最後，將調整列數後的條碼儲存為 PNG 檔案。

```csharp
// Step 6: Save the barcode image with the row setting applied
rowBarcodeGenerator.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

您現在擁有兩個不同的 PNG 檔案：

* `DatabarCols4.png` – 4 欄，1 列。  
* `DatabarRows3.png` – 1 欄，3 列。

兩張圖皆可立即在應用程式、報告或列印標籤中使用。

## 如何在 C# 中以自訂尺寸產生 barcode PNG 檔案

上述模式可重複使用於任何 DataBar 變體或函式庫支援的其他符號。以下是一個可直接複製貼上的精簡範本，供您放入工具類別中使用：

```csharp
public static void GenerateDatabar(string data, int columns = 1, int rows = 1, string outputPath = "output.png")
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, data);
    generator.Parameters.Barcode.DataBar.Columns = columns;
    generator.Parameters.Barcode.DataBar.Rows = rows;
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

以以下方式呼叫此方法：

```csharp
GenerateDatabar("1234567890123", columns: 4, outputPath: "DatabarCols4.png");
GenerateDatabar("1234567890123", rows: 3, outputPath: "DatabarRows3.png");
```

**需要考慮的邊緣情況**

* **資料長度** – DataBar Expanded Stacked 最多可編碼 74 個數字字元。超過此上限會拋出例外。請在呼叫產生器前驗證輸入長度。  
* **無效尺寸** – 此符號的欄數限制為 1‑4，列數限制為 1‑3。提供超出此範圍的值會被忽略或導致錯誤。  
* **圖像 DPI** – 若需更高解析度以供列印，請在儲存前設定 `generator.Parameters.ImageResolution`。

## 預期輸出

當您開啟 `DatabarCols4.png` 或 `DatabarRows3.png` 時，應能看到清晰、高對比度的 DataBar 條碼。使用相容 GS1 的掃描器掃描此圖像，會回傳原始文字 `"Databar Expanded Stacked long"`。

![使用 barcode generator C# 儲存為 PNG 的 DataBar Expanded Stacked 條碼範例](image.png)

*Alt text: 使用 barcode generator C# 儲存為 PNG 的 DataBar Expanded Stacked 條碼範例*

## 結論

本教學示範了如何使用 **barcode generator C#** 來 **建立 DataBar 條碼**，以及如何以自訂列與欄設定 **產生 barcode PNG** 檔案。透過六個步驟——初始化產生器、設定欄或列，並儲存為 PNG，您即可取得可直接投入生產的圖像，適用於庫存系統、票務或任何需要可靠條碼呈現的情境。

接下來，您可以探索：

* 為 PNG 加入顏色或背景圖（仍與大多數掃描器相容）。  
* 使用相同的 `BarcodeGenerator` API 產生其他符號，如 QR、Code 128 或 PDF417。  
* 將產生的 PNG 直接嵌入 ASP.NET Core MVC 視圖或 Blazor 元件中。

歡迎嘗試不同的資料字串、尺寸與圖像格式（例如 JPEG、BMP）。相同的模式適用於各種情況，使 **barcode generator C#** 成為任何 .NET 開發者工具箱中多功能的工具。祝開發愉快！

## 接下來您應該學習什麼？

以下教學涵蓋與本指南技術密切相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [產生 barcode C# – 建立 DataBar 條碼](/barcode/english/python-java/general/generate-barcode-c-create-databar-barcode/)
- [Barcode Generator 範例 – 在 C# 中建立 DataBar 圖像](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [Barcode Generator 範例（C#） – 設定欄、列與匯出圖像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}