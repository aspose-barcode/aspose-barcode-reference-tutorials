---
category: general
date: 2026-09-29
description: 學習如何在 C# 中建立 Databar Expanded Stacked 條碼並產生條碼圖像。本分步指南示範如何使用 BarcodeGenerator
  設定列與欄。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- how to create barcode
- how to set rows
- barcode generator c#
- generate barcode image
language: zh-hant
lastmod: 2026-09-29
og_description: 說明在 C# 中產生 Databar Expanded Stacked 條碼。跟隨教學以建立條碼圖像、設定列數，並使用 BarcodeGenerator
  儲存 PNG 檔案。
og_image_alt: Screenshot of a Databar Expanded Stacked barcode saved as a PNG file
og_title: 在 C# 中生成 Databar Expanded Stacked 條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: Learn how to create a Databar Expanded Stacked barcode and generate
    barcode image in C#. This step‑by‑step guide shows how to set rows and columns
    using BarcodeGenerator.
  headline: Databar Expanded Stacked barcode generation in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: C# 中的 Databar Expanded Stacked 條碼產生
url: /zh-hant/python-java/general/databar-expanded-stacked-barcode-generation-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 Databar Expanded Stacked 條碼

如果您需要在 C# 中產生 **Databar Expanded Stacked** 條碼，本指南將向您展示 **如何建立條碼** 圖片，並可自訂列與欄位。您將看到 **如何設定列**、如何設定欄位，以及如何使用 Aspose.BarCode `BarcodeGenerator` 類別 **產生條碼圖像** 檔案。

在本教學中您將會：

* 安裝所需的 NuGet 套件。
* 為 Databar Expanded Stacked 符號初始化 `BarcodeGenerator`。
* 設定欄位與列的數量。
* 儲存產生的 PNG 檔案。
* 了解常見的陷阱，例如缺少授權或圖像路徑錯誤。

唯一的前置條件是近期的 .NET SDK（≥ .NET 6）以及 Visual Studio 2022 等 IDE。無需任何外部服務。

## 安裝與設定 BarcodeGenerator C# 函式庫

在撰寫任何程式碼之前，先將 Aspose.BarCode 套件加入您的專案：

```bash
dotnet add package Aspose.BarCode
```

如果您使用 Visual Studio，也可以透過 **NuGet 套件管理員**（搜尋 *Aspose.BarCode*）安裝。套件還原完成後，即可開始編寫程式碼。

> **專業提示：** 免費評估版會在產生的條碼上加上小水印。正式使用時，請取得授權檔並在建立任何條碼物件前呼叫 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`。

## 產生 Databar Expanded Stacked 條碼圖像

建立一個新的主控台應用程式（或將程式碼整合至任何 C# 專案），並加入以下 `using` 陳述式：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

接著撰寫完整程式。程式碼遵循原範例的每一步，並加入說明性註解。

```csharp
// Program.cs
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // --------------------------------------------------------------------
        // Step 1: Create a barcode generator for Databar Expanded Stacked
        // --------------------------------------------------------------------
        // The EncodeTypes enum tells the generator which symbology to use.
        var databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 2: Set the number of columns (the default is 1)
        // --------------------------------------------------------------------
        // Columns control the horizontal density of the barcode.
        databarGenerator.Parameters.Barcode.DataBar.Columns = 4;

        // --------------------------------------------------------------------
        // Step 3: Save the barcode image that uses 4 columns
        // --------------------------------------------------------------------
        // BarCodeImageFormat.Png creates a lossless PNG file.
        databarGenerator.Save("DatabarCols4.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 4 columns to DatabarCols4.png");

        // --------------------------------------------------------------------
        // Step 4: Re‑initialize the generator for the same barcode type
        // --------------------------------------------------------------------
        // Re‑creating the object ensures that row settings start from defaults.
        databarGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarExpandedStacked,
            "Databar Expanded Stacked long");

        // --------------------------------------------------------------------
        // Step 5: Set the number of rows (the default is 1)
        // --------------------------------------------------------------------
        // Rows affect the vertical stacking of the barcode modules.
        databarGenerator.Parameters.Barcode.DataBar.Rows = 3;

        // --------------------------------------------------------------------
        // Step 6: Save the barcode image that uses 3 rows
        // --------------------------------------------------------------------
        databarGenerator.Save("DatabarRows3.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with 3 rows to DatabarRows3.png");
    }
}
```

### 為何每一步都很重要

* **Step 1** 建立一個綁定至 *Databar Expanded Stacked* 符號的 `BarcodeGenerator`，此符號是 GS1 相容零售掃描所必需的。
* **Step 2** 透過先調整欄位間接示範 **如何設定列**——這說明欄位與列的設定是獨立的。
* **Step 3** 儲存圖像，讓您能驗證欄位數量對視覺效果的影響。
* **Step 4** 重新初始化產生器，使列的設定不會繼承先前設定的欄位值，這是常見的混淆來源。
* **Step 5** 明確展示 **如何設定列**，這也是次要關鍵字的主要焦點。
* **Step 6** 儲存第二張圖像，讓您能並排比較欄位密度與列密度的差異。

執行程式後，會在輸出目錄產生兩個 PNG 檔案：

```
DatabarCols4.png   // 4 columns, default row count (1)
DatabarRows3.png   // 3 rows, default column count (1)
```

使用圖像檢視器開啟任一檔案，即可確認條碼正確呈現。

## 常見變化與邊緣案例

| 情境 | 要變更的項目 | 原因 |
|----------|----------------|--------|
| **不同的資料負載** | 將 `BarcodeGenerator` 的第二個參數替換為您自己的字串（例如 `"123456789012"`）。 | 條碼會編碼提供的文字；請確保符合 Databar 的 GS1 規範。 |
| **其他圖像格式** | 使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。 | 選擇符合下游處理流程的格式。 |
| **較高解析度** | 呼叫 `databarGenerator.Save("file.png", BarCodeImageFormat.Png, 300);`，最後一個參數為 DPI。 | 在列印大型標籤時提升可讀性。 |
| **授權處理** | 在任何產生器建立之前加入 `License` 程式碼片段。 | 移除評估版水印，解鎖完整功能。 |

## 可靠條碼產生的技巧

* **驗證輸入字串** – Databar Expanded Stacked 需要最多 70 個字元的數字資料。提供非數字字元可能會拋出例外。
* **檢查檔案路徑** – 使用 `Path.Combine(Environment.CurrentDirectory, "output.png")` 以避免硬編碼的目錄在目標機器上不存在。
* **釋放物件** – `BarcodeGenerator` 實作 `IDisposable`。若在迴圈中大量產生條碼，請將其包在 `using` 區塊中，以即時釋放原生資源。

```csharp
using (var generator = new BarcodeGenerator(...))
{
    // configure and save
}
```

## 結論

您現在已了解 **如何建立 Databar Expanded Stacked 條碼** 以及 **如何設定列**（與欄位），並可使用 **barcode generator C#** API **產生條碼圖像**（PNG 格式）。依照上述完整範例，您即可將 Databar 條碼整合至庫存系統、銷售點應用程式，或任何需要高密度 GS1 條碼的 .NET 解決方案。

**下一步**

* 嘗試其他符號，例如 `EncodeTypes.DatabarExpanded` 或 `EncodeTypes.QR`。  
* 探索 `BarcodeReader` 類別，以驗證產生的圖像是否可被掃描。  
* 結合條碼產生與 PDF 建立（例如使用 `Aspose.PDF`），製作可列印的標籤。

祝編程愉快！

## 接下來應該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，並提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何為 Databar Expanded Stacked 條碼設定欄位 – 完整 C# 教學](/barcode/english/python-java/general/how-to-set-columns-for-a-databar-expanded-stacked-barcode-co/)
- [如何在 C# 中使用 DataBar Stacked 調整條碼大小](/barcode/english/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/)
- [Databar expanded stacked：在 C# 中產生條碼圖像](/barcode/english/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}