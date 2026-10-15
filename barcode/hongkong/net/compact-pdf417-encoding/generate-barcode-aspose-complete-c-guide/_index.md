---
category: general
date: 2026-10-14
description: 了解如何使用 Aspose.BarCode 產生 pdf417，加入自訂文字、巨集中繼資料，並在一步一步的 C# 教學中將結果匯出為 PNG
  圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417
- generate barcode aspose
- pdf417 macro metadata
- custom text barcode
- Aspose.BarCode C#
lastmod: 2026-10-14
og_description: 了解如何使用 Aspose.BarCode 產生 pdf417。本指南逐步說明如何加入自訂文字、巨集中繼資料，並將條碼儲存為 PNG
  圖像。
og_image_alt: Screenshot of a MacroPdf417 barcode generated with Aspose.BarCode in
  C#
og_title: 如何產生 pdf417 – 完整 C# 教學指南
schemas:
- author: Aspose
  dateModified: '2026-10-14'
  description: Learn how to generate pdf417 with Aspose.BarCode, add custom text,
    macro metadata, and export the result as a PNG.
  headline: How to generate pdf417 – complete C# guide
  type: TechArticle
tags:
- pdf417
- Aspose.BarCode
- C# barcode generation
- macro barcode
title: 如何產生 pdf417 – 完整 C# 教學指南
url: /zh-hant/net/compact-pdf417-encoding/generate-barcode-aspose-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何產生 pdf417 – 完整 C# 教學

如果您需要 **產生 pdf417** 以用於 MacroPdf417 符號，本教學將帶您完整走過整個流程。您將會看到如何設定宏專屬選項、嵌入自訂 Unicode 文字，並將條碼儲存為 PNG 圖片。完成本指南後，您將擁有一段可直接放入任何 .NET 專案的 C# 程式碼，無論是主控台應用程式、Windows 服務，或是雲端微服務。

## 快速回答
- **我需要什麼函式庫？** Aspose.BarCode for .NET（支援 70+ 種條碼）。  
- **可以加入 Unicode 字元嗎？** 可以 – API 完全支援 UTF‑8 字串，如 `"Åspóse.Barcóde©"`。  
- **生產環境需要授權嗎？** 需要有效的 Aspose.BarCode 授權才能無限制使用；免費評估版可用於測試。  
- **支援哪些 .NET 版本？** .NET 6+、.NET 5、.NET Core 3.1 與 .NET Framework 4.7+。  
- **PNG 是列印的最佳格式嗎？** PNG 保留無損品質，適合高解析度條碼列印。

## 什麼是 pdf417？
`PDF417` 是一種堆疊式線性條碼，每個符號可編碼約 1 700 個字元。它廣泛應用於交通票證、身分證與庫存追蹤，因為它能在緊湊且機器可讀的格式中儲存大量資料。

## 為什麼使用 Aspose.BarCode 產生 pdf417？
Aspose.BarCode 支援 **70+ 條碼類型**，可處理高達 **2 GB** 的檔案而不需將整個文件載入記憶體，並保證 **100 % 符合 ISO/IEC 15438**。在基準測試中，該函式庫能在典型開發筆記型電腦上於 **150 ms** 內產生完整的 MacroPdf417 條碼，足以應付高吞吐量的伺服器情境。

## 前置條件

在開始之前，請確保您已具備：

* **.NET 6.0 或更新版本**（程式碼亦可在 .NET Framework 4.7+ 上執行）。  
* 一份 **有效的 Aspose.BarCode for .NET 授權**（免費試用版可用於開發）。  
* **Visual Studio 2022** 或您偏好的其他 C# IDE。  
* 基本的 C# 語法與物件導向概念。  

除 **Aspose.BarCode** 之外，無需額外的 NuGet 套件。

## 如何使用宏選項產生 pdf417？

載入 `BarcodeGenerator` 並使用 `EncodeTypes.MacroPdf417` 列舉，設定模組大小、配置宏欄位，最後儲存影像。以下步驟示範正確的執行順序，以避免常見陷阱。

### 步驟 1：安裝 Aspose.BarCode NuGet 套件

在 Visual Studio 開啟您的專案，於套件管理員主控台執行以下指令：

```powershell
Install-Package Aspose.BarCode
```

此套件會加入 `Aspose.BarCode` 命名空間，內含本教學中多次使用的 `BarcodeGenerator` 類別。

### 步驟 2：建立 MacroPdf417 的條碼產生器

`BarcodeGenerator` 是 Aspose.BarCode 用來產生條碼的核心類別。  
第一行程式碼會建立一個針對 **MacroPdf417** 符號的 `BarcodeGenerator` 實例，並嵌入您想要編碼的自訂文字。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

// Step 2: Initialize the generator with custom text
using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The rest of the configuration goes here
}
```

`BarcodeGenerator` 為 Aspose.BarCode 的核心類別，負責保存所有編碼選項與渲染設定。

### 步驟 3：定義基本模組大小

`XDimension` 設定條碼中單一模組（像素）的寬度。  
模組大小會影響條碼的視覺密度。將像素值設為 `2` 可產生清晰的影像，適合一般標籤印表機列印。

```csharp
    // Step 3: Set the X‑dimension (module width) in pixels
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

增大此值會使條碼變大，減小則可能在低解析度裝置上造成掃描問題。

### 步驟 4：配置 PDF417 宏專屬的版面選項

`Columns` 決定 PDF417 條碼的資料欄位數。  
MacroPdf417 需要額外的參數，這些設定讓您能將資料切分成多個檔案、辨識每個段落，並驗證完整性。

```csharp
    // Step 4: Macro‑specific layout
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;       // Current segment number
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

`Columns` 屬性會影響條碼寬度，而宏欄位（`FileID`、`SegmentID`、`SegmentsCount`、`FileName`）則讓下游系統能正確重組原始資料。

### 步驟 5：加入額外的宏中繼資料

`MacroPdf417Terminator` 表示目前段落是否為宏系列的最後一段。  
Aspose.BarCode 允許您嵌入可選的宏欄位，如校驗碼、檔案大小、時間戳記以及寄件人/收件人資訊，這些欄位對於稽核與錯誤偵測相當有用。

```csharp
    // Step 5: Optional macro metadata
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                 // CCITT‑16 example
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // Approximate size in bytes
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                       // Creation date
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                       // Marks the last segment
```

校驗碼可防止傳輸錯誤，時間戳記與寄件人欄位則提供下游處理的上下文資訊。將 `MacroPdf417Terminator` 設為 `Set` 即表示此段為宏系列的最後一段。

### 步驟 6：將條碼儲存為 PNG 影像

`Save` 會將產生的條碼影像寫入指定格式的檔案。  
最後，將條碼寫入磁碟。PNG 保留無損品質，最適合掃描使用。

```csharp
    // Step 6: Export the barcode
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

程式執行完畢後，檔案 `ExtPDF417Meta.png` 會包含一張高解析度的 MacroPdf417 條碼，內含自訂文字與所有宏中繼資料。

#### 預期輸出

開啟 `ExtPDF417Meta.png` 會看到垂直排列的條碼，列與欄清晰可辨。使用任何 PDF417 讀取器掃描此影像，會回傳原始字串 **Åspóse.Barcóde©** 以及您設定的宏欄位（檔案 ID、段落 ID、校驗碼等）。

## 如何在不使用宏選項的情況下產生 pdf417？

若要建立標準 PDF417 條碼，只需將符號設定為 `EncodeTypes.Pdf417`，提供要編碼的文字，必要時調整 `XDimension` 與 `Columns` 等尺寸參數，最後呼叫 `Save`。此方式不會使用任何宏專屬屬性，產生單段條碼，適合大多數應用情境。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(
           EncodeTypes.Pdf417, "Standard PDF417 data"))
{
    generator.Parameters.Barcode.XDimension.Pixels = 3;
    generator.Parameters.Barcode.Pdf417.Columns = 6;
    generator.Save("StandardPdf417.png", BarCodeImageFormat.Png);
}
```

此程式碼示範了在不需要宏功能時 **快速產生 pdf417** 的方法。直接答案是：建立 `BarcodeGenerator` 並指定 `EncodeTypes.Pdf417`，設定 `CodeText`，視需要調整 `XDimension` 與 `Columns`，最後以所需的影像格式呼叫 `Save`。

## 常見問題與專業技巧

| 問題 | 為何會發生 | 解決方式 |
|------|------------|----------|
| 條碼太小無法掃描 | X‑dimension 設為 1 像素或欄位數過高 | 將 `XDimension` 設為至少 `2` 像素，且欄位數維持在 `3`~`9` 之間，以符合一般標籤尺寸 |
| Unicode 字元顯示為 � | 專案檔案編碼不一致 | 確認專案檔案以 UTF‑8 儲存，且來源檔案包含正確的 BOM |
| 掃描器忽略宏欄位 | 最後一段未設定 `MacroPdf417Terminator` | 在最後一段設定 `MacroPdf417Terminator = Pdf417MacroTerminator.Set` |
| 圖檔損毀 | 輸出串流未正確關閉 | 使用 `using` 陳述式（如範例所示）確保產生器正確釋放資源 |

## 完整可執行範例

`BarcodeGenerator` 為產生條碼影像的類別。  
將以下程式碼複製到新的主控台應用程式中並執行。程式會產生條碼、儲存檔案，並在主控台印出輸出路徑。

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace AsposeBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with custom Unicode text
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Basic size
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

                // Macro layout
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Optional macro metadata
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save as PNG
                string outputFile = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
                barcodeGenerator.Save(outputFile, BarCodeImageFormat.Png);

                Console.WriteLine($"Barcode saved to: {outputFile}");
            }
        }
    }
}
```

執行程式後會印出類似以下的訊息：

```
Barcode saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

開啟該檔案即可驗證視覺輸出。

## 常見問答

**Q: 可以在 ASP.NET Core Web API 中使用這段程式碼嗎？**  
A: 可以。只要參考 `Aspose.BarCode` 程式集，`BarcodeGenerator` 類別即可在任何 .NET 執行環境（包括 ASP.NET Core）中使用。

**Q: Aspose.BarCode 支援其他影像格式嗎？**  
A: 當然支援。您可以傳入對應的 `BarCodeImageFormat` 列舉值，將條碼儲存為 PNG、JPEG、BMP、TIFF，甚至 SVG。

**Q: 編碼資料的最大長度是多少？**  
A: 單一 PDF417 符號最多可容納約 1 700 個字元；使用 MacroPdf417 時可將資料切分為多段，實質上支援無限長度。

**Q: 能否為條碼加入顏色？**  
A: 能。於呼叫 `Save` 前設定 `ForeColor` 與 `BackColor` 屬性，即可產生彩色條碼。

**Q: 若要直接將條碼嵌入 PDF，該怎麼做？**  
A: 可使用 Aspose.PDF 將產生的 PNG 或 SVG 影像插入 PDF 頁面，或直接使用 Aspose.BarCode 內建的 PDF 匯出功能。

## 結論

您現在已掌握 **如何產生 pdf417** 於 MacroPdf417 符號，能嵌入自訂 Unicode 文字、設定宏中繼資料，並將結果匯出為 PNG 影像。相同的程式模式亦可用於產生不含宏選項的普通 PDF417 條碼，且可輕鬆擴充至 Aspose.BarCode 支援的其他條碼格式。請嘗試不同的 `XDimension`、欄位數與宏欄位組合，以微調條碼以符合您的印表機或掃描器需求。

接下來，您可以探索相關主題，例如 **為 QR Code 建立條碼自訂文字**、使用 `Color` 參數加入顏色濾鏡，或利用 Aspose.PDF 將條碼直接嵌入 PDF 文件。Aspose.BarCode 的彈性讓您只需幾行 C# 程式碼，即可處理從簡單單行條碼到複雜多段宏條碼的各種情境。

祝程式開發順利，並享受 Aspose.BarCode 為您的 .NET 條碼解決方案帶來的可靠性！

## 接下來該學什麼？

以下教學與本指南所示技術緊密相關，能協助您進一步精通 API 功能並探索其他實作方式：

- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何產生 DataMatrix 條碼 – Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/)
- [產生 Barcode Java - 使用 Aspose.BarCode 設定 Code Text](/barcode/english/java/text-and-styling/setting-code-text/)

---

**最後更新：** 2026-10-14  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [使用 Aspose Barcode C 建立 Macro Pdf417 條碼](/barcode/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/)
- [調整條碼大小 C 指南 – 產生 Pdf417 條碼](/barcode/net/compact-pdf417-encoding/adjust-barcode-size-c-guide-to-generate-pdf417-barcodes/)
- [使用 C 從影像讀取條碼 – 完整宏 Pdf417 教學](/barcode/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}