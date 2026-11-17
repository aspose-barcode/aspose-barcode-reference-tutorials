---
category: general
date: 2026-11-17
description: 學習 Aspose 條碼產生，透過一步一步的指南自訂條碼尺寸、設定模組寬度，並調整條碼尺寸，以獲得完美結果。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generation
- customize barcode size
- barcode with module width
- adjust barcode dimensions
language: zh-hant
lastmod: 2026-11-17
og_description: Aspose 條碼產生讓您自訂條碼大小、設定模組寬度，並調整尺寸。請依照本指南完成可直接執行的完整解決方案。
og_image_alt: Screenshot of a barcode created with Aspose barcode generation showing
  customized size
og_title: Aspose 條碼生成：在 C# 中自訂尺寸與模組寬度
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn Aspose barcode generation with step‑by‑step guide to customize
    barcode size, set module width, and adjust barcode dimensions for perfect results.
  headline: How to use Aspose barcode generation to customize barcode size in C#
  type: TechArticle
tags:
- Aspose.BarCode
- C#
- barcode customization
title: How to use Aspose barcode generation to customize barcode size in C#
url: /zh-hant/python-java/general/how-to-use-aspose-barcode-generation-to-customize-barcode-si/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose 條碼生成自訂條碼尺寸

如果您需要執行 Aspose 條碼生成並精確控制輸出尺寸，本指南將示範完整流程。您將學會設定模組寬度、變更條碼高度，並將結果儲存為 PNG 圖片——只需幾個簡潔步驟。

在條碼尺寸必須符合特定標籤、介面元件或列印範本時，自訂條碼尺寸相當重要。在本教學中，您將學會產生 GS1 DataBar Omni‑Directional 條碼、調整其尺寸，並驗證輸出結果。

## 前置條件

開始之前，請確保您已具備：

- 已安裝 .NET 6.0 或更新版本
- **Aspose.BarCode** 授權（免費試用版可用於評估）
- Visual Studio 2022 或您慣用的 C# IDE
- 基本的 C# 主控台應用程式知識

## 步驟 1：在 C# 專案中設定 Aspose 條碼生成

建立一個新的主控台專案，並加入 Aspose.BarCode NuGet 套件。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`Aspose.BarCode` 函式庫提供 `BarcodeGenerator` 類別，這是 Aspose 條碼生成的核心。加入套件後，即可在後續步驟中使用 API。

## 步驟 2：初始化條碼產生器並選擇條碼類型

以下程式碼建立一個用於 GS1 DataBar Omni‑Directional 條碼的產生器。此條碼類型非常適合需要緊湊數字資料的零售應用。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

// Step 1: Create a barcode generator for GS1 DataBar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

**為什麼重要：** `EncodeTypes.DatabarOmniDirectional` 列舉值告訴 Aspose 條碼生成要套用哪種編碼規則。資料字串 `"(01)12345678901231"` 符合 GS1 應用識別碼格式，確保條碼能被標準零售掃描器讀取。

## 步驟 3：使用模組寬度與條碼高度自訂條碼尺寸

Aspose 條碼生成允許您分別控制 **模組寬度**（最小條或空白）與 **條碼高度**。調整這兩個參數會直接影響條碼的視覺尺寸。

```csharp
// Step 2: Set visual parameters – X dimension (module width) and bar height
generator.Parameters.Barcode.XDimension.Pixels = 2;      // 2 px module width
generator.Parameters.Barcode.BarHeight.Pixels = 30;    // 30 px bar height
```

- **使用模組寬度的條碼** – 設定 `XDimension.Pixels` 以定義單一模組佔多少像素。數值較小會產生較緊湊的條碼，數值較大則會增加整體寬度。
- **調整條碼尺寸** – `BarHeight.Pixels` 控制條的垂直大小。提升此數值會讓條碼變高，但不會影響寬度。

這兩項設定結合起來，即可 **自訂條碼尺寸** 以符合任何版面需求。

## 步驟 4：將條碼儲存為影像檔

設定完尺寸後，將條碼匯出為 PNG 檔案。PNG 會保留您先前定義的精確像素尺寸。

```csharp
// Step 3: Save the barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY/DatabarBarHeight30Pixels.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

`Save` 方法會依照先前設定的尺寸寫入影像。產生的檔案寬度由編碼資料長度乘以模組寬度決定，高度則為先前指定的 30 px。

## 完整、可執行的範例

以下是完整程式碼，您可以直接複製、貼上並執行。它包含所有必要的 `using` 指示，示範從初始化到儲存的完整流程。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for GS1 DataBar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Customize size: set module width and bar height
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // barcode with module width = 2 px
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // adjust barcode dimensions (height)

            // Save the barcode image
            string outputPath = @"DatabarBarHeight30Pixels.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode generated and saved to {outputPath}");
        }
    }
}
```

**預期輸出：** 執行程式後，您會在專案資料夾中看到 `DatabarBarHeight30Pixels.png`。該影像顯示一個寬度與資料長度成比例、 高度為 30 px 的清晰 GS1 DataBar Omni‑Directional 條碼。您可以使用任何影像檢視器開啟檔案，以確認尺寸是否正確。

![aspose barcode generation example showing customized barcode size](https://example.com/placeholder.png "aspose barcode generation example showing customized barcode size")

*Image alt text:* *aspose barcode generation example showing customized barcode size* – 這段文字說明了教學的視覺結果。

## 實用技巧與常見陷阱

- **專業提示：** 若目標是高解析度印表機，請將模組寬度提升至至少 3 px，以避免像素化。
- **注意事項：** 模組寬度過小可能導致條碼在低品質掃描器上無法辨識。請在最終確定尺寸前，以實體掃描器測試。
- **邊緣情況：** 編碼長數字字串時，整體寬度可能超過一般標籤尺寸。此時可考慮減少模組寬度，或改用 `DatabarLimited` 等更緊湊的條碼類型。
- **相容性說明：** 此程式碼相容 .NET 6.0、.NET 7.0 以及 .NET Framework 4.8。若使用完整框架，請確保引用正確版本的 `Aspose.BarCode.dll`。

## 結論

現在您已掌握一套完整的 Aspose 條碼生成指南，涵蓋 **自訂條碼尺寸**、設定特定 **條碼模組寬度**，以及 **調整條碼尺寸** 的方法，適用於任何 C# 專案。依循本步驟，您可以產生完美貼合 UI、標籤或列印材料的條碼。

想要深入探索嗎？嘗試變更 `EncodeTypes` 產生 QR Code，或使用 `Parameters` 物件實驗背景顏色與邊距。Aspose.BarCode API 提供豐富的選項，讓您微調條碼的每一個視覺細節。祝您開發順利！

## 接下來該學什麼？

以下教學與本指南的技術緊密相關，能幫助您進一步掌握 API 功能並在專案中探索其他實作方式。每篇資源皆附完整可執行的程式碼範例與逐步說明。

- [How to customize barcode dimensions in Java with Aspose](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to set custom barcode size java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/configuring-custom-size-barcode/)
- [Set Barcode Margins Java – Adjust Barcode Image Spacing with Aspose](/barcode/english/java/image-manipulation/setting-margins-barcode-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}