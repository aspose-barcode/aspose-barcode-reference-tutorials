---
category: general
date: 2026-10-05
description: 在 C# 中建立條碼 PNG，並學習如何為堆疊式 DataBar 全方向條碼設定長寬比 15。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: zh-hant
lastmod: 2026-10-05
og_description: 在 C# 中建立條碼 PNG，並在幾個步驟內了解如何將堆疊式 DataBar 全向條碼的長寬比設定為 15。
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: 在 C# 中建立條碼 PNG – 設定寬高比 15 教學
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何在 C# 中使用自訂長寬比建立條碼 PNG
url: /zh-hant/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用自訂長寬比建立條碼 PNG

如果您需要在 C# 中 **建立條碼 PNG**，本指南將向您展示如何將堆疊式 DataBar 全方向條碼的 **長寬比設定為 15**。我們會逐步說明每個 API 呼叫，解釋長寬比為何重要，並提供一個完整、可執行的範例，您可以直接放入任何 .NET 專案中。

產生條碼影像是庫存系統、運送標籤以及零售銷售點應用程式的常見需求。完成本教學後，您將擁有符合合作夥伴精確視覺規格的 PNG 檔案。無需外部工具，無需手動影像編輯——只需程式碼。

## 前置條件

* .NET 6.0 或更新版本（範例使用 .NET 6，但亦相容於 .NET 5+）
* Visual Studio 2022（或任何支援 .NET 的 IDE）
* **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 具寫入權限於您欲儲存 PNG 檔案的資料夾

這些需求相當簡潔；相同的程式碼可在 .NET Core、.NET Framework 或主控台應用程式中執行。

## 使用 Aspose.BarCode 建立條碼 PNG

第一步是以正確的條碼類型實例化 `BarcodeGenerator` 類別。在本例中，我們使用 `EncodeTypes.DatabarStackedOmniDirectional`，它會產生可從任意方向讀取的堆疊式 DataBar。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*為何重要：* 建構子接受兩個參數——**條碼符號**與**資料字串**。DataBar 格式需要 GS1 應用程式識別碼，這也是範例資料以 `(01)` 開頭的原因。

## 如何設定堆疊式 DataBar 的長寬比

DataBar 的視覺寬度受 **長寬比** 屬性控制。較高的比例會使條紋變寬，從而提升低解析度印表機的掃描可靠性。

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` 定義單一模組（最小條或空格）的大小。將其保持在 2 px 可產生清晰、高密度的影像，適用於大多數標籤印表機。

## 設定長寬比 15 – 程式碼說明

現在我們套用 **設定長寬比 15** 的需求。這是本教學的核心，示範您需要的精確 API 呼叫。

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*為何是 15？* 堆疊式 DataBar 的預設長寬比為 12。將其提升至 15 會使每條條紋寬度增加 25 %，這常符合物流供應商要求較寬條碼以加速掃描的規格。

## 將條碼儲存為 PNG

在完成產生器設定後，最後一步是將影像寫入磁碟。`Save` 方法接受檔案路徑與影像格式列舉值。

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

PNG 格式保留無損品質，確保條碼在任何顯示器或印表機上皆能如設計般精確呈現。

## 完整範例與預期輸出

以下是完整程式碼，您可將其複製到主控台應用程式的 `Main` 方法中。它包含上述所有步驟，並附帶一則簡短的驗證訊息。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**預期輸出**

執行程式後會產生名為 `DatabarAspectRatio15.png` 的檔案，內含清晰、寬闊的堆疊式 DataBar 條碼。開啟 PNG 時，您應該會看到水平拉伸的條碼，仍符合 GS1 DataBar 規範。

![Barcode PNG with aspect ratio 15](barcode-aspect15.png)

*Image alt text:* **建立條碼 PNG，顯示長寬比為 15 的堆疊式 DataBar**

### 提示與常見陷阱

| 情況 | 建議 |
|-----------|----------------|
| **影像模糊** | 將 `XDimension.Pixels` 提升至 3 px 或更高，但請將整體影像尺寸維持在 500 px 以下，以免檔案過大。 |
| **掃描器無法讀取條碼** | 確認資料字串符合 GS1 格式（以 `(01)` 為前綴）。同時，確保印表機解析度至少為 300 dpi。 |
| **需要其他檔案格式** | 將 `BarCodeImageFormat.Png` 改為 `Jpeg`、`Bmp` 或 `Gif`——API 支援所有主要的點陣圖格式。 |
| **在 Web 應用程式中執行** | 使用 `generator.Save(Stream, BarCodeImageFormat.Png)` 直接寫入 HTTP 回應，無需觸及檔案系統。 |

### 擴充範例

* **在單一影像中放置多個條碼：** 建立額外的 `BarcodeGenerator` 實例，並使用 `Graphics` 在同一個 `Bitmap` 上繪製。  
* **加入可讀文字：** 設定 `generator.Parameters.Caption.Visible = true`，並透過 `generator.Parameters.Caption.Font` 自訂字型。  
* **動態長寬比：** 從設定檔或資料庫取得比例值，即時產生寬度不同的條碼。

## 結論

在本教學中，您學會了如何在 C# 中 **建立條碼 PNG**，以及如何精確地為堆疊式全方向 DataBar 條碼 **設定長寬比** 15。完整且可執行的程式碼示範了所有必要的 API 呼叫，說明每個設定為何重要，並提供實務部署的實用技巧。  

接下來，您可以探索如何為其他條碼類型（例如 QR Code 或 Code 128）**設定長寬比**，或將產生器整合至 ASP .NET Core 服務，以按需回傳條碼影像。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在本教學示範的技巧之上。每個資源皆提供完整可運作的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 C# 與 Aspose.Barcode 建立 databar PNG 影像](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [如何在 C# 中使用 Aspose.Barcode 建立堆疊式 databar 條碼](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [在 .NET 中自訂堆疊式全方向 databar 長寬比](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}