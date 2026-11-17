---
category: general
date: 2026-11-17
description: 學習如何使用 C# 產生 PDF417 條碼、設定條碼尺寸，並將條碼渲染成圖像。完整的逐步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- render barcode to image
- how to set barcode size
language: zh-hant
lastmod: 2026-11-17
og_description: 在 C# 中產生 PDF417 條碼並將條碼渲染為圖像。遵循本指南設定條碼大小並儲存為 PNG 檔案。
og_image_alt: Screenshot of a generated PDF417 barcode saved as a PNG image
og_title: 產生 PDF417 條碼並渲染為 PNG – C# 教學
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  headline: How to generate PDF417 barcode and render it as PNG
  type: TechArticle
- description: Learn how to generate PDF417 barcode, set barcode size, and render
    barcode to image using C#. Complete step‑by‑step guide.
  name: How to generate PDF417 barcode and render it as PNG
  steps:
  - name: Open the PNG file in any image viewer.
    text: Open the PNG file in any image viewer.
  - name: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
    text: Use a smartphone barcode scanning app that supports PDF417 (e.g., Google
      Lens, QR & Barcode Scanner).
  - name: Scan the image; the app should return the text *Layout demo*.
    text: Scan the image; the app should return the text *Layout demo*.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: 如何產生 PDF417 條碼並將其渲染為 PNG
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-and-render-it-as-png/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何產生 PDF417 條碼並將其渲染為 PNG

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本教學將完整示範。您將會看到如何設定條碼大小、配置版面配置，並以幾行 C# 程式碼 **將條碼渲染為影像**。

在需要將大量資料編碼以供行動裝置或印表機掃描時，產生 PDF417 條碼是常見需求。完成本指南後，您將擁有可直接使用的 PNG 檔案，可嵌入報告、電子郵件或網頁中。

## 前置條件

- .NET 6.0 SDK 或更新版本已安裝  
- C# IDE，例如 Visual Studio 2022（任何編輯器皆可）  
- **Aspose.BarCode for .NET** NuGet 套件（或任何提供 `BarcodeGenerator` 的相容函式庫）  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立 C# 主控台專案

首先，建立一個最小的主控台應用程式，以容納條碼產生程式碼。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation logic will be placed here.
        }
    }
}
```

> **專業提示：** 讓 `Main` 方法保持簡潔，將繁重的工作委派給輔助方法。這樣可提升可讀性，且更易於單元測試。

## 步驟 2：以自訂大小產生 PDF417 條碼

現在我們將 **產生 PDF417 條碼** 並指定模組（X‑dimension）大小。X‑dimension 決定條碼中每個微小方塊的寬度，從而設定整體條碼大小。

```csharp
static void GeneratePdf417(string text, string outputPath)
{
    // Initialize a PDF417 barcode generator with the desired text
    BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, text);

    // Set the size of a single barcode module (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

    // Optional: adjust the number of columns and rows for layout control
    generator.Parameters.Barcode.Pdf417.Columns = 4;   // 4 columns
    generator.Parameters.Barcode.Pdf417.Rows    = 9;   // 9 rows

    // Render the barcode and save it as a PNG image
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

### 為何要設定 X‑dimension？

設定條碼大小的 **how to set barcode size** 步驟很重要，因為過小的 X‑dimension 會導致低解析度掃描器無法辨識條碼，而過大的值則會浪費空間。`2` 像素的數值在大多數螢幕顯示與列印情境下表現良好。

## 步驟 3：從 `Main` 呼叫產生方法

透過呼叫 `GeneratePdf417` 並傳入欲產生的文字與輸出位置，將所有元件串接起來。

```csharp
static void Main(string[] args)
{
    string barcodeText = "Layout demo";
    string outputFile = @"C:\Barcodes\LayoutPdf417.png";

    GeneratePdf417(barcodeText, outputFile);

    Console.WriteLine($"PDF417 barcode saved to {outputFile}");
}
```

執行程式後會產生包含條碼的 `LayoutPdf417.png`：

![已產生的 PDF417 條碼](/images/layout-pdf417.png "由教學程式產生的 PDF417 條碼"){: .align-center alt="已產生的 PDF417 條碼已儲存為 PNG"}

> **預期輸出：** 大約 200 × 100 px（視欄位/列設定而定）的 PNG 檔案，顯示清晰的 PDF417 圖樣，可供掃描使用。

## 步驟 4：驗證條碼是否可用

確保條碼有效，請執行以下步驟：

1. 在任何影像檢視器中開啟 PNG 檔案。  
2. 使用支援 PDF417 的智慧手機條碼掃描應用程式（例如 Google Lens、QR & Barcode Scanner）。  
3. 掃描影像；應用程式應回傳文字 *Layout demo*。

若掃描失敗，請再次確認 X‑dimension 以及欄位/列的數值——較大的模組可提升低解析度相機的可讀性。

## 常見變化與邊緣情況

| Scenario | Adjustment |
|----------|------------|
| **更多資料**（例如 URL） | 增加 `Columns` 或 `Rows` 以容納額外的 codewords。 |
| **高解析度列印** | 將 `XDimension.Pixels` 提升至 3‑4 像素，以獲得更銳利的條紋。 |
| **透明背景** | Use `generator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent })`. |
| **不同的影像格式** | 視需求將 `BarCodeImageFormat.Png` 替換為 `Jpeg` 或 `Bmp`。 |

這些變化回應了不同需求下的 **how to generate PDF417** 問題，同時保持核心邏輯不變。

## 結論

您現在已了解如何使用 C# **產生 PDF417 條碼**、**設定條碼大小**，以及 **將條碼渲染為影像**。完整且可執行的範例會產生可嵌入任何需要機器可讀條碼之處的 PNG 檔案。

接下來，您可以探索相關主題，例如 **將 PNG 嵌入 PDF**（搜尋 *render barcode to PDF*）或 **產生其他 2‑D 條碼** 如 QR Code。調整版面參數以符合您的 UI 設計，並嘗試使用顏色選項進行品牌化。

祝程式開發順利，讓您的條碼發揮重任！

## 接下來您可以學習什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在所示技術之上。每個資源皆提供完整可運作的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何在 C# 中產生 PDF417 條碼 – 完整逐步指南](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-step-by-step-guide/)
- [如何在 C# 中產生微型 PDF417 條碼 – 逐步指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [如何設定 PDF417 條碼的錯誤等級 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}