---
category: general
date: 2026-08-22
description: 如何快速產生條碼，並學習在使用 Aspose.BarCode 匯出 PNG 格式條碼圖像時調整條碼大小。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- change barcode size
- export barcode image
language: zh-hant
lastmod: 2026-08-22
og_description: 如何在 C# 中產生條碼，並在匯出為 PNG 圖像前輕鬆調整條碼大小。請跟隨本完整指南。
og_image_alt: Screenshot showing how to generate barcode with Aspose.BarCode in C#
og_title: 如何在 C# 中產生自訂尺寸的條碼圖片
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to generate barcode quickly and learn how to change barcode size
    while exporting the barcode image as PNG using Aspose.BarCode.
  headline: How to generate barcode images with custom size in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中生成自訂大小的條碼圖片
url: /zh-hant/python-java/general/how-to-generate-barcode-images-with-custom-size-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生自訂尺寸的條碼影像

如果您需要 **產生條碼** 用於郵件自動化、庫存追蹤或活動票券，本教學將示範一個完整、可直接執行的 C# 解決方案。您還會學會 **如何變更條碼尺寸** 以及 **匯出條碼影像** 為 PNG 格式，且全程不離開 IDE。

我們將使用 Aspose.BarCode 函式庫，因為它支援 OneCode 符號、可逐像素控制尺寸，且只需一次方法呼叫即可完成影像匯出。完成教學後，您將得到四個 PNG 檔案——每個檔案皆為不同位數的 OneCode 條碼。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.6+）
- Visual Studio 2022（或您慣用的任何 C# 編輯器）
- 以 NuGet 方式加入 **Aspose.BarCode** (`Install-Package Aspose.BarCode`)
- 具備基本的 C# 語法概念

> **專業小技巧：** 若您正在評估此函式庫，Aspose 提供 30 天免費試用，包含所有條碼功能。

## 步驟 1：建立最小化的 Console 專案

建立一個新的 Console 應用程式，並加入 Aspose.BarCode 套件：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

產生的 `Program.cs` 會放置完整的條碼產生邏輯。

## 步驟 2：產生條碼 – 建立可重複使用的方法

以下是一個自包含的方法，接受資料字串、目標檔名，以及可選的尺寸參數。此方法示範 **產生條碼** 的核心模式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Example calls for different digit lengths
            GenerateOneCode("12345678901234567890", "PostalOneCodeBarcode20Digits.png");
            GenerateOneCode("1234567890123456789012345", "PostalOneCodeBarcode25Digits.png");
            GenerateOneCode("12345678901234567890123456789", "PostalOneCodeBarcode29Digits.png");
            GenerateOneCode("1234567890123456789012345678901", "PostalOneCodeBarcode31Digits.png");
        }

        /// <summary>
        /// Generates a OneCode barcode, applies size settings, and saves as PNG.
        /// </summary>
        /// <param name="data">Numeric string to encode (OneCode supports 20‑31 digits).</param>
        /// <param name="fileName">Target PNG file name.</param>
        /// <param name="xDimension">Width of a single module in pixels (default 4).</param>
        /// <param name="barHeight">Height of the barcode in pixels (default 50).</param>
        static void GenerateOneCode(string data, string fileName,
                                    int xDimension = 4, int barHeight = 50)
        {
            // 1️⃣ Initialize the generator for OneCode symbology
            var generator = new BarcodeGenerator(EncodeTypes.OneCode, data);

            // 2️⃣ **Change barcode size** – adjust module width and total height
            generator.Parameters.Barcode.XDimension.Pixels = xDimension; // module width
            generator.Parameters.Barcode.BarHeight.Pixels = barHeight;   // overall height

            // 3️⃣ **Export barcode image** as PNG; you can also choose JPEG, BMP, etc.
            generator.Save(fileName, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {fileName}");
        }
    }
}
```

### 為何這個方法很重要

- **封裝性：** 所有與尺寸相關的設定集中於一處，讓您只要傳入不同的參數即可輕鬆呼叫。
- **可重用性：** 同一個方法可用於任何 OneCode 字串長度，這點很重要，因為 OneCode 只接受 20‑31 位數字。
- **可讀性：** 以 Emoji 標註的註解會引導讀者了解三個邏輯階段——初始化、尺寸變更與匯出。

## 步驟 3：依需求變更條碼尺寸

有時掃描器需要較高的條碼，或列印版面要求較窄的模組。`XDimension.Pixels` 屬性控制單一條碼模組的寬度，而 `BarHeight.Pixels` 則設定整體高度。

```csharp
// Example: generate a larger barcode (8‑pixel modules, 80‑pixel height)
GenerateOneCode(
    data: "12345678901234567890",
    fileName: "LargeOneCode.png",
    xDimension: 8,
    barHeight: 80);
```

**變更尺寸時的重點：**

- **最小 X‑dimension：** 雖然技術上允許 1 像素，但大多數掃描器至少需要 2 像素才能穩定讀取。
- **最大高度：** 沒有硬性上限，但過高的條碼可能超出標準標籤的可列印範圍。
- **長寬比例：** 保持高度與模組寬度的比例在約 12‑15 倍左右，以免產生變形。

## 步驟 4：匯出條碼影像為其他格式（可選）

`Save` 方法接受多種 `BarCodeImageFormat` 值：`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`。若需要無損向量格式，可改為匯出 `Svg`。

```csharp
// Export to SVG for infinite scaling
generator.Save("OneCode.svg", BarCodeImageFormat.Svg);
```

以 PNG 匯出是最常見的選擇，因為它保留清晰的邊緣，且廣受網頁瀏覽器與列印流程支援。

## 預期輸出

執行程式後，專案資料夾會產生四個 PNG 檔案：

- `PostalOneCodeBarcode20Digits.png` – 20 位 OneCode 條碼
- `PostalOneCodeBarcode25Digits.png` – 25 位 OneCode 條碼
- `PostalOneCodeBarcode29Digits.png` – 29 位 OneCode 條碼
- `PostalOneCodeBarcode31Digits.png` – 31 位 OneCode 條碼

每張影像會類似下方的佔位圖（實際圖形取決於您提供的數字資料）。

![產生條碼範例](https://example.com/placeholder.png "產生條碼範例")

*此圖像的 alt 文字包含主要關鍵字，以提升可及性與 SEO 效果。*

## 常見問題與邊緣情況

| 問題 | 解答 |
|----------|--------|
| **如果資料字串少於 20 位數會怎樣？** | OneCode 必須至少 20 位。請在字串前補零，或改用其他符號（例如 Code128）。 |
| **可以在多執行緒環境下產生條碼嗎？** | 可以。`BarcodeGenerator` 並非執行緒安全，請為每個執行緒建立獨立的產生器實例。 |
| **如何設定背景顏色？** | 在呼叫 `Save` 前加入 `generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.White;` 即可。 |
| **有沒有辦法直接把影像嵌入 HTML 頁面？** | 可將影像儲存至 `MemoryStream`，轉成 Base64，然後以 `<img src="data:image/png;base64,..." />` 方式嵌入。 |

## 結論

您現在已掌握 **在 C# 中使用 Aspose.BarCode 產生條碼** 影像的技巧，了解如何透過調整 X‑dimension 與條碼高度 **變更條碼尺寸**，以及如何 **匯出條碼影像** 為 PNG（或其他）格式。可重用的 `GenerateOneCode` 方法讓您只需一行程式碼，即可產生 20 至 31 位的任意 OneCode 條碼。

接下來您可以：

- 嘗試其他符號（`EncodeTypes.Code128`、`EncodeTypes.QR`）。
- 將產生器整合至 Web API，依需求即時回傳條碼影像。
- 結合 PNG 輸出與 PDF 函式庫，將條碼嵌入運送標籤。

祝開發順利，歡迎在留言區分享您的變化與心得！

## 接下來您可以學習什麼？

以下教學與本篇內容緊密相關，能進一步深化您對 API 功能的掌握，並探索在專案中實作的其他方式。

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟說明](/barcode/english/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [如何產生與調整 One‑Dimensional Databar 條碼高度 – Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}