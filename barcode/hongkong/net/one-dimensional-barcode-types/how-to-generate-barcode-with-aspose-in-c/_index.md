---
category: general
date: 2026-09-19
description: 如何在 C# 中使用 Aspose 產生條碼 – 一個快速且可靠的逐步指南，教您快速、穩妥地建立條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create barcode with aspose
language: zh-hant
lastmod: 2026-09-19
og_description: 如何在 C# 中使用 Aspose 產生條碼。請參考本指南，使用 Aspose 建立條碼、設定 MacroPdf417，並儲存為 PNG。
og_image_alt: Screenshot showing a MacroPdf417 barcode generated with Aspose in C#
og_title: 如何使用 Aspose 生成條碼 – 完整 C# 指南
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  headline: How to generate barcode with Aspose in C#
  type: TechArticle
- description: How to generate barcode using Aspose in C# – a step‑by‑step guide to
    create barcode with Aspose quickly and reliably.
  name: How to generate barcode with Aspose in C#
  steps:
  - name: What if I need a different image format?
    text: Aspose supports `BarCodeImageFormat.Jpeg`, `Bmp`, `Tiff`, `Svg`, and `Pdf`.
      Just replace `BarCodeImageFormat.Png` with the desired enum value.
  - name: How do I generate multiple segments automatically?
    text: You can place the code above inside a loop, incrementing `MacroPdf417SegmentID`
      on each iteration and updating the data string. Remember to keep `MacroPdf417SegmentsCount`
      constant across all segments.
  - name: What if the data exceeds the capacity of a single MacroPdf417 symbol?
    text: MacroPdf417 is designed for large payloads, but every barcode has a theoretical
      maximum (≈ 1.1 KB per segment). Split the source file into chunks that fit this
      limit, then encode each chunk as a separate segment.
  - name: Does the checksum need to be calculated manually?
    text: Aspose can generate the CCITT‑16 checksum automatically if you set `MacroPdf417Checksum`
      to `0`. In the example we supplied a hard‑coded value for illustration; in production
      code you’d typically let the library compute it.
  - name: How can I change the barcode’s foreground/background colors?
    text: 'Use the `BarColor` and `BackColor` properties:'
  type: HowTo
tags:
- barcode
- Aspose
- C#
- .NET
title: 如何在 C# 中使用 Aspose 生成條碼
url: /zh-hant/net/one-dimensional-barcode-types/how-to-generate-barcode-with-aspose-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose 產生條碼

在 C# 中產生條碼非常簡單，只要使用 Aspose.BarCode 函式庫。本教學將逐步說明如何 **使用 Aspose 建立條碼**，涵蓋 MacroPdf417 格式、常見外觀設定，以及如何將結果儲存為 PNG 圖片。

您將學會：

* 安裝與參考 Aspose.BarCode for .NET  
* 設定 MacroPdf417 專屬屬性，例如檔案 ID、段落 ID 與檢查碼  
* 調整視覺選項，如 X‑dimension 與欄位數量  
* 將條碼匯出為影像檔  

不需要任何 Aspose 的先前經驗——只要具備 C# 與 Visual Studio 的基本概念即可。

## 前置條件

在開始之前，請確保您已具備以下條件：

| 需求 | 細節 |
|-------------|--------|
| .NET runtime | .NET 6.0 or later (the code also works with .NET Framework 4.7+) |
| IDE | Visual Studio 2022, Rider, or any editor that supports C# |
| Aspose.BarCode | NuGet package `Aspose.BarCode` (free trial or licensed version) |
| Basic C# knowledge | Familiarity with `using` statements and object initialization |

您可以透過 NuGet 套件管理員將 Aspose.BarCode 加入專案：

```bash
dotnet add package Aspose.BarCode
```

## 如何在 C# 中產生條碼 – 整體工作流程

此流程包含四個邏輯步驟：

1. **建立 `BarcodeGenerator` 實例**，指定所需的編碼類型（MacroPdf417）以及要編碼的文字。  
2. **設定常見外觀選項**，例如 X‑dimension 與欄位數量。  
3. **設定 MacroPdf417 專屬屬性**，如檔案 ID、段落 ID 與時間戳記。  
4. **將條碼儲存**為您選擇的檔案格式（本例為 PNG）。

以下將逐步說明每個步驟的細節。

## 步驟 1：為 MacroPdf417 建立條碼產生器

`BarcodeGenerator` 類別是所有條碼產生任務的入口點。建立實例時，需要傳入兩個參數：

* `EncodeTypes.MacroPdf417` – 告訴 Aspose 使用 MacroPdf417 符號。  
* 資料字串 – 將被編碼至條碼內的文字。  

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – instantiate the generator with MacroPdf417 and sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Subsequent steps go here
            }
        }
    }
}
```

> **為何重要：** MacroPdf417 是一種二維條碼，能攜帶大量資料，且支援檔案分段等宏功能，適用於將大型檔案分段傳輸。

## 步驟 2：設定條碼的常見外觀選項

即使 MacroPdf417 有許多專屬設定，您仍然需要控制視覺密度與版面。最常用的參數包括：

* **X‑dimension** – 最小模組（像素）的寬度。較小的值會產生更密集的圖像。  
* **Columns** – 每列的資料欄位數量；較大的數值會降低條碼的高度。  

```csharp
// Step 2 – adjust appearance
generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel modules
generator.Parameters.Barcode.Pdf417.Columns = 5;    // 5 columns per row
```

> **提示：** 在大多數螢幕顯示情境下，將 `XDimension` 保持在 2 到 4 像素之間。較大的值可提升低解析度印表機的可讀性，但會增加整體圖像大小。

## 步驟 3：設定 MacroPdf417 專屬屬性

MacroPdf417 增加了一組中繼資料欄位，讓您能將大型檔案分割成多個條碼段。以下屬性通常是必需的：

| 屬性 | 用途 |
|----------|---------|
| `MacroPdf417FileID` | 整個檔案的唯一識別碼（最多 8 位數）。 |
| `MacroPdf417SegmentID` | 目前段落的索引（從 0 開始）。 |
| `MacroPdf417SegmentsCount` | 檔案的總段落數。 |
| `MacroPdf417FileName` | 原始檔案的可讀名稱。 |
| `MacroPdf417Checksum` | 可選的 CCITT‑16 檢查碼，用於錯誤偵測。 |
| `MacroPdf417FileSize` | 原始檔案的位元組大小。 |
| `MacroPdf417TimeStamp` | 檔案產生的時間戳記。 |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | 可選的字串，用於識別收件人/寄件人。 |
| `MacroPdf417Terminator` | 決定條碼是否為最後一段（`Set`）或中間段（`Unset`）。 |

```csharp
// Step 3 – set macro‑specific data
generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example
generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // in bytes
generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

> **為何這些欄位有用：**  
> *當您需要透過低頻寬通道傳送大型文件時，可將文件分割成多個 MacroPdf417 條碼。接收端會依據每個段落的中繼資料重建原始檔案。*

## 步驟 4：將產生的條碼儲存為影像

Aspose 支援多種輸出格式：PNG、JPEG、BMP、TIFF、SVG 與 PDF。PNG 為無損格式，適合用於網頁或 UI 顯示。

```csharp
// Step 4 – export the barcode
string outputPath = @"C:\Barcodes\MacroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

執行程式後，您會在目錄中看到一個 PNG 檔案，其外觀類似下圖所示。

![使用 Aspose 在 C# 產生的 MacroPdf417 條碼](placeholder-image.png){.img-fluid alt="如何使用 Aspose 在 C# 產生條碼"}

> **預期輸出：** 一個 300 × 150 像素的 PNG，顯示編碼文字 “Sample” 以及您提供的 MacroPdf417 中繼資料的條碼。

## 完整、可執行範例

將上述所有步驟整合起來，以下是您可以直接複製、貼上並執行的完整程式碼：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create the generator for MacroPdf417
            using (BarcodeGenerator generator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Sample"))
            {
                // Appearance settings
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // MacroPdf417 specific data
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputPath = @"C:\Barcodes\MacroPdf417.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

使用 `dotnet run` 執行程式（或在 Visual Studio 按 **F5**）。執行完畢後，請確認 PNG 檔案已產生且能正常開啟。

## 常見問題與特殊情況處理

### 如果需要不同的影像格式該怎麼辦？

Aspose 支援 `BarCodeImageFormat.Jpeg`、`Bmp`、`Tiff`、`Svg` 與 `Pdf`。只需將 `BarCodeImageFormat.Png` 替換為您想要的列舉值即可。

### 如何自動產生多個段落？

您可以將上述程式碼放入迴圈中，在每次迭代時遞增 `MacroPdf417SegmentID` 並更新資料字串。請記得在所有段落中保持 `MacroPdf417SegmentsCount` 為相同值。

### 如果資料超過單一 MacroPdf417 符號的容量該怎麼辦？

MacroPdf417 為大量資料設計，但每個條碼仍有理論上的最大容量（約每段 1.1 KB）。請將來源檔案切割成符合此限制的區塊，然後將每個區塊編碼為獨立的段落。

### 是否需要手動計算檢查碼？

Aspose 能在將 `MacroPdf417Checksum` 設為 `0` 時自動產生 CCITT‑16 檢查碼。範例中為說明起見使用了硬編碼值；在正式程式碼中通常會讓函式庫自行計算。

### 如何變更條碼的前景/背景顏色？

使用 `BarColor` 與 `BackColor` 屬性：

```csharp
generator.Parameters.Barcode.BarColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

## 結論

現在您已了解如何在 C# 使用 Aspose.BarCode **產生條碼**，以及如何為 MacroPdf417 符號 **使用 Aspose 建立條碼**。本教學涵蓋了安裝、外觀設定與宏專屬欄位的配置。

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟說明指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [如何在 C# 使用 Aspose 產生 PDF417 條碼影像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}