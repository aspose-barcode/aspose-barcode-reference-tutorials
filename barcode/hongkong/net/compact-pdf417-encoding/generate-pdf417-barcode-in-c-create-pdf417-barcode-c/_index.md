---
category: general
date: 2026-07-24
description: 使用 Aspose.BarCode 在 C# 中產生 PDF417 條碼。學習如何在幾分鐘內以緊湊模式建立 PDF417 條碼（C#）。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- create pdf417 barcode c#
- c# barcode generator pdf417
- how to generate pdf417 barcode
language: zh-hant
lastmod: 2026-07-24
og_description: 使用 Aspose.BarCode 在 C# 中快速生成 PDF417 條碼。本教程將示範如何在緊湊模式下使用 C# 建立 PDF417
  條碼，涵蓋設定、程式碼與驗證。
og_image_alt: Screenshot of generated compact PDF417 barcode saved as PNG using C#
  code
og_title: 在 C# 中產生 PDF417 條碼 – 快速指南
schemas:
- author: Aspose
  dateModified: '2026-07-24'
  description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  headline: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  type: TechArticle
- description: Generate PDF417 barcode in C# using Aspose.BarCode. Learn how to create
    PDF417 barcode C# with compact mode in minutes.
  name: Generate PDF417 Barcode in C# – Create PDF417 Barcode C#
  steps:
  - name: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
    text: '**Data definition** – PDF417 can store up to ~1850 characters, but we keep
      it short for the demo. Unicode support means those accented characters won’t
      break anything.'
  - name: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
    text: '**Generator construction** – The `EncodeTypes.Pdf417` enum value tells
      Aspose which symbology to use; swapping it for `EncodeTypes.QR` would give you
      a QR code instead.'
  - name: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
    text: '**X‑dimension** – This controls the width of each module (the tiny squares
      that make up the barcode). A value of `2` pixels yields a crisp image that’s
      still readable when printed at 300 dpi.'
  - name: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
    text: '**PDF417 options** – `Columns` influences the barcode’s aspect ratio; fewer
      columns make the image taller, which can be useful for receipts. `Truncate`
      (also called *Compact mode*) removes the start/stop pattern padding, reducing
      file size without sacrificing data integrity.'
  - name: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
    text: '**Output path** – Using `Environment.CurrentDirectory` ensures the image
      lands next to the executable, making it easy to locate during development.'
  - name: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
    text: '**Saving** – `BarCodeImageFormat.Png` gives lossless quality, perfect for
      further processing or embedding in PDFs.'
  type: HowTo
tags:
- barcode
- pdf417
- csharp
title: 在 C# 中產生 PDF417 條碼 – 建立 PDF417 條碼 C#
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-create-pdf417-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 PDF417 條碼 – 完整程式教學

有沒有想過如何在 C# 應用程式中 **產生 PDF417 條碼**，卻不必在無盡的論壇討論中搜尋？你並不是唯一有此需求的人。無論你是要建立票務系統、製作安全身分證，或只是需要一個快速的方式將資料嵌入可列印的格式，精通 PDF417 格式都能為你節省大量的試錯時間。

本教學將逐步說明一個 **完整、可直接執行的範例**，示範如何使用廣受歡迎的 Aspose.BarCode 函式庫 **在 C# 中建立 PDF417 條碼**。我們會涵蓋從安裝 NuGet 套件到調整緊湊模式的所有步驟，讓你可以直接複製貼上程式碼並立即看到結果。

## 你將學會

- 如何在 .NET 專案中設定 Aspose.BarCode 函式庫。  
- 產生 PDF417 條碼所需的完整 C# 語句，包含自訂文字、模組大小與欄位數。  
- 為何切換 *Compact*（Truncate）選項對於高密度資料很重要。  
- 如何將條碼儲存為 PNG 並驗證輸出。  

不需要任何條碼經驗；只要具備基本的 C# 與 Visual Studio（或任何你偏好的 IDE）知識即可。完成後，你將擁有一個可重複使用的方法，能直接嵌入任何需要 PDF417 圖像的專案中。

## 前置條件

| Requirement | Why it matters |
|-------------|----------------|
| .NET 6.0 or later (or .NET Framework 4.7+) | Aspose.BarCode 兩者皆支援；較新的執行環境可提供更佳效能。 |
| Visual Studio 2022 (or VS Code with C# extensions) | 提供 IntelliSense 及簡易除錯功能。 |
| Internet connection (for the first NuGet restore) | 此函式庫會從 NuGet.org 取得。 |
| Basic C# knowledge | 需要了解類別結構與方法呼叫。 |

如果你已具備上述條件，太好了——讓我們開始吧。

## 安裝 Aspose.BarCode NuGet 套件

在終端機中開啟你的專案資料夾，執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

或者在 Visual Studio 中，右鍵點選 **Dependencies → Manage NuGet Packages**，搜尋 *Aspose.BarCode*，然後點擊 **Install**。這行指令會將我們將使用的所有類型（包括 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat`）全部加入。

> **小技巧：** 安裝完成後，請清理並重新建置解決方案，以確保正確參考到組件。

## 產生 PDF417 條碼 – 設定與相依性

首先，我們需要一個 `using` 區塊，將相關的命名空間匯入作用域。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

這些命名空間讓我們可以存取產生器類別與條碼類型的列舉。沒有什麼複雜的——只要三行程式碼，我們就可以開始建立條碼了。

## 建立 PDF417 條碼 C# – 步驟實作

以下是一個 **獨立的主控台程式**，它會使用字串 `"Åspóse.Barcóde©"` 產生緊湊的 PDF417 條碼，並儲存為 `CompactPdf417.png`。你可以隨意替換成任何文字；產生器會直接支援 Unicode 字元。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "Åspóse.Barcóde©";

            // 2️⃣ Initialise the generator for PDF417.
            //    EncodeTypes.Pdf417 tells Aspose we want a PDF417 barcode.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Adjust the module (X‑dimension) size.
            //    Smaller values give a tighter image; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Configure PDF417‑specific options.
            //    • Columns = 3 → fewer columns, taller barcode.
            //    • Truncate = true → enables Compact mode, which removes unnecessary padding.
            generator.Parameters.Barcode.Pdf417.Columns = 3;
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 5️⃣ Choose the output folder – adjust as needed.
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CompactPdf417.png");

            // 6️⃣ Save the image as PNG.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ PDF417 barcode saved to: {outputPath}");
        }
    }
}
```

### 為何每一步都很重要

1. **資料定義** – PDF417 最多可儲存約 1850 個字元，但我們在示範中僅使用較短的內容。Unicode 支援確保這些帶重音的字元不會造成問題。  
2. **產生器建構** – `EncodeTypes.Pdf417` 列舉值告訴 Aspose 使用哪種符號；若改成 `EncodeTypes.QR`，則會產生 QR Code。  
3. **X‑dimension** – 此參數控制每個模組（組成條碼的微小方格）的寬度。設定為 `2` 像素可產生清晰的影像，即使在 300 dpi 列印時仍具可讀性。  
4. **PDF417 選項** – `Columns` 會影響條碼的長寬比；欄位較少會使影像較高，這在收據上可能較為實用。`Truncate`（亦稱 *Compact mode*）會移除起始/結束圖樣的填充，減少檔案大小，同時不影響資料完整性。  
5. **輸出路徑** – 使用 `Environment.CurrentDirectory` 可確保影像儲存在執行檔旁邊，方便開發時快速找到。  
6. **儲存** – `BarCodeImageFormat.Png` 提供無損品質，適合進一步處理或嵌入 PDF 中。  

執行程式（`dotnet run` 或在 Visual Studio 按 **F5**）。幾秒鐘後，你應該會在主控台看到確認檔案位置的訊息，且 PNG 會出現在專案資料夾中。

![產生 pdf417 條碼範例 – 使用 C# 建立的緊湊 PDF417 條碼 PNG 圖像](generated-pdf417.png)

*圖片替代文字：產生 pdf417 條碼範例 – 使用 C# 建立的緊湊 PDF417 條碼 PNG 圖像。*

## 設定緊湊模式 – C# 條碼產生器 PDF417 選項

如果需要較大的條碼（例如遠距離掃描），可調整 `Columns` 與 `Rows` 屬性。以下是一段快速程式碼片段，示範其他配置方式：

```csharp
// Increase columns for a wider, shorter barcode.
generator.Parameters.Barcode.Pdf417.Columns = 6;

// Disable Compact mode if the scanning hardware struggles with it.
generator.Parameters.Barcode.Pdf417.Truncate = false;

// Optionally set error correction level (0–8). Higher values increase redundancy.
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;
```

> **常見問題：** *停用 Truncate 會破壞現有掃描器嗎？*  
> 通常不會。大多數現代掃描器都能辨識完整尺寸與緊湊模式的 PDF417。但若你的目標是舊版硬體，請將 `Truncate` 保持為 `false`。

## 儲存與驗證 – 如何產生 PDF417 條碼輸出

儲存後，你可以使用任何圖像檢視器開啟 PNG。若要再次確認條碼編碼的資料正確，請使用 Aspose 的 `BarCodeReader`：



## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何使用 Aspose.BarCode 建立條碼 – 緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [java 條碼函式庫 – 使用 Aspose 將條碼加入 PDF](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}