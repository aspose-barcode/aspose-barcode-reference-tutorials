---
category: general
date: 2026-10-05
description: 學習如何在 C# 中建立 PDF417 條碼，並以逐步程式碼產生條碼 PNG，提供最佳實踐技巧。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- generate barcode PNG
- how to generate PDF417
language: zh-hant
lastmod: 2026-10-05
og_description: 在 C# 中建立 PDF417 條碼並即時產生條碼 PNG。遵循此完整教學，獲得可投入生產的解決方案。
og_image_alt: Example of a compact PDF417 barcode created with C#
og_title: 在 C# 中建立 PDF417 條碼 – 完整的 PNG 生成指南
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  headline: How to create PDF417 barcode and save it as PNG in C#
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# and generate barcode PNG with
    step‑by‑step code and best‑practice tips.
  name: How to create PDF417 barcode and save it as PNG in C#
  steps:
  - name: Expected output
    text: When you open `CompactPdf417.png`, you should see a vertical, high‑density
      barcode that encodes the string *Åspóse.Barcóde©*. Scanning the image with any
      PDF417 reader returns the original text.
  - name: Generating other image formats
    text: 'If you prefer JPEG or BMP, change the `BarCodeImageFormat` enum:'
  - name: Adjusting error correction
    text: 'For harsh environments (e.g., outdoor signage), increase the error‑correction
      level:'
  - name: Encoding binary data
    text: 'PDF417 can encode binary payloads. Pass a `byte[]` instead of a string:'
  - name: Handling very long strings
    text: 'When the data exceeds the default capacity, the generator automatically
      creates additional rows. You can limit the row count to avoid oversized images:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- image generation
title: 如何在 C# 中建立 PDF417 條碼並將其儲存為 PNG
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立 PDF417 條碼並儲存為 PNG

如果您需要在 .NET 應用程式中 **建立 PDF417 條碼**，本指南將會精確說明操作步驟。您將取得一段可直接使用的 C# 程式碼片段，能產生高品質的 **條碼 PNG** 檔案，並且了解所有影響輸出的設定。

產生條碼是票務系統、庫存追蹤與安全文件編碼等常見需求。完成本教學後，您即可以完整、可執行的範例回答「**如何產生 PDF417**」的問題。

## 前置條件

* .NET 6.0 SDK 或更新版本已安裝  
* 開發環境，例如 Visual Studio 2022 或 VS Code  
* **Aspose.BarCode for .NET** NuGet 套件（或任何支援 PDF417 的相容函式庫）  

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

以下程式碼使用 Aspose API，因為它提供對 PDF417 參數的細緻控制，且內建支援 PNG 匯出。

## 步驟 1：設定專案並匯入命名空間

建立一個新的 Console 專案，並匯入所需的命名空間：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

`Aspose.BarCode.Generation` 命名空間包含 `BarcodeGenerator` 類別，它是 **建立 PDF417 條碼** 圖像的入口點。

## 步驟 2：使用目標文字建立 PDF417 條碼

以 `EncodeTypes.Pdf417` 列舉值以及您想要編碼的資料實例化產生器。範例使用包含特殊字元的字串，以示範 Unicode 處理：

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

產生器現在持有一個條碼物件，您可以在渲染前進行設定。

## 步驟 3：設定視覺參數

微調條碼可提升可讀性並減少圖像大小。最常調整的設定為 **X‑dimension**、**columns** 與 **compact mode**。

```csharp
// Step 3: Set the X‑dimension (module width) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Step 4: Define the number of columns for the PDF417 code
generator.Parameters.Barcode.Pdf417.Columns = 3;

// Step 5: Enable compact (truncated) mode to reduce the barcode size
generator.Parameters.Barcode.Pdf417.Truncate = true;
```

* **X‑dimension** 控制每個模組的寬度；設定為 `2` 像素可產生緊湊且仍具可讀性的條碼。  
* **Columns** 決定程式碼使用的資料欄位數量。較少的欄位會使條碼變窄但變高。  
* **Truncate** 會啟用 PDF417 規範中定義的「緊湊」模式，移除不必要的填充列。  

如果您的使用情境需要更高的抗損毀能力，可嘗試調整 `Rows` 與 `ErrorCorrectionLevel`。

## 步驟 4：將條碼儲存為 PNG 圖像

最後，將條碼匯出為 PNG 檔案。PNG 能保留清晰的邊緣並支援透明度，非常適合網頁與列印情境。

```csharp
// Step 6: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\CompactPdf417.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

執行程式會在指定目錄產生 `CompactPdf417.png`。圖像如下所示：

![使用 C# 建立的緊湊 PDF417 條碼](compact-pdf417.png "使用 C# 建立的緊湊 PDF417 條碼範例")

*上述的 alt 文字包含主要關鍵字，滿足 SEO 與可及性需求。*

## 完整、可執行範例

將所有部份組合在一起，以下是一個可自行複製、貼上並執行的完整程式：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1. Initialize the generator with PDF417 type and sample data
        var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");

        // 2. Configure size and compactness
        generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
        generator.Parameters.Barcode.Pdf417.Columns = 3;           // number of columns
        generator.Parameters.Barcode.Pdf417.Truncate = true;       // enable compact mode

        // 3. Optional: increase error correction for damaged prints
        // generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5;

        // 4. Export to PNG
        string outputPath = @"C:\Barcodes\CompactPdf417.png";
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

### 預期輸出

開啟 `CompactPdf417.png` 後，您應該會看到一個垂直的高密度條碼，編碼的字串為 *Åspóse.Barcóde©*。使用任何 PDF417 讀取器掃描此圖像，即可還原原始文字。

## 為何這些設定很重要

* **X‑dimension** 會影響實體尺寸與掃描速度。較小的模組提升資料密度，但可能需要較高解析度的掃描器。  
* **Columns** 會影響長寬比。對於行動收據而言，較少的欄位可使條碼足夠窄，以適應窄紙張。  
* **Truncate** 會減少列數，節省墨水與空間，同時不影響資料完整性，因為 PDF417 已內建錯誤更正碼字。  

了解這些參數後，您即可依目標媒介的限制調整條碼——無論是標籤印表機、網頁或行動應用程式。

## 常見變化與邊緣案例

### 產生其他影像格式

如果您偏好 JPEG 或 BMP，可變更 `BarCodeImageFormat` 列舉：

```csharp
generator.Save(@"C:\Barcodes\Pdf417.jpg", BarCodeImageFormat.Jpeg);
```

JPEG 會壓縮圖像，但可能產生影響小尺寸掃描的雜訊。

### 調整錯誤更正

在惡劣環境（例如戶外標示）下，提升錯誤更正等級：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 8; // max is 8
```

較高的等級會增加冗餘，使條碼變大但更具韌性。

### 編碼二進位資料

PDF417 能編碼二進位負載。傳入 `byte[]` 而非字串：

```csharp
byte[] binaryData = new byte[] { 0x01, 0xFF, 0xA5 };
generator = new BarcodeGenerator(EncodeTypes.Pdf417, binaryData);
```

函式庫會自動切換至二進位模式。

### 處理極長字串

當資料超過預設容量時，產生器會自動產生額外列。您可以限制列數以避免圖像過大：

```csharp
generator.Parameters.Barcode.Pdf417.Rows = 30; // max rows
```

若內容仍無法容納，請考慮將其分割為多個條碼。

## 專業技巧

* **Cache the generator**：如果需要使用相同設定產生大量條碼，快取產生器可避免重複分配內部資源。  
* **Set `Resolution`**：若列印需要特定 DPI，請在 `ImageOptions` 上設定 `Resolution`：

  ```csharp
  generator.Parameters.ImageResolution = 300; // DPI
  ```

* **Validate the output**：使用 `BarCodeReader` 程式化驗證輸出，確保產生的 PNG 在提供給使用者前可被解碼。

## 結論

您現在已了解如何在 C# 中 **建立 PDF417 條碼**，以及如何 **產生條碼 PNG** 檔案，並完整掌控尺寸、欄位與緊湊模式。完整範例示範了標準做法，說明每個設定的意義，並涵蓋錯誤更正、其他格式與二進位資料等變化。請運用上述技巧，將此解決方案套用於您的工作流程，無論是票務系統、物流標籤產生器，或是安全文件編碼器。

---

**下一步**

* 使用相同的 `BarcodeGenerator` 類別探索其他 2D 符號（DataMatrix、QR）。  
* 將條碼產生整合至 ASP.NET Core API，以按需提供 PNG。  
* 結合條碼圖像與 PDF 產生函式庫，直接嵌入報告中。

祝開發順利！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在所示技術之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中建立 pdf417 條碼 – 步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中產生 micro pdf417 條碼 – 步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-micro-pdf417-barcode-in-c-step-by-step-guide/)
- [如何在 C# 中使用緊湊模式建立 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}