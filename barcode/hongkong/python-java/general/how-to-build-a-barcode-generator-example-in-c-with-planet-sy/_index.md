---
category: general
date: 2026-10-05
description: C# 條碼產生器範例，示範如何產生 Planet 條碼並建立條碼圖像。請遵循此一步一步的指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- generate planet barcode
- create barcode image c#
language: zh-hant
lastmod: 2026-10-05
og_description: C# 條碼產生器範例一步步教你如何產生 Planet 條碼並建立條碼圖像（C#），取得完整、可執行的解決方案。
og_image_alt: Screenshot of a generated Planet barcode image created by a C# barcode
  generator example
og_title: C# 條碼產生器範例 – 快速產生 Planet 條碼
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: barcode generator example in C# that shows you how to generate planet
    barcode and create barcode image c#. Follow this step‑by‑step guide.
  headline: How to build a barcode generator example in C# with Planet symbology
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Planet 符號建立條碼產生器範例
url: /zh-hant/python-java/general/how-to-build-a-barcode-generator-example-in-c-with-planet-sy/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 條碼產生器範例 – 產生 Planet 條碼並建立條碼圖像

如果您需要 C# 的 **條碼產生器範例**，本指南將精確示範如何在幾行程式碼內產生 Planet 條碼並建立條碼圖像 (c#)。您將看到一個完整、可直接執行的解決方案，能直接放入任何 .NET 專案中。

Planet 條碼是郵政服務用來編碼路由資訊的。完成本教學後，您將了解為何函式庫會自動決定條碼高度、如何控制 X 維度，以及如何將結果儲存為 PNG 檔案。無需任何外部工具——只需 Aspose.BarCode for .NET 套件與 .NET 開發環境。

## 前置條件

* .NET 6.0 SDK 或更新版本已安裝  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 套件 (`Aspose.BarCode`)  

您可以從指令列安裝此套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：初始化 Planet 編碼的條碼產生器

在任何 **條碼產生器範例** 中的第一步是建立 `BarcodeGenerator` 實例並指定編碼類型。對於 Planet 條碼，您需要使用 `EncodeTypes.Planet` 並傳入欲編碼的資料字串。

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

**為什麼這很重要：** `EncodeTypes.Planet` 列舉告訴函式庫使用 Planet 符號，該符號具有郵政標準要求的固定模組模式。提供資料（此例為 `"123456"`）可確保條碼包含正確的數字路由碼。

## 步驟 2：設定 X 維度（模組寬度）像素

X 維度控制每個單一模組（最小條）的寬度。調整它會改變條碼的整體尺寸，同時不影響可讀性。

```csharp
// Set the X dimension (module width) to 4 pixels
generator.Parameters.Barcode.XDimension.Pixels = 4;
```

**為什麼這很重要：** 較大的 X 維度會產生較大的條碼，適合在大信封上列印。函式庫會自動縮放高度，以維持 Planet 條碼的正確長寬比。

## 步驟 3：將條碼圖像儲存至磁碟

最後，您將儲存產生的圖像。函式庫會自行決定最佳高度，您只需指定輸出路徑與格式。

```csharp
using Aspose.BarCode;

// Define the output file path
string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";

// Save the barcode as a PNG image
generator.Save(outputFile, BarCodeImageFormat.Png);
```

**為什麼這很重要：** 以 PNG 儲存可保留條碼的清晰邊緣，這對可靠掃描至關重要。`Save` 方法亦支援其他格式（JPEG、BMP、TIFF），若您需要不同的輸出可使用。

### 預期輸出

執行程式碼後，您會在 `C:\Barcodes` 中找到名為 **PlanetAutoHeight.png** 的檔案。圖像將類似下方示意圖（替代文字：*條碼產生器範例顯示 Planet 條碼*）。

![C# 範例產生的 Planet 條碼](/images/planet-barcode-example.png){alt="條碼產生器範例顯示 Planet 條碼"}

## 步驟 4：可選 – 自訂前景與背景顏色

如果您的應用程式需要不同的視覺樣式，您可以在儲存前變更條碼顏色。

```csharp
// Set foreground (bars) to dark blue and background to light gray
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

// Save the customized image
generator.Save(@"C:\Barcodes\PlanetCustomColors.png", BarCodeImageFormat.Png);
```

**提示：** 請務必使用實體掃描器測試自訂條碼，以確認顏色變更不會影響可讀性。

## 步驟 5：錯誤處理與驗證

若資料不符合 Planet 符號的要求（例如含非數字字元），Aspose.BarCode 函式庫會拋出 `ArgumentException`。請將產生程式碼包在 try‑catch 區塊中，以提供清晰的回饋。

```csharp
try
{
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "ABC123");
    generator.Save(@"C:\Barcodes\InvalidPlanet.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid data for Planet barcode: {ex.Message}");
}
```

**為什麼這很重要：** Planet 條碼僅接受特定長度的數字資料。適當的驗證可防止執行時失敗，並節省整合測試的時間。

## 完整、可執行範例

將所有步驟整合在一起，即可得到一個可自行執行的程式，您可以直接複製、貼上並執行。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Initialize the generator with Planet encoding
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Set the X dimension (module width) to 4 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Optional: customize colors (comment out if not needed)
        // generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
        // generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.LightGray;

        // Step 3: Save the barcode image
        string outputFile = @"C:\Barcodes\PlanetAutoHeight.png";
        generator.Save(outputFile, BarCodeImageFormat.Png);

        Console.WriteLine($"Planet barcode saved to {outputFile}");
    }
}
```

編譯並執行程式：

```bash
dotnet run
```

您應該會在主控台看到確認檔案位置的訊息，且 PNG 檔案將包含產生的 Planet 條碼。

## 常見變化與邊緣案例

| 變化 | 實作方式 | 使用時機 |
|-----------|------------------|------------|
| **不同的資料長度** | 將 `new BarcodeGenerator(EncodeTypes.Planet, "987654321")` 中的第二個參數改為其他值 | 郵政服務需要較長的路由編號時 |
| **較高解析度** | 在 `Save` 之前設定 `generator.Parameters.ImageResolution = 300;` | 在高 DPI 列印機上列印時 |
| **不同的影像格式** | 使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Tiff` | 當 PNG 不適合您的工作流程時 |
| **動態檔名** | `string outputFile = Path.Combine(folder, $"Planet_{DateTime.Now:yyyyMMdd_HHmmss}.png");` | 批次處理多個條碼時 |

## 專業提示：打造穩健的條碼產生器範例

* **重複使用產生器實例** 於建立多個使用相同設定的條碼時；只需變更 `EncodeTypes` 或資料字串即可提升效能。  
* **驗證輸入** 在傳遞給 `BarcodeGenerator` 之前。簡單的正規表達式如 `^\d{6,9}$` 可確保資料符合 Planet 的要求。  
* **釋放資源** 若在長時間執行的服務中產生數千張圖像。`BarcodeGenerator` 實作 `IDisposable`，因此在適當時機使用 `using` 區塊包住。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data))
{
    // configure and save...
}
```

## 結論

本 **條碼產生器範例** 示範了如何使用 Aspose.BarCode for .NET **產生 Planet 條碼** 並 **建立條碼圖像 (C#)**。您已學會如何初始化產生器、設定 X 維度、可選地自訂顏色、處理驗證錯誤，並將結果儲存為 PNG 檔案。提供完整的原始碼後，您即可立即將 Planet 條碼產生整合至任何 C# 應用程式。

接下來，您可以探索其他符號如 QR、Code128 或 DataMatrix——它們皆遵循相同的建立 `BarcodeGenerator`、設定參數、呼叫 `Save` 的流程。相同的原則適用，使您能輕鬆在各種業務情境中擴充條碼產生功能。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [建立 Planet 條碼圖像 – 步驟指南](/barcode/english/python-java/general/create-planet-barcode-image-step-by-step-guide/)
- [條碼產生器 C# – 建立 Planet 條碼與 RM4SCC 範例](/barcode/english/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/)
- [使用條碼產生器範例建立 C# 條碼圖像](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}