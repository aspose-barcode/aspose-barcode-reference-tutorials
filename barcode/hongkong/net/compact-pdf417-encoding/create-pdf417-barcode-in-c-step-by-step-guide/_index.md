---
category: general
date: 2026-10-04
description: 快速在 C# 中建立 PDF417 條碼。了解如何產生 PDF417 條碼以及如何使用 Aspose.Barcode 將條碼圖像儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode c#
- barcode for mobile scanning
- aspose barcode png generation
lastmod: 2026-10-04
og_description: 使用 Aspose.Barcode 在 C# 中建立 PDF417 條碼。本教學示範如何產生緊湊的 PDF417 條碼、設定外觀，並將其儲存為
  PNG 圖像，以供行動掃描或標籤列印使用。
og_image_alt: 'Developer guide: Create PDF417 barcode in C# and save as PNG using
  Aspose.Barcode'
og_title: 在 C# 中建立 PDF417 條碼 – 完整步驟式指南
schemas:
- author: Aspose
  dateModified: '2026-10-04'
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
- Aspose.Barcode
title: 在 C# 中建立 PDF417 條碼 – 步驟式指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立 PDF417 條碼 – 步驟指南

如果您需要在 .NET 應用程式中**建立 PDF417 條碼**，本指南會精確說明如何產生 PDF417 條碼以及如何將條碼影像儲存為 PNG 檔案。最終您會得到一個適合行動掃描、票務系統或標籤印表機的緊湊影像。

## 快速答案
- **哪個函式庫負責 PDF417 產生？** Aspose.Barcode for .NET.  
- **範例儲存為何種格式？** PNG，使用 `BarCodeImageFormat.Png`.  
- **需要多少行程式碼？** 約 10 行（設定專案後）。  
- **我可以自訂大小與截斷嗎？** 可以 – `Columns`、`Rows` 與 `Truncate` 屬性。  
- **此程式碼相容 .NET‑6 嗎？** 完全相容，亦可在 .NET Framework 4.7+ 上執行。

## 在 C# 中建立 PDF417 條碼需要什麼？
首先，您需要最新的 .NET SDK、如 Visual Studio 2022 的 IDE，以及 **Aspose.Barcode for .NET** NuGet 套件。這些工具可讓範例在不需額外設定的情況下編譯與執行。

- .NET 6.0 SDK 或更新版本（亦可在 .NET Framework 4.7+ 上執行）
- Visual Studio 2022 或任何相容 C# 的編輯器
- 具備網際網路連線以下載 Aspose.Barcode NuGet 套件

## 如何設定 .NET 專案以產生 PDF417 條碼？
建立一個新的主控台專案，加入 Aspose.Barcode 套件，並開啟產生的 `Program.cs`。這會建立一個乾淨的工作區，讓您可以實例化條碼產生器並寫入輸出檔案。

```bash
   dotnet new console -n Pdf417Demo
   cd Pdf417Demo
   ```

## 如何使用 Aspose.Barcode 產生 PDF417 條碼？
`BarcodeGenerator` 是 Aspose.Barcode 的類別，用於根據提供的資料與符號產生條碼影像。您需要指定 PDF417 符號，提供要編碼的文字，並可選擇調整大小或錯誤更正設定。

```bash
   dotnet add package Aspose.Barcode
   ```

### 為何這很重要
* **EncodeTypes.Pdf417** 告訴函式庫使用 PDF417 標準，支援大量資料負載與錯誤更正。  
* 提供 Unicode 字元可證明產生器在無需額外設定的情況下處理非 ASCII 輸入。

## 如何設定 PDF417 條碼的外觀？
您可以控制模組大小、欄位數量，以及條碼是否使用緊湊（截斷）模式。這些設定會直接影響小螢幕上的可讀性以及 PNG 影像的整體檔案大小。

`generator.Parameters.Barcode.XDimension` 設定單一模組的寬度，而 `Columns` 與 `Rows` 定義矩陣的尺寸。將 `Truncate` 設為 `true` 會移除靜止區，以產生更緊湊的影像。

```csharp
   using System;
   using Aspose.Barcode.Generation;
   using Aspose.Barcode;
   ```

### 實用技巧
如果水平空間受限需要較高的條碼，可增加 `Columns`。將 `Truncate` 設為 `true` 會透過移除靜止區降低整體高度，非常適合行動螢幕。

## 如何將條碼影像儲存為 PNG？
`Save` 是 `BarcodeGenerator` 的方法，用於將產生的影像寫入檔案。傳入檔案路徑與 `BarCodeImageFormat.Png` 即可一步完成 PNG 影像的建立。

```csharp
// Step 1: Initialise the generator with PDF417 symbology and sample text.
// The text includes Unicode characters to demonstrate full‑range support.
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

### 預期結果
執行程式會在專案資料夾中產生 `CompactPdf417.png`。開啟該檔案會看到一個緊湊的 PDF417 條碼，編碼字串 *Åspóse.Barcóde©*。此影像可嵌入 HTML、PDF 報告，或列印於標籤上。

## 如何驗證產生的條碼檔案？
程式執行完畢後，您可以使用簡單指令確認檔案是否存在。此檢查可驗證產生與儲存步驟已順利完成且無錯誤。

```csharp
// Step 2: Set the module (X) dimension – each barcode element will be 2 pixels wide.
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 3: Configure PDF417‑specific options.
generator.Parameters.Barcode.Pdf417.Columns = 3;      // Number of columns (affects height)
generator.Parameters.Barcode.Pdf417.Truncate = true; // Enable compact mode
```

如果檔案出現，**建立 PDF417 條碼**的流程即成功。

## 產生 PDF417 條碼時常見的變化與例外情況有哪些？
不同情境可能需要調整產生器設定。以下是快速參考表，說明如何處理常見的變化。

| 情況 | 調整 |
|-----------|------------|
| **較長的資料字串** | 增加 `Columns` 或設定 `Rows` 以容納更多碼字。 |
| **不同的影像格式** | 將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`。 |
| **較高的解析度** | 在 `Save` 前設定 `generator.Parameters.ImageResolution`。 |
| **背景顏色** | 使用 `generator.Parameters.Barcode.ImageBackgroundColor = Color.White;`。 |
| **例外處理** | 將 `generator.Save` 包在 `try/catch` 區塊中，以捕捉 I/O 錯誤。 |

這些變化讓您能針對特定裝置或品牌需求自訂條碼。

## 建立條碼後的下一步是什麼？
既然您已能產生並儲存 PDF417 條碼，接下來可以探索相關功能，例如產生 QR Code、將條碼嵌入 PDF 文件，或自訂顏色以符合品牌。上述皆使用相同的 `BarcodeGenerator` API，您可以輕鬆擴充範例。

## 相關指南
- [如何使用 Aspose.BarCode 建立條碼 – 緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

## 常見問題

**問：我可以在 Web 應用程式中使用此程式碼嗎？**  
**答：** 可以。相同的 `BarcodeGenerator` 類別可在 ASP.NET、MVC 或 Blazor 專案中使用；只需確保伺服器對輸出資料夾具有寫入權限。

**問：Aspose.Barcode 支援其他 2‑D 符號嗎？**  
**答：** 當然。支援超過 30 種 2‑D 條碼類型，包括 QR、DataMatrix 與 Aztec。

**問：我能建立多大的條碼？**  
**答：** PDF417 在單一符號中可編碼最多 1,850 個字元；您也可以透過調整 `Rows` 與 `Columns` 將資料分散至多列。

**問：商業使用是否需要授權？**  
**答：** 需要。提供免費試用供評估，但部署時必須購買商業授權。

**問：相容的 .NET 版本有哪些？**  
**答：** Aspose.Barcode 支援 .NET Framework 4.5+、.NET Core 3.1+ 以及 .NET 5/6/7。

---

**最後更新：** 2026-10-04  
**測試環境：** Aspose.Barcode 24.11 for .NET  
**作者：** Aspose  

```csharp
// Step 4: Save the generated barcode as a PNG image.
string outputPath = @"./CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```
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
```bash
dotnet run && ls -l CompactPdf417.png
```

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}