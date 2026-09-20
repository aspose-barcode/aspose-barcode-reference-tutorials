---
category: general
date: 2026-09-19
description: 條碼產生器 C# 指南示範如何產生 Planet 條碼，並只需幾行程式碼即可將條碼圖像匯出為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- how to generate barcode
- create planet barcode
- export barcode image
language: zh-hant
lastmod: 2026-09-19
og_description: 條碼產生器 C# 讓您快速建立 Planet 條碼，並將圖像匯出為 PNG，適用於任何 .NET 應用程式。
og_image_alt: Screenshot of a Planet barcode generated with barcode generator C# showing
  empty bars
og_title: 條碼產生器 C# – 建立 Planet 條碼並匯出圖像
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator C# guide shows how to generate a Planet barcode and
    export barcode image as PNG in just a few lines.
  headline: How to use barcode generator C# for Planet barcode
  type: TechArticle
tags:
- barcode
- C#
- image export
title: 如何在 C# 中使用條碼產生器產生 Planet 條碼
url: /zh-hant/python-java/general/how-to-use-barcode-generator-c-for-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼產生器產生 Planet 條碼

如果您需要一個 **barcode generator C#** 能夠產生 Planet 條碼，本教學將提供完整解決方案。您將學會 **如何產生條碼** 資料、客製化外觀，並 **匯出條碼影像** 為 PNG 檔，只需幾行程式碼。

產生條碼是庫存系統、票券平台與 IoT 裝置的常見需求。完成本教學後，您將擁有一個自給自足的主控台應用程式，能產生乾淨的 Planet 條碼、停用條紋填充，並將結果儲存至磁碟。除了條碼函式庫外，無需其他外部工具。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本  
* 相容 C# 的條碼函式庫（本範例使用 **Aspose.BarCode for .NET**，支援 Planet 符號）  
* 如 Visual Studio 2022、VS Code 或 Rider 等 IDE 或編輯器  

可透過 NuGet 加入函式庫：

```bash
dotnet add package Aspose.BarCode
```

> **小技巧：** 使用套件的最新穩定版，以獲得錯誤修正與效能提升。

## 使用 barcode generator C# 建立 Planet 條碼

第一步是以 Planet 符號與您要編碼的資料建立產生器實例。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

`BarcodeGenerator` 是所有條碼操作的入口點。建構子接受符號 (`EncodeTypes.Planet`) 與原始資料 (`"123456"`)。此程式碼 **建立一個 Planet 條碼**，之後可渲染為影像。

## 調整條碼參數

若要控制視覺品質，可修改 X‑dimension（模組寬度）並決定條紋是否填充。

```csharp
        // Step 2: Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;
```

* 將 `XDimension.Pixels` 設為 **4**，可在不大幅增加檔案大小的情況下提升條碼解析度。  
* `FilledBars = false` 產生僅有輪廓的樣式，適合條碼需與背景融合或在低墨水設備上列印的情況。

## 匯出條碼影像

設定完產生器後，將結果儲存為 PNG 檔。`Save` 方法接受完整路徑與目標影像格式。

```csharp
        // Step 4: Save the generated barcode image as a PNG file
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

程式碼會將 **export barcode image** `PlanetEmptyBars.png` 寫入使用者的桌面。PNG 為無損格式，能保留條碼的銳利邊緣，適合螢幕顯示與高解析度列印。

> **例外情況：** 若需其他格式（JPEG、BMP、GIF），請將 `BarCodeImageFormat.Png` 替換為相應的列舉值。JPEG 會產生壓縮雜訊，可能影響掃描器可讀性，僅在檔案大小極為重要時使用。

## 完整可執行範例

以下是完整程式碼，您可以直接複製、貼上並執行。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Create a barcode generator for the Planet symbology with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Adjust the X-dimension (module width) to 4 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 4;

        // Disable filling of the bars so that only the outlines are drawn
        generator.Parameters.Barcode.FilledBars = false;

        // Define the output file path (Desktop folder is used for convenience)
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "PlanetEmptyBars.png");

        // Export the barcode image as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

執行程式後，您應會看到類似以下的訊息：

```
Barcode saved to: C:\Users\YourName\Desktop\PlanetEmptyBars.png
```

開啟 PNG 檔案即可看到一個乾淨的 Planet 條碼，條紋為空白，正如設定所示。

![barcode generator C# example](/images/barcode-generator-csharp.png){alt="條碼產生器 C# 範例"}

## 常見問題與除錯

| 問題 | 解答 |
|----------|--------|
| **我可以用相同程式碼產生其他符號嗎？** | 可以。將 `EncodeTypes.Planet` 替換為任意支援的類型，例如 `EncodeTypes.Code128` 或 `EncodeTypes.QR`。 |
| **條碼無法掃描時該怎麼辦？** | 確認資料長度符合 Planet 規範（恰好 6 位數字）。同時確保條碼與背景之間有足夠對比度。 |
| **如何變更影像尺寸？** | 調整 `generator.Parameters.ImageWidth` 與 `generator.Parameters.ImageHeight`，或修改 `XDimension` 以比例放大條碼。 |
| **能在條碼下方加入說明文字嗎？** | 使用 `generator.Parameters.Barcode.CodeTextVisible = true;`，並自訂 `CodeTextParameters` 以設定字型、對齊方式與邊距。 |

## 往後的步驟

掌握 **如何產生條碼** 圖片與 **barcode generator C#** 後，您可以進一步探索：

* 使用 CSV 清單批次產生條碼檔案。  
* 以 Aspose.PDF 將 PNG 嵌入 PDF 發票。  
* 轉換為 SVG 等 `export barcode image` 格式，以取得可縮放的網頁圖形。  

這些延伸功能能加深您對 .NET 條碼自動化的理解，並為實務整合情境做好準備。

---

**摘要：** 本教學示範了完整的 **barcode generator C#** 工作流程——建立 Planet 條碼、客製化外觀，並 **匯出條碼影像** 為 PNG。您可將相同模式套用於其他符號、影像格式與輸出目的地。祝開發順利！

## 接下來該學什麼？

以下教學與本指南的技術緊密相關，提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [Barcode generator C# – generate barcode image](/barcode/english/python-java/general/barcode-generator-c-generate-barcode-image/)
- [Create Planet Barcode Image in C# – How to Generate Postal Barcode](/barcode/english/python-java/general/create-planet-barcode-image-in-c-how-to-generate-postal-barc/)
- [Barcode Generator Example in C# – Set Columns, Rows & Export Image](/barcode/english/python-java/general/barcode-generator-example-in-c-set-columns-rows-export-image/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}