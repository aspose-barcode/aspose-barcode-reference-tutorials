---
category: general
date: 2026-11-17
description: 快速在 C# 中建立條碼 PNG – 一步一步指南，示範如何產生 Planet 條碼、調整尺寸並儲存圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to create barcode
- barcode generator example
- generate planet barcode
- customize barcode size
language: zh-hant
lastmod: 2026-11-17
og_description: 使用 Aspose.Barcode 在 C# 中建立條碼 PNG。了解如何產生 Planet 條碼、調整其尺寸，並儲存高品質的 PNG
  圖像。
og_image_alt: C# code snippet that creates a barcode PNG file
og_title: 在 C# 中建立條碼 PNG – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode PNG in C# quickly – a step‑by‑step guide that shows
    how to generate a Planet barcode, customize its size, and save the image.
  headline: How to create barcode PNG in C# using Aspose.Barcode
  type: TechArticle
- description: Create barcode PNG in C# quickly – a step‑by‑step guide that shows
    how to generate a Planet barcode, customize its size, and save the image.
  name: How to create barcode PNG in C# using Aspose.Barcode
  steps:
  - name: '**Instantiate** the generator with the desired symbology and data.'
    text: '**Instantiate** the generator with the desired symbology and data.'
  - name: '**Adjust parameters** such as size and bar style.'
    text: '**Adjust parameters** such as size and bar style.'
  - name: '**Save** the image in the format you need.'
    text: '**Save** the image in the format you need.'
  type: HowTo
tags:
- barcode
- C#
- Aspose.Barcode
title: 如何在 C# 中使用 Aspose.Barcode 產生條碼 PNG
url: /zh-hant/python-java/general/how-to-create-barcode-png-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.Barcode 建立條碼 PNG

如果您需要從 C# 程式碼**建立條碼 PNG**檔案，本指南會一步步說明如何操作。無論您是構建郵件標籤系統或是 POS 應用程式，您都會學到完整的**條碼產生器範例**，它能產生 Planet 條碼、讓您**自訂條碼尺寸**，並將結果儲存為 PNG 圖片。

您將完成本教學，得到一個可直接執行的程式，您可以將其放入任何 .NET 專案。無需外部服務——只需要 Aspose.Barcode 函式庫和幾行程式碼。

## 前置條件

在開始之前，請確保您已具備以下條件：

| 需求 | 原因 |
|------|------|
| .NET 6.0 SDK 或更新版本 | 提供 C# 主控台應用程式的執行環境 |
| Visual Studio 2022（或任何 IDE） | 讓您編譯與偵錯程式碼 |
| Aspose.Barcode for .NET NuGet package | 包含範例中使用的 `BarcodeGenerator` 類別 |

從命令列安裝 NuGet 套件：

```bash
dotnet add package Aspose.Barcode
```

> **專業提示：** 若您偏好在 Visual Studio 使用套件管理員主控台，請執行 `Install-Package Aspose.Barcode`。

## 步驟 1：建立新主控台專案

開啟終端機並執行：

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
```

這會產生一個名為 **BarcodePngDemo** 的最小 C# 主控台應用程式。

## 步驟 2：在 C# 中建立條碼 PNG（解決方案核心）

本教學的核心是 `BarcodeGenerator` 物件。在此步驟中，我們透過以 *Planet* 符號與欲編碼的資料實例化產生器，**建立條碼 PNG**。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2.1: Initialize the generator for the Planet barcode type
        // "123456" is the data that will be encoded.
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2.2: Set the module (X‑dimension) size – 4 pixels per bar gives a clear image.
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 2.3: Choose the empty‑bars style (unfilled bars) for a postal‑friendly look.
        generator.Parameters.Barcode.FilledBars = false;

        // Step 2.4: Save the generated barcode as a PNG file.
        // Adjust the path as needed for your environment.
        generator.Save("postal_planet_empty_bars.png", BarCodeImageFormat.Png);

        System.Console.WriteLine("Barcode PNG created successfully.");
    }
}
```

### 為何這些設定很重要

* **EncodeTypes.Planet** – *Planet* 符號是為郵件應用設計；它能有效編碼數字資料。  
* **XDimension.Pixels = 4** – 此**自訂條碼尺寸**設定控制每條條紋的寬度。4 像素的數值在大多數印表機上兼顧可讀性與檔案大小。  
* **FilledBars = false** – 空條樣式會產生白底黑條的影像，在高對比度紙張上掃描效果佳，這是郵件標籤的常見需求。  
* **BarCodeImageFormat.Png** – PNG 能保留銳利邊緣且不使用有損壓縮，確保條碼仍可被掃描。

## 步驟 3：如何建立條碼 – 基本設定回顧

如果您是條碼產生新手，上述三行程式碼已概括整個**如何建立條碼**的工作流程：

1. **實例化** 產生器，指定所需的符號與資料。  
2. **調整參數**，例如尺寸與條紋樣式。  
3. **儲存** 圖片為您需要的格式。  

您可以將 `EncodeTypes.Planet` 替換為其他支援的類型（例如 `EncodeTypes.Code128`），而不必更改其他程式碼。

## 步驟 4：條碼產生器範例 – 加入更多自訂

除了尺寸與空條之外，Aspose.Barcode 還允許您微調顏色、邊距與文字。以下是一個快速擴充範例，加入紅色前景與白色背景，然後以不同名稱儲存相同條碼。

```csharp
// Change colors (optional)
generator.Parameters.Barcode.BarColor = System.Drawing.Color.Red;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;

// Save a second version
generator.Save("postal_planet_red.png", BarCodeImageFormat.Png);
```

> **注意：** 使用低對比度的顏色可能導致某些掃描器無法讀取條碼。務必使用目標硬體進行測試。

## 步驟 5：產生帶空條的 Planet 條碼（完整範例）

將所有步驟整合起來，以下是完整程式碼，您可以直接複製貼上至 `Program.cs`：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for a Planet barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Customize size – 4 pixels per module.
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Use empty‑bars style for postal friendliness.
            generator.Parameters.Barcode.FilledBars = false;

            // Save the primary PNG.
            generator.Save("postal_planet_empty_bars.png", BarCodeImageFormat.Png);

            // Optional: change colors and save a second version.
            generator.Parameters.Barcode.BarColor = System.Drawing.Color.Red;
            generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
            generator.Save("postal_planet_red.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both barcode PNG files have been generated.");
        }
    }
}
```

執行程式：

```bash
dotnet run
```

您應該會在專案資料夾中看到兩個 PNG 檔案：

* `postal_planet_empty_bars.png` – 具空條的經典黑底白條條碼。  
* `postal_planet_red.png` – 顯示額外**自訂條碼尺寸**選項的彩色變體。  

在圖像檢視器中開啟任一檔案，即可看到乾淨且可掃描的條碼，已可直接列印。

## 常見問題與除錯

| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 條碼顯示模糊 | X‑dimension 設定過低（例如 1 像素） | 將 `XDimension.Pixels` 提升至至少 3‑4 像素。 |
| 掃描器無法讀取影像 | 顏色對比度不足 | 使用深色條紋於淺色背景，或恢復預設的黑白配色。 |
| `Save` 拋出 `ArgumentException` | 檔案路徑無效或缺少寫入權限 | 確認目錄存在且應用程式具有寫入權限。 |
| 列印出錯誤的符號 | `EncodeTypes` 列舉值錯誤 | 再次確認您選擇了 `EncodeTypes.Planet`（或預期的類型）。 |

## 生產環境最佳實踐

* **驗證輸入資料** 再傳遞給 `BarcodeGenerator`。Planet 條碼僅接受特定長度的數字字串。  
* **快取產生器**，若需大量產生相同設定的條碼，重複使用物件可提升效能。  
* **使用 PNG 進行螢幕顯示**，**使用 PDF 或 TIFF 進行高解析度列印**——兩者皆受 Aspose.Barcode 支援。  
* **使用實際的掃描器** 進行測試。不同裝置對條寬與對比度的容忍度各異。  

## 結論

現在您已了解如何在 C# 中**建立條碼 PNG**檔案，並掌握簡潔的**條碼產生器範例**。本教學涵蓋了：

* 為 **Planet** 符號實例化 `BarcodeGenerator`。  
* 使用 X‑dimension 屬性**自訂條碼尺寸**。  
* 套用空條樣式以符合郵件需求。  
* 將結果儲存為 PNG 圖片，並可選擇調整顏色。  

接下來您可以探索其他符號、加入可讀文字，或將程式碼整合至回傳條碼 PNG 的 Web API 中。祝開發順利，掃描永遠精準！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何在 C# 中建立條碼 PNG – 步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-barcode-png-in-c-step-by-step-guide/)
- [如何在 C# 中建立具有自訂長寬比的條碼 PNG](/barcode/english/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/)
- [如何使用 C# 條碼產生器建立 Planet 條碼](/barcode/english/python-java/general/how-to-use-a-c-barcode-generator-to-create-a-planet-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}