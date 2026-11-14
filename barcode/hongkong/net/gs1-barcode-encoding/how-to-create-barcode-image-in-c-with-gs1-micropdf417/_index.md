---
category: general
date: 2026-11-14
description: 學習如何使用 Aspose.BarCode 在 C# 中建立條碼影像。本分步指南涵蓋條碼產生器 C# 設定、GS1 格式化以及 PNG 匯出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to generate barcode
- barcode generator c#
- create gs1 barcode
- barcode image from data
language: zh-hant
lastmod: 2026-11-14
og_description: 快速在 C# 中建立條碼圖像。跟隨本指南學習如何生成條碼、使用 C# 條碼產生器，並匯出 GS1 MicroPDF417 PNG。
og_image_alt: Screenshot of a GS1 MicroPDF417 barcode generated in C#
og_title: 在 C# 中建立條碼圖像 – GS1 MicroPDF417 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to create barcode image in C# using Aspose.BarCode. This
    step‑by‑step guide covers barcode generator c# setup, GS1 formatting and PNG export.
  headline: How to create barcode image in C# with GS1 MicroPDF417
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中使用 GS1 MicroPDF417 建立條碼圖像
url: /zh-hant/net/gs1-barcode-encoding/how-to-create-barcode-image-in-c-with-gs1-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 GS1 MicroPDF417 建立條碼影像

如果您需要 **建立條碼影像**，本指南提供完整、可直接執行的解決方案。您將學會 **產生符合 GS1 標準的條碼** 資料、設定產生器，並匯出高品質的 PNG 檔案。

本教學涵蓋從安裝必要函式庫到處理常見資料格式問題的全部步驟。完成後，您只需幾行程式碼即可 **從資料產生條碼影像**，並了解每個設定的意義。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 .NET 6.0 或更新版本（此程式碼亦相容 .NET Framework 4.7+）。
* 如 Visual Studio 2022 或 Visual Studio Code 等開發環境。
* **Aspose.BarCode for .NET** NuGet 套件。使用以下指令安裝：

```bash
dotnet add package Aspose.BarCode
```

* 具備基本的 C# 語法與 GS1 應用識別碼（AI）格式概念。

> **專業提示：** 請保持函式庫版本為最新；最新發行版加入了對新條碼符號的支援與效能提升。

## 使用 BarcodeGenerator 建立條碼影像

本節提供核心實作。程式碼會建立 **barcode generator c#** 實例、設定可讀性的 X‑dimension，並將結果儲存為 PNG 檔案。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialise the generator with the GS1 MicroPDF417 symbology
// The data string follows the GS1 syntax: (01)GTIN(21)SerialNumber
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,
    "(01)12345678901234(21)ABC123");

// Step 2: Adjust the module width (X‑dimension) to improve scan reliability
// A value of 2 pixels works well for most screen‑displayed barcodes.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Export the barcode as a PNG image
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "GS1MicroPdf417.png");
generator.Save(outputPath, BarCodeImageFormat.Png);
```

### 為何每一行都很重要

* **EncodeTypes.MicroPdf417** 告訴函式庫使用 GS1 MicroPDF417 符號，該符號緊湊且適合行動裝置掃描。
* **資料字串** 必須以 GS1 AI `(01)`（全球貿易項目編號 GTIN）開頭，接著是 `(21)`（序號）。若格式不正確，產生器會拋出例外。
* **XDimension.Pixels** 控制最小條的寬度。較大的數值可提升低解析度螢幕的可讀性，較小的數值則可減少影像大小。
* **BarCodeImageFormat.Png** 產生無損影像，保留掃描所需的銳利邊緣。

執行程式後，會在桌面產生 `GS1MicroPdf417.png`。開啟檔案即可看到一個密集的黑白條碼，編碼了 GTIN `12345678901234` 與序號 `ABC123`。

## 如何使用 GS1 MicroPDF417 產生條碼

若您對 GS1 格式不熟悉，以下列出關鍵規則：

| GS1 AI | 含義                     | 範例               |
|--------|--------------------------|--------------------|
| (01)   | 全球貿易項目編號 (GTIN)   | 12345678901234     |
| (21)   | 序號（可選）              | ABC123             |

將 AI 與其值串接時，請將每個 AI 包於括號內，且緊接其後放入對應的值。產生的字串即可直接傳遞給 **barcode generator c#**，無需額外編碼。

### 常見陷阱

* **缺少括號** – 產生器會將字串視為原始資料，且不會套用 GS1 檢查。
* **超過長度限制** – MicroPDF417 最多支援 155 個字元。請去除不必要的空白。
* **不合法字元** – GTIN 只能使用數字；序號可包含大寫英文字母與數字。

## 從資料自訂條碼影像

除了基本的 X‑dimension，Aspose.BarCode 還提供許多視覺調整選項。以下示範幾項您可能根據專案需求調整的設定。

```csharp
// Set background to transparent (useful for overlaying on UI)
generator.Parameters.ImageBackgroundColor = Color.Transparent;

// Change foreground color to dark blue for branding
generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);

// Increase image resolution to 300 dpi for print‑ready output
generator.Parameters.ImageResolution = 300;
```

每個設定皆為可選項目；預設值已能產生乾淨、可掃描的 **條碼影像**。在確認掃描器仍能讀取後，再嘗試變更顏色與解析度。

## 以其他格式儲存條碼

雖然 PNG 是網頁與行動裝置最常使用的格式，您也可能需要 JPEG、BMP 或 SVG。`Save` 方法接受任何 `BarCodeImageFormat` 列舉值。

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

* JPEG 可減少檔案大小，但壓縮產生的雜訊可能影響可讀性。
* SVG 保留向量品質，適合響應式網頁設計。

## 驗證產生的條碼

快速確認 **create barcode image** 步驟是否成功的方法，是使用支援 GS1 MicroPDF417 的手機掃描應用程式。掃描已儲存的 PNG，應顯示：

```
GTIN: 12345678901234
Serial: ABC123
```

若掃描器回報錯誤，請再次檢查 AI 格式與 X‑dimension 設定。

## 完整範例 – 獨立執行的 Console 程式

以下提供一個完整程式，您可直接複製、貼上並執行（除 NuGet 安裝步驟外無需其他修改）。

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with GS1 MicroPDF417 and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "(01)12345678901234(21)ABC123");

            // Improve readability by setting module width
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Optional visual customisation
            generator.Parameters.ImageBackgroundColor = Color.Transparent;
            generator.Parameters.Barcode.BarColor = Color.FromArgb(0, 0, 139);
            generator.Parameters.ImageResolution = 300;

            // Define output path (Desktop folder)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "GS1MicroPdf417.png");

            // Save the barcode as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

執行程式後，主控台會印出完整檔案路徑，PNG 會出現在桌面。此範例示範了 **如何產生條碼** 資料、客製化外觀，並在單一工作流程中匯出 **從資料產生條碼影像**。

## 常見問與答

| 問題 | 答案 |
|------|------|
| *我可以產生其他 GS1 符號嗎？* | 可以。將 `EncodeTypes.MicroPdf417` 改為 `EncodeTypes.Pdf417`、`EncodeTypes.DataMatrix` 等，並相應調整資料字串。 |
| *如果我的資料超過 MicroPDF417 容量該怎麼辦？* | 改用一般的 PDF417 符號，該符號支援更長的負載。 |
| *使用 Aspose.BarCode 是否需要授權？* | 免費評估授權可用於開發。正式上線時，請購買授權以移除評估浮水印。 |
| *PNG 是否適合列印於標籤上？* | 請將 `ImageResolution` 提升至 300 dpi 或更高，亦可考慮以 TIFF 格式儲存以符合工業印表機需求。 |

## 結論

您現在已掌握如何在 C# 中使用 **barcode generator c#** 方法 **建立條碼影像**、為 **create gs1 barcode** 場景格式化資料，並將結果匯出為 PNG 或其他影像類型。完整範例展示了從資料準備到視覺客製化的每一步，讓您能將條碼產生整合至任何 .NET 應用程式。

接下來，您可以探索如 **barcode image from data** 的 QR 代碼應用、在單一 PDF 中加入多個條碼，或為庫存系統自動批次產生條碼。試著調整 X‑dimension 與影像格式，找出最適合您掃描環境的最佳組合。

祝開發順利，讓您的應用程式能 **建立可靠的條碼影像**，在實務中發揮效用！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [How to create barcode image with Aspose.Barcode in C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}