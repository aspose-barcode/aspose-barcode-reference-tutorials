---
category: general
date: 2026-07-18
description: 使用 C# 快速建立 Planet 條碼。學習如何產生實心與空心條、設定 X 軸尺寸，並儲存 PNG 圖片——一次教學搞掂。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planet barcode
- Planet barcode generator
- BarcodeGenerator parameters
- XDimension pixels
- filled bars vs empty bars
language: zh-hant
lastmod: 2026-07-18
og_description: 即時建立 Planet 條碼。本指南會示範如何設定 X 尺寸、在實心條與空心條之間切換，以及使用 Aspose.BarCode 匯出
  PNG 檔案。
og_image_alt: Screenshot of a generated Planet barcode saved as PNG
og_title: 在 C# 中建立 Planet 條碼 – 完整程式教學
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  headline: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  type: TechArticle
- description: Create Planet barcode quickly with C#. Learn how to generate filled
    and empty bars, set X‑dimension, and save PNG images – all in one tutorial.
  name: Create Planet Barcode in C# – Full Step‑by‑Step Guide
  steps:
  - name: “Can I change the image format?”
    text: Absolutely. The `Save` method accepts `BarCodeImageFormat.Jpeg`, `Bmp`,
      `Gif`, etc. Just replace `BarCodeImageFormat.Png` with your desired format.
  - name: “What if I need a different barcode height?”
    text: 'Use `planetBarcode.Parameters.Barcode.BarHeight` (in points) to increase
      or decrease the vertical size. For example:'
  - name: “Is there a way to add a human‑readable caption?”
    text: 'Yes. Set the `CodeText` property on `planetBarcode.Parameters.Caption`:'
  - name: “Do I need to dispose the generator?”
    text: 'The `BarcodeGenerator` implements `IDisposable`. Wrap it in a `using` block
      if you’re creating many barcodes in a loop:'
  - name: “What about error handling?”
    text: 'Enclose the `Save` calls in a `try…catch` block to capture `IOException`
      (disk issues) or `ArgumentException` (invalid parameters). Example:'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 在 C# 中建立 Planet 條碼 – 完整逐步指南
url: /zh-hant/python-java/general/create-planet-barcode-in-c-full-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 Planet 條碼 – 完整步驟指南

是否曾需要 **建立 planet 條碼** 圖片卻不確定要調整哪些屬性？你並不孤單。許多開發者在預設的實心條不符合規範，或是條寬必須符合印表機 DPI 時卡住了。

在本教學中，你將學會如何使用 Aspose.BarCode 函式庫 **建立 planet 條碼** 檔案、如何控制 **XDimension 像素**，以及如何在 **實心條** 與 **空心條** 之間切換而不必重新撰寫程式碼。完成後，你會得到兩個 PNG 檔案——一個實心條、一個空心條——可供任何需要 Planet 符號的郵務系統使用。

## 前置條件

- .NET 6.0 或更新版本（程式碼同樣適用於 .NET Framework 4.7 +）  
- Aspose.BarCode for .NET NuGet 套件（`Install-Package Aspose.BarCode`）  
- 基本的 C# 知識（稍後會說明為何使用 `using` 陳述式）  
- 可寫入的磁碟資料夾，用來儲存 PNG  

只要具備上述條件，即可直接進入實作階段。

## 第一步 – 設定專案並加入函式庫

首先，建立一個新的 Console 應用程式（或任何 C# 專案），並參考 **Planet 條碼產生器** 函式庫。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The rest of the code lives here
        }
    }
}
```

> **小技巧：** 在 Visual Studio 中，右鍵點擊專案 → *Manage NuGet Packages* → 搜尋 **Aspose.BarCode** 並點選 *Install*。這樣即可取得 `BarcodeGenerator` 以及所有需要的 **BarcodeGenerator 參數**。

## 第二步 – 初始化 Planet 條碼產生器

現在真正 **建立 planet 條碼** 產生器實例，並將要編碼的資料（本例為 `"123456"`）傳入。`EncodeTypes.Planet` 列舉告訴函式庫使用哪種符號。

```csharp
// Step 2: Initialise the generator with Planet symbology and data
BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

> **為何重要：** `EncodeTypes.Planet` 旗標會自動套用正確的檢查碼與版面規則，讓你不必手動計算。

## 第三步 – 設定 X‑Dimension（條寬）

大多數印表機要求每條的寬度為特定像素數。此處將 **XDimension 像素** 設為 `4`，這是 203 dpi 熱感印表機的常見值。

```csharp
// Step 3: Set the width of each bar (X‑dimension) to 4 pixels
planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;
```

> **例外情況：** 若目標是 300 dpi 印表機，可能需要 `3` 或 `5` 像素。請依據設備文件調整此數值。

## 第四步 – 儲存實心條版本

預設情況下產生器會產生 **實心條**（實心黑色矩形）。將其寫入磁碟：

```csharp
// Step 4: Save the barcode with default (filled) bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

將 `YOUR_DIRECTORY` 替換為你的程式可寫入的絕對或相對路徑。執行此行後，你會在磁碟上看到一個看起來像傳統 Planet 條碼的 PNG 檔案，適合用來測試郵務掃描器。

## 第五步 – 切換為空心條

有時郵務服務要求「空心條」樣式，即條紋從白色背景中挖空而非塗黑。函式庫提供簡易開關：

```csharp
// Step 5: Re‑configure the generator to produce empty bars
planetBarcode.Parameters.Barcode.FilledBars = false;
```

將 `FilledBars` 設為 `false` 即可讓渲染器反轉條紋填充邏輯。無需重新建立 `BarcodeGenerator` 實例，只要調整現有的 **BarcodeGenerator 參數** 即可。

## 第六步 – 儲存空心條版本

最後，匯出第二張圖片：

```csharp
// Step 6: Save the barcode with empty bars
planetBarcode.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

現在你擁有兩個不同的 PNG 檔案，各自符合不同的視覺需求。

## 完整範例程式

將所有步驟整合，以下是可直接複製貼上的完整程式：

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Initialise the Planet barcode generator with data
            BarcodeGenerator planetBarcode = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // Configure bar width (X‑dimension) – 4 pixels works for most 203 dpi printers
            planetBarcode.Parameters.Barcode.XDimension.Pixels = 4;

            // Save the default filled‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Switch to empty‑bars style
            planetBarcode.Parameters.Barcode.FilledBars = false;

            // Save the empty‑bars version
            planetBarcode.Save(@"C:\Barcodes\PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Both Planet barcode images have been generated successfully.");
        }
    }
}
```

**預期輸出**（於主控台）：

```
Both Planet barcode images have been generated successfully.
```

在 `C:\Barcodes\` 目錄下，你會看到：

- `PostalPlanetFilledBars.png` – 實心黑條  
- `PostalPlanetEmptyBars.png` – 白底黑框條  

使用任何影像檢視器開啟，它們都應符合 Planet 規範。

## 常見問題與小技巧

### 「可以更換影像格式嗎？」

當然可以。`Save` 方法接受 `BarCodeImageFormat.Jpeg`、`Bmp`、`Gif` 等。只要將 `BarCodeImageFormat.Png` 換成你想要的格式即可。

### 「如果需要不同的條碼高度呢？」

使用 `planetBarcode.Parameters.Barcode.BarHeight`（單位為點）即可調整垂直尺寸。例如：

```csharp
planetBarcode.Parameters.Barcode.BarHeight = 30; // 30 points tall
```

### 「可以加入可讀的文字說明嗎？」

可以。設定 `planetBarcode.Parameters.Caption.CodeText` 屬性：

```csharp
planetBarcode.Parameters.Caption.Visible = true;
planetBarcode.Parameters.Caption.TopMargin = 5; // space between barcode and text
planetBarcode.Parameters.Caption.Text = "123456";
```

### 「需要釋放產生器資源嗎？」

`BarcodeGenerator` 實作了 `IDisposable`。若在迴圈中大量產生條碼，建議使用 `using` 區塊：

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save
}
```

### 「錯誤處理該怎麼做？」

將 `Save` 呼叫包在 `try…catch` 區塊，以捕捉 `IOException`（磁碟問題）或 `ArgumentException`（參數無效）等例外。範例：

```csharp
try
{
    planetBarcode.Save(path, BarCodeImageFormat.Png);
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Failed to save barcode: {ex.Message}");
}
```

## 重點回顧

我們已說明如何在 C# 中 **建立 planet 條碼** 圖片：

1. 使用你的資料初始化 **Planet 條碼產生器**。  
2. 調整 **XDimension 像素** 以符合印表機規格。  
3. 儲存 **實心條** PNG。  
4. 將 `FilledBars` 切換為 `false` 產生 **空心條**。  
5. 儲存第二張 PNG。  

接下來，你可以探索更多 **BarcodeGenerator 參數**、嘗試其他符號（`EncodeTypes.Postnet`、`EncodeTypes.Code128` 等），或將圖像整合至郵寄工作流程中。

---

**準備好下一步了嗎？** 嘗試在同一文件中加入 QR Code，或使用 `foreach` 迴圈從 CSV 清單批次產生 Planet 條碼。Aspose.BarCode API 足夠彈性，支援大量操作、自訂顏色，甚至向量化的 SVG 輸出。

若遇到任何問題，歡迎在下方留言或參考官方 Aspose.BarCode 文件，深入了解進階功能。祝開發順利！

## 接下來該學什麼？

以下教學與本指南的技術緊密相關，能幫助你進一步掌握 API 功能，並在專案中探索其他實作方式。

- [Create Barcode with Aspose - Set X & Y Dimensions in Java](/barcode/english/java/barcode-configuration/managing-x-y-dimension-barcode/)
- [How to create code128 barcode images in Java with Aspose.BarCode](/barcode/english/java/advanced-settings-and-optimization/saving-barcode-images-different-formats/)
- [How to create code128 barcode Java and set bar height](/barcode/english/java/barcode-configuration/setting-bars-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}