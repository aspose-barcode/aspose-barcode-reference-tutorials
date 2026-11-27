---
category: general
date: 2026-11-27
description: 使用 C# 建立條碼圖像，並以 PNG 格式儲存 – Aspose.BarCode 步驟指南.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: zh-hant
lastmod: 2026-11-27
og_description: 使用 Aspose.BarCode 在 C# 中建立條碼圖像，並以 PNG 格式儲存圖像。請跟隨本教學逐步生成 Macro PDF417
  條碼。
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: 在 C# 中建立條碼圖像並儲存為 PNG 格式 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 在 C# 中建立條碼圖像並儲存為 PNG 格式
url: /zh-hant/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立條碼圖像並儲存為 PNG 格式

如果您需要在 .NET 應用程式中**建立條碼圖像**，本指南將示範如何使用 Aspose.BarCode 產生 Macro PDF417 條碼並**儲存為 PNG 格式**。您將獲得完整、可執行的範例，以及每個設定的說明，讓您能將程式碼套用到自己的需求。

產生條碼不只是呼叫單一方法；您必須設定模組大小、宏參數以及輸出格式。完成本教學後，您將了解每個屬性的意義、如何處理常見的邊緣情況，以及如何驗證 PNG 檔案是否正確寫入。

## 您需要的環境

- .NET 6.0 或更新版本（程式碼亦可於 .NET Framework 4.6+ 執行）
- Aspose.BarCode for .NET（可透過 NuGet 取得：`Install-Package Aspose.BarCode`）
- 如 Visual Studio 2022 或 Visual Studio Code 等 IDE
- 具寫入權限的資料夾，以儲存 PNG 檔案

## 步驟 1：初始化條碼產生器

第一步是建立 `BarcodeGenerator` 實例，指定 `EncodeTypes.MacroPdf417` 符號系統以及您想要編碼的文字。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**為什麼這很重要：**  
`EncodeTypes.MacroPdf417` 告訴函式庫使用 PDF417 的宏變體，支援檔案分段與額外的中繼資料。建構子同時接受將被編碼進條碼的人類可讀文字。

## 步驟 2：定義模組大小（X‑dimension）

X‑dimension 控制單一條碼模組（最小的黑白單元）的寬度。`2` 像素的值在螢幕顯示的 PNG 中表現良好。

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**實用提示：**  
若您計畫列印條碼，請將像素值提升（例如 `4` 或 `5`），以避免在低解析度印表機上產生模糊的輸出。

## 步驟 3：設定 PDF417 宏參數

Macro PDF417 會加入多個可選欄位，協助辨識來源檔案、段落順序與完整性檢查。以下是一組常見的完整參數；您可自行省略不需要的欄位。

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**為什麼這些欄位有用：**  

| 參數 | 用途 |
|-----------|---------|
| `Columns` | 控制條碼寬度；列數較少會產生較高的條碼。 |
| `MacroPdf417FileID` | 將所有段落連結在一起的唯一識別碼。 |
| `MacroPdf417SegmentID` | 此段在整個檔案中的位置。 |
| `MacroPdf417SegmentsCount` | 段落總數；重建時必需。 |
| `MacroPdf417FileName` | 可由掃描應用程式顯示的可讀檔名。 |
| `MacroPdf417Checksum` | 協助接收端驗證資料完整性（CCITT‑16）。 |
| `MacroPdf417FileSize` | 原始檔案的可選大小提示。 |
| `MacroPdf417TimeStamp` | 原始檔案建立的時間戳記。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 用於路由或所有權的中繼資料。 |
| `MacroPdf417Terminator` | 指示此段是否為最後段（`Set`）或中間段（`Unset`）。 |

**邊緣情況：** 若您產生單段條碼，請將 `MacroPdf417SegmentsCount` 設為 `1`，且 `MacroPdf417Terminator` 設為 `Unset`。函式庫會自動省略不適用的段落相關欄位。

## 步驟 4：將產生的條碼儲存為 PNG 圖像

最後，呼叫 `Save` 並傳入檔案路徑與 `BarCodeImageFormat.Png` 列舉值。此方法會以無損的 PNG 格式將圖像寫入磁碟。

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**為什麼選擇 PNG？**  
PNG 能保留精確的像素值，對依賴高對比度的條碼掃描器而言至關重要。JPEG 壓縮可能產生破壞條碼圖樣的雜訊。

### 驗證輸出

程式執行完畢後，您應該會在執行目錄看到名為 `ExtPDF417Meta.png` 的檔案。以任何圖像檢視器開啟，即可看到密集的矩形條碼。您可以使用支援 PDF417 宏的手機條碼讀取器掃描圖像，通常會顯示嵌入的中繼資料（檔案 ID、段落編號等）。

## 常見陷阱與避免方法

| 症狀 | 可能原因 | 解決方法 |
|---------|--------------|-----|
| 條碼顯示模糊 | X‑dimension 對所選 DPI 太低 | 增加 `XDimension.Pixels` 或以較高 DPI（`generator.Parameters.ImageResolution`）渲染。 |
| 掃描器回報「checksum error」 | `MacroPdf417Checksum` 值不正確 | 省略此屬性讓 Aspose 自動計算校驗碼，或確保值符合 CCITT‑16 演算法。 |
| PNG 檔案為空或未建立 | 輸出路徑無效或缺乏寫入權限 | 使用 `Path.Combine` 結合已知可寫入的資料夾（例如 `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`）。 |
| 宏欄位被忽略 | `EncodeTypes` 設為普通 `Pdf417` 而非 `MacroPdf417` | 確認建構子使用 `EncodeTypes.MacroPdf417`。 |

## 完整、可執行的範例

以下是可直接貼入主控台應用程式的完整程式碼。使用 .NET 6.0 編譯，即可產生前述的 PNG 檔案。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**預期輸出（主控台）：**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

開啟 `ExtPDF417Meta.png` 後，即可看到清晰的 Macro PDF417 條碼，隨時可供掃描。

## 後續步驟

- **變更圖像格式** – 若需要其他檔案類型，可將 `BarCodeImageFormat.Png` 替換為 `Jpeg` 或 `Bmp`。請記得 JPEG 會產生壓縮雜訊，可能影響掃描可靠性。  
- **調整解析度** – 使用  

## 接下來該學什麼？

以下教學與本指南緊密相關，能幫助您進一步掌握 API 功能並探索其他實作方式。

- [如何在 C# 中使用 Aspose.Barcode 建立條碼圖像](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [如何在 C# 中使用 Macro PDF417 選項建立 PDF417 條碼圖像](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [如何使用 C# 與 Aspose.BarCode 從圖像讀取條碼 – 步驟說明指南](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}