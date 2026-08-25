---
category: general
date: 2026-08-25
description: 使用 Aspose.BarCode 在 C# 中建立 PDF417 條碼。本教學說明如何快速產生 PDF417 條碼，並提供清晰的程式碼範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode
- how to generate pdf417 barcode
- create barcode with aspose
language: zh-hant
lastmod: 2026-08-25
og_description: 使用 Aspose.BarCode 在 C# 中建立 PDF417 條碼。了解如何透過完整且可執行的範例產生 PDF417 條碼。
og_image_alt: Screenshot of a generated PDF417 barcode created with Aspose.BarCode
og_title: 使用 Aspose.BarCode 建立 PDF417 條碼 – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create PDF417 barcode using Aspose.BarCode in C#. This tutorial explains
    how to generate PDF417 barcode quickly with clear code examples.
  headline: Create PDF417 barcode with Aspose.BarCode – step-by-step guide
  type: TechArticle
tags:
- Aspose.BarCode
- PDF417
- C#
title: 使用 Aspose.BarCode 建立 PDF417 條碼 – 步驟指南
url: /zh-hant/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-barcode-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 建立 PDF417 條碼 – 步驟教學

如果您需要在 .NET 應用程式中 **建立 PDF417 條碼**，本教學將示範如何使用 Aspose.BarCode 產生 PDF417 條碼。您將看到完整、可直接執行的範例，了解每個設定的意義，並學會如何依不同情境調整程式碼。

本教學涵蓋：

* 將 Aspose.BarCode 套件加入專案  
* 設定條碼產生器（文字、X‑dimension、欄位）  
* 將條碼儲存為 PNG 檔案  
* 處理 Unicode 字元與常見陷阱  

不需要額外文件——以下內容已完整提供。

## 前置條件

開始之前，請確保您具備：

* .NET 6.0 SDK 或更新版本（此程式碼亦可於 .NET Framework 4.7+ 執行）  
* 最新版 **Aspose.BarCode for .NET** NuGet 套件  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* 任意您慣用的 IDE 或編輯器（Visual Studio、VS Code、Rider 等）

## 步驟 1：建立專案並匯入命名空間

建立一個新的 Console 專案，並匯入所需的 Aspose.BarCode 命名空間。

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
            // The full barcode generation logic starts here.
```

*`Aspose.BarCode`* 包含核心類別，而 *`Aspose.BarCode.Generation`* 提供用於產生條碼的 `BarcodeGenerator`。

## 步驟 2：以欲編碼的文字建立 PDF417 條碼產生器

第一行會為 PDF417 符號建立 `BarcodeGenerator`，並將您要編碼的資料傳入。

```csharp
            // Step 2: Create a PDF417 barcode generator with the desired text
            // Unicode characters such as Å, ó, and © are supported out of the box.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**為什麼這很重要：**  
PDF417 最多可儲存 1 850 個字元，適合用於文件、票證或身分證等。直接將文字傳入建構子，可確保資料在套用任何視覺設定前已正確編碼。

## 步驟 3：設定視覺參數（X‑dimension 與欄位）

微調外觀可提升掃描可靠度，並符合版面需求。

```csharp
            // Step 3: Set the X‑dimension (module width) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Step 4: Define the number of columns for the PDF417 barcode
            // Fewer columns produce a taller barcode; more columns make it wider.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
```

* **X‑dimension** – 控制單一條碼模組的寬度。`2` 像素的設定在大多數螢幕上兼具可讀性與檔案大小的平衡。  
* **Columns** – 決定條碼的資料欄位數量。請依據資料量與目標媒介的可用空間調整此值。

## 步驟 4：儲存條碼影像

選擇符合後續工作流程的影像格式。PNG 為無損品質，適合進一步處理或列印。

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

`Save` 方法會將影像寫入指定路徑。若需其他格式（JPEG、BMP、SVG），只要將 `BarCodeImageFormat.Png` 替換為對應的列舉值即可。

## 完整、可執行的範例

將下方整段程式碼貼入新 Console 專案的 `Program.cs`，執行 `dotnet run`，即可在專案資料夾中看到 `Pdf417Basic.png`。

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
            // Create a PDF417 barcode generator with Unicode text
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Adjust visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // Save as PNG
            string outputPath = "Pdf417Basic.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### 預期輸出

執行程式後會產生如下圖所示的 PNG 檔案。

![Create PDF417 barcode example](https://example.com/images/pdf417-sample.png "Create PDF417 barcode example")

*圖中顯示一個清晰的 PDF417 條碼，具備三個欄位且模組寬度為 2 px。*

## 如何以自訂資料長度產生 PDF417 條碼

若資料量超過預設容量，可能需要調整其他參數：

| 參數 | 推薦設定 | 原因 |
|-----------|--------------------|--------|
| `Pdf417.Rows` | `0` (auto) | 讓 Aspose 自行計算最佳列數。 |
| `Pdf417.ErrorLevel` | `2` (default) | 較高的等級會增加冗餘，提高受損媒介的掃描可靠度。 |
| `Pdf417.SecurityLevel` | `0`–`8` | 僅在需要超出預設的錯誤更正時使用。 |

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 0;          // Auto‑calculate rows
generator.Parameters.Barcode.Pdf417.ErrorLevel = 2;   // Standard error correction
generator.Parameters.Barcode.Pdf417.SecurityLevel = 5; // Optional extra security
```

**小技巧：** 請務必使用目標掃描器實機測試產生的條碼。較高的錯誤等級會使影像變大，可能影響版面限制。

## 常見陷阱與避免方法

| 問題 | 成因 | 解決方式 |
|-------|-------|-----|
| 條碼顯示模糊 | 以低解析度 PNG 儲存 | 增加 `XDimension.Pixels` 或匯出為 SVG (`BarCodeImageFormat.Svg`) |
| 字元被替換成 � | 輸入字串未以 UTF‑8 編碼 | 確認來源檔案已以 UTF‑8 編碼儲存（大多數 IDE 預設即為此） |
| 掃描器無法讀取條碼 | 欄位數量不足以容納資料量 | 增加 `Pdf417.Columns` 或省略此設定讓 Aspose 自動決定欄位數 |

## 使用 Aspose 建立其他類型條碼 – 超出 PDF417

Aspose.BarCode 支援多種符號（QR、Code128、DataMatrix 等）。只要更改 `EncodeTypes` 列舉，即可切換至其他類型：

```csharp
BarcodeGenerator qrGenerator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
qrGenerator.Save("QRCode.png", BarCodeImageFormat.Png);
```

此範例展示 **create barcode with Aspose** 的通用模式：以欲使用的 `EncodeTypes` 值實例化 `BarcodeGenerator`、設定參數，最後呼叫 `Save`。

## 結論

您現在已掌握如何在 C# 中使用 Aspose.BarCode **建立 PDF417 條碼**，從專案設定、視覺參數微調到 Unicode 資料處理。完整、可執行的範例可依需求調整為更大資料集、不同影像格式或其他符號。

接下來可以探索的方向：

* **如何在 Web API (ASP.NET Core) 中產生 PDF417 條碼** – 適合即時產生需求。  
* 使用 Aspose.PDF 將條碼嵌入 PDF 文件。  
* 使用 `Pdf417.Rows` 與 `Pdf417.ErrorLevel` 以符合特定掃描標準。

歡迎自行嘗試不同的欄位數、X‑dimension 值與輸出格式，以配合您的實際使用情境。祝開發順利！

## 接下來該學什麼？

以下教學與本篇內容密切相關，能進一步深化您在本指南中學到的技巧。每篇資源皆提供完整可執行的程式碼範例與步驟說明，協助您掌握更多 API 功能，並探索在專案中的其他實作方式。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}