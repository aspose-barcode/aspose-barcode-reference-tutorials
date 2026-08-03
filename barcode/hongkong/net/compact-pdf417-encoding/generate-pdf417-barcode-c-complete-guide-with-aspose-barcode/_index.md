---
category: general
date: 2026-08-03
description: 使用 Aspose.BarCode 於 C# 產生 PDF417 條碼。一步一步學習如何加入 Macro PDF417 中繼資料並儲存為
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate PDF417 barcode C#
- Macro PDF417 barcode
- Aspose.BarCode
- C# barcode generation
- PDF417 metadata
- barcode image PNG
language: zh-hant
lastmod: 2026-08-03
og_description: 使用 Aspose.BarCode 於 C# 產生 PDF417 條碼。本教學說明如何嵌入 Macro PDF417 元資料，並將結果匯出為
  PNG 圖像。
og_image_alt: Screenshot of a generated PDF417 barcode created with C#
og_title: 產生 PDF417 條碼 C# – 逐步 Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  headline: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  type: TechArticle
- description: Generate PDF417 barcode C# using Aspose.BarCode. Learn step‑by‑step
    how to add Macro PDF417 metadata and save as PNG.
  name: Generate PDF417 barcode C# – complete guide with Aspose.BarCode
  steps:
  - name: Create a Macro PDF417 barcode generator
    text: First, instantiate `BarcodeGenerator` with the `EncodeTypes.MacroPdf417`
      enum. The constructor also accepts the text you want to encode – in this example
      we use a string that contains Unicode characters to demonstrate full‑width support.
  - name: Adjust basic barcode appearance
    text: Next, define the visual size of the barcode. `XDimension.Pixels` controls
      the width of a single module (the smallest black/white square), while `Pdf417.Columns`
      influences the overall shape by setting the number of columns.
  - name: Populate Macro PDF417 metadata
    text: Macro PDF417 allows you to embed file‑level information that many back‑office
      systems rely on (e.g., file ID, segment ID, timestamp). The following properties
      illustrate the most common fields.
  - name: Save the barcode image as PNG
    text: Finally, call `Save` to write the barcode to disk. PNG is lossless, making
      it ideal for high‑quality scanning.
  - name: How to verify the result
    text: 1. Open `ExtPDF417Meta.png` in any image viewer. 2. Use a PDF417 scanner
      app (e.g., *Zebra Scanner* or *BarCode Reader* on Android/iOS). 3. Confirm that
      the decoded payload includes the original text and a JSON‑like block with the
      macro fields you set.
  - name: Next steps
    text: '- Experiment with other barcode formats (e.g., QR, Code128) by changing
      `EncodeTypes`. - Explore `Pdf417.ErrorCorrectionLevel` to improve scan reliability
      under poor lighting. - Integrate the generated image into a PDF report using
      Aspose.PDF for end‑to‑end document automation.'
  type: HowTo
tags:
- PDF417
- C#
- Barcode
title: 在 C# 中產生 PDF417 條碼 – 使用 Aspose.BarCode 的完整指南
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-c-complete-guide-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生 PDF417 條碼 C# – 完整指南

如果您需要為物流或文件管理系統 **generate PDF417 barcode C#**，本教學將向您展示如何使用 Aspose.BarCode 完成。您將看到如何設定條碼、嵌入 Macro PDF417 中繼資料，並僅用幾行程式碼將結果儲存為 PNG 圖片。

在 C# 中產生 PDF417 條碼通常需要處理額外資訊，如檔案識別碼、段落編號或時間戳記。本指南涵蓋這些細節，讓您不必在零散的文件中搜尋。文章結束時，您將擁有一個可直接執行的程式，產生符合規範的 Macro PDF417 條碼圖像。

## 您需要的條件

- .NET 6.0 或更新版本（此程式碼亦可在 .NET Framework 4.7+ 上執行）
- Aspose.BarCode for .NET (v23.9 或更新) – 透過 NuGet 安裝 `Install-Package Aspose.BarCode`
- 開發環境，例如 Visual Studio 2022 或 Visual Studio Code
- 基本熟悉 C# 語法

> **專業提示：** 使用最新的 Aspose.BarCode 版本，以獲得錯誤修正與最新 PDF417 規格的支援。

## 如何使用 Aspose.BarCode 產生 PDF417 條碼 C#

此流程包含四個邏輯步驟。每個步驟都以清晰的程式碼區塊包裹，讓您可以直接複製、貼上並執行。

### 步驟 1：建立 Macro PDF417 條碼產生器

首先，使用 `EncodeTypes.MacroPdf417` 列舉實例化 `BarcodeGenerator`。建構函式同時接受您想要編碼的文字——在此範例中，我們使用包含 Unicode 字元的字串，以示範全形支援。

```csharp
using System;
using Aspose.BarCode.Generation;

// Create a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417,
           "Åspóse.Barcóde©"))
{
    // Subsequent steps go inside this using block
```

*此設定的重要性*：`MacroPdf417` 類型告訴 Aspose.BarCode 將此符號視為 macro 條碼，能攜帶額外的檔案層級中繼資料。若未設定此旗標，之後設定的額外欄位將會被忽略。

### 步驟 2：調整條碼基本外觀

接著，定義條碼的視覺尺寸。`XDimension.Pixels` 控制單一模組（最小的黑白方格）的寬度，而 `Pdf417.Columns` 透過設定欄數影響整體形狀。

```csharp
    // Adjust basic barcode appearance
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

*此設定的重要性*：較小的 `XDimension` 會產生較高解析度的圖像，適用於需要從螢幕掃描條碼的情況。調整欄數可在不犧牲資料容量的前提下，使條碼更易於適配有限空間。

### 步驟 3：填入 Macro PDF417 中繼資料

Macro PDF417 允許您嵌入許多後端系統依賴的檔案層級資訊（例如檔案 ID、段落 ID、時間戳記）。以下屬性示範最常見的欄位。

```csharp
    // Populate Macro PDF417 metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*此設定的重要性*：每個欄位直接對應至 macro 條碼規範的某段。例如，`MacroPdf417FileID` 唯一標識邏輯檔案，而 `MacroPdf417SegmentsCount` 告訴掃描器預期的段數。提供正確的中繼資料可確保下游系統無誤地重建原始文件。

### 步驟 4：將條碼圖像儲存為 PNG

最後，呼叫 `Save` 將條碼寫入磁碟。PNG 為無損格式，適合高品質掃描。

```csharp
    // Save the barcode image as PNG
    barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

*此設定的重要性*：`BarCodeImageFormat.Png` 列舉確保輸出檔案包含您設定的精確像素資料。若需可縮放的向量格式，只需將 `Png` 改為 `Svg` —— Aspose.BarCode 內建支援。

#### 預期輸出

執行完整程式會產生名為 **ExtPDF417Meta.png** 的檔案。圖像顯示一個密集的多列 PDF417 符號，內含文字 “Åspóse.Barcóde©” 以及您提供的 macro 中繼資料。使用相容 PDF417 的讀取器掃描條碼，可取得原始文字以及包含檔案 ID、段落 ID、時間戳記等欄位的結構化資料區塊。

![產生的 PDF417 條碼截圖](/images/pdf417-example.png){: .center-image alt="產生 PDF417 條碼 C# 範例輸出"}

## 完整原始碼（可直接複製貼上）

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a Macro PDF417 barcode generator with the desired text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417,
                       "Åspóse.Barcóde©"))
            {
                // Step 2: Adjust basic barcode appearance
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // size of a single module
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol

                // Step 3: Populate Macro PDF417 metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;          // CCITT‑16 example
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image as PNG
                barcodeGenerator.Save("YOUR_DIRECTORY/ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### 如何驗證結果

1. 在任何圖像檢視器中開啟 `ExtPDF417Meta.png`。  
2. 使用 PDF417 掃描應用程式（例如 Android/iOS 上的 *Zebra Scanner* 或 *BarCode Reader*）。  
3. 確認解碼後的資料包含原始文字以及您設定的 macro 欄位的 JSON 類似區塊。

## 常見問題與邊緣情況處理

| Question | Answer |
|----------|--------|
| **我可以產生向量圖像而非 PNG 嗎？** | 可以。將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Svg`。其餘程式碼保持不變。 |
| **如果我的資料超過預設容量怎麼辦？** | 增加 `Pdf417.Columns` 或手動設定 `Pdf417.Rows`。較大的數值可在每個段落中容納更多碼字。 |
| **編碼文字是否支援 Unicode？** | 當然支援。範例使用 “Åspóse.Barcóde©”。Aspose.BarCode 會在需要時自動切換為 UTF‑8 編碼。 |
| **我需要為 Aspose.BarCode 申請授權嗎？** | 在正式環境中應申請授權以避免評估水印。於建立產生器前呼叫 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`。 |
| **儲存檔案時如何處理錯誤？** | 將 `Save` 呼叫包在 try/catch 區塊中，並記錄 `IOException` 或 `BarCodeException` 以便除錯。 |

## 結論

您現在已了解如何使用 Aspose.BarCode **generate PDF417 barcode C#**，嵌入完整的 Macro PDF417 中繼資料，並將結果匯出為高品質 PNG 圖像。這些步驟——建立產生器、調整外觀、填入中繼資料以及儲存圖像——構成可重複使用的模式，您可將其套用於發票、運送標籤或任何需要豐富條碼資料的情境。

### 後續步驟

- 嘗試透過變更 `EncodeTypes` 來實驗其他條碼格式（例如 QR、Code128）。  
- 探索 `Pdf417.ErrorCorrectionLevel` 以提升在光線不足情況下的掃描可靠性。  
- 使用 Aspose.PDF 將產生的圖像整合至 PDF 報告，實現端對端文件自動化。  

歡迎依照您的業務規則調整中繼資料欄位，讓條碼產生成為 C# 應用程式中無縫的一環。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417（德文）](/barcode/german/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Java 條碼函式庫 – 使用 Aspose 將條碼加入 PDF](/barcode/english/java/barcode-basics/adding-barcode-to-pdf-document/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}