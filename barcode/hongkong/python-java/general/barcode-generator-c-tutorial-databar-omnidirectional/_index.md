---
category: general
date: 2026-11-14
description: 條碼產生器 C# 教學，示範如何建立 DataBar Omnidirectional 條碼、設定 X 尺寸，以及以像素調整條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c# tutorial
- DataBar Omnidirectional
- set bar height
- XDimension pixels
- BarCodeImageFormat PNG
language: zh-hant
lastmod: 2026-11-14
og_description: 條碼產生器 C# 教學逐步說明如何產生 DataBar Omnidirectional 條碼、以像素定義 XDimension，並調整條碼高度以輸出
  PNG。
og_image_alt: Screenshot of barcode generator C# tutorial output showing a DataBar
  barcode
og_title: 條碼產生器 C# 教學 – 建立 DataBar 條碼
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Barcode generator C# tutorial that shows how to create DataBar Omnidirectional
    barcodes, set X‑dimension, and adjust bar height in pixels.
  headline: 'Barcode generator C# tutorial: DataBar Omnidirectional'
  type: TechArticle
tags:
- barcode
- C#
- DataBar
- tutorial
title: 條碼產生器 C# 教學：DataBar 全向
url: /zh-hant/python-java/general/barcode-generator-c-tutorial-databar-omnidirectional/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器 C# 教學 – 建立 DataBar 全向條碼

如果你在尋找 **barcode generator C# tutorial**，恭喜你來對地方了。本指南將帶領你建立 DataBar 全向條碼、以像素設定 XDimension，並調整條碼高度以產生 PNG 圖片。

你將看到一個完整且可執行的範例，涵蓋從初始化產生器到以不同條碼高度儲存多張圖片的所有步驟。無需額外文件——只要複製程式碼、執行，即可得到兩個可直接使用的條碼檔案。

## 前置條件

* .NET 6.0 或更新版本已安裝  
* 參考提供 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 的條碼函式庫（例如 Aspose.BarCode for .NET）  
* 基本了解 C# 語法以及 Visual Studio 或你慣用的 IDE  

> **專業提示：** 若你使用 Aspose.BarCode，請將 NuGet 套件 `Aspose.BarCode` 加入你的專案。

## 條碼產生器 C# 教學 – 第一步：建立產生器

第一步是以 `DatabarOmniDirectional` 編碼類型以及你想要編碼的資料，實例化一個 `BarcodeGenerator`。

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a DataBar Omnidirectional barcode generator with the desired data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*為什麼這很重要：* `EncodeTypes.DatabarOmniDirectional` 告訴函式庫產生可從任意方向讀取的條碼，這對零售包裝與物流特別適用。

## 設定條碼的 XDimension（像素）

X‑dimension 定義條碼中最小模組（即「像素」）的寬度。以像素設定可讓你精確控制條碼的視覺密度。

```csharp
        // Step 2: Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

*說明：* 設為 `2` 像素可產生足以讓大多數掃描器辨識的清晰條碼，同時保持圖檔大小適中。

## 調整條碼高度並儲存圖像

條碼高度決定條紋的高度。你可以透過變更 `BarHeight.Pixels` 屬性並再次呼叫 `Save`，產生不同高度的多張圖像。

```csharp
        // Step 3: Set the bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        string outputPath = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
```

`BarCodeImageFormat.Png` 列舉值確保輸出為無損的 PNG 檔案，這是條碼圖形的建議格式，因為它能保留精確尺寸。

## 變更條碼高度以產生多張圖像

通常你會需要相同條碼的不同尺寸——例如，一張用於小標籤，另一張用於大型海報。變更條碼高度並重複使用同一個產生器實例：

```csharp
        // Step 4: Change the bar height to 60 px and save a second image
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        outputPath = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);
    }
}
```

*邊緣情況：* 若條碼高度設定過低（例如低於 10 px），部分掃描器可能無法順利讀取。務必使用目標掃描硬體測試產生的圖像。

## 完整原始碼

以下是完整程式碼，你可以直接貼到新的 Console 專案中。它包含所有必要的 `using` 指令，並示範兩種條碼高度的變化。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a DataBar Omnidirectional barcode generator
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Set XDimension to 2 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image – 30 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            string path30 = @"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png";
            generator.Save(path30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 30 px barcode to {path30}");

            // Second image – 60 px bar height
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            string path60 = @"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png";
            generator.Save(path60, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved 60 px barcode to {path60}");
        }
    }
}
```

執行程式，將 `YOUR_DIRECTORY` 替換為有效的資料夾路徑，即可在該位置找到兩個 PNG 檔案：

* `DatabarBarHeight30Pixels.png` – 條碼高度 30 px  
* `DatabarBarHeight60Pixels.png` – 條碼高度 60 px  

![條碼產生器 C# 教學輸出](images/databar-example.png "條碼產生器 C# 教學顯示兩張 DataBar 圖片")

## 常見問題

| 問題 | 解答 |
|----------|--------|
| **我可以更改圖像格式嗎？** | 可以。視需求將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。PNG 因為無損品質而被優先推薦。 |
| **如果我需要不同的 XDimension 該怎麼辦？** | 將 `generator.Parameters.Barcode.XDimension.Pixels` 調整為任意整數。較大的數值會使條碼整體寬度增加。 |
| **DataBar 全向條碼適合手機掃描嗎？** | 可以，只要列印尺寸符合掃描器的最小模組尺寸（通常為 0.33 mm）。以像素為基礎的 XDimension 可協助你滿足此要求。 |
| **如何將條碼嵌入 PDF？** | 儲存 PNG 後，使用 PDF 函式庫（例如 iTextSharp）將圖像插入 PDF 頁面。 |

## 結論

本 **barcode generator C# tutorial** 示範了如何建立 DataBar 全向條碼、以像素設定 XDimension，並產生不同條碼高度的 PNG 檔案。現在你擁有可重複使用的程式碼片段，可套用於任何需要條碼產生的 C# 專案。

### 接下來？

* 探索其他 `EncodeTypes`（如 `Code128` 或 `QR`），擴充你的條碼種類。  
* 結合產生的 PNG 與 PDF 產生函式庫，製作可列印的發票。  
* 嘗試使用 `generator.Parameters.Barcode.Color` 加入自訂顏色，同時遵守掃描器規範。

歡迎自行修改範例、嘗試其他條碼高度，或變更輸出格式。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在專案中探索其他實作方式。

- [如何設定 GS1 DataBar 全向條碼的寬度與調整高度](/barcode/english/python-java/general/how-to-set-width-and-adjust-height-for-a-gs1-databar-omni-di/)
- [如何設定條碼高度、在 C# 中產生 DataBar 條碼](/barcode/english/python-java/general/how-to-set-barcode-height-generate-databar-barcode-in-c/)
- [如何在 C# 中建立全向 Databar 條碼](/barcode/english/python-java/general/how-to-create-omnidirectional-databar-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}