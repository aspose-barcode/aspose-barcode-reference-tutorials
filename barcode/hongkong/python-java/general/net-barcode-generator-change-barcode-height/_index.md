---
category: general
date: 2026-07-18
description: 了解如何使用 .net 條碼產生器產生條碼圖像，並輕鬆調整 GS1‑Databar 全方向符號的條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- .net barcode generator
- how to generate barcode
- change barcode height
- GS1‑Databar Omni‑Directional
- barcode image export
language: zh-hant
lastmod: 2026-07-18
og_description: .NET 條碼產生器讓您快速建立條碼圖像。本指南說明如何產生條碼、調整條碼高度，以及儲存 PNG 檔案。
og_image_alt: Screenshot of a .net barcode generator output showing different bar
  heights
og_title: 使用 .NET 條碼產生器更改條碼高度
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  headline: .net barcode generator – change barcode height
  type: TechArticle
- description: Learn how to generate barcode images with a .net barcode generator
    and easily change barcode height for GS1‑Databar Omni‑Directional symbols.
  name: .net barcode generator – change barcode height
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `BarcodeGenerator generator = new
      BarcodeGenerator(...);` | Instantiates the **.net barcode generator** with the
      desired symbology and data payload. The `EncodeTypes.DatabarOmniDirectional`
      enum tells the library to use the GS1‑Databar Omni‑Directional format. |'
  - name: Adjusting the X‑dimension for larger prints
    text: '```csharp generator.Parameters.Barcode.XDimension.Pixels = 4; // Double
      the narrow bar width ``` Increasing the X‑dimension makes the whole barcode
      larger without altering the encoded data. This is handy when you print on large
      labels.'
  - name: Switching output formats
    text: '```csharp generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
      ``` SVG scales infinitely, which is perfect for web‑based scanners that need
      crisp vectors.'
  - name: Adding human‑readable text
    text: '```csharp generator.Parameters.Barcode.CodeTextVisible = true; generator.Parameters.Barcode.CodeTextAlignment
      = CodeLocation.Below; ``` Enabling `CodeTextVisible` appends the raw data under
      the barcode, useful for verification during testing.'
  type: HowTo
tags:
- barcode
- .net
- image export
title: .NET 條碼產生器 – 更改條碼高度
url: /zh-hant/python-java/general/net-barcode-generator-change-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# .net barcode generator – 更改條碼高度

有沒有想過 **如何在不使用一堆第三方工具** 的情況下產生條碼圖像？在 .NET 世界中，有一個相當簡潔的方式，而關鍵就在 **.net barcode generator**。只要幾行 C# 程式碼，就能產生 GS1‑Databar Omni‑Directional 符號、調整條碼高度，並將結果輸出為 PNG 檔案。

無論你在開發庫存系統、運單列印機，或任何需要可掃描碼的應用程式，本教學都能在幾分鐘內讓你從零開始得到可用的條碼。我們會逐段說明完整程式碼、解釋每個設定的意義，並示範如何 **更改條碼高度** 而不違背規範。

## 你需要的環境

- .NET 6.0 或更新版本（在 .NET Framework 4.7+ 上 API 行為相同）
- 條碼函式庫的參考（例如 Aspose.BarCode for .NET —— 多數商業套件皆使用相同類別）
- 開發環境（Visual Studio、Rider，或安裝 C# 擴充功能的 VS Code）
- 具寫入權限的資料夾 —— 教學會把 PNG 檔案儲存於此

就這些。除了條碼函式庫本身，無需額外的 NuGet 套件。

## 使用 .net barcode generator 更改條碼高度

以下是一個 **完整、可執行的 Console 程式**。將它貼到新的 C# 專案中，調整輸出資料夾路徑，然後按 F5 執行。

```csharp
using System;
using Aspose.BarCode.Generation;   // Namespace for the barcode generator
using Aspose.BarCode;               // For BarCodeImageFormat enum

namespace BarcodeHeightDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a GS1‑Databar Omni‑Directional symbol.
            // The string "(01)12345678901231" follows the GS1 Application Identifier syntax.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Define common visual parameters.
            // X‑dimension controls the width of the narrowest bar; 2 pixels works well for screen display.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set the initial bar height to 30 pixels.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Save the first image – a compact barcode.
            string outFolder = @"YOUR_DIRECTORY"; // ← replace with a real path
            generator.Save($"{outFolder}/DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // 5️⃣ Increase the bar height to 60 pixels for a larger, more readable code.
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 6️⃣ Save the second image – a taller barcode.
            generator.Save($"{outFolder}/DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Two barcode images have been generated successfully.");
        }
    }
}
```

### 為什麼每一行都很重要

| 行 | 原因 |
|------|--------|
| `BarcodeGenerator generator = new BarcodeGenerator(...);` | 使用所需的條碼類型與資料內容實例化 **.net barcode generator**。`EncodeTypes.DatabarOmniDirectional` 列舉告訴函式庫使用 GS1‑Databar Omni‑Directional 格式。 |
| `XDimension.Pixels = 2;` | X‑dimension 為最細條的寬度。設定為 *2 像素* 可在大多數螢幕上產生清晰圖像，同時保持檔案尺寸低。 |
| `BarHeight.Pixels = 30;` | 這就是 **更改條碼高度** 的步驟，決定每根條的高度。30 像素是小標籤的良好預設值。 |
| `generator.Save(...);` | 將條碼寫入 PNG 檔案。PNG 為無損格式，掃描器能看到你產生的精確圖樣。 |
| `BarHeight.Pixels = 60;` | 這裡再次 **更改條碼高度** —— 這次設定為 60 像素。呼叫第二次 `Save` 時，函式庫會自動以新尺寸重新繪製符號。 |
| `Console.WriteLine(...);` | 快速回饋程式已順利完成且未拋出例外。 |

> **小技巧：** 若需更高解析度的列印輸出，可將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Tiff`，並提升 `Resolution` 屬性（例如 `generator.Parameters.ImageResolution = 300;`）。條碼高度仍會被遵守，只是以更細的 DPI 呈現。

## 如何使用不同設定產生條碼圖像

上面的程式碼示範了基礎用法，但實務上常會需要額外調整：

### 調整 X‑dimension 以適應較大列印
```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4; // Double the narrow bar width
```
提升 X‑dimension 會讓整個條碼變大，但不會改變編碼資料。這在大型標籤列印時相當方便。

### 切換輸出格式
```csharp
generator.Save($"{outFolder}/Databar.svg", BarCodeImageFormat.Svg);
```
SVG 可無限縮放，非常適合需要向量圖的 Web 掃描器。

### 加入可讀文字
```csharp
generator.Parameters.Barcode.CodeTextVisible = true;
generator.Parameters.Barcode.CodeTextAlignment = CodeLocation.Below;
```
啟用 `CodeTextVisible` 後，條碼下方會顯示原始資料，便於測試時驗證。

## 常見陷阱：在 **更改條碼高度** 時要注意

1. **高度過小** – 某些掃描器要求最小條高（常見為實體 10 mm）。若把 `BarHeight.Pixels` 設得太低，產生的圖像在實機掃描時可能無法辨識。務必以目標硬體測試。  
2. **X‑dimension 與高度不匹配** – 巨大的條高搭配極細的 X‑dimension 會讓條碼看起來被拉長，可能導致解碼錯誤。除非規範另有說明，建議保持大約 3:1 至 5:1 的比例。  
3. **忘記重設參數** – 產生器在多次儲存間會保留狀態。若在產生第一張圖後改變 `BarHeight`，再使用同一個實例產生另一張條碼，先前的高度會被保留下來。請在每次產生不同條碼前重設屬性，或直接重新建立 `BarcodeGenerator` 實例。

## 完整端對端範例（含 NuGet 安裝）

如果從頭開始，請依照以下步驟建立專案：

```bash
dotnet new console -n BarcodeHeightDemo
cd BarcodeHeightDemo
dotnet add package Aspose.BarCode
```

將自動產生的 `Program.cs` 替換為前面示範的程式碼，**記得把 `YOUR_DIRECTORY`** 改成類似 `Path.Combine(Environment.CurrentDirectory, "output")` 的路徑。接著：

```bash
dotnet run
```

執行後，你會在 `output` 資料夾看到兩個 PNG 檔案：

- `DatabarBarHeight30Pixels.png` – 高度為 30 像素的緊湊條碼。  
- `DatabarBarHeight60Pixels.png` – 高度為 60 像素的較高條碼。

兩張圖看起來相似，但第二張的條更長，對低解析度掃描器更友好。

![Barcode height example](/images/barcode-height.png){alt=".net barcode generator output showing different bar heights"}

## 重點回顧與後續步驟

我們說明了如何使用 **.net barcode generator** **產生條碼** 圖像、微調 **更改條碼高度** 的屬性，並以 PNG 格式儲存。關鍵要點如下：

- 使用正確的 `EncodeTypes` 來實例化產生器。  
- 透過 `XDimension` 與 `BarHeight` 控制視覺尺寸。  
- 每次變更後呼叫 `Save` 產出新圖檔。  
- 需要時調整解析度與格式。

## 接下來可以學什麼？

以下教學與本篇內容緊密相關，能幫助你進一步掌握 API 功能並探索其他實作方式：

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to create dotcode extended codetext with Aspose.BarCode for .NET](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}