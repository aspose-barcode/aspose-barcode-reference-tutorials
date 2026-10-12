---
category: general
date: 2026-09-19
description: 如何在 C# 中生成條碼（逐步教學）。學習自訂 PDF417 條碼設定，並建立可即時使用的條碼圖像，供 C# 開發者使用。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- customize pdf417 barcode
- create barcode image c#
language: zh-hant
lastmod: 2026-09-19
og_description: 如何在 C# 中產生條碼，提供詳細說明。自訂 PDF417 條碼參數，並建立 C# 專案今天即可使用的條碼影像。
og_image_alt: Screenshot of a generated MicroPDF417 barcode image created with C#
  code
og_title: 如何在 C# 中生成條碼並自訂 PDF417 條碼
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  headline: How to generate barcode and customize PDF417 barcode in C#
  type: TechArticle
- description: How to generate barcode in C# with a step‑by‑step guide. Learn to customize
    PDF417 barcode settings and create a barcode image C# developers can use instantly.
  name: How to generate barcode and customize PDF417 barcode in C#
  steps:
  - name: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
    text: Check that the X‑dimension is not set below 1 pixel (some scanners cannot
      resolve sub‑pixel modules).
  - name: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
    text: Ensure the output file is not corrupted—re‑run the program and compare file
      sizes.
  - name: Increase `ErrorLevel` to improve tolerance.
    text: Increase `ErrorLevel` to improve tolerance.
  type: HowTo
tags:
- barcode
- C#
- pdf417
title: 如何在 C# 中產生條碼並自訂 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-barcode-and-customize-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生條碼並自訂 PDF417 條碼

如果您需要 **如何產生條碼** 在 .NET 應用程式中，本教學提供完整、可直接執行的解決方案。您將學會如何自訂 PDF417 條碼尺寸、選擇欄位數量，最後 **建立條碼影像 C#** 專案可直接嵌入。

產生條碼不需要複雜的建置流程。完成本指南後，您將得到一個 PNG 檔案，內含符合您精確尺寸與解析度需求的 MicroPDF417 條碼。

## 前置條件

開始之前，請先安裝以下項目：

* .NET 6.0 SDK 或更新版本（此程式碼亦支援 .NET Framework 4.6 以上）
* Visual Studio 2022（或您偏好的 C# 編輯器）
* Aspose.BarCode for .NET NuGet 套件 – 以以下指令安裝  
  `dotnet add package Aspose.BarCode`

不需要其他外部工具。

## 第 1 步：建立專案並匯入命名空間

建立一個新的 console 專案，並加入 Aspose.BarCode 參考。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

開啟 `Program.cs`，加入必要的 `using` 指令：

```csharp
using System;
using Aspose.BarCode.Generation;   // Provides BarcodeGenerator and EncodeTypes
using Aspose.BarCode;               // Contains BarCodeImageFormat enum
```

這些命名空間提供讓您 **如何產生條碼** 並控制 PDF417‑專屬選項的類別。

## 第 2 步：以欲編碼的文字初始化 MicroPDF417 產生器

第一行會建立一個針對 MicroPDF417 符號的 `BarcodeGenerator` 實例。建構子接受編碼類型與您想要編碼的資料字串。

```csharp
// Step 2: Create a MicroPDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");
```

**為什麼重要：** MicroPDF417 是完整 PDF417 標準的緊湊變體，適合小標籤或行動裝置螢幕。以正確的 `EncodeTypes` 初始化產生器，可確保函式庫使用正確的編碼演算法。

## 第 3 步：自訂 X‑dimension（模組寬度）以獲得更細緻的解析度

X‑dimension 控制單一條碼模組（最小的黑條或白條）的寬度。將其設定為較低的像素值即可產生較高解析度的影像。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels for finer resolution
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼重要：** 較大的 X‑dimension 讓低解析度掃描器較易讀取條碼；較小的數值則能在有限空間內容納更多資料。請依掃描環境調整此數值。

## 第 4 步：定義欄位數以控制條碼大小

MicroPDF417 支援 1‑4 欄。欄位越多，條碼越短且寬；欄位越少，條碼則較高且窄。

```csharp
// Step 4: Define the number of columns (1‑4 are allowed) to control barcode size
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**為什麼重要：** 正確的欄位數讓您能在特定 UI 元件或印刷標籤內放入條碼，而不必手動縮放。

## 第 5 步：將條碼儲存為 PNG 影像

最後，將產生的條碼寫入磁碟。PNG 具備無損品質，對於清晰掃描相當重要。

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\MicroPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

若目標目錄不存在，`Save` 方法會拋出 `ArgumentException`。您可以使用簡單的檢查來避免此情況：

```csharp
if (!System.IO.Directory.Exists(@"C:\Barcodes"))
{
    System.IO.Directory.CreateDirectory(@"C:\Barcodes");
}
```

### 完整原始碼

將上述片段組合起來，即為完整、可執行的程式：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample");

            // 2️⃣ Set the X‑dimension (module width) in pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns (1‑4 are allowed) to control barcode size
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Ensure the output folder exists
            string folder = @"C:\Barcodes";
            if (!System.IO.Directory.Exists(folder))
                System.IO.Directory.CreateDirectory(folder);

            // 4️⃣ Save the generated barcode as a PNG image
            string outputPath = System.IO.Path.Combine(folder, "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

執行此程式後會產生名為 **MicroPdf417.png** 的檔案，外觀如下圖（此處省略螢幕截圖）。條碼編碼文字 *Sample*，並遵循您先前設定的 X‑dimension 與欄位參數。

## 自訂其他 PDF417 參數

本指南聚焦於 **自訂 pdf417 條碼** 之尺寸參數，Aspose.BarCode 亦提供許多額外設定供您使用：

| 屬性 | 目的 | 常見值 |
|----------|---------|----------------|
| `generator.Parameters.Barcode.Pdf417.Rows` | 控制列數（高度） | 3‑30 |
| `generator.Parameters.Barcode.Pdf417.ErrorLevel` | 設定錯誤更正等級（等級越高容錯越高） | 0‑8 |
| `generator.Parameters.Barcode.Pdf417.Truncated` | 產生截斷條碼（無停止圖樣） | `true`/`false` |
| `generator.Parameters.Barcode.Pdf417.CompactionMode` | 選擇數字、文字或位元組壓縮模式 | `CompactionModes.Numeric` 等 |

**專業提示：** 當您需要條碼符合固定寬度時，可先增加 `Columns` 並降低 `XDimension`。若掃描器回報遺漏符號，提升 `ErrorLevel` 以增強冗餘度。

## 處理例外情況

* **文字過長超出 MicroPDF417 限制：** Micro 變體最多支援 1 KB 資料。若字串超過此上限，請改用完整的 `Pdf417` 符號，將 `EncodeTypes.MicroPdf417` 改為 `EncodeTypes.Pdf417`。
* **不支援的影像格式：** `BarCodeImageFormat` 亦支援 `Jpeg`、`Bmp` 與 `Gif`。請選擇符合下游處理流程的格式。
* **跨平台路徑問題：** 針對 Linux 或 macOS，請使用 `Path.Combine` 取代硬編碼的反斜線。

## 驗證條碼

您可以使用任何標準條碼掃描應用程式（行動或桌面）驗證產生的影像。掃描器應回傳原始文字 **Sample**。若驗證失敗：

1. 確認 X‑dimension 未設定低於 1 像素（部分掃描器無法解析次像素模組）。
2. 確認輸出檔案未損毀——重新執行程式並比較檔案大小。
3. 提升 `ErrorLevel` 以改善容錯能力。

## 結論

您現在已掌握 **如何在 C# 中產生條碼**，以及 **自訂 pdf417 條碼** 的尺寸與欄位數，並能 **建立條碼影像 C#** 讓專案直接嵌入。完整範例示範了從專案設定到最終 PNG 輸出的實務工作流程。

接下來，您可以透過切換 `EncodeTypes` 列舉值，探索 QR、Code128 或 DataMatrix 等其他符號。調整 `Resolution`、`Margin` 等額外參數，即可為您的特定應用微調每一條條碼。

祝開發順利，讓條碼為您的下一個自動化專案注入動能！

## 接下來該學什麼？

以下教學與本指南所示技術緊密相關，提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [How to Generate PDF417 Barcode Image in C# with Aspose](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [How to Save Barcode in C# – Generate PDF417 Barcodes](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}