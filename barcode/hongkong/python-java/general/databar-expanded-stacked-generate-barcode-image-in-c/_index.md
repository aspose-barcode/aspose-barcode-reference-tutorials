---
category: general
date: 2026-08-15
description: Databar 在 C# 中擴充堆疊條碼產生功能。了解如何產生條碼圖像、設定 DataBar 版面的欄與列。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- databar expanded stacked
- generate barcode image
- how to generate barcode
- how to set columns
- how to set rows
language: zh-hant
lastmod: 2026-08-15
og_description: Databar 在 C# 中擴充堆疊條碼產生功能。請依照此一步步指南，快速產生條碼圖像、設定欄位與列。
og_image_alt: Screenshot of a databar expanded stacked barcode generated with C#
og_title: Databar 擴展堆疊 – 在 C# 中生成條碼圖像
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  headline: 'Databar expanded stacked: generate barcode image in C#'
  type: TechArticle
- description: Databar expanded stacked barcode generation in C#. Learn how to generate
    barcode image, set columns and rows for DataBar layouts.
  name: 'Databar expanded stacked: generate barcode image in C#'
  steps:
  - name: 1. Install the Aspose.BarCode library
    text: 'The code uses the **Aspose.BarCode for .NET** library, which provides the
      `BarcodeGenerator` class. Install the NuGet package with the following command:'
  - name: 2. Create a barcode generator for **databar expanded stacked**
    text: The generator is the entry point for all barcode operations. You must specify
      the symbology (`EncodeTypes.DatabarExpandedStacked`) and the text to encode.
  - name: 3. How to set columns for DataBar
    text: The `Columns` property controls how many vertical modules appear in the
      stacked barcode. Valid values are 2, 3, or 4. Setting columns influences the
      barcode’s width and the amount of data it can store.
  - name: 4. Save the 4‑column barcode image
    text: Saving the image produces a file that you can embed in reports, invoices,
      or mobile apps. The `Save` method accepts a file path and an image format.
  - name: 5. How to set rows for DataBar
    text: Rows add a second dimension to the stacked layout, allowing more data to
      be encoded without widening the barcode. The `Rows` property defaults to 1;
      you can increase it up to 3 for the expanded stacked variant.
  - name: 6. Save the 3‑row barcode image
    text: '```csharp // Step 5: Save the 3‑row barcode image barcode.Save("YOUR_DIRECTORY/DatabarRows3.png",
      BarCodeImageFormat.Png); ```'
  - name: 7. Complete C# example to generate barcode image
    text: 'Putting all steps together yields a self‑contained program you can copy
      into a console application:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Databar 擴展堆疊式：在 C# 中產生條碼圖像
url: /zh-hant/python-java/general/databar-expanded-stacked-generate-barcode-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Databar expanded stacked：在 C# 中產生條碼圖像

如果您需要在 C# 中產生 **databar expanded stacked** 條碼圖像，本指南將完整示範 **如何產生條碼** 圖像，並可自訂欄與列的版面配置。您將會看到如何設定欄、設定列，以及如何在不離開 IDE 的情況下儲存產生的圖像。

本教學內容包括：

* 為 **databar expanded stacked** 符號建立條碼產生器。  
* 設定 4 欄版面與 3 列版面。  
* 將每種配置儲存為 PNG 檔案。  
* 處理如欄數無效等邊緣案例的技巧。

不需要額外的文件說明；完整且可執行的範例已包含於此。

![Databar expanded stacked barcode example](YOUR_DIRECTORY/DatabarCols4.png){: .center alt="databar expanded stacked barcode generated with C#" }

## Databar expanded stacked 條碼產生步驟

### 1. 安裝 Aspose.BarCode 函式庫

程式碼使用 **Aspose.BarCode for .NET** 函式庫，提供 `BarcodeGenerator` 類別。使用以下指令安裝 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

套件安裝完成後，於檔案頂部加入必要的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

### 2. 為 **databar expanded stacked** 建立條碼產生器

產生器是所有條碼操作的入口點。必須指定符號 (`EncodeTypes.DatabarExpandedStacked`) 以及要編碼的文字。

```csharp
// Step 1: Create a barcode generator for Databar Expanded Stacked
BarcodeGenerator barcode = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked,
    "Databar Expanded Stacked long");
```

*為什麼這很重要：* `EncodeTypes` 列舉告訴函式庫要產生哪種條碼格式。使用 **databar expanded stacked** 可確保產生的圖像符合 GS1 DataBar 的堆疊版規範。

### 3. 如何設定 DataBar 的欄 (Columns)

`Columns` 屬性控制堆疊條碼中垂直模組的數量。有效值為 2、3 或 4。設定欄位會影響條碼的寬度以及可儲存的資料量。

```csharp
// Step 2: Configure a 4‑column layout
barcode.Parameters.Barcode.DataBar.Columns = 4;
```

**提示：** 若嘗試指派超出允許範圍的值，函式庫會拋出 `ArgumentException`。在向使用者提供欄位選擇時，務必先驗證輸入。

### 4. 儲存 4 欄條碼圖像

儲存圖像會產生可嵌入報表、發票或行動應用程式的檔案。`Save` 方法接受檔案路徑與影像格式。

```csharp
// Step 3: Save the 4‑column barcode image
barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
```

檔案寫入後，您可以使用任何圖像檢視器開啟，以確認 **databar expanded stacked** 圖樣正確顯示。

### 5. 如何設定 DataBar 的列 (Rows)

列為堆疊版面加入第二維度，讓在不增加條碼寬度的情況下編碼更多資料。`Rows` 屬性預設為 1；對於擴展堆疊變體，可提升至最多 3 列。

```csharp
// Step 4: Switch to a 3‑row layout (columns remain unchanged)
barcode.Parameters.Barcode.DataBar.Rows = 3;
```

**為什麼列很重要：** 增加列數可在保持資料容量的同時減少整體寬度，對於窄標籤或行動螢幕空間特別有用。

### 6. 儲存 3 列條碼圖像

```csharp
// Step 5: Save the 3‑row barcode image
barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
```

現在您擁有兩個 PNG 檔案——一個為 4 欄版面，另一個為 3 列版面——皆使用 **databar expanded stacked** 符號。

### 7. 完整 C# 範例：產生條碼圖像

將所有步驟整合即可得到一個可直接複製到主控台應用程式的自足程式：

```csharp
using System;
using Aspose.BarCode.Generation;

namespace DatabarExpandedStackedDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Databar Expanded Stacked
            BarcodeGenerator barcode = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked,
                "Databar Expanded Stacked long");

            // Configure a 4‑column layout and save
            barcode.Parameters.Barcode.DataBar.Columns = 4;
            barcode.Save("YOUR_DIRECTORY/DatabarCols4.png", BarCodeImageFormat.Png);
            Console.WriteLine("4‑column barcode saved.");

            // Change to a 3‑row layout (columns stay at 4) and save
            barcode.Parameters.Barcode.DataBar.Rows = 3;
            barcode.Save("YOUR_DIRECTORY/DatabarRows3.png", BarCodeImageFormat.Png);
            Console.WriteLine("3‑row barcode saved.");
        }
    }
}
```

**預期輸出**

執行程式會印出：

```
4‑column barcode saved.
3‑row barcode saved.
```

並在 `YOUR_DIRECTORY` 中建立兩個 PNG 檔案。開啟檔案即可驗證每張圖像皆顯示有效的 **databar expanded stacked** 條碼。

## 常見陷阱與實用技巧

* **目錄是否存在** – `Save` 不會自動建立缺少的資料夾。請確保 `YOUR_DIRECTORY` 已存在，或在儲存前使用 `Directory.CreateDirectory`。
* **欄位限制** – 除 2、3、4 之外的值會觸發例外。可使用簡單的範圍檢查來防止使用者輸入錯誤：

  ```csharp
  int columns = 4;
  if (columns < 2 || columns > 4) throw new ArgumentOutOfRangeException(nameof(columns));
  barcode.Parameters.Barcode.DataBar.Columns = columns;
  ```

* **列數限制** – 擴展堆疊變體最多支援 3 列。將 `Rows` 設為 0 或大於 3 的值同樣會拋出例外。
* **影像格式** – `BarCodeImageFormat.Png` 提供無損品質，最適合列印。只有在檔案大小是主要考量時才使用 `Jpeg`。

## 後續步驟

現在您已了解如何使用自訂欄與列配置 **產生條碼** 圖像，您可以：

* 將產生器整合至 Web API，隨需提供條碼圖像。  
* 結合條碼與 PDF 產生函式庫，將其嵌入發票中。  
* 使用相同的 `Parameters.Barcode.DataBar` 物件，嘗試其他 DataBar 變體（`DatabarExpanded`、`DatabarLimited`）。

如需更深入的客製化——例如變更條紋顏色、加入可讀文字，或套用 QR‑code 疊加——請參考 Aspose.BarCode 文件中 `BarcodeGenerator` 屬性的說明。

---

依照本指南操作，您已掌握 **databar expanded stacked** 工作流程，學會 **如何設定欄**、**如何設定列**，並產生兩個可直接投入生產使用的條碼圖像。祝開發順利！

## 接下來該學什麼？

以下教學與本指南示範的技巧密切相關，提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能並在專案中探索替代實作方式。

- [產生條碼圖像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [建立 DotCode 條碼圖像 – 列與欄 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [如何產生條碼 – 一維條碼類型](/barcode/english/net/one-dimensional-barcode-types/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}