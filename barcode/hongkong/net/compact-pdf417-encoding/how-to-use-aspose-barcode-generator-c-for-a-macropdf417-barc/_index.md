---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# 讓您輕鬆加入宏資料並產生 PDF417 條碼。一步一步學習如何加入宏元資料並建立
  PDF417 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: zh-hant
lastmod: 2026-10-05
og_description: Aspose 條碼產生器 C# 向您展示如何在幾行程式碼中加入宏元資料並產生 PDF417 條碼。
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Aspose 條碼產生器 C# – 新增宏並產生 PDF417 條碼
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: 如何在 C# 中使用 Aspose 條碼產生器產生 MacroPdf417 條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose Barcode Generator 產生 MacroPdf417 條碼

如果您需要在 C# 中建立 MacroPdf417 條碼，**Aspose Barcode Generator C#** 提供簡潔的 API，能同時處理條碼影像與所需的宏資料。本教學將逐步說明如何加入宏資訊並產生 PDF417 條碼影像，只需幾個步驟。

您將學會如何設定視覺參數、嵌入如檔案 ID 與時間戳記等宏欄位，並將結果儲存為 PNG。無需外部工具——只需要 Aspose.BarCode 函式庫與 .NET 開發環境。

## 前置條件

* 已安裝 .NET 6.0 或更新版本  
* Visual Studio 2022（或任何 C# IDE）  
* 已取得 **Aspose.BarCode for .NET** 的授權或評估版  

此程式碼可在 Windows、Linux 與 macOS 上執行，因為函式庫是跨平台的。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在 Visual Studio 中開啟您的專案，然後在 **Package Manager Console** 執行以下指令：

```powershell
Install-Package Aspose.BarCode
```

此指令會將 `Aspose.BarCode` 程式集及其相依性加入您的專案。

## 步驟 2：建立條碼產生器實例

第一行會為 **MacroPdf417** 符號建立 `BarcodeGenerator` 物件，並提供您想要編碼的文字。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*為什麼這很重要*：`EncodeTypes.MacroPdf417` 參數告訴函式庫需要處理宏相關欄位，您將在下一步設定這些欄位。

## 步驟 3：定義視覺外觀

您可以控制每個模組（最小的黑白方格）的大小，以及 PDF417 矩陣的欄數。調整 `XDimension` 會影響整體影像解析度。

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

增大 `Columns` 會降低條碼高度，而較大的 `XDimension` 則能在高 DPI 螢幕上呈現更清晰的影像。

## 步驟 4：加入宏資料（如何加入宏）

MacroPdf417 需要多個額外欄位來描述來源檔案及其分段。以下屬性直接對應 PDF417 宏規格：

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*為什麼需要這些欄位*：  
* `MacroPdf417FileID` 將所有分段串聯起來，確保掃描器能重新組合原始文件。  
* `MacroPdf417SegmentID` 與 `MacroPdf417SegmentsCount` 讓解碼器知道分段的順序與總數。  
* `MacroPdf417FileSize` 與 `MacroPdf417Checksum` 提供完整性檢查，對於大量資料傳輸相當重要。

## 步驟 5：儲存條碼影像（如何產生 PDF417）

最後，將條碼寫入磁碟。`Save` 方法接受檔案路徑與影像格式。PNG 能保留條碼的清晰邊緣，且不會產生壓縮雜訊。

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

程式執行後，您會在輸出資料夾中看到 **ExtPDF417Meta.png**。開啟此影像即可看到乾淨的 MacroPdf417 條碼，適合列印或嵌入 PDF 中。

### 預期輸出

| 檔案名稱 | 格式 | 尺寸（約） |
|--------------------|--------|----------------------|
| ExtPDF417Meta.png  | PNG    | 300 × 150 px (varies with `XDimension`) |

使用支援 PDF417 的讀取器（例如 ZXing、Aspose.BarCode for .NET）掃描此影像，即可取得原始文字 **“Åspóse.Barcóde©”** 以及所有宏欄位。

## 常見陷阱與避免方法

| 問題 | 發生原因 | 解決方案 |
|-------|----------------|-----|
| **`EncodeTypes` 設定錯誤** | 使用 `EncodeTypes.Pdf417` 而非 `EncodeTypes.MacroPdf417` 會關閉宏欄位。 | 請務必以 `EncodeTypes.MacroPdf417` 建立產生器。 |
| **缺少宏欄位** | 若省略必要的宏欄位，部分掃描器會忽略此條碼。 | 至少填寫 `FileID`、`SegmentID`、`SegmentsCount` 與 `Terminator`。 |
| **`XDimension` 設定過小** | 小於 1 像素的值會在低解析度顯示器上產生無法辨識的條碼。 | 在大多數螢幕與列印情境下，將 `XDimension` 保持在 ≥ 2 像素。 |
| **檔案路徑錯誤** | 提供不存在的相對路徑會拋出例外。 | 使用 `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` 或絕對路徑。 |

## 完整原始碼

以下為完整、可執行的範例，您可以將其複製到新的 Console 專案中。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
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

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

執行程式 (`dotnet run`)。執行完畢後，主控台會顯示成功訊息，且 PNG 檔案會出現在專案的輸出資料夾中。

## 後續步驟

* **編碼更大量資料** – 增加 `Columns` 或調整 `Rows`（透過 `Pdf417.Rows`）以容納更多字元。  
* **嵌入 PDF** – 使用 Aspose.PDF 將產生的 PNG 放入文件中。  
* **掃描驗證** – 利用 `Aspose.BarCode.Reader` 解碼條碼，並以程式方式驗證宏欄位。  

探索這些主題可加深您對 **如何產生 PDF417** 條碼且帶有豐富宏資訊的理解，並為批次文件處理或安全資料交換等實務情境做好準備。

---

*祝程式開發愉快！若您覺得本指南有幫助，歡迎與同事分享或在 GitHub 上為 Aspose.BarCode 倉庫加星。*

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何在 C# 使用 Aspose.BarCode 建立 Macro PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [如何使用 Barcode Generator 在 C# 產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose 條碼範例：在 C# 中產生 Macro PDF417](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}