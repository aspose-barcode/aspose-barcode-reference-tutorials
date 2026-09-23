---
category: general
date: 2026-08-12
description: 使用 BarCodeGenerator 在 C# 中建立條碼圖像。了解如何產生 DataBar、控制條碼圖像尺寸，以及有效率地建立多個條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- create multiple barcodes
- how to generate databar
- barcode image size
language: zh-hant
lastmod: 2026-08-12
og_description: 使用 BarCodeGenerator 在 C# 中建立條碼圖像。本教學逐步說明如何產生 DataBar 條碼、調整條碼圖像大小，以及產生多個條碼。
og_image_alt: Screenshot of a generated DataBar barcode image saved as PNG
og_title: 在 C# 中建立條碼圖像 – 完整的 BarCodeGenerator 指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  headline: Create barcode image in C# with BarCodeGenerator
  type: TechArticle
- description: Create barcode image in C# using BarCodeGenerator. Learn how to generate
    DataBar, control barcode image size, and create multiple barcodes efficiently.
  name: Create barcode image in C# with BarCodeGenerator
  steps:
  - name: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
    text: Setting up a **barcode generator c#** instance for DataBar Omni‑directional
      encoding.
  - name: Adjusting **barcode image size** by changing X‑dimension and bar height.
    text: Adjusting **barcode image size** by changing X‑dimension and bar height.
  - name: Using a loop to **create multiple barcodes** with different heights.
    text: Using a loop to **create multiple barcodes** with different heights.
  - name: Saving the images as PNG files and verifying the output.
    text: Saving the images as PNG files and verifying the output.
  type: HowTo
tags:
- barcode
- csharp
- barcodegenerator
- databar
- image-processing
title: 使用 BarCodeGenerator 在 C# 中建立條碼圖像
url: /zh-hant/python-java/general/create-barcode-image-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中使用 BarCodeGenerator 建立條碼圖像

如果您需要在 .NET 應用程式中 **建立條碼圖像**，本指南將向您展示如何使用 `BarCodeGenerator` 類別完成。無論您是構建零售 POS 系統或庫存追蹤工具，您都將學會產生 DataBar 符號、控制條碼圖像大小，並一次產生多個條碼。

您還會發現 **barcode generator c#** API 如何讓您調整尺寸、切換輸出格式，並處理如無效資料字串等邊緣情況。完成本教學後，您即可自信地 **建立多個條碼**，而無需撰寫重複程式碼。

## 前置條件

- 已安裝 .NET 6.0 或更新版本  
- 開發環境 (Visual Studio、Rider 或 VS Code)  
- Aspose.BarCode for .NET NuGet 套件（或任何提供 `BarCodeGenerator` 的相容函式庫）  

您可以使用以下方式加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 本教學涵蓋內容

1. 為 DataBar Omni‑directional 編碼設定 **barcode generator c#** 實例。  
2. 透過變更 X‑dimension 與 bar height 來調整 **barcode image size**。  
3. 使用迴圈 **create multiple barcodes**，並設定不同高度。  
4. 將圖像儲存為 PNG 檔案並驗證輸出。  

所有程式碼片段皆完整，可直接複製貼上至新的主控台專案。

![Create barcode image example](barcode-example.png){alt="建立條碼圖像範例"}

## 步驟 1：初始化產生器 – 建立條碼圖像基礎

第一步是以所需的符號實例化 `BarCodeGenerator`。若要產生 DataBar Omni‑directional 符號，請使用 `EncodeTypes.DatabarOmniDirectional`。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for DataBar Omni‑directional.
            // The string "(01)12345678901231" follows the GS1 Application Identifier format.
            var generator = new BarCodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // The rest of the steps are performed below.
        }
    }
}
```

**為什麼重要：** 實例化產生器會定義編碼規則與資料負載。若省略正確的 `EncodeTypes` 值，函式庫將產生不支援的條碼或拋出例外。

## 步驟 2：設定 X‑dimension 與 bar height – 控制條碼圖像大小

條碼的視覺大小由兩個參數決定：

| 參數 | 控制項目 | 典型範圍 |
|-----------|------------------|---------------|
| `x_dimension.pixels` | 最小模組（「點」）的寬度 | 1 – 4 px |
| `bar_height.pixels`  | 垂直條的高度 | 30 – 150 px |

```csharp
// Set the module width to 2 px for a crisp, readable image.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set an initial bar height of 30 px.
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**專業提示：** 較小的 X‑dimension 會產生較高解析度的圖像，但在低品質印表機上可能較難掃描。請根據目標掃描設備調整此數值。

## 步驟 3：儲存第一個條碼 – 為 30 px 高度建立條碼圖像

現在您可以產生圖像並寫入磁碟。`Save` 方法接受檔案路徑與圖像格式列舉值。

```csharp
// Save the 30 px high barcode as a PNG file.
string outputFolder = @"C:\Barcodes";
generator.Save($"{outputFolder}\\Databar30.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar30.png (30 px height)");
```

**預期結果：** 會在 `C:\Barcodes` 中產生名為 `Databar30.png` 的 PNG 檔案。開啟該檔案可看到 DataBar Omni‑directional 符號，圖案清晰且高對比。

## 步驟 4：變更高度並產生其他圖像 – 建立多個條碼

若要 **create multiple barcodes** 且使用不同尺寸，只需修改 `BarHeight` 屬性並再次呼叫 `Save`。此方式避免重新實例化產生器，可節省記憶體與 CPU 時間。

```csharp
// Increase the bar height to 60 px for a larger barcode.
generator.Parameters.Barcode.BarHeight.Pixels = 60;
generator.Save($"{outputFolder}\\Databar60.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved Databar60.png (60 px height)");

// You can repeat the process for any height you need.
int[] heights = { 90, 120 };
foreach (int h in heights)
{
    generator.Parameters.Barcode.BarHeight.Pixels = h;
    generator.Save($"{outputFolder}\\Databar{h}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved Databar{h}.png ({h} px height)");
}
```

**為什麼可行：** `BarCodeGenerator` 物件保存所有設定狀態。變更單一屬性即會更新渲染引擎，供下一次 `Save` 呼叫使用，讓您能有效率地 **create multiple barcodes**。

## 步驟 5：進階 – 如何以自訂資料產生 DataBar

上述範例使用靜態 GS1 負載。在實務情境中，您常需嵌入可變的產品識別碼。函式庫接受任何符合 DataBar 規範的字串。

```csharp
string[] gtins = { "01234567890123", "98765432109876", "12345678901234" };
foreach (var gtin in gtins)
{
    // GS1 Application Identifier (01) + GTIN
    generator.CodeText = $"(01){gtin}";
    generator.Parameters.Barcode.BarHeight.Pixels = 50; // uniform height
    generator.Save($"{outputFolder}\\Databar_{gtin}.png", BarCodeImageFormat.Png);
    Console.WriteLine($"Saved barcode for GTIN {gtin}");
}
```

**重點：** 設定 `generator.CodeText` 可在不重新建立物件的情況下更新編碼資料。這是在處理大量資料時，建議的 **how to generate databar** 模式。

## 步驟 6：驗證與除錯 – 確保條碼圖像尺寸正確

產生圖像後，您可能想以程式方式確認尺寸是否符合預期。`System.Drawing` 中的 `Image` 類別可讀取檔案並回報其大小。

```csharp
using System.Drawing;

// Verify image dimensions
string[] files = { "Databar30.png", "Databar60.png", "Databar90.png" };
foreach (var file in files)
{
    using var img = Image.FromFile($"{outputFolder}\\{file}");
    Console.WriteLine($"{file}: {img.Width}px × {img.Height}px");
}
```

如果高度未反映您設定的值，請檢查：

- **X‑dimension**：過小的數值可能導致渲染器將高度四捨五入。  
- **Image format**：某些格式（例如 JPEG）在儲存時會進行壓縮，可能改變像素尺寸。PNG 可保留精確尺寸。

## 步驟 7：條碼圖像尺寸與效能的最佳實踐

| 建議 | 原因 |
|----------------|--------|
| 對大多數掃描器，將 `x_dimension.pixels` 保持在 2 – 3 px 之間。 | 在可讀性與檔案大小之間取得平衡。 |
| 在圖像將被列印時，使用 PNG 以獲得無損輸出。 | 確保精確尺寸與銳利邊緣。 |
| 產生大量條碼時，重複使用單一 `BarCodeGenerator` 實例。 | 減少物件分配的開銷。 |
| 在指派給 `CodeText` 前，先根據 GS1 標準驗證輸入字串。 | 避免執行時例外與無效掃描。 |
| 將產生的圖像存放於專用資料夾，並使用清晰的命名規則（例如 `Databar_{GTIN}.png`）。 | 簡化後續處理與稽核追蹤。 |

## 完整範例程式

以下為完整程式，涵蓋從初始化到驗證的所有步驟。將程式碼複製到新的主控台專案並執行。



## 接下來您應該學習什麼？

以下教學涵蓋與本指南示範技術密切相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [產生條碼圖像 – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [建立 DotCode 條碼圖像 – 行與列 (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)
- [如何使用 Aspose.BarCode for .NET 為 ITF-14 建立條碼安靜區](/barcode/english/net/itf-14-barcode-customization/itf-14-barcode-quiet-zone-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}