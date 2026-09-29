---
category: general
date: 2026-08-22
description: 如何在 C# 中使用 Aspose.BarCode 產生條碼。一步一步學習建立條碼圖像（C#），停用 2D 元件，並儲存為 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode image c#
language: zh-hant
lastmod: 2026-08-22
og_description: 如何使用 Aspose.BarCode 在 C# 中產生條碼。本教學示範如何使用 DataBar Expanded 於 C# 建立條碼圖像、切換
  2‑D 元件，並儲存 PNG 檔案。
og_image_alt: C# code screenshot generating a DataBar Expanded barcode image without
  the 2‑D component
og_title: 如何在 C# 中生成條碼 – 完整指南：創建條碼圖像 C#
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode in C# using Aspose.BarCode. Learn to create
    barcode image c# step‑by‑step, disable the 2‑D component, and save PNG files.
  headline: How to generate barcode in C# – create barcode image c# with DataBar Expanded
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
- image generation
title: 如何在 C# 中產生條碼 – 使用 DataBar Expanded 建立條碼影像 (C#)
url: /zh-hant/python-java/general/how-to-generate-barcode-in-c-create-barcode-image-c-with-dat/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生條碼 – 使用 DataBar Expanded 建立條碼影像 (C#)

在 C# 中產生條碼是當您需要在應用程式中嵌入機器可讀資料時的常見需求。本指南將示範如何使用 Aspose.BarCode 函式庫建立條碼影像 (C#)，停用 2‑D 複合元件，並將結果儲存為 PNG 檔案。

您將看到完整、可執行的程式範例、每個設定選項的說明，以及自訂輸出的技巧。無需額外文件——只要以下程式碼與 .NET 開發環境即可。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* Aspose.BarCode for .NET NuGet 套件（`Aspose.BarCode`）  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

此函式庫提供在本教學中全程使用的 `BarcodeGenerator` 類別。

## Step 1: 設定專案並匯入命名空間

建立一個新的主控台應用程式，並匯入所需的命名空間：

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The rest of the code lives here
        }
    }
}
```

`Aspose.BarCode.Generation` 命名空間包含設定與產生條碼所需的所有類別。

## Step 2: 初始化 DataBar Expanded 條碼產生器

第一行功能程式碼會為 **DataBar Expanded** 符號建立 `BarcodeGenerator`，並提供原始資料字串。資料字串遵循 GS1 應用識別碼格式 `(01)12345678901231`。

```csharp
// Step 2: Create a DataBar Expanded barcode generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

建立產生器會配置內部位圖畫布，讓您在渲染前調整尺寸與外觀。

## Step 3: 定義模組寬度 (X‑dimension)

X‑dimension 控制最小條碼元素的寬度。以像素設定可精確掌握最終影像大小。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

`2` 像素的值在螢幕顯示上表現良好；若需更高解析度的列印，可將其調高。

## Step 4: 停用 2‑D 複合元件

DataBar Expanded 可選擇性包含攜帶額外資訊的 2‑D 元件。若要產生 **不含** 此元件的條碼，將旗標設為 `false`。

```csharp
// Step 4: Disable the 2‑D composite component of the DataBar barcode
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
```

停用該元件可降低視覺複雜度，並產生較小的 PNG 檔案。

## Step 5: 儲存不含 2‑D 元件的條碼影像

選擇輸出目錄並將影像寫入磁碟。`BarCodeImageFormat.Png` 列舉確保產出為無損 PNG 檔案。

```csharp
// Step 5: Save the barcode image without the 2‑D component
string outputDir = "YOUR_DIRECTORY/"; // replace with your actual path
barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);
```

此呼叫完成後，`Databar2DComponentDisabled.png` 會包含一個純淨的 DataBar Expanded 條碼。

## Step 6: 啟用 2‑D 複合元件

若需要額外的資料層，重新將旗標設為 `true`。同一個產生器實例即可重複使用，避免建立第二個物件。

```csharp
// Step 6: Enable the 2‑D composite component
barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
```

## Step 7: 儲存啟用 2‑D 元件的條碼影像

使用相同設定（唯獨 2‑D 旗標不同）渲染第二張影像。

```csharp
// Step 7: Save the barcode image with the 2‑D component enabled
barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

此時 `Databar2DComponentEnabled.png` 會顯示帶有額外 2‑D 圖樣的條碼。

## 完整原始程式碼

將以下程式碼全部複製到 `Program.cs`，然後執行專案。程式會在您指定的資料夾中產生兩個 PNG 檔案。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Create a DataBar Expanded barcode generator with the desired data
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarExpanded, "(01)12345678901231");

            // Set the X‑dimension (module width) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the output directory (change to a valid path on your machine)
            string outputDir = "YOUR_DIRECTORY/";

            // ---------- First image: 2‑D component disabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentDisabled.png",
                                 BarCodeImageFormat.Png);

            // ---------- Second image: 2‑D component enabled ----------
            barcodeGenerator.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
            barcodeGenerator.Save($"{outputDir}Databar2DComponentEnabled.png",
                                 BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

### 預期輸出

執行程式會印出：

```
Barcode images generated successfully.
```

並建立兩個檔案：

* `Databar2DComponentDisabled.png` – 不含 2‑D 元件的條碼  
* `Databar2DComponentEnabled.png` – 含 2‑D 元件的條碼  

使用任何影像檢視器開啟 PNG，即可驗證視覺差異。

## 常見變化與例外情況

| 情境 | 調整方式 |
|-----------|------------|
| **不同符號** | 將 `EncodeTypes.DatabarExpanded` 替換為其他值，例如 `EncodeTypes.Code128`。 |
| **更高解析度** | 將 `XDimension.Pixels` 提升至 4 或 5，或在 `barcodeGenerator.Parameters.Image` 中設定 `Resolution`。 |
| **其他影像格式** | 使用 `BarCodeImageFormat.Jpeg`、`BarCodeImageFormat.Bmp` 或 `BarCodeImageFormat.Svg`。 |
| **在 Web 應用程式中執行** | 直接將影像位元組串流至 HTTP 回應，而非儲存至磁碟。 |
| **記憶體管理** | 若目標為 .NET Framework，請將產生器包在 `using` 區塊中，以確保釋放非受控資源。 |

## 專業技巧

* **重複使用產生器** – 僅變更 2‑D 旗標即可避免重新實例化物件，節省 CPU 資源。  
* **驗證資料** – GS1 資料必須符合精確的長度與檢查碼規則；不合法的輸入會拋出 `ArgumentException`。  
* **批次處理** – 迭代資料字串集合，根據需要切換 2‑D 旗標，並以唯一檔名儲存每張影像。  

## 結論

現在您已掌握如何在 C# 中產生條碼，並以完整控制 2‑D 複合元件的方式建立條碼影像 (C#)。本範例示範了產生器的初始化、X‑dimension 設定、元件切換與 PNG 儲存。接下來，您可以探索其他符號、將影像嵌入 PDF，或將條碼產生整合至 ASP.NET Core 服務中。

--- 

*下一步*：嘗試產生 QR Code、實驗不同的影像解析度，或使用 Aspose.PDF 將產生的 PNG 嵌入 PDF。這些延伸功能皆基於相同的 `BarcodeGenerator` API，讓您的工作流程保持一致。

## 接下來該學什麼？

以下教學與本指南所示技術緊密相關，能進一步擴展您的應用。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索替代實作方式。

- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}