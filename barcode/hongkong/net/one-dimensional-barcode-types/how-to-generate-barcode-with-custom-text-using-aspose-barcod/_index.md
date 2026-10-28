---
category: general
date: 2026-10-28
description: 如何使用 Aspose.BarCode 產生帶有自訂文字的條碼 – 為 .NET 開發者提供的逐步指南，創建 Aspose 條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- generate barcode custom text
- create barcode aspose
language: zh-hant
lastmod: 2026-10-28
og_description: 如何在 .NET 中使用 Aspose.BarCode 產生帶有自訂文字的條碼。請參考本完整指南，建立並儲存 Macro PDF417
  條碼。
og_image_alt: how to generate barcode example PNG image showing a Macro PDF417 barcode
og_title: 如何使用自訂文字產生條碼 – Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  headline: How to generate barcode with custom text using Aspose.BarCode for .NET
  type: TechArticle
- description: How to generate barcode with custom text using Aspose.BarCode – step‑by‑step
    guide for .NET developers to create barcode Aspose images.
  name: How to generate barcode with custom text using Aspose.BarCode for .NET
  steps:
  - name: Why each line matters
    text: '* **EncodeTypes.MacroPdf417** – selects the Macro PDF417 symbology, which
      supports segmented data and metadata. * **XDimension.Pixels** – controls the
      size of each module; a value of 2 pixels yields a clear, scannable image. *
      **Pdf417.Columns** – reduces the overall width, making the barcode more c'
  - name: Using a different barcode type
    text: If you need to **generate barcode custom text** for a QR code instead of
      Macro PDF417, replace `EncodeTypes.MacroPdf417` with `EncodeTypes.QR`. The rest
      of the parameter structure stays the same, but QR codes do not support Macro
      metadata fields.
  - name: Handling Unicode characters
    text: The example already includes Unicode characters (`Å`, `ó`, `©`). Aspose.BarCode
      handles UTF‑8 input out of the box, but you should ensure the source file is
      saved with UTF‑8 encoding to avoid compile‑time warnings.
  - name: Saving to other image formats
    text: 'Aspose.BarCode supports BMP, JPEG, TIFF, and SVG in addition to PNG. Change
      the `BarCodeImageFormat` enum value accordingly:'
  - name: Large data sets
    text: Macro PDF417 can split data across multiple segments. When the text exceeds
      the capacity of a single segment, increment `MacroPdf417SegmentID` and keep
      `MacroPdf417SegmentsCount` consistent across all generated parts. This approach
      is essential for **create barcode aspose** scenarios where the paylo
  - name: Error handling
    text: 'Wrap the generation logic in a try‑catch block to surface runtime issues
      such as invalid file paths or unsupported characters:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- .NET
title: 如何使用 Aspose.BarCode for .NET 產生帶自訂文字的條碼
url: /zh-hant/net/one-dimensional-barcode-types/how-to-generate-barcode-with-custom-text-using-aspose-barcod/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 產生帶自訂文字的條碼

在需要將識別碼、時間戳記或其他中繼資料直接嵌入視覺碼時，產生帶自訂文字的條碼是一項常見需求。本教學示範如何使用 **Aspose.BarCode** .NET 函式庫產生攜帶自訂文字與完整中繼資料的 Macro PDF417 條碼。

您將學會如何設定產生器、套用自訂文字、設定 Macro PDF417 專屬欄位，並將結果儲存為 PNG 圖片。無需任何外部工具——只需要 Aspose.BarCode NuGet 套件與 .NET 開發環境。

## 前置條件

開始之前，請確保您已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* **Aspose.BarCode for .NET** NuGet 套件（`Install-Package Aspose.BarCode`）  

上述前置條件可確保程式碼能順利編譯與執行，且不需額外設定。

## 步驟 1：安裝 Aspose.BarCode 套件

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新的穩定版 Aspose.BarCode 加入專案，讓您可以使用 `BarcodeGenerator` 類別以及所有相關參數。

## 步驟 2：建立新的主控台應用程式

建立一個最小的主控台應用程式，以容納條碼產生邏輯：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // The full barcode generation flow is encapsulated in a separate method
            GenerateMacroPdf417Barcode();
        }

        /// <summary>
        /// Generates a Macro PDF417 barcode with custom text and metadata, then saves it as PNG.
        /// </summary>
        private static void GenerateMacroPdf417Barcode()
        {
            // Step 1: Instantiate the generator with the desired encode type and data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Define the visual appearance of the barcode
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // Size of a single module
                generator.Parameters.Barcode.Pdf417.Columns = 5;            // Number of columns in the symbol

                // Step 3: Populate Macro PDF417 specific metadata fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 example value
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 4: Save the barcode image to disk
                string outputPath = @"ExtPDF417Meta.png";
                generator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Barcode saved to {outputPath}");
            }
        }
    }
}
```

### 為何每一行都很重要

* **EncodeTypes.MacroPdf417** – 選取支援分段資料與中繼資料的 Macro PDF417 符號。  
* **XDimension.Pixels** – 控制每個模組的大小；設定為 2 像素即可產生清晰且易於掃描的圖像。  
* **Pdf417.Columns** – 減少整體寬度，使條碼在列印標籤時更為緊湊。  
* **MacroPdf417* 屬性** – 直接將檔案層級資訊（ID、段數、時間戳記等）嵌入條碼。此功能為 Macro PDF417 所獨有，常用於物流或文件管理系統。  
* **Save(..., BarCodeImageFormat.Png)** – 輸出無損 PNG 檔案，保留條碼的銳利邊緣，確保掃描可靠。

## 步驟 3：執行程式並驗證輸出

編譯並執行主控台應用程式：

```bash
dotnet run
```

程式會在專案的工作目錄中產生 `ExtPDF417Meta.png`。開啟該檔案即可看到一個編碼文字 **“Åspóse.Barcóde©”** 以及您提供的中繼資料的 Macro PDF417 條碼。

**預期輸出** – 如下圖所示的 PNG 圖片：

![示範產生條碼的 PNG 圖片（顯示 Macro PDF417 條碼）](ExtPDF417Meta.png)

*圖片的替代文字（「示範產生條碼的 PNG 圖片」）加強了可及性與 SEO 的主要關鍵字。*

## 常見變形與邊緣案例

### 使用不同的條碼類型

若需為 QR Code 而非 Macro PDF417 產生 **條碼自訂文字**，只要將 `EncodeTypes.MacroPdf417` 改為 `EncodeTypes.QR` 即可。其餘參數結構保持不變，但 QR Code 不支援 Macro 中繼資料欄位。

### 處理 Unicode 字元

範例已包含 Unicode 字元（`Å`、`ó`、`©`）。Aspose.BarCode 內建支援 UTF‑8 輸入，但請確保原始檔案以 UTF‑8 編碼儲存，以免產生編譯警告。

### 儲存為其他影像格式

除了 PNG，Aspose.BarCode 亦支援 BMP、JPEG、TIFF 與 SVG。只要相應調整 `BarCodeImageFormat` 列舉值：

```csharp
generator.Save("barcode.svg", BarCodeImageFormat.Svg);
```

### 大量資料集

Macro PDF417 可將資料分割至多個段落。當文字超過單一段落容量時，請遞增 `MacroPdf417SegmentID`，並確保所有產生的段落之 `MacroPdf417SegmentsCount` 保持一致。此作法對於 **create barcode aspose** 的情境（負載大於單一條碼可容納）相當重要。

### 錯誤處理

將產生邏輯包裹於 try‑catch 區塊，以捕捉執行時問題（例如無效的檔案路徑或不支援的字元）：

```csharp
try
{
    GenerateMacroPdf417Barcode();
}
catch (Exception ex)
{
    Console.Error.WriteLine($"Barcode generation failed: {ex.Message}");
}
```

## 提升條碼產生可靠性的專業技巧

* **使用 `BarCodeReader` 驗證條碼**。此步驟可確認編碼資料與預期相符。

  ```csharp
  using (BarCodeReader reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.MacroPdf417))
  {
      if (reader.Read())
          Console.WriteLine($"Decoded text: {reader.GetCodeText()}");
  }
  ```

* **將 X‑dimension 設為 2 – 4 像素**，適用於大多數掃描器。過小的數值可能在低解析度裝置上產生無法辨識的圖像。

* **避免在 `MacroPdf417FileName` 中使用過長檔名**。規範限制此欄位最多 32 個字元。

* **使用一致的時間戳記（UTC）** 產生多段條碼，以簡化後續處理流程。

## 結論

現在您已掌握 **如何使用 Aspose.BarCode for .NET 產生帶自訂文字的條碼**、如何設定 Macro PDF417 中繼資料，以及如何將結果儲存為 PNG 圖片。完整可執行的範例示範了從安裝 NuGet 套件、處理 Unicode 字元到儲存輸出的每一步。

接下來您可以：

* 為其他符號系統（QR、DataMatrix 等） **產生條碼自訂文字**  
* 建立 **Create barcode Aspose** 工作流程，批次處理數千張影像  
* 將條碼產生程式碼整合至 ASP.NET Core 服務、Windows 服務或 Azure Functions  

盡情嘗試不同參數、探索更多中繼資料欄位，並將條碼納入文件自動化流程。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在專案中探索其他實作方式。

- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)
- [Generate barcode from text using Aspose.BarCode – C# Guide](/barcode/english/net/one-dimensional-barcode-types/generate-barcode-from-text-using-aspose-barcode-c-guide/)
- [How to use Aspose.BarCode to create DataMatrix code text in .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}