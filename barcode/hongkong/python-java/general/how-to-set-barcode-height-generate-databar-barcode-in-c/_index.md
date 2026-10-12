---
category: general
date: 2026-10-12
description: 如何在 C# 中使用 Aspose.BarCode 設定條碼高度並產生 DataBar 條碼。跟隨一步一步的指南，提供完整程式碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- generate barcode c#
- how to create databar
- create databar barcode
- change barcode height
language: zh-hant
lastmod: 2026-10-12
og_description: 如何在 C# 中設定條碼高度，並使用 Aspose.BarCode 產生 DataBar 條碼。了解完整程式碼、每個步驟的重要性，以及如何更改條碼高度。
og_image_alt: Screenshot showing how to set barcode height in a C# barcode generator
og_title: 如何在 C# 中設定條碼高度並產生 DataBar 條碼
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to set barcode height and generate a DataBar barcode in C# using
    Aspose.BarCode. Follow a step‑by‑step guide with complete code.
  headline: How to set barcode height, generate DataBar barcode in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何設定條碼高度，並在 C# 中產生 DataBar 條碼
url: /zh-hant/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何設定條碼高度，於 C# 產生 DataBar 條碼

如果您需要以程式方式 **how to set barcode** 設定條碼尺寸，本指南將示範完整步驟。您將學習如何產生 DataBar Omni‑directional 條碼、調整其高度，並將兩個版本儲存為 PNG 檔案。

變更條碼的條紋高度是將條碼整合至收據、商品標籤或行動螢幕時的常見需求。以下範例使用 Aspose.BarCode 函式庫，支援完整的 GS1 DataBar 符號集。

## 您將達成的目標

* **how to set barcode** 高度（用於 DataBar Omni‑directional 條碼）  
* 產生 **generate barcode c#** 程式碼，建立兩個高度不同的影像  
* 了解 **how to create databar** 符號以及條碼高度的重要性  
* 套用 **change barcode height** 邏輯，無需重新建立產生器  

不需要任何外部工具，僅需 Aspose.BarCode NuGet 套件與 .NET 6+ 執行環境。

## 前置條件

* .NET 6 SDK 或更新版本已安裝  
* Visual Studio 2022（或任何 C# 編輯器）  
* Aspose.BarCode for .NET – 透過 `dotnet add package Aspose.BarCode` 安裝  

> **專業提示：** 如果您沒有商業授權金鑰，可使用 Aspose 的免費試用授權；API 的使用方式相同。

## 步驟 1：安裝 Aspose.BarCode 套件

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode` 命名空間，內含我們將用來 **generate barcode c#** 產生影像的 `BarcodeGenerator` 類別。

## 步驟 2：建立 DataBar 條碼產生器

第一個具體動作是以 **how to set barcode** 參數建立 `BarcodeGenerator`，指定所需的符號類型與資料字串。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 2: Initialize the generator for a DataBar Omni‑directional barcode
var barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, // symbology
    "(01)12345678901231");               // GS1 data payload
```

*此點重要原因:* `EncodeTypes.DatabarOmniDirectional` 產生緊湊且全方向的 DataBar，可從任意角度掃描——非常適合小型標籤。

## 步驟 3：設定通用條碼參數（包括初始條碼高度）

現在我們先設定 **how to set barcode** 的 X‑dimension 與條碼高度，然後儲存第一張影像。

```csharp
// Step 3: Configure X‑dimension (module width) and initial bar height
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;    // 2‑pixel modules
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;   // 30‑pixel height
```

X‑dimension 控制每根條紋的總寬度；設定為 2 像素可在大多數螢幕上產生清晰可讀的圖像。之後的 **change barcode height** 步驟會重複使用同一個產生器，節省時間與記憶體。

## 步驟 4：儲存第一張條碼影像（30 像素高度）

```csharp
// Step 4: Save the 30‑pixel barcode image
barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
```

`DatabarHeight30.png` 檔案現在包含一個條紋高度為 30 像素的 DataBar 條碼。

## 步驟 5：僅將條碼高度更改為 60 像素

為了示範 **change barcode height**，我們只修改 `BarHeight` 屬性。其他設定保持不變，這是從單一產生器產出多種尺寸的最有效方式。

```csharp
// Step 5: Update the bar height to 60 pixels
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
```

## 步驟 6：儲存第二張條碼影像（60 像素高度）

```csharp
// Step 6: Save the 60‑pixel barcode image
barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
```

您現在擁有兩個 PNG 檔案，條碼高度不同但資料與 X‑dimension 完全相同。

## 完整、可執行的範例

以下是完整程式碼，您可以直接貼到新建的主控台應用程式（`dotnet new console`）中執行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator for a DataBar Omni‑directional barcode
        var barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231");

        // Set X‑dimension and initial bar height (30 pixels)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;

        // Save the first image (30‑pixel height)
        barcodeGenerator.Save("DatabarHeight30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight30.png");

        // Change only the bar height to 60 pixels
        barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;

        // Save the second image (60‑pixel height)
        barcodeGenerator.Save("DatabarHeight60.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved DatabarHeight60.png");
    }
}
```

### 預期輸出

執行程式後，執行檔的工作目錄會產生兩個檔案：

* `DatabarHeight30.png` – 條紋高度為 30 像素的 DataBar 條碼。  
* `DatabarHeight60.png` – 同樣的條碼，但每根條紋高度加倍。

兩張影像皆可用任何圖像檢視器開啟，或直接嵌入 PDF、HTML 頁面或列印標籤中。

## 為何調整條碼高度很重要

* **Scanning reliability:** 某些掃描器在低解析度媒介上對極短的條紋辨識困難；提升高度可改善偵測率。  
* **Design constraints:** 行動應用可能需要緊湊的條碼（30 px），而列印收據則可能需要較大的條碼（60 px）。  
* **Regulatory compliance:** 部分產業規範要求 GS1 DataBar 符號必須具備最低條紋高度。

透過重複使用同一個 `BarcodeGenerator` 實例，可避免重新解析資料字串的開銷，對高吞吐量環境特別有利。

## 常見變化與邊緣情況

| Situation | Recommended tweak |
|-----------|-------------------|
| 需要不同的 X‑dimension | 在第一次 `Save` 之前變更 `XDimension.Pixels`。 |
| 想使用不同的符號集（例如 DataBar Stacked） | 在建立 `BarcodeGenerator` 時使用 `EncodeTypes.DatabarStacked`。 |
| 必須將條碼嵌入 PDF | 使用 `barcodeGenerator.Save(stream, BarCodeImageFormat.Png)`，並將該串流加入 PDF 函式庫。 |
| 在 .NET Framework 4.6 上執行 | 相同程式碼可運作，只需參考相應的 Aspose.BarCode 組件。 |

## 可靠條碼產生的專業提示

* **快取產生器**：當您需要產生大量使用相同資料但尺寸不同的條碼時，可快取 `BarcodeGenerator` 以提升效能。  
* ** 

## 接下來您可以學習什麼？

以下教學與本指南示範的技巧緊密相關，提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [如何使用 Aspose.BarCode for .NET 產生與調整單維 DataBar 條碼高度](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [如何使用 C# 與 Aspose.BarCode 建立 DataBar PNG 影像](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [如何產生自訂尺寸的條碼並以 C# 儲存影像](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}