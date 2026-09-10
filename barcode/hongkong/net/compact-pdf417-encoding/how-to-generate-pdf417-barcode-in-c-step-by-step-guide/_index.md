---
category: general
date: 2026-09-10
description: 在 C# 中快速產生 PDF417 條碼。只需幾行程式碼，即可了解如何產生 PDF417 以及如何使用 Aspose.BarCode 調整條碼大小。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- how to generate PDF417
- how to change barcode size
language: zh-hant
lastmod: 2026-09-10
og_description: 即時在 C# 中生成 PDF417 條碼。本教學展示如何生成 PDF417 以及如何使用 Aspose.BarCode 調整條碼大小。
og_image_alt: generate PDF417 barcode example showing 4 columns and 9 rows
og_title: 使用 C# 生成 PDF417 條碼 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  headline: How to generate PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Generate PDF417 barcode in C# quickly. Learn how to generate PDF417
    and how to change barcode size with Aspose.BarCode in just a few lines.
  name: How to generate PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Create a new console project:'
    text: 'Create a new console project:'
  - name: Add the Aspose.BarCode reference (see prerequisites).
    text: Add the Aspose.BarCode reference (see prerequisites).
  - name: Open `Program.cs` and replace its content with the full example below.
    text: Open `Program.cs` and replace its content with the full example below.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中產生 PDF417 條碼 – 步驟教學
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生 PDF417 條碼 – 逐步指南

如果您需要在 .NET 應用程式中**產生 PDF417 條碼**，本指南會完整說明操作步驟。您將看到一個簡潔、可直接執行的範例，能建立 PDF417 條碼、控制其尺寸，並將結果儲存為 PNG 圖片。

產生 PDF417 條碼是庫存系統、登機證與文件追蹤等常見需求。在本教學中，我們亦會說明**如何變更條碼尺寸**，讓程式碼能因應不同的列印或螢幕顯示需求。

## 先決條件

* .NET 6.0 或更新版本（此程式碼亦可於 .NET Framework 4.6+ 執行）
* Visual Studio 2022 或任何 C# IDE
* **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 具備 C# 主控台應用程式的基本知識

## 專案設定

1. 建立新的主控台專案：

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. 加入 Aspose.BarCode 參考（請參考先決條件）。

3. 開啟 `Program.cs`，將其內容取代為以下完整範例。

## 步驟 1：產生 PDF417 條碼

第一步是建立一個 `BarcodeGenerator` 實例，並設定為 **PDF417** 符號。此物件是所有條碼操作的入口點。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");
```

*為何重要* – `EncodeTypes.Pdf417` 列舉值告訴 Aspose.BarCode 使用 PDF417 標準，而第二個參數則提供要編碼的資料。此產生器現在持有完整的條碼物件，您可在儲存前自行客製化。

## 步驟 2：如何變更條碼尺寸（模組大小）

PDF417 條碼由小方形模組組成。調整模組大小會改變影像的整體尺寸，但不會影響已編碼的資料。

```csharp
        // Step 2: Define the module size (X‑dimension) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module
```

*為何重要* – 較大的 `XDimension` 會產生較大的條碼，適合高解析度列印；較小的值則較適合螢幕顯示。預設通常為 1 px，在現代顯示器上可能顯得過於擁擠。

## 步驟 3：設定版面 – 欄與列

PDF417 允許您定義欄與列的數量，這會影響條碼的形狀以及錯誤更正能力。

```csharp
        // Step 3: Configure the layout – set the number of columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        generator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

*為何重要* – 欄數增加會使條碼變寬，列數增加則會使條碼變高。請依 UI 或列印標籤的可用空間調整這些數值。

## 步驟 4：儲存條碼影像

最後，將條碼寫入檔案。此處使用 PNG，因為它能保留清晰的邊緣並支援透明度。

```csharp
        // Step 4: Save the generated barcode as a PNG image
        string outputPath = "LayoutPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"PDF417 barcode saved to {outputPath}");
    }
}
```

執行程式後會在專案的輸出資料夾產生 `LayoutPdf417.png`。影像如下所示：

![產生 PDF417 條碼範例（顯示 4 欄 9 列）](https://example.com/images/pdf417-sample.png){#barcode-image alt="產生 PDF417 條碼範例（顯示 4 欄 9 列）"}

*提示*：若需其他影像格式（JPEG、BMP、TIFF），請將 `BarCodeImageFormat.Png` 替換為相應的列舉值。

## 如何產生 PDF417 – 替代資料來源

上述程式碼使用硬編碼字串 `"Layout test"`。在實務情境中，您通常會從資料庫、檔案或使用者輸入取得資料。

```csharp
string dataFromDb = GetOrderNumber(); // your own method
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, dataFromDb);
```

其餘步驟（尺寸、版面、儲存）保持不變。此範例示範了**如何從動態來源產生 PDF417**，且不需額外的複雜度。

## 常見陷阱與避免方法

| 問題 | 發生原因 | 解決方法 |
|-------|----------------|-----|
| 條碼顯示模糊 | `XDimension` 設定過低，無法符合輸出解析度 | 增加 `XDimension.Pixels`，或以向量格式（如 SVG (`BarCodeImageFormat.Svg`)）儲存 |
| 文字無法適應所選版面 | 所選的列/欄容納的字元過多 | 減少列/欄數量，或將資料分割成多個條碼 |
| 影像檔未建立 | 輸出資料夾不存在或缺少寫入權限 | 確保資料夾已存在（`Directory.CreateDirectory`），且應用程式具備適當權限 |

## 驗證條碼

產生影像後，您可以使用任何 PDF417 掃描應用程式（手機上有免費掃描器）或內建的 Aspose.BarCode 讀取器來驗證：

```csharp
using Aspose.BarCode.BarCodeRecognition;

// Load the image we just saved
BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
if (reader.Read())
{
    Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
}
else
{
    Console.WriteLine("Failed to decode the barcode.");
}
```

若輸出與原始文字相符，則 **產生 PDF417 條碼** 的流程即成功。

## 完整、可執行範例

以下為完整程式碼，您可直接複製貼上至 `Program.cs`。它包含所有 using 指令、錯誤處理與註解。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Prepare output directory
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);
        string outputPath = Path.Combine(outputDir, "LayoutPdf417.png");

        // 1️⃣ Create the generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout test");

        // 2️⃣ Change barcode size (module size)
        generator.Parameters.Barcode.XDimension.Pixels = 2; // 2 px per module

        // 3️⃣ Set layout – columns and rows
        generator.Parameters.Barcode.Pdf417.Columns = 4;
        generator.Parameters.Barcode.Pdf417.Rows    = 9;

        // 4️⃣ Save as PNG
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"PDF417 barcode saved to {outputPath}");

        // 5️⃣ Verify the barcode by reading it back
        BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.Pdf417);
        if (reader.Read())
        {
            Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
        }
        else
        {
            Console.WriteLine("Failed to decode the barcode.");
        }
    }
}
```

執行此程式會輸出：

```
PDF417 barcode saved to C:\...\output\LayoutPdf417.png
Decoded text: Layout test
```

現在您已擁有一個**完整、獨立的解決方案**，可用於產生 PDF417 條碼並控制其尺寸。

## 結論

在本教學中，您學會了如何使用 Aspose.BarCode 在 C# 中**產生 PDF417 條碼**，以及透過調整 X‑dimension 來**變更條碼尺寸**，並設定欄與列以控制版面。您亦了解了如何以程式方式驗證結果，以及如何將程式碼套用於動態資料。

接下來，您可以探索：

* **如何產生 PDF417**（調整錯誤更正等級） (`generator.Parameters.Barcode.Pdf417.ErrorLevel`)
* 匯出為**向量格式**（SVG、EPS），以實現無限縮放
* 將條碼嵌入 PDF 文件，使用**Aspose.PDF**

請嘗試不同的模組大小與版面設定，以符合您的 UI 或列印需求。祝開發順利！

## 接下來您應該學習什麼？

以下的教學涵蓋與本指南緊密相關的主題，並以此為基礎。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何使用 Aspose 產生 PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [調整條碼尺寸 – C# 產生 PDF417 條碼指南](/barcode/english/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [如何在 C# 中儲存條碼 – 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}