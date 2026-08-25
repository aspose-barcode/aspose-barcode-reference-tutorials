---
category: general
date: 2026-08-25
description: 學習如何在 C# 中使用條碼產生器 C# PDF417 函式庫產生 PDF417 條碼——一步一步的程式碼範例。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode
- barcode generator C# PDF417
- PDF417 barcode C#
- barcode resolution C#
- Aspose.BarCode PDF417
language: zh-hant
lastmod: 2026-08-25
og_description: 使用 C# PDF417 函式庫的條碼產生器，在 C# 中產生 PDF417 條碼。請參考此簡明教學，取得完整程式碼與最佳實踐。
og_image_alt: Generated PDF417 barcode example
og_title: 在 C# 中生成 PDF417 條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Learn how to generate PDF417 barcode in C# with the barcode generator
    C# PDF417 library – step-by-step code examples.
  headline: How to generate PDF417 barcode in C# with Barcode Generator
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中使用條碼產生器生成 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼產生器產生 PDF417 條碼

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本教學提供一個可直接執行的解決方案。使用 **barcode generator C# PDF417** 函式庫，您只需幾行程式碼即可控制尺寸、欄位、列數以及影像格式。

您將學會如何建立高解析度條碼、客製化版面配置，並將結果儲存為 PNG 檔案——全部在 IDE 內完成。

## 您需要的環境

- .NET 6.0 或更新版本（程式碼同樣適用於 .NET Framework 4.6+）
- Aspose.BarCode for .NET 套件（透過 NuGet 安裝：`Install-Package Aspose.BarCode`）
- 用於存放產生 PNG 影像的資料夾
- 基本的 C# 語法概念

## 步驟 1：設定專案並匯入命名空間

建立一個新的 Console 應用程式（或將程式碼加入現有專案），並加入必要的 using 指令：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Aspose.BarCode.Generation` 命名空間提供 `BarcodeGenerator`，而 `Aspose.BarCode` 則包含 `BarCodeImageFormat` 列舉。

## 步驟 2：初始化 PDF417 條碼產生器

以 PDF417 編碼類型與欲編碼的文字建立 `BarcodeGenerator` 實例。範例使用含有非 ASCII 字元的字串，以示範 Unicode 支援。

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

**為什麼這很重要：**  
`EncodeTypes.Pdf417` 告訴函式庫產生 PDF417 條碼，這是一種堆疊式線性條碼，適合儲存大量資料。於建構子即傳入文字，可讓產生器立即就緒。

## 步驟 3：使用 X‑dimension 提升解析度

X‑dimension（模組寬度）決定每條細條佔用多少像素。數值較大時，影像會更清晰，特別是在列印時。

```csharp
// Step 3: Define the module (X) dimension in pixels for better resolution
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

將 `Pixels = 2` 設為一個在尺寸與可讀性之間的良好平衡。若需高 DPI 輸出，可提高此數值，但檔案大小也會隨之增長。

## 步驟 4：以固定欄位數產生條碼

PDF417 條碼可以以特定欄位數排列。此處我們要求 **2 欄**，讓函式庫自動決定列數。

```csharp
// Step 4: Generate a barcode with 2 columns and save it as PNG
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 2;   // columns = 2, rows = auto
barcodeGenerator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
```

**結果：** `Pdf417Columns2.png` 會產生一個包含兩個垂直堆疊的緊湊條碼。

## 步驟 5：讓函式庫決定欄位，並設定固定列數

當您需要特定列數（例如配合標籤高度）時，可設定列數，同時讓欄位保持 *auto*。

```csharp
// Step 5: Generate a barcode with 6 rows (columns set to auto) and save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 0;   // columns = auto
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 6;      // rows = 6
barcodeGenerator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
```

函式庫會計算出在六列內容納資料的最佳欄位數。

## 步驟 6：同時指定欄位與列數以自訂版面

若版面限制嚴格（例如預先列印的表單），您可以明確設定兩個維度：

```csharp
// Step 6: Generate a barcode with 4 columns and 9 rows, then save it
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;   // columns = 4
barcodeGenerator.Parameters.Barcode.Pdf417.Rows = 9;      // rows = 9
barcodeGenerator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
```

這會產生一個完全符合 4 × 9 網格的條碼，方便與實體模板對齊。

## 完整可執行範例

以下程式碼示範一次執行上述五個步驟。將內容貼入 `Program.cs` 後即可執行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create the generator with sample text containing Unicode characters
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

            // Improve image sharpness
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 1️⃣ Two columns, rows auto
            generator.Parameters.Barcode.Pdf417.Columns = 2;
            generator.Parameters.Barcode.Pdf417.Rows = 0; // explicit auto
            generator.Save("Pdf417Columns2.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Columns2.png");

            // 2️⃣ Six rows, columns auto
            generator.Parameters.Barcode.Pdf417.Columns = 0; // auto columns
            generator.Parameters.Barcode.Pdf417.Rows = 6;
            generator.Save("Pdf417Rows6.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows6.png");

            // 3️⃣ Custom layout: 4 columns × 9 rows
            generator.Parameters.Barcode.Pdf417.Columns = 4;
            generator.Parameters.Barcode.Pdf417.Rows = 9;
            generator.Save("Pdf417Rows9Columns4.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved: Pdf417Rows9Columns4.png");
        }
    }
}
```

**預期輸出**

執行程式後，專案輸出資料夾會產生三個 PNG 檔案：

- `Pdf417Columns2.png` – 兩個垂直欄位的條碼  
- `Pdf417Rows6.png` – 延伸至六列的條碼  
- `Pdf417Rows9Columns4.png` – 以 4 × 9 網格排列的條碼  

您可使用一般影像檢視器開啟任一檔案，並以 PDF417 掃描應用程式驗證條碼是否正確。

## 專業技巧與常見陷阱

- **Unicode 處理**：產生器會自動編碼 Unicode 字元，但請確認目標掃描器支援您使用的字元集。  
- **影像格式**：PNG 具備無損品質。如需向量格式（例如 SVG）以便縮放，將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Svg`。  
- **效能**：如範例所示，重複使用同一個 `BarcodeGenerator` 實例比每次建立新實例更有效率。  
- **錯誤處理**：將 `Save` 呼叫包在 `try/catch` 中，以捕捉 I/O 錯誤，特別是寫入受保護目錄時。  
- **列印考量**：對於列印標籤，建議將 `XDimension.Pixels` 提升至 3 或 4，以避免在常見 300 dpi 下出現像素化。

## 結論

現在您已掌握如何在 C# 中使用 **barcode generator C# PDF417** 函式庫 **產生 PDF417 條碼**。本教學說明了設定解析度、控制版面配置等關鍵步驟。

## 您接下來該學什麼？

以下教學與本篇內容緊密相關，能進一步深化您對 API 功能的運用，並探索其他實作方式：

- [How to Generate PDF417 Barcode – Compact PDF417 Encoding](/barcode/english/net/compact-pdf417-encoding/)
- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [java barcode library – Add barcode to PDF using Aspose](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}