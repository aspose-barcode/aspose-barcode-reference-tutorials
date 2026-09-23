---
category: general
date: 2026-08-03
description: 快速在 C# 中建立 PDF417 條碼。了解如何產生 PDF417 條碼以及如何使用 Aspose.Barcode 將條碼圖像儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- how to save barcode image
language: zh-hant
lastmod: 2026-08-03
og_description: 使用 C# 及 Aspose.Barcode 建立 PDF417 條碼。請參考本指南了解如何產生 PDF417 條碼以及如何有效儲存條碼影像。
og_image_alt: Screenshot of a generated compact PDF417 barcode saved as PNG
og_title: 在 C# 中建立 PDF417 條碼 – 完整程式教學
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  headline: Create PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Create PDF417 barcode in C# quickly. Learn how to generate PDF417 barcode
    and how to save barcode image as PNG with Aspose.Barcode.
  name: Create PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: Why this matters
    text: '* **EncodeTypes.Pdf417** tells the library to use the PDF417 standard,
      which supports large data payloads and error correction. * Providing Unicode
      characters proves the generator handles non‑ASCII input without extra configuration.'
  - name: Practical tip
    text: If you need a taller barcode for limited horizontal space, increase `Columns`.
      Setting `Truncate` to `true` reduces the overall height by removing quiet zones,
      which is ideal for mobile screens.
  - name: Expected result
    text: Running the program creates `CompactPdf417.png` in the project folder. Opening
      the file shows a compact PDF417 barcode that encodes the string *Åspóse.Barcóde©*.
      The image can be embedded in HTML, PDF reports, or printed on labels.
  - name: Verifying the output
    text: 'After the program finishes, you can verify the file exists with a quick
      command:'
  type: HowTo
tags:
- barcode
- C#
- PDF417
- image generation
title: 在 C# 中建立 PDF417 條碼 – 步驟指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 PDF417 條碼 – 步驟指南

如果您需要在 .NET 應用程式中 **建立 PDF417 條碼**，本指南會精確說明如何產生 PDF417 條碼以及如何儲存條碼影像。最終您會得到一個可用於報告、票證或行動掃描應用程式的 PNG 檔案。

本教學涵蓋從專案設定到最終 PNG 檔案的全部步驟。無需參考外部文件，只要依照步驟執行程式碼即可。

## 您需要的條件

在開始之前，請確保您具備以下環境：

* .NET 6.0 SDK 或更新版本（此程式碼亦可在 .NET Framework 4.7+ 上執行）
* Visual Studio 2022 或任何支援 C# 的 IDE
* 具備網際網路連線以安裝 **Aspose.Barcode for .NET** NuGet 套件

這些前置條件可確保程式碼在不需額外設定的情況下成功編譯。

## 建立 PDF417 條碼 – 專案設定

1. 開啟命令提示字元並建立新的主控台專案：

   ```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

2. 加入 Aspose.Barcode 函式庫：

   ```bash
   dotnet add package Aspose.Barcode
   ```

3. 開啟產生的 `Program.cs` 檔案。檔案頂部的 `using` 陳述式讓您可以使用條碼相關類別：

   ```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

專案現在已準備好 **建立 PDF417 條碼**。

## 使用 Aspose.Barcode 產生 PDF417 條碼

條碼產生的核心在 `BarcodeGenerator` 類別。您需要指定條碼類型（`EncodeTypes.Pdf417`）以及要編碼的資料。

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### 為何這很重要

* **EncodeTypes.Pdf417** 告訴函式庫使用 PDF417 標準，該標準支援大量資料負載與錯誤更正。  
* 提供 Unicode 字元可證明產生器在未額外設定的情況下能處理非 ASCII 輸入。

## 設定條碼外觀

您可以控制每個模組的大小、欄位數量，以及條碼是否使用緊湊（截斷）模式。這些設定會同時影響可讀性與檔案大小。

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

### 實用技巧

如果水平空間受限需要較高的條碼，請增加 `Columns`。將 `Truncate` 設為 `true` 會透過移除安靜區（quiet zones）降低整體高度，非常適合行動裝置螢幕。

## 將條碼影像儲存為 PNG

完成產生器設定後，呼叫 `Save` 並傳入檔案路徑與目標影像格式。此方法會直接將影像寫入磁碟。

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

### 預期結果

執行程式後會在專案資料夾產生 `CompactPdf417.png`。開啟該檔案會看到一個緊湊的 PDF417 條碼，編碼的字串為 *Åspóse.Barcóde©*。此影像可嵌入 HTML、PDF 報告，或列印於標籤上。

## 完整原始碼

以下是完整且可執行的程式。將內容複製到 `Program.cs` 後執行 `dotnet run`。

```csharp
using System;
using Aspose.Barcode.Generation;
using Aspose.Barcode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with PDF417 symbology and sample text.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.Pdf417,
                "Åspóse.Barcóde©");

            // Set the module width to 2 pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Configure PDF417‑specific options.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // Define the output file path.
            string outputPath = @"./CompactPdf417.png";

            // Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 驗證輸出

程式結束後，您可以使用以下指令快速確認檔案是否存在：

```bash
dotnet run && ls -l CompactPdf417.png
```

如果檔案出現，表示 **建立 PDF417 條碼** 的流程已成功完成。

## 常見變化與邊緣案例

| 情況 | 調整方式 |
|-----------|------------|
| **Longer data string** | 增加 `Columns` 或設定 `Rows` 以容納更多程式碼字。 |
| **Different image format** | 將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。 |
| **Higher resolution** | 在 `Save` 之前設定 `generator.Parameters.ImageResolution`。 |
| **Background color** | 使用 `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`。 |
| **Exception handling** | 將 `generator.Save` 包裹於 `try/catch` 區塊以捕捉 I/O 錯誤。 |

這些變化讓您能依需求為特定裝置或品牌需求客製化條碼。

## 結論

您現在已了解如何在 C# 中使用 Aspose.Barcode **建立 PDF417 條碼**、設定其外觀，並 **將條碼影像儲存為 PNG**。完整範例示範了從專案設定到驗證的每一步，讓您能將條碼產生整合至任何 .NET 解決方案。

接下來，您可以探索相關主題，例如 **如何產生 QR Code**、**在 PDF 文件中嵌入條碼**，或 **自訂條碼顏色**。這些主題皆基於相同的產生器 API，讓您以最小的努力擴充應用程式的掃描功能。祝開發順利！

## 接下來您應該學習什麼？

以下教學涵蓋與本指南技術緊密相關的主題，每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 建立條碼 – 緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}