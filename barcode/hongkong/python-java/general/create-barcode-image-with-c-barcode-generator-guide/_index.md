---
category: general
date: 2026-08-09
description: 使用 C# 條碼產生器建立條碼圖像，並在數分鐘內學會以自訂長寬比產生多個條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: zh-hant
lastmod: 2026-08-09
og_description: 使用 C# 條碼產生器建立條碼圖像。本教學示範如何產生多個條碼、調整長寬比，並有效率地儲存 PNG 檔案。
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: 使用 C# 條碼產生器建立條碼圖像 – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: 使用 C# 條碼產生器建立條碼圖像 – 指南
url: /zh-hant/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 條碼產生器建立條碼圖像 – 教學指南

如果您需要 **快速建立條碼圖像**，本指南將示範如何使用 C# 條碼產生器完成。您將學會產生多個條碼、調整長寬比，並將每張圖像儲存為 PNG 檔案。

產生條碼圖像是建置庫存系統、銷售點終端機或運送標籤時的常見需求。完成本教學後，您將擁有兩個可直接使用的 PNG 檔案，展示不同的長寬比，並了解如何將此方式擴充至任意數量的條碼。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 C# 的 IDE）  
* 支援 DataBar Stacked Omnidirectional 的條碼函式庫（例如 **Aspose.BarCode for .NET**）。程式碼片段使用 Aspose API，但概念同樣適用於其他具備類似屬性的函式庫。

此範例不需要額外的資料庫或 Web 伺服器——僅為純粹的主控台應用程式。

## 步驟 1：建立主控台專案

建立一個新的主控台專案，並透過 NuGet 加入條碼函式庫。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet add package` 指令會下載最新穩定版的 **Aspose.BarCode**，其中提供稍後會使用的 `BarcodeGenerator` 類別。

## 步驟 2：撰寫完整程式

開啟 *Program.cs*，將內容取代為以下完整範例。程式會 **建立條碼圖像**、調整長寬比，並儲存兩個 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### 為何每個部分都很重要

* **Create barcode image** – `BarcodeGenerator` 建構子會以指定的條碼類型與資料初始化物件。  
* **c# barcode generator** – `Parameters` 屬性讓您完整掌控繪製選項；設定 `XDimension.Pixels` 可確保每根條紋在螢幕上都清晰。  
* **generate multiple barcodes** – 透過在儲存前變更 `DataBar.AspectRatio`，同一個產生器實例即可產生兩張不同的圖像，避免重複建立物件，提高效能。

## 步驟 3：執行程式並檢視結果

執行應用程式：

```bash
dotnet run
```

您應該會看到類似以下的主控台輸出：

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

開啟 `BarcodeOutputs` 資料夾，您會看到兩個 PNG 檔案：

* **DatabarAspectRatio15.png** – 適用於高度受限標籤的緊湊條碼。  
* **DatabarAspectRatio30.png** – 較高的條碼，許多掃描器在遠距離時能更可靠地讀取。

兩張圖像皆可直接嵌入 PDF、列印於收據，或傳送至行動應用程式。

## 步驟 4：將解決方案擴充至任意數量的條碼

上述模式非常容易擴展：

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – 迴圈會遍歷長寬比陣列，為每個值建立獨立的 **barcode image**。  
* 只要調整 `EncodeTypes` 或編碼字串，即可產生 QR Code、Code 128 或其他條碼類型，且不必更動其餘程式邏輯。

## 實用技巧與常見陷阱

| 提示 | 說明 |
|-----|------|
| **Reuse the same generator** | 為每張圖像重新初始化 `BarcodeGenerator` 會產生不必要的開銷。於 `Save` 之間變更參數更快且佔用較少記憶體。 |
| **Validate the output folder** | 儲存前務必呼叫 `Directory.CreateDirectory`；否則 `Save` 會拋出 `DirectoryNotFoundException`。 |
| **Choose an appropriate X‑dimension** | 像素值過低（例如 1）會使條碼在低解析度螢幕上難以辨識。2–3 的值對大多數印表機而言表現良好。 |
| **Mind the encoding** | GS1 DataBar 需要以 `(01)` 作為 GTIN 的前置符號。若省略括號，函式庫可能產生無效條碼。 |
| **Test with a real scanner** | 僅靠目視檢查不足以驗證。請使用實際的掃描硬體測試 PNG 檔案。 |

## 預期輸出（視覺說明）

*兩個 PNG 檔案皆顯示深色在淺色背景的 DataBar Stacked Omnidirectional 條碼。長寬比 15 的版本較短，長寬比 30 的版本高度約為前者的兩倍。*  

若將圖像嵌入文件中，因為我們將 `XDimension.Pixels = 2`，所以會呈現銳利的顯示效果。

## 結論

您現在已掌握如何使用 **C# 條碼產生器** **建立條碼圖像**，並可透過調整長寬比或其他參數 **產生多個條碼**。完整且可執行的範例示範了最佳實踐，包括重複使用產生器實例、處理輸出目錄以及驗證檔案建立。

接下來，您可以探索：

* 使用 `generator.Parameters.Barcode.Color` 加入自訂顏色（次要關鍵字：**c# barcode generator**）  
* 匯出為 JPEG 或 SVG 等其他格式（`BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Svg`）  
* 將條碼產生邏輯整合至 Web API，提供即時圖像服務（次要關鍵字

## 接下來該學什麼？

以下教學與本指南緊密相關，能在您已掌握的技巧基礎上，進一步深入 API 功能或探索其他實作方式。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您在專案中靈活運用。

- [建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [barcode generator tutorial c# – 使用 Aspose.BarCode for .NET 自訂 Code 16K 條碼長寬比](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [使用 Aspose.BarCode for .NET 以自訂長寬比產生 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}