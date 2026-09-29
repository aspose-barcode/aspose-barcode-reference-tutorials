---
category: general
date: 2026-08-03
description: 條碼產生器 C# 教學示範如何使用 Aspose.BarCode 產生條碼圖像、設定列與行，並將 DataBar Expanded Stacked
  儲存為 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- generate barcode image
language: zh-hant
lastmod: 2026-08-03
og_description: 條碼產生器 C# 教學說明如何使用 Aspose.BarCode 產生條碼圖像、設定 DataBar Expanded Stacked
  的欄與列，並儲存 PNG 檔案。
og_image_alt: Screenshot of a DataBar Expanded Stacked barcode generated with C#
og_title: 條碼產生器 C# – 逐步指南：生成條碼圖像
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial shows how to generate barcode image with
    Aspose.BarCode, set columns and rows, and save PNG files for DataBar Expanded
    Stacked.
  headline: Barcode generator C# – generate barcode image
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 條碼產生器 C# – 產生條碼圖片
url: /zh-hant/python-java/general/barcode-generator-c-generate-barcode-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器 C# – 產生條碼圖像

如果您需要一個能夠為 DataBar Expanded Stacked 產生條碼圖像的 C# 條碼產生器，本指南將帶您完成完整流程。您將學習如何設定欄與列、將結果儲存為 PNG，以及如何將程式碼套用到其他條碼類型。

以程式方式產生條碼圖像可省去手動步驟，確保發票、運送標籤與庫存系統之間的一致性。本教學涵蓋從專案設定到完整原始碼的所有內容，讓您能立即執行範例。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 或更新版本已安裝  
* 如 Visual Studio 2022 等 IDE（任何支援 C# 的編輯器皆可）  
* **Aspose.BarCode for .NET** 授權 – 可使用免費評估版進行測試  
* 基本的 C# 語法熟悉度  

若缺少上述任一項目，請前往 dotnet.microsoft.com 下載 .NET SDK，並使用以下指令取得 Aspose.BarCode NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立條碼產生器 C# 專案

建立一個新的主控台應用程式，並加入必要的 `using` 指示詞：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // The implementation starts in the next sections
        }
    }
}
```

`BarcodeGenerator` 類別是條碼產生器 C# API 的核心。它接受條碼類型與要編碼的文字。

## 步驟 2：產生 DataBar Expanded Stacked 條碼並設定欄數

以下範例建立一個具有四個欄的條碼。調整 `Columns` 屬性會改變 DataBar Expanded Stacked 條碼的視覺密度。

```csharp
// Step 2: Create a barcode generator for DataBar Expanded Stacked
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of columns to 4
barcodeGenerator.Parameters.Barcode.DataBar.Columns = 4;

// Save the barcode image as PNG
string colsPath = @"YOUR_DIRECTORY\DatabarCols4.png";
barcodeGenerator.Save(colsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 4 columns saved to {colsPath}");
```

**為什麼這很重要：** 欄數會影響在緊湊空間內可儲存的資料量。設定為 4 會產生較寬的條碼，但仍能被大多數掃描器讀取。

## 步驟 3：產生具有自訂列數的條碼

第二個範例示範如何透過設定 `Rows` 屬性來控制垂直佈局。三列配置在水平空間受限時，可產生較高的條碼。

```csharp
// Step 3: Create a second barcode generator for the same type
BarcodeGenerator barcodeGeneratorRows = new BarcodeGenerator(
    EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

// Set the number of rows to 3
barcodeGeneratorRows.Parameters.Barcode.DataBar.Rows = 3;

// Save the barcode image as PNG
string rowsPath = @"YOUR_DIRECTORY\DatabarRows3.png";
barcodeGeneratorRows.Save(rowsPath, BarCodeImageFormat.Png);

Console.WriteLine($"Barcode with 3 rows saved to {rowsPath}");
```

**為什麼這很重要：** 調整列數可讓條碼適應窄欄位，同時保持可讀性。條碼產生器 C# 會自動重新計算模組大小以符合規格。

## 步驟 4：完整、可執行的範例

以下是一個結合前述步驟的獨立程式。將程式碼複製到 `Program.cs`，將 `YOUR_DIRECTORY` 替換為實際的資料夾路徑，然後執行應用程式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // ---------- Generate barcode with 4 columns ----------
            BarcodeGenerator colsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            colsGenerator.Parameters.Barcode.DataBar.Columns = 4;

            string colsFile = @"YOUR_DIRECTORY\DatabarCols4.png";
            colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with columns saved to {colsFile}");

            // ---------- Generate barcode with 3 rows ----------
            BarcodeGenerator rowsGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");

            rowsGenerator.Parameters.Barcode.DataBar.Rows = 3;

            string rowsFile = @"YOUR_DIRECTORY\DatabarRows3.png";
            rowsGenerator.Save(rowsFile, BarCodeImageFormat.Png);
            Console.WriteLine($"Generated barcode image with rows saved to {rowsFile}");
        }
    }
}
```

### 預期輸出

執行程式後，目標目錄會出現兩個 PNG 檔案：

* **DatabarCols4.png** – 具有四個欄的 DataBar Expanded Stacked 條碼  
* **DatabarRows3.png** – 同樣資料以三列方式編碼  

使用任何圖像檢視器開啟這些檔案，即可看到清晰、可掃描的條碼，適合列印或嵌入 PDF 中。

## 如何使用自訂尺寸產生條碼圖像

若需要特定的圖像大小，可在呼叫 `Save` 之前調整 `ImageHeight` 與 `ImageWidth` 屬性：

```csharp
colsGenerator.Parameters.ImageHeight = 150; // pixels
colsGenerator.Parameters.ImageWidth = 300;  // pixels
colsGenerator.Save(colsFile, BarCodeImageFormat.Png);
```

變更尺寸不會影響編碼資料；僅會調整視覺呈現的比例。此技巧在將條碼整合至具有固定版面限制的 UI 元件時特別有用。

## 常見陷阱與專業提示

* **路徑分隔符號：** 使用逐字字串 (`@"C:\Path\file.png"`) 或 `Path.Combine` 以避免 Windows 上的跳脫字元問題。  
* **授權強制執行：** 若未使用有效授權，產生的圖像會帶有浮水印。請於應用程式啟動時盡早載入授權：

  ```csharp
  Aspose.BarCode.License license = new Aspose.BarCode.License();
  license.SetLicense("Aspose.BarCode.lic");
  ```

* **編碼限制：** DataBar Expanded Stacked 最多支援 74 個數字字元。超過此上限會拋出例外。請在建立產生器前驗證輸入長度。  
* **效能考量：** 重複使用同一個 `BarcodeGenerator` 實例進行多次儲存，可減少記憶體配置。若編碼文字相同，只需在儲存間變更 `Rows` 或 `Columns` 屬性。

## 後續步驟

現在您已能使用條碼產生器 C# 產生條碼圖像，建議進一步探索：

* **不同條碼類型** – 嘗試 `EncodeTypes.QR`、`EncodeTypes.Code128` 或 `EncodeTypes.Pdf417`。  
* **顏色客製化** – 設定 `Parameters.Barcode.ForeColor` 與 `BackColor` 以符合品牌色彩。  
* **嵌入 PDF** – 結合產生的 PNG 與 Aspose.PDF，建立可列印的文件。  

透過這些延伸功能，您可以打造完整的條碼解決方案，應用於庫存、物流或零售等領域。

---


## 接下來應該學什麼？

以下教學與本指南所示技術緊密相關，提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索其他實作方式。

- [產生條碼圖像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [建立 DotCode 條碼圖像 – 行與欄 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}