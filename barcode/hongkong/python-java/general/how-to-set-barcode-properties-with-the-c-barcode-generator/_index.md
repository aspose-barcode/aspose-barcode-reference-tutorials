---
category: general
date: 2026-09-10
description: 如何在 C# 中使用條碼產生器設定條碼。調整條碼模組寬度、產生條碼圖像，並學習如何儲存條碼檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- c# barcode generator
- barcode module width
- how to generate barcode
- how to save barcode
language: zh-hant
lastmod: 2026-09-10
og_description: 如何在 C# 中使用條碼產生器設定條碼。學習調整模組寬度、產生條碼，並有效地儲存條碼圖像。
og_image_alt: Screenshot showing a Planet barcode with filled and empty bars generated
  by C# code
og_title: 如何使用 C# 條碼產生器設定條碼屬性
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: How to set barcode in C# using a Barcode Generator. Adjust barcode
    module width, generate barcode images, and learn how to save barcode files.
  headline: How to set barcode properties with the C# Barcode Generator
  type: TechArticle
tags:
- barcode
- c#
- image generation
title: 如何使用 C# 條碼產生器設定條碼屬性
url: /zh-hant/python-java/general/how-to-set-barcode-properties-with-the-c-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 C# 條碼產生器設定條碼屬性

設定條碼屬性在需要精確控制條碼視覺樣式時相當重要。本教學說明如何產生 Planet 條碼、調整條碼模組寬度，並使用 C# 條碼產生器將條碼影像儲存。

您將看到一個完整、可執行的範例，涵蓋從建立條碼物件到寫入 PNG 檔案至磁碟的每一步。只需要以下程式碼與 Aspose.BarCode 函式庫（或任何相容的條碼 SDK），不需額外文件。完成教學後，您即可回答「如何以自訂尺寸產生條碼？」以及「如何以不同格式儲存條碼？」等問題。

## 前置條件

在開始之前，請確保您已具備：

* .NET 6.0 或更新版本  
* Visual Studio 2022（或任何 C# IDE）  
* **Aspose.BarCode** NuGet 套件（或提供 `BarcodeGenerator` 的其他函式庫）  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 如何設定條碼模組寬度

*模組寬度*（亦稱 X‑dimension）決定條碼中每條窄條的像素大小。設定此值即可控制影像的整體尺寸與可讀性。

```csharp
// Create a barcode generator for the Planet symbology
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width to 4 pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*為什麼重要*：較大的 X‑dimension 會產生較大的條碼，讓掃描器在較遠距離也能輕鬆讀取；較小的數值則可減少檔案大小，適合螢幕顯示。

## 產生填滿條的條碼

Planet 條碼的預設樣式使用 **填滿條**（實心黑條）。以下程式碼會建立影像並以 PNG 格式儲存。

```csharp
// Save the barcode with filled bars
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

> **結果**：`PostalPlanetFilledBars.png` 包含標準 Planet 條碼，所有條都已填滿。

## 建立空心條條碼

有時您需要只顯示條的輪廓（空心條）。為此，只需複製產生器、保持相同的模組寬度，並關閉 `FilledBars` 旗標。

```csharp
// Duplicate the generator for an empty‑bar version
BarcodeGenerator emptyBarGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Apply the same X‑dimension
emptyBarGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars so only the outlines are drawn
emptyBarGenerator.Parameters.Barcode.FilledBars = false;

// Save the empty‑bar barcode
emptyBarGenerator.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

> **結果**：`PostalPlanetEmptyBars.png` 顯示相同資料，但條為未填滿狀態，適合需要與背景融合的設計文件。

## 如何以不同格式儲存條碼

`Save` 方法接受 SDK 支援的任何格式，例如 **Jpeg**、**Bmp**、**Gif** 或 **Svg**。只要更換 `BarCodeImageFormat` 列舉值即可變更格式。

```csharp
// Example: save as SVG for lossless scaling
barcodeGenerator.Save("YOUR_DIRECTORY/PostalPlanet.svg", BarCodeImageFormat.Svg);
```

*小技巧*：當需要可在不失真的情況下縮放的向量圖時，請使用 SVG，特別適用於列印用 PDF。

## 完整、可執行範例

將所有片段整合，即可得到一個可直接貼入 Console 應用程式的自包含程式。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // 1. Create a filled‑bar Planet barcode
        BarcodeGenerator filledGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        filledGenerator.Parameters.Barcode.XDimension.Pixels = 4; // barcode module width
        filledGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // 2. Create an empty‑bar version of the same barcode
        BarcodeGenerator emptyGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        emptyGenerator.Parameters.Barcode.XDimension.Pixels = 4; // same module width
        emptyGenerator.Parameters.Barcode.FilledBars = false;   // how to set barcode to empty bars
        emptyGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

        // 3. Optional: save as SVG for scalable use
        filledGenerator.Save("PostalPlanet.svg", BarCodeImageFormat.Svg);
    }
}
```

**預期輸出**

| 檔案名稱                     | 說明                                      |
|-----------------------------|-------------------------------------------|
| `PostalPlanetFilledBars.png`| Planet 條碼，實心黑條                     |
| `PostalPlanetEmptyBars.png` | 相同資料，條以輪廓方式呈現               |
| `PostalPlanet.svg`          | 向量版本，可無損縮放                     |

執行程式、開啟產生的檔案，確認條碼與數字字串「123456」相符。

## 常見變化與例外情況

| 情境                                 | 調整方式                                                               |
|--------------------------------------|------------------------------------------------------------------------|
| 需要較粗的條碼                       | 增加 `XDimension.Pixels`（例如 `8`）                                   |
| 想要較小的檔案大小                   | 使用 `BarCodeImageFormat.Jpeg` 或降低 X‑dimension                       |
| 產生其他條碼類型                     | 將 `EncodeTypes.Planet` 替換為 `EncodeTypes.Code128`、`QR` 等            |
| 在高解析度印表機上列印               | 使用 `BarCodeImageFormat.Tiff` 取得無損點陣輸出                         |
| 在無頭伺服器上執行                   | 不需要 UI 程式碼；產生器可在 Console 或服務環境中運作                  |

**專業提示**：在投入正式環境前，務必使用掃描器或驗證工具檢查產生的條碼。模組寬度或格式不當都可能導致掃描失敗。

## 結論

您現在已掌握如何使用 C# 條碼產生器設定條碼屬性、控制條碼模組寬度、產生填滿與空心兩種條樣式，並以 PNG 或 SVG 格式儲存條碼。這些步驟為在任何 .NET 應用程式中加入條碼產生功能奠定了堅實基礎。

接下來，可探索以下相關主題，如 **c# barcode generator performance tuning**、**embedding barcodes in PDF documents** 以及 **creating QR codes with custom colors**。嘗試不同的 `EncodeTypes` 與影像格式，找出最適合您專案的組合。

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題，提供完整的程式碼範例與逐步說明，協助您在實作時掌握更多 API 功能與替代實作方式。

- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Barcode Generator Tutorial: How to Generate PDF417 Barcode in C#](/barcode/english/net/compact-pdf417-encoding/barcode-generator-tutorial-how-to-generate-pdf417-barcode-in/)
- [How to Set Error Level in PDF417 Barcode – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}