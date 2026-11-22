---
category: general
date: 2026-11-20
description: 學習如何在 C# 中使用 Aspose.Barcode 產生條碼。本指南將帶領您建立 MicroPdf417 條碼，並將其儲存為 PNG
  圖片。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: zh-hant
lastmod: 2026-11-20
og_description: 如何在 C# 中使用 Aspose.Barcode 產生條碼。請參考本完整教學，建立 MicroPdf417 條碼並匯出為 PNG。
og_image_alt: 'How to generate barcode: sample MicroPdf417 image produced by Aspose.Barcode'
og_title: 如何使用 Aspose.Barcode 產生條碼 – C# 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  headline: How to generate barcode using Aspose.Barcode in C#
  type: TechArticle
- description: Learn how to generate barcode with Aspose.Barcode in C#. This guide
    walks you through creating a MicroPdf417 barcode and saving it as a PNG image.
  name: How to generate barcode using Aspose.Barcode in C#
  steps:
  - name: Install the Aspose.Barcode NuGet package
    text: 'Open a terminal in your project folder and run:'
  - name: Create a `BarcodeGenerator` instance for MicroPdf417
    text: '```csharp using Aspose.Barcode.Generation;'
  - name: Adjust the X‑dimension (module width)
    text: '```csharp // Step 3: Set the module width in pixels – 2 px yields a clear,
      print‑ready image generator.Parameters.Barcode.XDimension.Pixels = 2; ```'
  - name: Choose the number of columns for the PDF417 component
    text: '```csharp // Step 4: Define how many columns the PDF417 component should
      use (1‑4 allowed) generator.Parameters.Barcode.Pdf417.Columns = 4; ```'
  - name: Save the barcode image
    text: '```csharp using System.IO;'
  - name: Full source code
    text: 'Putting all steps together yields a complete, self‑contained console application:'
  - name: Generating other symbologies
    text: 'If you want to **create barcode with Aspose** for QR codes, Code128, or
      UPC, replace `EncodeTypes.MicroPdf417` with the appropriate enum value, e.g.:'
  - name: Changing image format
    text: 'Aspose.Barcode supports multiple raster formats. To export as JPEG with
      90 % quality:'
  - name: Handling large data payloads
    text: MicroPdf417 can store up to 1 KB of data. For larger payloads switch to
      full `EncodeTypes.Pdf417` and adjust `Rows` and `Columns` accordingly.
  - name: Unicode and special characters
    text: The library automatically encodes Unicode strings. However, some legacy
      scanners only recognize ASCII. If you target such devices, limit the input to
      the ASCII range or use a different symbology that guarantees compatibility.
  type: HowTo
tags:
- barcode generation
- Aspose.Barcode
- C#
- MicroPdf417
title: 如何在 C# 中使用 Aspose.Barcode 產生條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-barcode-using-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.Barcode 產生條碼

如果您需要在桌面或網頁應用程式中 **產生條碼**，Aspose.Barcode 提供了簡易的 API。本教學會完整示範如何產生 MicroPdf417 條碼、調整其尺寸，並將結果儲存為 PNG 檔案。您亦會看到如何 **使用 Aspose 建立條碼** 以支援其他格式，且不必離開 IDE。

產生條碼是庫存系統、票務平台與安全文件工作流程的常見需求。完成本指南後，您將擁有一個可執行的程式，能產生高品質的條碼影像，隨時供列印或嵌入使用。

## 您需要的環境

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本（此程式碼亦相容 .NET Framework 4.7+）
* Visual Studio 2022（或任何 C# 編輯器）
* 有效的 Aspose.Barcode for .NET 授權——免費試用版可用於開發與測試
* 基本的 C# 語法概念

除 `Aspose.Barcode` 之外，無需額外的 NuGet 套件。

## 如何使用 Aspose.Barcode 產生條碼

以下各節將流程拆解為獨立步驟。每一步皆說明 **為何** 需要此程式碼，而不僅是 **做什麼**。

### 步驟 1：安裝 Aspose.Barcode NuGet 套件

在專案資料夾的終端機執行：

```bash
dotnet add package Aspose.Barcode
```

此指令會將最新的穩定版 Aspose.Barcode 加入專案檔，確保 `BarcodeGenerator` 類別在編譯時可用。

**為何重要：** 套件內含核心渲染引擎與一組預定義的 `EncodeTypes`。若未安裝，編譯器將無法解析 `BarcodeGenerator` 或 `EncodeTypes`。

### 步驟 2：為 MicroPdf417 建立 `BarcodeGenerator` 實例

```csharp
using Aspose.Barcode.Generation;

// Step 2: Initialize the generator with the desired symbology and data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.MicroPdf417,          // MicroPdf417 is a compact 2‑D barcode
    "Åspóse.Barcóde©");               // Sample text – Unicode characters are supported
```

**為何重要：** 建構子會將符號類型（`EncodeTypes.MicroPdf417`）與欲編碼的原始資料關聯。MicroPdf417 在需要比完整 PDF417 更小尺寸、且仍支援字母數字資料時非常適合。

### 步驟 3：調整 X‑dimension（模組寬度）

```csharp
// Step 3: Set the module width in pixels – 2 px yields a clear, print‑ready image
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為何重要：** X‑dimension 決定每個條碼單元格的大小。數值過低會產生模糊影像，過高則會使條碼不必要地變大。兩個像素是大多數螢幕與列印情境的平衡預設值。

### 步驟 4：設定 PDF417 元件的欄數

```csharp
// Step 4: Define how many columns the PDF417 component should use (1‑4 allowed)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**為何重要：** MicroPdf417 內部使用 PDF417 元件。調整欄數會影響條碼的長寬比與資料容量。四欄可在保持可讀性的前提下取得緊湊外形。

### 步驟 5：儲存條碼影像

```csharp
using System.IO;

// Step 5: Export the barcode as a PNG file
string outputPath = Path.Combine(
    Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
    "MicroPdf417.png");

generator.Save(outputPath, BarCodeImageFormat.Png);
```

**為何重要：** `Save` 會將渲染好的條碼寫入磁碟。PNG 為無損格式，可保留掃描器所需的銳利邊緣。若工作流程需要其他格式，可將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。

### 完整程式碼

將上述步驟整合，即可得到一個完整、獨立的主控台應用程式：

```csharp
using System;
using System.IO;
using Aspose.Barcode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize generator with MicroPdf417 symbology and sample data
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©");

            // Configure visual appearance
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Determine output location (Desktop for easy access)
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");

            // Save the barcode image as PNG
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to: {outputPath}");
        }
    }
}
```

執行程式（`dotnet run`）後，您會在桌面上看到 `MicroPdf417.png`。開啟該檔案，即可看到清晰的 MicroPdf417 條碼，編碼文字為 `"Åspóse.Barcóde©"`。

## 驗證條碼

確認條碼正確產生的方法：

1. 在任何影像檢視器中開啟 PNG。
2. 使用支援 PDF417 或 MicroPdf417 的手機條碼掃描 App。
3. 掃描影像；App 應顯示原始文字，包括特殊字元。

若掃描失敗，請檢查以下項目：

* **X‑dimension：** 小於 1 px 的值可能導致渲染雜訊。
* **欄數：** 超出 1‑4 的值會拋出例外。
* **字元集：** Aspose.Barcode 支援 UTF‑8；請確保來源檔案以 UTF‑8 編碼儲存。

## 常見變形與邊緣案例

### 產生其他符號類型

若想 **使用 Aspose 建立條碼** 以支援 QR Code、Code128 或 UPC，只需將 `EncodeTypes.MicroPdf417` 替換為相應的列舉值，例如：

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

其他設定步驟（X‑dimension、儲存）保持不變。

### 變更影像格式

Aspose.Barcode 支援多種點陣格式。若要以 90 % 品質輸出 JPEG：

```csharp
generator.Save(outputPath, BarCodeImageFormat.Jpeg, 90);
```

### 處理大量資料

MicroPdf417 最多可儲存 1 KB 資料。若資料量更大，請改用完整的 `EncodeTypes.Pdf417`，並相應調整 `Rows` 與 `Columns`。

### Unicode 與特殊字元

函式庫會自動編碼 Unicode 字串。但部分舊版掃描器僅支援 ASCII。若目標裝置屬於此類，請將輸入限制於 ASCII 範圍，或改用保證相容性的其他符號類型。

## 生產環境的實用技巧

* **快取 generator**：在大量產生相同設定的條碼時，可減少物件建立開銷。
* **設定 `Resolution`**（`generator.Parameters.ImageResolution`）為 300 dpi，以取得高品質列印輸出。
* **啟用錯誤更正**：對 2‑D 條碼使用 `generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel`，提升受損媒介上的掃描可靠度。
* **將儲存程式碼包在 `try / catch`** 中，以處理 I/O 例外，特別是寫入網路共享時。

## 結論

現在您已掌握 **如何在 C# 中使用 Aspose.Barcode 產生條碼**。本教學涵蓋了 NuGet 套件安裝、建立 `BarcodeGenerator`、設定尺寸與欄數，以及將結果儲存為 PNG 影像。憑藉此基礎，您可以 **使用 Aspose 建立條碼** 以支援任何支援的符號類型，調整視覺參數，並將條碼產生整合至更大型的 .NET 解決方案。

想進一步探索嗎？試著為 URL 縮短服務產生 QR Code、在 PDF 報表中嵌入條碼（使用 Aspose.PDF），或自動化批次產生庫存管理條碼。每個新情境都建立在此處示範的核心概念之上。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能延伸您在本篇中學到的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索替代實作方式。

- [How to Generate PDF417 Barcode with Aspose – Complete Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [How to Generate DataMatrix Barcodes Using Aspose.BarCode for .NET – Step‑by‑Step Guide](/barcode/english/net/datamatrix-barcode-configuration/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}