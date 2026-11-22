---
category: general
date: 2026-11-20
description: 學習如何在 C# 中使用 BarcodeGenerator 產生 PDF417 條碼。此一步一步的指南涵蓋 X 尺寸、列設定以及 PNG
  匯出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- PDF417 barcode in C#
- BarcodeGenerator EncodeTypes
- set XDimension pixels
- configure PDF417 columns
- save barcode as PNG
language: zh-hant
lastmod: 2026-11-20
og_description: 快速在 C# 中產生 PDF417 條碼。請依照本指南設定尺寸、欄位，並將條碼匯出為 PNG 圖像。
og_image_alt: Screenshot of C# code that generates a PDF417 barcode and saves it as
  a PNG file
og_title: 在 C# 中生成 PDF417 條碼 – 完整逐步指南
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  headline: How to generate PDF417 barcode in C# with BarcodeGenerator
  type: TechArticle
- description: Learn how to generate PDF417 barcode in C# using BarcodeGenerator.
    This step‑by‑step guide covers X‑Dimension, column settings, and PNG export.
  name: How to generate PDF417 barcode in C# with BarcodeGenerator
  steps:
  - name: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
    text: '**Initialize the generator** – The `BarcodeGenerator` ties the chosen symbology
      (`EncodeTypes.Pdf417`) to the data you want to encode. Without this object you
      cannot access any further configuration.'
  - name: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
    text: '**Set X‑Dimension** – PDF417 is built from tiny rectangular modules. Changing
      `XDimension.Pixels` lets you control the barcode’s visual density, which is
      crucial for readability on low‑resolution displays or printers.'
  - name: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
    text: '**Configure columns** – PDF417 can arrange its codewords in a variable
      number of columns. Fewer columns produce a taller barcode, while more columns
      flatten it. Adjust this to fit the space where the image will be placed.'
  - name: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
    text: '**Save as PNG** – PNG is a loss‑less format, preserving the sharp edges
      required for accurate scanning. You could also choose JPEG or BMP, but PNG is
      the safest default.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 BarcodeGenerator 產生 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcodegenerator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 BarcodeGenerator 產生 PDF417 條碼

如果您需要在 .NET 應用程式中**產生 PDF417 條碼**，本指南將會完整示範如何操作。您將看到一個完整、可執行的範例，設定 X‑Dimension、選擇欄位數量，並將結果儲存為 PNG 圖片。

在需要將大量資料（例如駕照、登機證或庫存記錄）編碼成緊湊、機器可讀的圖像時，產生 PDF417 條碼是常見需求。在本教學中，我們使用 Aspose.BarCode 函式庫的 **BarcodeGenerator** 類別，但其概念同樣適用於任何支援 PDF417 的函式庫。

閱讀完本篇文章後，您將能夠：

* 為 PDF417 編碼初始化 `BarcodeGenerator`。  
* 使用 **set XDimension pixels** 調整模組大小。  
* 透過 **configure PDF417 columns** 控制版面配置。  
* **Save barcode as PNG**，以供網頁、行動應用程式或印刷品使用。  

> **先決條件**  
> * .NET 6.0 或更新版本（程式碼亦相容於 .NET Framework 4.7 以上）。  
> * 參考 **Aspose.BarCode** NuGet 套件 (`Install-Package Aspose.BarCode`)。  
> * 具備 C# 與 Visual Studio（或您偏好的任何 IDE）的基本知識。

---

## 如何在 C# 中產生 PDF417 條碼

此解決方案的核心是一個簡短的四步驟流程。每一步皆封裝於獨立的方法中，方便在更大型的專案中重複使用。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Initialize the generator with the desired text
            var generator = CreateGenerator("Åspóse.Barcóde©");

            // 2️⃣ Adjust the X‑Dimension (module size)
            SetXDimension(generator, 2);

            // 3️⃣ Define how many columns the barcode should have
            SetPdf417Columns(generator, 3);

            // 4️⃣ Save the barcode as a PNG file
            SaveAsPng(generator, @"YOUR_DIRECTORY\Pdf417Basic.png");

            Console.WriteLine("PDF417 barcode generated successfully.");
        }

        // ---------------------------------------------------------
        // Step 1: Create a BarcodeGenerator for PDF417
        // ---------------------------------------------------------
        private static BarcodeGenerator CreateGenerator(string text)
        {
            // EncodeTypes.Pdf417 tells the library to use the PDF417 symbology.
            return new BarcodeGenerator(EncodeTypes.Pdf417, text);
        }

        // ---------------------------------------------------------
        // Step 2: Set the X‑Dimension (size of a single module)
        // ---------------------------------------------------------
        private static void SetXDimension(BarcodeGenerator generator, int pixels)
        {
            // XDimension controls the width of the smallest black/white bar.
            // A value of 2 pixels works well for most screen resolutions.
            generator.Parameters.Barcode.XDimension.Pixels = pixels;
        }

        // ---------------------------------------------------------
        // Step 3: Configure the number of columns in the PDF417 barcode
        // ---------------------------------------------------------
        private static void SetPdf417Columns(BarcodeGenerator generator, int columns)
        {
            // Columns affect the barcode’s aspect ratio.
            // Small numbers (e.g., 3) produce a tall barcode; larger numbers make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = columns;
        }

        // ---------------------------------------------------------
        // Step 4: Export the barcode as a PNG image
        // ---------------------------------------------------------
        private static void SaveAsPng(BarcodeGenerator generator, string outputPath)
        {
            // BarCodeImageFormat.Png ensures lossless quality.
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### 為何這四個步驟很重要

1. **Initialize the generator** – `BarcodeGenerator` 將所選的符號類型 (`EncodeTypes.Pdf417`) 與您欲編碼的資料關聯起來。若沒有此物件，將無法進一步設定。  
2. **Set X‑Dimension** – PDF417 由微小的矩形模組組成。調整 `XDimension.Pixels` 可控制條碼的視覺密度，這對於低解析度螢幕或印表機的可讀性至關重要。  
3. **Configure columns** – PDF417 能以可變的欄位數排列碼字。欄位較少會產生較高的條碼，欄位較多則使條碼變寬。請依圖像放置的空間調整此設定。  
4. **Save as PNG** – PNG 為無損格式，能保留掃描所需的銳利邊緣。雖然也可選擇 JPEG 或 BMP，但 PNG 是最安全的預設選項。

---

## 設定條碼尺寸 (X‑Dimension)

**set XDimension pixels** 步驟直接影響掃描器對條碼的解讀。若模組過小，低畫質相機可能無法捕捉到單一條紋；若過大，條碼則會變得不必要地龐大。

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 2; // 2‑pixel modules
```

**最佳實踐：** 在預期的列印尺寸下測試產生的圖像。對於高密度列印（300 dpi 以上），`1` 或 `2` 的數值表現良好。對於 96 dpi 的螢幕顯示，`2`–`3` 可提供清晰的視覺效果。

---

## 設定 PDF417 欄位數

**configure PDF417 columns** 步驟讓您決定條碼的形狀。

```csharp
generator.Parameters.Barcode.Pdf417.Columns = 3; // three columns → tall barcode
```

### 何時調整欄位數

| 欄位數 | 產生形狀 | 典型使用情境 |
|--------|----------|--------------|
| 1–3    | 高且窄   | 寬度受限的標籤 |
| 4–9    | 平衡     | 一般用途掃描 |
| 10+    | 寬且短   | 大型標示或網頁圖形 |

如果您的資料負載超過預設容量，函式庫會自動加入額外的列，但仍可透過調整欄位數來影響長寬比。

---

## 匯出條碼為 PNG

將條碼儲存為 PNG 圖片相當簡單：

```csharp
generator.Save(@"C:\Barcodes\Pdf417Basic.png", BarCodeImageFormat.Png);
```

**為何選擇 PNG？**  
* 無損壓縮保留條碼閱讀器所需的銳利邊緣。  
* PNG 支援透明度，若日後將條碼覆蓋於彩色背景上會很有用。

若需其他格式，只需將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Svg`——API 會自動處理轉換。

---

## 常見問題與故障排除

| 問題 | 可能原因 | 解決方式 |
|------|----------|----------|
| 條碼看起來模糊 | X‑Dimension 對輸出解析度而言過小 | 將 `XDimension.Pixels` 增加至 3 或 4。 |
| 掃描器無法讀取條碼 | 所選字型不支援 Unicode 字元 | 確保函式庫的字型支援該字元，或改用 ASCII 等效字元。 |
| 未產生輸出檔案 | 路徑無效或缺乏寫入權限 | 使用絕對路徑並確認資料夾寫入權限。 |
| 列過多，條碼變高 | 欄位數對資料長度而言過低 | 將 `Pdf417.Columns` 提升至較高的數值（例如 6）。 |

---

## 完整範例回顧

以下是您可以直接複製貼上至新 Console 專案的**完整程式**。除 `using` 陳述式與 Aspose.BarCode 套件外，無需其他程式碼。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Save(@"YOUR_DIRECTORY\Pdf417Basic.png", BarCodeImageFormat.Png);
            Console.WriteLine("PDF417 barcode generated and saved as PNG.");
        }
    }
}
```

**預期輸出：** 產生名為 `Pdf417Basic.png` 的檔案，內含清晰的 PDF417 條碼，編碼字串為 `Åspóse.Barcóde©`。開啟後，圖像應顯示一系列堆疊的矩形條紋，左側密度較高（因為採用三欄布局）。

---

## 結論

現在您已了解如何在 C# 中使用 `BarcodeGenerator` 類別**產生 PDF417 條碼**。本教學涵蓋了初始化產生器、**set XDimension pixels**、**configure PDF417 columns**，以及**save barcode as PNG**——這些是任何可投入生產的條碼工作流程的必要步驟。

接下來您可以：

* 嘗試不同的 `EncodeTypes`（例如 QR、Code128）。  
* 透過 `generator.Parameters.Barcode.Pdf417.ErrorLevel` 加入錯誤更正等級。  
* 將條碼直接渲染至 `MemoryStream` 以供 Web API 使用。  

歡迎將程式碼套用到自己的專案，並在留言或 Stack Overflow（使用 `#pdf417` 標籤）分享您的成果。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [Generate PDF417 barcode as PNG in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-as-png-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# – step‑by‑step guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}