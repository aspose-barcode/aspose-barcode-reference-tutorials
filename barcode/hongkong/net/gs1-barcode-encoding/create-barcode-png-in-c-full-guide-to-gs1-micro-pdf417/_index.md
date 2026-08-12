---
category: general
date: 2026-08-12
description: 使用 Aspose.BarCode 在 C# 中快速產生條碼 PNG。學習如何在 C# 生成 PDF417 條碼，並在單一教學中精通條碼產生器的使用。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode PNG
- generate PDF417 barcode C#
- barcode generator usage
- GS1 Micro PDF417 example
- Aspose.BarCode C#
language: zh-hant
lastmod: 2026-08-12
og_description: 使用 Aspose.BarCode 在 C# 中建立條碼 PNG。本教學將示範如何在 C# 中產生 PDF417 條碼，並有效使用條碼產生器。
og_image_alt: create barcode PNG example showing a GS1 Micro PDF417 code
og_title: 在 C# 中建立條碼 PNG – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-08-12'
  description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  headline: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  type: TechArticle
- description: Create barcode PNG in C# quickly with Aspose.BarCode. Learn how to
    generate PDF417 barcode C# and master barcode generator usage in a single tutorial.
  name: Create barcode PNG in C# – full guide to GS1 Micro PDF417
  steps:
  - name: Why each line matters
    text: '| Line | Reason | |------|--------| | `EncodeTypes.Gs1MicroPdf417` | Selects
      the specific PDF417 variant required for GS1 applications. | | Data string `"(01)12345678901231(10)ABC123"`
      | Demonstrates the GS1 AI syntax for a GTIN (01) and a lot number (10). | |
      `XDimension.Pixels = 2` | Controls the '
  - name: Expected visual result
    text: The PNG contains a rectangular barcode with evenly spaced black modules.
      Scanning it with a GS1‑compatible scanner returns the string `(01)12345678901231(10)ABC123`,
      confirming that **generate PDF417 barcode C#** succeeded.
  - name: Changing the symbology
    text: 'If you need a regular PDF417 instead of the micro version, replace the
      encode type:'
  - name: Adjusting image format
    text: 'Aspose.BarCode supports many formats. To create a JPEG instead:'
  - name: Saving to a stream (useful for web APIs)
    text: '```csharp using (var ms = new MemoryStream()) { generator.Save(ms, BarCodeImageFormat.Png);
      // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
      } ```'
  - name: What’s next?
    text: '* Explore **barcode reader integration** to verify generated images automatically.
      * Experiment with **custom colors** and **logo embedding** for brand‑aware barcodes.
      * Review the Aspose.BarCode documentation for advanced error‑correction settings
      and multi‑page PDF417 generation.'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 使用 C# 產生條碼 PNG – GS1 Micro PDF417 完整指南
url: /zh-hant/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立條碼 PNG – 完整指南：GS1 Micro PDF417

如果你需要在 .NET 應用程式中 **create barcode PNG**，本指南會精確示範如何操作。你將學習在 C# 中產生 PDF417 條碼，並了解在生產環境中可行的 **barcode generator usage** 模式。

產生條碼影像是庫存系統、運送標籤與票務平台的常見需求。完成本教學後，你將擁有一個自包含的主控台程式，能寫入包含 GS1 Micro PDF417 條碼的 PNG 檔案，供後續處理使用。

## 前置條件

* .NET 6.0 SDK 或更新版本已安裝（此程式碼亦可於 .NET Framework 4.7.2+ 執行）。
* 最近版本的 **Aspose.BarCode for .NET** NuGet 套件。使用以下指令安裝：  
  `dotnet add package Aspose.BarCode`.
* 具備 C# 主控台專案的基本知識。
* 對將 PNG 儲存至的資料夾具有寫入權限。

這些需求讓範例保持輕量，同時符合真實環境的設定。

## 步驟 1：設定 C# 專案

建立新的主控台專案並加入 Aspose.BarCode 參考：

```bash
dotnet new console -n BarcodePngDemo
cd BarcodePngDemo
dotnet add package Aspose.BarCode
```

`dotnet` CLI 會產生 `Program.cs` 檔案並還原 NuGet 套件。此步驟對 **barcode generator usage** 至關重要，因為程式庫內含我們將使用的 `BarcodeGenerator` 類別。

## 步驟 2：撰寫完整的條碼產生程式碼

將 `Program.cs` 的內容取代為以下程式碼。它包含了從頭到尾 **create barcode PNG** 所需的每一行程式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodePngDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------
            // 1️⃣ Create a BarcodeGenerator for GS1 Micro PDF417
            // -------------------------------------------------
            // EncodeTypes.Gs1MicroPdf417 tells Aspose.BarCode to use the
            // GS1 Micro PDF417 symbology. The data string follows the
            // Application Identifier (AI) format required by GS1.
            var generator = new BarcodeGenerator(
                EncodeTypes.Gs1MicroPdf417,
                "(01)12345678901231(10)ABC123");

            // -------------------------------------------------
            // 2️⃣ Adjust the X‑dimension (module width)
            // -------------------------------------------------
            // XDimension controls the physical size of each barcode module.
            // Lower values produce a smaller image; higher values increase
            // readability on low‑resolution scanners.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -------------------------------------------------
            // 3️⃣ (Optional) Set image resolution and background
            // -------------------------------------------------
            // Higher DPI yields a sharper PNG, useful when the image
            // will be printed. BackgroundColor can be set to Transparent.
            generator.Parameters.ImageResolution = 300;      // DPI
            generator.Parameters.Barcode.BackgroundColor = System.Drawing.Color.Transparent;

            // -------------------------------------------------
            // 4️⃣ Save the barcode as a PNG file
            // -------------------------------------------------
            // The Save method writes the image to disk. You can also
            // choose other formats such as Jpeg, Bmp, or Gif.
            string outputPath = "output.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode PNG created at: {outputPath}");
        }
    }
}
```

### 為何每一行都很重要

| 行號 | 原因 |
|------|------|
| `EncodeTypes.Gs1MicroPdf417` | 選擇 GS1 應用所需的特定 PDF417 變體。 |
| Data string `"(01)12345678901231(10)ABC123"` | 示範 GTIN (01) 與批號 (10) 的 GS1 AI 語法。 |
| `XDimension.Pixels = 2` | 控制條碼的實體尺寸；常見的螢幕顯示預設值。 |
| `ImageResolution = 300` | 提升 DPI，確保列印時 PNG 清晰。 |
| `BackgroundColor = Transparent` | 使 PNG 可於 UI 中疊加使用。 |
| `Save(..., BarCodeImageFormat.Png)` | 將條碼保存為 PNG，滿足 **create barcode PNG** 目標。 |

## 步驟 3：執行程式並驗證輸出

執行主控台應用程式：

```bash
dotnet run
```

你應該會看到確認訊息，且在專案資料夾中找到 `output.png`。開啟該檔案會顯示一個編碼了範例資料的 GS1 Micro PDF417 條碼。

![create barcode PNG 範例顯示 GS1 Micro PDF417 條碼](barcode-example.png)

### 預期視覺結果

此 PNG 包含一個矩形條碼，黑色模組均勻排列。使用支援 GS1 的掃描器掃描後會回傳字串 `(01)12345678901231(10)ABC123`，證實 **generate PDF417 barcode C#** 成功。

## 步驟 4：探索常見變化

### 更改符號系統

如果需要一般的 PDF417 而非微型版本，請替換編碼類型：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Your data here");
```

### 調整影像格式

Aspose.BarCode 支援多種格式。若要改為 JPEG：

```csharp
generator.Save("output.jpg", BarCodeImageFormat.Jpeg);
```

### 儲存至串流（適用於 Web API）

以下示範儲存至串流（適用於 Web API）：

```csharp
using (var ms = new MemoryStream())
{
    generator.Save(ms, BarCodeImageFormat.Png);
    // ms.ToArray() now contains the PNG bytes – return them from an API endpoint.
}
```

這些程式碼片段示範了超越基本檔案儲存情境的彈性 **barcode generator usage**。

## 專業提示與常見陷阱

* **Validate data length** – GS1 Micro PDF417 有最大資料容量；超過會拋出例外。使用 `generator.Parameters.Barcode.IsValidData(data)` 事先檢查。
* **Avoid tiny XDimension values** – 小於 1 像素的值可能在低解析度裝置上產生無法辨識的條碼。
* **Set `QuietZone`** 若將 PNG 嵌入較大的圖形中；預設的靜區可確保掃描器定位起始/結束圖樣。
* **Thread safety** – `BarcodeGenerator` 實例非執行緒安全。於 Web 服務中每個請求都建立新實例。

## 結論

現在你已了解如何在 C# 中使用 Aspose.BarCode **create barcode PNG**，以及如何使用 GS1 Micro 變體 **generate PDF417 barcode C#**，並掌握有效 **barcode generator usage** 的關鍵模式。完整且可執行的範例可直接放入任何 .NET 專案，且可依需求擴充不同的符號系統、影像格式或串流輸出。

### 接下來？

* 探索 **barcode reader integration** 以自動驗證產生的影像。  
* 嘗試 **custom colors** 與 **logo embedding**，打造具品牌識別的條碼。  
* 查閱 Aspose.BarCode 文件，了解進階錯誤更正設定與多頁 PDF417 產生。

祝程式開發愉快，讓你的應用程式以清晰可靠的 barcode PNG 與機器對話！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在已示範的技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通其他 API 功能，並在專案中探索替代實作方式。

- [如何建立條碼 – 緊湊 PDF417（使用 Aspose.BarCode）](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 DataMatrix C40 以 Aspose.BarCode 儲存 PNG](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [如何產生條碼 – Code 39 設定（使用 Aspose.BarCode）](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}