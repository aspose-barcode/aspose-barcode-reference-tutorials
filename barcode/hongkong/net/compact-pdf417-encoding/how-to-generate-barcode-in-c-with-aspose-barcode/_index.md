---
category: general
date: 2026-09-16
description: 學習如何在 C# 中產生條碼並設定條碼大小。使用 Aspose.BarCode 的逐步指南，建立 Micro PDF417 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- set barcode size
language: zh-hant
lastmod: 2026-09-16
og_description: 如何在 C# 中使用 Aspose.BarCode 產生條碼並設定條碼大小。請跟隨此簡潔教學以產出 Micro PDF417 PNG。
og_image_alt: Example output showing how to generate barcode using C#
og_title: 如何在 C# 中生成條碼 – 完整的 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-09-16'
  description: Learn how to generate barcode and set barcode size in C#. Step‑by‑step
    guide using Aspose.BarCode to create a Micro PDF417 image.
  headline: How to generate barcode in C# with Aspose.BarCode
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Aspose.BarCode 產生條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 產生條碼

如果您需要了解 **如何在 .NET 專案中產生條碼**，本教學將帶您使用 Aspose.BarCode 套件完成整個流程。您還會學會如何 **設定條碼大小**，讓影像符合 UI 或列印需求。

本指南涵蓋從安裝 NuGet 套件、設定 Micro PDF417 符號，到儲存為 PNG 檔案的全部步驟。完成後，您將擁有一段可直接放入任何 C# 主控台或 Web 應用程式的可執行範例程式碼。

## 您需要的環境

- .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.6+）
- Visual Studio 2022 或任何支援 C# 的 IDE
- 具網路連線以下載 **Aspose.BarCode** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
- 基本的 C# 語法概念

## 如何使用 Aspose.BarCode 產生條碼

第一步是建立 `BarcodeGenerator` 實例，告訴程式要使用哪種條碼類型以及要編碼的資料。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Micro PDF417 barcode generator with the data to encode
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");
```

**為什麼這很重要：** `EncodeTypes.MicroPdf417` 讓函式庫產生緊湊版的 PDF417，適合小標籤或類似 QR Code 的佈局。字串 `"Micro data"` 會成為條碼中嵌入的人類可讀負載。

## 設定條碼大小與尺寸

可讀的條碼必須具備正確的模組（X）尺寸以及足夠的欄位數以容納資料。這裡就是 **設定條碼大小** 的地方。

```csharp
// Step 2: Define the module size (X dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Set the maximum number of columns for the Micro PDF417 symbol
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

- **XDimension** 控制最小條的寬度（即「模組」）。`2` 像素在螢幕上顯示效果良好；若要高解析度列印可將其調高。
- **Pdf417.Columns** 限制垂直欄位數。Micro PDF417 格式最多支援 7 欄；`4` 可在不犧牲資料容量的前提下取得平衡尺寸。

> **小技巧：** 若產生的影像過小，可將 `XDimension.Pixels` 提升至 `3` 或 `4`。相反地，若 UI 空間緊湊，可降至 `1`，但請確認您使用的掃描器仍能正確讀取。

## 儲存條碼影像

設定完尺寸後，只要指示產生器將影像寫入磁碟即可。

```csharp
// Step 4: Save the generated barcode as a PNG image
barcodeGenerator.Save("micro.png", BarCodeImageFormat.Png);
```

`Save` 方法接受 Aspose.BarCode 支援的任何格式（`Png`、`Jpeg`、`Bmp`、`Gif`、`Tiff`）。PNG 為無損格式，能保留掃描所需的清晰邊緣。

**預期輸出：** 專案工作目錄下會出現名為 `micro.png` 的檔案。開啟後即可看到一個小型、高對比度的 Micro PDF417 條碼，適合使用任何標準掃描器測試。

## 完整範例

將所有片段組合起來，即可得到一個可直接執行的完整程式。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for Micro PDF417
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Micro data");

            // Set size parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
            generator.Parameters.Barcode.Pdf417.Columns = 4;    // column count

            // Choose output path (adjust as needed)
            string outputPath = "micro.png";

            // Save as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

在主控台執行程式（`dotnet run`），您會看到確認訊息。產生的 PNG 可嵌入報表、印在產品標籤上，或顯示於網頁中。

## 常見問題與邊緣案例

| 問題 | 解答 |
|---|---|
| **我可以產生其他條碼類型嗎？** | 可以。將 `EncodeTypes.MicroPdf417` 替換為 `EncodeTypes` 列舉中的任意值（例如 `EncodeTypes.Code128`、`EncodeTypes.QR`）。 |
| **如果需要更大的影像該怎麼辦？** | 提升 `XDimension.Pixels`，或使用 `generator.Parameters.Image.Width/Height` 強制指定像素尺寸。 |
| **套件支援透明背景嗎？** | 在呼叫 `Save` 前設定 `generator.Parameters.Barcode.BackColor = System.Drawing.Color.Transparent;` 即可。 |
| **要如何讀取已產生的條碼？** | 使用 `Aspose.BarCode.BarCodeReader` 讀取已儲存的影像，函式庫會自動偵測條碼類型。 |
| **PNG 影像適合列印嗎？** | PNG 為無損格式，但若需 CMYK 列印，建議改存為 TIFF（`BarCodeImageFormat.Tiff`）。 |

## 結論

現在您已掌握 **如何在 C# 中產生條碼** 以及 **如何設定條碼大小**，全部透過 Aspose.BarCode 完成。完整範例示範了建立 Micro PDF417 符號、調整尺寸並匯出 PNG 檔案的流程。以此為基礎，您可以探索其他條碼類型、客製化顏色，或將條碼產生整合至 ASP.NET Core 服務中。

### 後續步驟

- 嘗試產生 QR Code（`EncodeTypes.QR`），比較模組大小。  
- 使用 `generator.Parameters.Image` 加入邊距或調整 DPI，以產出列印就緒的影像。  
- 結合 **Aspose.PDF**，直接將條碼影像嵌入 PDF 報表。

祝開發順利，盡情體驗 Aspose.BarCode 為 .NET 條碼專案帶來的彈性！

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能在此基礎上延伸技術與實作方式。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能並探索不同的實作方法。

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}