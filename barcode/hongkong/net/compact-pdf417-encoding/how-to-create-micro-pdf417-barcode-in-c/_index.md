---
category: general
date: 2026-11-14
description: 使用 Aspose.BarCode 在 C# 中建立 micro PDF417 條碼 – 步驟式指南，涵蓋產生器設定、X 尺寸、列數及 PNG
  匯出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- micro pdf417 barcode generator
- set XDimension pixels
- define barcode columns
- save barcode as PNG
- Aspose.BarCode C# example
language: zh-hant
lastmod: 2026-11-14
og_description: 使用 Aspose.BarCode 在 C# 中建立微型 PDF417 條碼。學習如何設定產生器、設定 XDimension、選擇欄位，並匯出為
  PNG。
og_image_alt: Screenshot of a generated micro PDF417 barcode saved as a PNG file
og_title: 在 C# 中建立微型 PDF417 條碼 – 完整程式設計指南
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  headline: How to create micro PDF417 barcode in C#
  type: TechArticle
- description: Create micro PDF417 barcode in C# with Aspose.BarCode – step‑by‑step
    guide covering generator setup, X‑dimension, columns, and PNG export.
  name: How to create micro PDF417 barcode in C#
  steps:
  - name: Open the PNG in an image viewer.
    text: Open the PNG in an image viewer.
  - name: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
    text: Use any smartphone barcode‑scanning app that supports PDF417 (most “QR‑code
      scanner” apps include it).
  - name: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
    text: Scan the image; the app should display the original text `"Åspóse.Barcóde©"`.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
- image generation
title: 如何在 C# 中建立微型 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立微型 PDF417 條碼  

如果您需要快速 **建立微型 PDF417 條碼**，本指南將向您展示一個完整、可直接執行的解決方案。您將看到如何實例化條碼產生器、設定 X‑dimension、選擇欄位數量，最後將結果儲存為 PNG 圖片——全部使用 Aspose.BarCode for .NET 函式庫。

產生微型 PDF417 條碼不需要複雜的建置流程。完成本教學後，您將擁有一個單一的 C# 檔案，可產生高品質的條碼圖像，並可嵌入報告、標籤或行動應用程式中。

## 前置條件  

* .NET 6.0 SDK 或更新版本（程式碼亦可於 .NET Framework 4.7+ 執行）。  
* 開發環境，例如 Visual Studio 2022、VS Code 或 Rider。  
* Aspose.BarCode for .NET 授權（或免費評估金鑰）。您可從 [Aspose website](https://purchase.aspose.com/barcode/net) 取得。  

> **專業提示：** 若您使用評估版，產生的 PNG 會包含小型「Evaluation」浮水印。授權版會自動移除。

## 第一步：設定專案  

建立一個新的 Console 專案，並加入 Aspose.BarCode NuGet 套件。

```bash
dotnet new console -n MicroPdf417Demo
cd MicroPdf417Demo
dotnet add package Aspose.BarCode --version 24.9.0
```

`dotnet add package` 指令會下載 **Aspose.BarCode C# example** 相依性，讓您不必手動管理 DLL。

## 第二步：撰寫完整程式碼  

將自動產生的 `Program.cs` 替換為以下程式碼。它示範如何從頭到尾 **建立微型 pdf417 條碼**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a MicroPDF417 barcode generator with the desired text.
            // The text can contain Unicode characters; here we use a sample string.
            var generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Åspóse.Barcóde©");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            // This determines the width of the smallest element (a bar or a space).
            generator.Parameters.Barcode.XDimension.Pixels = 2; // secondary keyword: set XDimension pixels

            // 3️⃣ Define the number of columns (allowed values: 1‑4 for MicroPDF417).
            // More columns mean a wider barcode but fewer rows, which can improve readability.
            generator.Parameters.Barcode.Pdf417.Columns = 4; // secondary keyword: define barcode columns

            // 4️⃣ Choose the output format and save the barcode as a PNG image.
            // PNG preserves the sharp edges of the barcode, which is ideal for scanning.
            string outputPath = "MicroPdf417.png";
            generator.Save(outputPath, BarCodeImageFormat.Png); // secondary keyword: save barcode as PNG

            Console.WriteLine($"Micro PDF417 barcode saved to {outputPath}");
        }
    }
}
```

### 為何每一行都很重要  

* **BarcodeGenerator constructor** – 建構 **微型 pdf417 條碼產生器**，並以您想編碼的文字初始化。  
* **XDimension.Pixels** – 控制模組寬度；設定為 `2` 像素可產生密集且高解析度的條碼，適合大多數掃描器。  
* **Pdf417.Columns** – MicroPDF417 只支援 1‑4 欄。選擇 `4` 可降低條碼高度，當垂直空間受限時很有幫助。  
* **Save method** – 將條碼寫入 PNG 檔案。PNG 為無損格式，可確保掃描器讀取到您產生的精確圖樣。

## 第三步：建置與執行  

編譯並執行程式：

```bash
dotnet run
```

您應該會看到主控台輸出：

```
Micro PDF417 barcode saved to MicroPdf417.png
```

專案資料夾中會出現名為 **MicroPdf417.png** 的檔案。使用任何影像檢視器開啟它，您會看到一個清晰的微型 PDF417 條碼，編碼的字串為 `"Åspóse.Barcóde©"`。

![產生的微型 PDF417 條碼範例](MicroPdf417.png "產生的微型 PDF417 條碼範例"){.center-image width=400 alt="產生的微型 PDF417 條碼圖像範例"}

*上圖為第 2 步所示程式碼的執行結果。*

## 第四步：常見變化與邊緣案例  

| 情境 | 如何調整程式碼 |
|-----------|----------------------|
| **不同的資料長度** | MicroPDF417 最多可編碼 1 200 個字元。只需變更 `BarcodeGenerator` 的第二個參數即可。 |
| **更高解析度** | 將 `XDimension.Pixels` 提升至 `3` 或 `4`。較大的模組可提升低解析度掃描器的可讀性，但會增加影像大小。 |
| **自訂顏色** | 在建立產生器後，設定 `generator.Parameters.Barcode.BarcodeColor = Color.Blue;` 以及 `generator.Parameters.Barcode.BackgroundColor = Color.White;`。 |
| **儲存其他格式** | 將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Gif`，視您的後續需求而定。 |
| **嵌入 PDF** | 使用 `generator.Save("barcode.pdf", BarCodeImageFormat.Pdf);`，然後使用 Aspose.PDF 將 PDF 與其他文件合併。 |

> **注意：** 將 `XDimension.Pixels` 設為小於 `1` 會拋出 `ArgumentOutOfRangeException`。請始終保持其值為 `1` 或以上。

## 第五步：驗證條碼  

為確保條碼能正確掃描：

1. 使用影像檢視器開啟 PNG。  
2. 使用任何支援 PDF417 的智慧手機條碼掃描應用程式（大多數「QR‑code 掃描器」應用程式皆包含此功能）。  
3. 掃描圖像；應用程式應顯示原始文字 `"Åspóse.Barcóde©"`。

若掃描失敗，請再次確認 **X‑dimension** 與 **column** 設定——過小的模組寬度或不支援的欄位數都可能導致圖樣無法辨識。

## 結論  

您現在已了解如何使用 Aspose.BarCode 在 C# 中 **建立微型 pdf417 條碼**。本教學涵蓋：

* 實例化 **微型 pdf417 條碼產生器**。  
* **設定 XDimension 像素** 以控制模組寬度。  
* **定義條碼欄位** 以調整形狀。  
* **將條碼儲存為 PNG**，以取得無損圖像輸出。  

接下來，您可以探索其他功能，例如顏色自訂、將條碼嵌入 PDF，或在 ASP.NET Core Web API 中即時產生條碼。祝開發愉快！

## 接下來您可以學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [在 C# 中建立條碼 PNG – 完整的 GS1 微型 PDF417 教學](/barcode/english/net/gs1-barcode-encoding/create-barcode-png-in-c-full-guide-to-gs1-micro-pdf417/)
- [如何在 C# 中使用 Aspose.BarCode 建立宏 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [在 C# 中使用 Aspose.BarCode 建立 PDF417 條碼 – 步驟教學](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-using-aspose-barcode-step-by-step/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}