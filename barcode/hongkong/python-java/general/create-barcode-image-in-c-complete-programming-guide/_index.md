---
category: general
date: 2026-08-09
description: 使用本分步指南在 C# 中建立條碼圖像。學習如何產生條碼、調整條碼高度（像素）以及高效地建立多個條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create multiple barcodes
- barcode height pixels
language: zh-hant
lastmod: 2026-08-09
og_description: 快速在 C# 中建立條碼圖像。跟隨本教學了解如何產生條碼、設定條碼高度像素，以及產生多個條碼。
og_image_alt: Screenshot of barcode images generated with C# code showing different
  heights
og_title: 在 C# 中建立條碼圖像 – 開發者完整指南
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  headline: Create barcode image in C# – complete programming guide
  type: TechArticle
- description: Create barcode image in C# with this step-by-step guide. Learn how
    to generate barcode, adjust barcode height pixels, and create multiple barcodes
    efficiently.
  name: Create barcode image in C# – complete programming guide
  steps:
  - name: Define the output folder
    text: Choose a folder where the generated PNG files will be stored. Using an absolute
      path avoids permission surprises.
  - name: Instantiate the barcode generator
    text: For a DataBar Omnidirectional barcode, pass `EncodeTypes.DatabarOmniDirectional`
      and the GS1‑128 data string.
  - name: Set common barcode parameters
    text: The most common visual tweaks are the X‑dimension (module width) and the
      bar height. Both are expressed in pixels.
  - name: Save the first barcode image
    text: '```csharp // Step 4: Save the barcode image with a 30 px height string
      file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"); barcode.Save(file30,
      BarCodeImageFormat.Png); ```'
  - name: Adjust the barcode height pixels
    text: Changing the height does not require a new `BarcodeGenerator` instance—just
      modify the parameter.
  - name: Save the second barcode image
    text: '```csharp // Step 6: Save the barcode image with the new 60 px height string
      file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"); barcode.Save(file60,
      BarCodeImageFormat.Png); ```'
  - name: Expected output
    text: 'After running the full sample, the `Barcodes` folder contains:'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 在 C# 中建立條碼圖像 – 完整程式設計指南
url: /zh-hant/python-java/general/create-barcode-image-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立條碼圖像 – 完整程式指南

如果您需要在 .NET 應用程式中**建立條碼圖像**，本指南將向您展示如何使用 Aspose.BarCode 函式庫**產生條碼**。您將看到如何控制**條碼高度（像素）**、儲存圖像，以及在不重複程式碼的情況下**產生多個條碼**。

本教學涵蓋從安裝套件到自訂尺寸的所有步驟，讓您可以直接複製貼上即能在專案中執行的範例。

## 前置條件

* 已安裝 .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何 C# IDE）  
* NuGet 套件 `Aspose.BarCode` – 透過以下方式安裝  

```bash
dotnet add package Aspose.BarCode
```

不需要其他相依性。

## 使用 BarcodeGenerator C# 產生條碼圖像

用於建立條碼圖像的核心類別是 `BarcodeGenerator`。它封裝了編碼類型、資料字串以及所有渲染參數。

### 步驟 1：定義輸出資料夾

選擇一個用來儲存產生的 PNG 檔案的資料夾。使用絕對路徑可避免權限問題。

```csharp
// Step 1: Define the output folder
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
Directory.CreateDirectory(outputFolder);
```

> **為什麼？** 以程式方式建立資料夾可確保即使在全新機器上，隨後的 `Save` 呼叫也能成功。

### 步驟 2：實例化條碼產生器

對於 DataBar Omnidirectional 條碼，傳入 `EncodeTypes.DatabarOmniDirectional` 以及 GS1‑128 資料字串。

```csharp
// Step 2: Create a DataBar Omnidirectional barcode generator with the data to encode
var barcode = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

> **注意：** `BarcodeGenerator` 物件可重複使用；您可以在不同的儲存之間變更其參數，以**從相同資料產生多個條碼**。

### 步驟 3：設定共用條碼參數

最常調整的視覺參數是 X‑dimension（模組寬度）與條碼高度，兩者皆以像素為單位。

```csharp
// Step 3: Set common barcode parameters (X‑dimension and initial height)
barcode.Parameters.Barcode.XDimension.Pixels = 2;   // thin modules for sharper output
barcode.Parameters.Barcode.BarHeight.Pixels = 30;  // initial height – 30 px
```

> **為什麼要設定 X‑dimension？** 較小的 X‑dimension 會產生更高的解析度，這在圖像需要列印或在高 DPI 螢幕上顯示時尤為重要。

### 步驟 4：儲存第一個條碼圖像

```csharp
// Step 4: Save the barcode image with a 30 px height
string file30 = Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png");
barcode.Save(file30, BarCodeImageFormat.Png);
```

檔案 `DatabarBarHeight30Pixels.png` 現在包含一個高度為 30 像素的 DataBar Omnidirectional 條碼。

### 步驟 5：調整條碼高度（像素）

變更高度不需要重新建立 `BarcodeGenerator` 實例，只需修改參數即可。

```csharp
// Step 5: Change the bar height to 60 px for the same barcode
barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

### 步驟 6：儲存第二個條碼圖像

```csharp
// Step 6: Save the barcode image with the new 60 px height
string file60 = Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png");
barcode.Save(file60, BarCodeImageFormat.Png);
```

現在您擁有兩個 PNG 檔案，具有不同的**條碼高度（像素）**，示範了**建立條碼圖像**變體是多麼簡單。

## 動態設定條碼高度（像素）

通常您需要一系列高度符合 UI 元件或列印標籤的條碼。以下輔助方法將高度變更抽象化：

```csharp
/// <summary>
/// Saves a barcode image with a custom height.
/// </summary>
/// <param name="generator">Configured BarcodeGenerator instance.</param>
/// <param name="heightPx">Desired bar height in pixels.</param>
/// <param name="fileName">Target file name (including path).</param>
void SaveBarcodeWithHeight(BarcodeGenerator generator, int heightPx, string fileName)
{
    generator.Parameters.Barcode.BarHeight.Pixels = heightPx;
    generator.Save(fileName, BarCodeImageFormat.Png);
}
```

現在您可以呼叫 `SaveBarcodeWithHeight(barcode, 45, "BarHeight45.png");`，在單行程式碼中**建立高度為 45 像素的條碼圖像**。

## 在迴圈中建立多個條碼

當您擁有一系列產品識別碼時，`foreach` 迴圈可避免重複程式碼。此範例示範如何從 GTIN 陣列**建立多個條碼**。

```csharp
string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
int[] heights = { 30, 45, 60 }; // different heights for visual variety

for (int i = 0; i < gtins.Length; i++)
{
    // Encode each GTIN as a DataBar Omnidirectional barcode
    var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                   $"(01){gtins[i]}");

    // Reuse the X‑dimension setting for consistency
    gen.Parameters.Barcode.XDimension.Pixels = 2;

    // Choose a height from the heights array (or calculate dynamically)
    int height = heights[i % heights.Length];
    string filePath = Path.Combine(outputFolder,
        $"Databar_{gtins[i]}_Height{height}px.png");

    SaveBarcodeWithHeight(gen, height, filePath);
}
```

此迴圈會產生三個 PNG 檔案，每個檔案的**條碼高度（像素）**值不同。由於 `SaveBarcodeWithHeight` 輔助方法已封裝高度變更，主迴圈保持簡潔且專注於資料。

### 預期輸出

執行完整範例後，`Barcodes` 資料夾會包含：

```
DatabarBarHeight30Pixels.png
DatabarBarHeight60Pixels.png
Databar_01234567890123_Height30px.png
Databar_09876543210987_Height45px.png
Databar_12345098765432_Height60px.png
```

開啟任一 PNG 檔案，即可看到清晰的 DataBar Omnidirectional 條碼，可被一般手機應用程式掃描。

## 常見陷阱與專業技巧

| 問題 | 為何會發生 | 如何避免 |
|------|------------|----------|
| **錯誤的 EncodeTypes** | 為 DataBar 使用 1D 類型會產生無法辨識的圖像。 | 對於 GS1‑128 負載，務必選擇 `EncodeTypes.DatabarOmniDirectional`（或其他 DataBar 變體）。 |
| **X‑dimension 不足** | 極低的 X‑dimension 會導致細條在低解析度螢幕上消失。 | 螢幕顯示時保持 `XDimension.Pixels` ≥ 2；列印時提升至 3‑4。 |
| **檔案路徑錯誤** | 相對路徑可能解析到非預期的目錄。 | 使用 `Path.Combine` 與 `Environment.CurrentDirectory` 來建立絕對路徑。 |
| **覆寫圖像** | 在迴圈中重複使用相同檔名會覆寫先前結果。 | 在檔名中加入唯一識別碼（例如 GTIN 或時間戳記）。 |
| **缺少 NuGet 套件** | 程式碼編譯通過，但執行時拋出 `FileNotFoundException`。 | 確認已安裝 `Aspose.BarCode` 並在專案中正確引用。 |

## 完整可執行範例

以下是完整程式碼，您可以複製到 Console 應用程式中。它包含所有步驟、輔助方法與錯誤處理。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Prepare output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // ---------- Single barcode with two heights ----------
        var barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        barcode.Parameters.Barcode.XDimension.Pixels = 2;
        barcode.Parameters.Barcode.BarHeight.Pixels = 30;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);

        // ---------- Helper for dynamic heights ----------
        void SaveBarcodeWithHeight(BarcodeGenerator gen, int heightPx, string fileName)
        {
            gen.Parameters.Barcode.BarHeight.Pixels = heightPx;
            gen.Save(fileName, BarCodeImageFormat.Png);
        }

        // ---------- Multiple barcodes ----------
        string[] gtins = { "01234567890123", "09876543210987", "12345098765432" };
        int[] heights = { 30, 45, 60 };

        for (int i = 0; i < gtins.Length; i++)
        {
            var gen = new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional,
                                           $"(01){gtins[i]}");
            gen.Parameters.Barcode.XDimension.Pixels = 2;

            int height = heights[i % heights.Length];
            string filePath = Path.Combine(outputFolder,
                $"Databar_{gtins[i]}_Height{height}px.png");

            SaveBarcodeWithHeight(gen, height, filePath);
        }

        Console.WriteLine($"Barcode images created in: {outputFolder}");
    }
}
```

執行此程式

## 接下來您可以學習什麼？

以下教學涵蓋與本指南密切相關的主題，並在此基礎上進一步說明。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [Create barcode image C# – GS1 DataMatrix Example](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/english/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}