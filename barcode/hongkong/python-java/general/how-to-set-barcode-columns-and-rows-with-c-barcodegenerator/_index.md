---
category: general
date: 2026-09-16
description: 學習如何在 C# 中使用 BarcodeGenerator 設定條碼欄位，並為 DataBar Expanded Stacked 條碼設定條碼列。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- set barcode columns
- set barcode rows
- DataBar Expanded Stacked
- BarcodeGenerator C#
- barcode image format
- configure barcode dimensions
language: zh-hant
lastmod: 2026-09-16
og_description: 快速在 C# 設定條碼欄位。本指南示範如何使用 BarcodeGenerator 配置欄位、列與圖像格式。
og_image_alt: DataBar Expanded Stacked barcode showing custom columns and rows
og_title: 在 C# 中設定條碼的列與欄 – 完整 BarcodeGenerator 指南
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to set barcode columns in C# using BarcodeGenerator and also
    set barcode rows for DataBar Expanded Stacked barcodes.
  headline: How to set barcode columns and rows with C# BarcodeGenerator
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何使用 C# BarcodeGenerator 設定條碼的欄與列
url: /zh-hant/python-java/general/how-to-set-barcode-columns-and-rows-with-c-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# BarcodeGenerator 設定條碼的欄與列

如果您需要在 C# 應用程式中設定條碼的欄位，本教學將展示所需的精確步驟。您將看到如何為 DataBar Expanded Stacked 條碼同時設定欄與列，然後將結果儲存為 PNG 圖片。

以程式方式產生條碼可免除手動設計的工作，並確保在報表、發票與產品標籤上保持一致性。以下範例涵蓋完整工作流程，從安裝函式庫到產生兩張圖片——一張使用自訂欄數，另一張使用自訂列數。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 .NET 6.0 或更新版本。
* 參考 **Aspose.BarCode for .NET** NuGet 套件。使用以下指令安裝：

```bash
dotnet add package Aspose.BarCode
```

* 具有寫入權限的資料夾，以便儲存產生的 PNG 檔案。

上述條件可確保程式碼能順利編譯與執行，無需額外設定。

## 如何在 C# 中設定條碼欄位

第一個主要步驟是建立一個 `BarcodeGenerator` 實例，使用 **DataBar Expanded Stacked** 符號，並指定想要的欄數。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1️⃣ Initialize a DataBar Expanded Stacked barcode generator with the target text.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 2️⃣ Configure the number of columns. The DataBar object exposes a Columns property.
        barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // 3️⃣ Save the image using the PNG format.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼這樣可行：**  
`EncodeTypes.DatabarExpandedStacked` 告訴函式庫要渲染哪種符號。設定 `Parameters.Barcode.DataBar.Columns` 會改變內部模組的排列方式，直接影響條碼的視覺寬度。`Save` 方法則會依指定的 `BarCodeImageFormat` 將影像寫入磁碟。

### 預期結果
在任何圖像檢視器中開啟 `C:\Barcodes\DatabarCols4.png`。您應該會看到一個比預設更寬的 DataBar Expanded Stacked 條碼，因為它使用了四個欄位。

## 如何在 C# 中設定條碼列數

在儲存完欄位圖像後，您可能想要透過調整列數來改變條碼的高度。此流程與欄位設定相似，只是改用 `Rows` 屬性。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 4️⃣ Re‑initialize the generator for a fresh configuration.
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // 5️⃣ Set the number of rows. This property controls the vertical module count.
        barcodeGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // 6️⃣ Save the barcode image with the row configuration.
        barcodeGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
    }
}
```

**為什麼這樣可行：**  
重新初始化產生器可確保先前的欄位設定不會影響列的配置。變更 `Parameters.Barcode.DataBar.Rows` 會調整條碼的高度，當列數超過預設值時，產生的圖像會變得更高。

### 預期結果
開啟 `C:\Barcodes\DatabarRows3.png`。條碼會顯得較高，呈現三列的配置。

## 完整端對端範例

以下是一個單一程式，可一次產生兩張圖像。將程式碼放在同一檔案中，可示範如何在不重新啟動應用程式的情況下切換欄位與列的設定。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Common text for both barcodes.
        const string barcodeText = "Databar Expanded Stacked long";

        // ---------- Column configuration ----------
        var colGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        colGenerator.Parameters.Barcode.DataBar.Columns = 4;
        colGenerator.Save(@"C:\Barcodes\DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // ---------- Row configuration ----------
        var rowGenerator = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, barcodeText);
        rowGenerator.Parameters.Barcode.DataBar.Rows = 3;
        rowGenerator.Save(@"C:\Barcodes\DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

執行程式後會產生兩個 PNG 檔案：

* **DatabarCols4.png** – 具有四個欄位的條碼。  
* **DatabarRows3.png** – 具有三個列的條碼。

兩個檔案皆使用 **條碼影像格式** PNG，能保留銳利邊緣並支援無損壓縮，適合列印與數位顯示。

## 常見問題與小技巧

| 問題 | 答案 |
|----------|--------|
| *我可以使用 JPEG 取代 PNG 嗎？* | 可以。將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Jpeg` 即可。JPEG 檔案較小，但會產生壓縮雜訊，可能影響掃描器的可靠度。 |
| *欄位或列數的最大上限是多少？* | 函式庫會依據 DataBar 規範驗證數值。超出允許範圍會拋出 `ArgumentException`。請參考 Aspose.BarCode 文件取得確切限制。 |
| *是否需要釋放 `BarcodeGenerator`？* | 此類別實作 `IDisposable`。若在迴圈中大量建立實例，建議使用 `using` 區塊以即時釋放非受控資源。 |
| *如何在不改變欄列數的前提下調整條碼尺寸？* | 可使用 `barcodeGenerator.Parameters.Image.Width` 與 `Height` 來縮放輸出影像，同時保持模組布局不變。 |

**專業提示：** 當為高解析度列印產生條碼時，建議增加輸出影像的尺寸（`Width`/`Height`），而非調整欄或列的數量。此作法可在保持符號標準模組大小的同時，提供更清晰的圖像。

## 結論

現在您已了解如何在 C# 中使用 **BarcodeGenerator** 類別設定條碼的欄與列。本文說明了產生器的初始化、欄列數的配置、以 PNG 格式儲存條碼，以及常見的變化情境（如影像格式切換與資源釋放）。

接下來，您可以探索以下相關主題，如 **自訂條碼顏色**、**加入可讀文字**，以及 **將條碼嵌入 PDF 文件**。所有這些延伸功能皆以本指南示範的配置模式為基礎，讓您能在任何 .NET 應用程式中打造完整的條碼解決方案。

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並提供其他實作方式的範例。

- [C# 條碼產生器範例 – 設定欄、列與匯出影像](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)
- [DataBar Expanded Stacked 條碼指南 – 如何在 C# 中產生與調整尺寸](/barcode/english/python-java/general/databar-expanded-stacked-barcode-guide-how-to-generate-and-s/)
- [C# 條碼產生器範例 – 設定寬度與高度](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}