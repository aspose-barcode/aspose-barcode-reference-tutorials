---
category: general
date: 2026-10-08
description: 學習如何使用 C# 條碼產生器範例調整條碼圖像大小，僅需幾行程式碼即可將條碼高度從 30 像素改為 60 像素。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to resize barcode
- barcode generator example c#
language: zh-hant
lastmod: 2026-10-08
og_description: 如何使用 C# 條碼產生器範例快速調整條碼尺寸。調整條碼高度、儲存 PNG 檔案，並避免常見陷阱。
og_image_alt: Screenshot showing a resized barcode generated with C# code
og_title: 如何在 C# 中調整條碼大小 – 步驟式產生器範例
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  headline: How to resize barcode using a barcode generator example in C#
  type: TechArticle
- description: Learn how to resize barcode images with a C# barcode generator example,
    adjusting bar height from 30 px to 60 px in just a few lines of code.
  name: How to resize barcode using a barcode generator example in C#
  steps:
  - name: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
    text: Open each PNG in an image viewer and verify the pixel dimensions (e.g.,
      150 × 30 px vs. 150 × 60 px).
  - name: Print the images at 100 % scale.
    text: Print the images at 100 % scale.
  - name: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
    text: Scan with a handheld barcode scanner or a mobile app. The decoded data should
      be
  type: HowTo
tags:
- barcode
- C#
- image processing
title: 如何使用 C# 條碼產生器範例調整條碼大小
url: /zh-hant/python-java/general/how-to-resize-barcode-using-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用條碼產生器範例（C#）調整條碼大小

如果您需要在 .NET 專案中 **調整條碼** 圖片大小，本指南提供完整解決方案。您將看到一個簡潔的 **條碼產生器範例 C#**，將條碼高度由 30 px 調整為 60 px，並將每個版本儲存為 PNG 檔案。

在收據、標籤或商品頁面需要以不同視覺比例呈現相同資料時，往往需要調整條碼大小。與其使用外部編輯器手動編輯點陣圖，不如以程式方式調整條碼尺寸，確保資料完整性不受影響。

在本教學中，您將會：

* 設定 DataBar Omni‑Directional 條碼產生器。
* 修改 X‑dimension 與條碼高度參數。
* 儲存兩個不同高度的圖像。
* 了解為何變更條碼高度可行，以及需要留意的邊緣情況。

> **Prerequisite** – 您已具備 .NET 開發環境（Visual Studio 2022 或更新版本）以及提供 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 的條碼函式庫。此程式碼相容於截至 2026 年 10 月的最新函式庫版本。

## 條碼產生器範例 C# 的先備條件

在開始之前，請確保您已具備以下項目：

| 項目 | 原因 |
|------|------|
| .NET 6.0 SDK 或更新版本 | 提供範例所使用的執行環境與語言功能。 |
| 條碼函式庫（例如 Aspose.BarCode、Dynamsoft，或任何提供 `BarcodeGenerator` 的函式庫） | 提供 `EncodeTypes.DatabarOmniDirectional` 列舉以及圖像匯出方法。 |
| 可寫入的資料夾（例如 `C:\Temp\Barcodes\`） | 範例會將 PNG 檔案儲存至此位置。 |
| 基本的 C# 知識 | 本教學假設您熟悉類別、屬性與字串插值。 |

若尚未安裝函式庫，請透過 NuGet 進行安裝：

```bash
dotnet add package Aspose.BarCode
```

將套件名稱替換為您實際使用的套件；下方示範的 API 介面在大多數條碼 SDK 中皆相同。

## 調整條碼大小 – 步驟 1：建立產生器

第一步是以目標條碼類型與資料內容實例化 `BarcodeGenerator`。本例產生 **DataBar Omni‑Directional** 條碼，編碼一個 GTIN‑14 值。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a DataBar Omni‑Directional barcode generator with the desired data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**Why this matters:** `EncodeTypes.DatabarOmniDirectional` 列舉告訴函式庫使用哪種條碼標準。資料字串遵循 GS1 應用識別碼 `(01)`，代表 14 位元的 GTIN，確保條碼符合全球貿易規範。

## 調整條碼大小 – 步驟 2：定義模組寬度與初始條碼高度

條碼的視覺尺寸取決於兩個參數：

* **X‑dimension** – 最小條（模組）的寬度，可使用像素或毫米表示。
* **Bar height** – 條的垂直長度。

在儲存之前設定這些值，可確保產生的圖像符合所需尺寸。

```csharp
// Step 2: Define the X‑dimension (module width) and set the bar height to 30 px
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2 px per module
generator.Parameters.Barcode.BarHeight.Pixels = 30; // 30 px tall bars
```

**Explanation:** X‑dimension 設為 2 px 可產生緊湊且仍具可掃描性的條碼。30 px 的高度是小標籤的常見預設值。若需要更密集或更稀疏的圖樣，可獨立調整 X‑dimension 與高度。

## 調整條碼大小 – 步驟 3：儲存第一張圖（30 px 高度）

將條碼匯出為 PNG 檔案。`Save` 方法接受檔案路徑與圖像格式列舉。

```csharp
// Step 3: Save the barcode image with a 30 px height
string outputPath = @"C:\Temp\Barcodes\";
generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Result:** `DatabarBarHeight30Pixels.png` 包含一張 30 px 高的條碼。您可使用任何圖像檢視器開啟檔案以驗證尺寸。

## 調整條碼大小 – 步驟 4：將條碼高度改為 60 px

若要產生較大的版本，只需修改 `BarHeight` 屬性。產生器會重用相同的資料與 X‑dimension，條碼圖樣保持不變——僅視覺尺寸變大。

```csharp
// Step 4: Change the bar height to 60 px for a larger barcode
generator.Parameters.Barcode.BarHeight.Pixels = 60;
```

**Why this works:** 條碼渲染引擎會在需要時即時計算每根條的幾何形狀。於下一次呼叫 `Save` 前更新高度屬性，即會以新尺寸重新光柵化。

## 調整條碼大小 – 步驟 5：儲存第二張圖（60 px 高度）

```csharp
// Step 5: Save the barcode image with a 60 px height
generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

現在您已擁有兩個 PNG 檔案，一個 30 px、另一個 60 px，適用於不同尺寸的標籤。

## 條碼產生器範例 C# 完整原始碼

以下是完整、可直接執行的程式。將其貼到新的 Console 專案中即可立即測試。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeResizeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with DataBar Omni‑Directional symbology
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Set X‑dimension and initial bar height (30 px)
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 3️⃣ Define output folder (ensure it exists)
            string outputPath = @"C:\Temp\Barcodes\";
            System.IO.Directory.CreateDirectory(outputPath);

            // 4️⃣ Save the 30 px version
            generator.Save($"{outputPath}DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30 px barcode.");

            // 5️⃣ Increase bar height to 60 px
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the 60 px version
            generator.Save($"{outputPath}DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60 px barcode.");
        }
    }
}
```

**Expected output in the console:**

```
Saved 30 px barcode.
Saved 60 px barcode.
```

執行後，開啟兩個 PNG 檔案即可看到視覺差異。兩者皆編碼相同的 GTIN‑14 值，掃描結果相同，無論高度如何。

## 為何調整條碼高度對掃描安全

條碼掃描器讀取的是亮暗模組的圖樣，而非絕對像素數。只要 **X‑dimension** 保持在掃描器容許的容差範圍（通常為實體單位 0.5 mm 至 2 mm），改變高度不會影響可讀性。函式庫會自動縮放模組，保留必要的靜止區與對齊圖樣。

## 常見陷阱與避免方式

| 陷阱 | 解決方法 |
|------|----------|
| **輸出資料夾不存在** | 在儲存前呼叫 `Directory.CreateDirectory(outputPath)`。 |
| **X‑dimension 設定不當導致掃描模糊** | 大多數印表機建議將 `XDimension.Pixels` 設於 1 px 至 4 px 之間，並以實體掃描器測試。 |
| **對非常大的條碼使用點陣圖格式** | 改用 `BarCodeImageFormat.Svg`，可無限縮放且不失真。 |
| **忘記在第二次儲存前重設 `BarHeight`** | 確保在再次呼叫 `Save` 前先指派新高度。 |

## 專業技巧：在迴圈中產生多種尺寸

若需要一系列高度（例如 30 px、45 px、60 px），使用簡單的 `foreach` 迴圈即可減少重複程式碼：

```csharp
int[] heights = { 30, 45, 60 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputPath}DatabarBarHeight{h}Pixels.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved {h} px barcode.");
}
```

此模式非常適合批次處理商品目錄。

## 邊緣情況：不同圖像格式與 DPI 設定

* **SVG 輸出** – 使用 `BarCodeImageFormat.Svg` 產生向量檔，可在不失真的情況下任意調整大小。
* **高 DPI PNG** – 設定 `generator.Parameters.Image.DpiX` 與 `DpiY` 為 300 或 600，以符合列印需求；條碼高度仍以像素計算，需相應放大。
* **非標準條碼類型** – 某些條碼（如 QR Code）使用獨立的 `Size` 屬性而非 `BarHeight`。請參考函式庫文件取得正確設定方式。

## 測試調整後的條碼

1. 在圖像檢視器中開啟每個 PNG，確認像素尺寸（例如 150 × 30 px 與 150 × 60 px）。  
2. 以 100 % 比例列印圖像。  
3. 使用手持條碼掃描器或手機應用程式掃描，解碼資料應與原始 GTIN‑14 完全相同。

## 接下來您應該學習什麼？

以下教學與本指南緊密相關，提供完整的程式碼範例與逐步說明，協助您深入掌握其他 API 功能，並探索在專案中實作的不同方式。

- [C# 條碼產生器範例 – 設定寬度與高度](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)
- [使用 Aspose.BarCode 在 C# 中調整條碼大小 – 步驟說明](/barcode/english/python-java/general/how-to-resize-barcode-in-c-with-aspose-barcode-step-by-step/)
- [使用條碼產生器 C# 儲存條碼圖像 – 步驟說明](/barcode/english/python-java/general/how-to-save-barcode-images-with-barcode-generator-c-step-by/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}