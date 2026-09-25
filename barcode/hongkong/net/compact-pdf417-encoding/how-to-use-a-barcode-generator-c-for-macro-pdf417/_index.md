---
category: general
date: 2026-08-22
description: 條碼產生器 C# 教學示範如何使用 Aspose.BarCode 建立帶有元資料的 Macro PDF417 條碼，並將其儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: zh-hant
lastmod: 2026-08-22
og_description: 條碼產生器 C# 讓您能夠產生帶有完整檔案層級中繼資料的 Macro PDF417 條碼，並匯出為 PNG。請遵循本指南實作此解決方案。
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: 條碼產生器 C# – 逐步創建 Macro PDF417 條碼
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中使用條碼產生器產生 Macro PDF417
url: /zh-hant/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用條碼產生器產生 Macro PDF417

如果您需要一個 **barcode generator C#** 能夠產生帶有檔案層級中繼資料的 Macro PDF417 符號，本指南提供完整、可直接執行的解決方案。您將會看到如何設定條碼外觀、嵌入如檔案 ID 與段落計數等宏資訊，最後將結果儲存為 PNG 圖片。

本範例使用 Aspose.BarCode 函式庫，這是一個廣受採用的 **C# barcode library**，支援完整的 PDF417 功能集。無需外部服務，且程式碼可於 .NET 6 或更新版本執行。

## 前置條件

* 已安裝 .NET 6 SDK（或任何更新版本）。
* Visual Studio 2022、VS Code 或其他 C# IDE。
* 參考 **Aspose.BarCode** 的 NuGet 套件 (`dotnet add package Aspose.BarCode`)。

了解基本的 C# 語法與 PDF417 條碼概念將有助於您跟隨步驟，但本教學會詳細說明每個設定選項。

## 本教學涵蓋內容

* 為 Macro PDF417 格式初始化 **barcode generator C#** 實例。  
* 調整視覺參數，如 X‑dimension 與欄位數。  
* 提供 Macro PDF417 檔案層級欄位：file ID、segment ID、segment count、file name、checksum、file size、timestamp、addressee、sender 與 terminator。  
* 將產生的符號儲存為 PNG 檔案。  
* 處理大型檔案或自訂時間戳等邊緣情況的技巧。

閱讀完本篇文章後，您將擁有一個自包含的程式，可產生完全符合規範的 Macro PDF417 條碼。

## 步驟 1：建立 barcode generator C# 實例

第一步是以 `EncodeTypes.MacroPdf417` 列舉值以及您想編碼的文字來實例化 `BarcodeGenerator`。建構子同時接受 payload 字串，該字串會成為宏條碼的資料部份。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**為什麼這很重要** – `EncodeTypes.MacroPdf417` 旗標告訴 Aspose.BarCode 將此符號視為宏條碼，從而啟用後續的額外欄位。若未設定此旗標，函式庫會產生普通的 PDF417 條碼，且不含檔案層級的中繼資料。

## 步驟 2：調整基本條碼外觀（PDF417 視覺設定）

視覺清晰度對於可靠掃描至關重要。兩個常見參數為模組寬度（`XDimension`）與欄位數。設定這些值可在尺寸與可讀性之間取得平衡。

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` 控制每條黑白條的寬度。**2** 的數值對大多數標籤印表機而言表現良好。  
* `Pdf417.Columns` 定義條碼使用的欄位數。五欄可產生緊湊的符號，同時不犧牲資料容量。

## 步驟 3：定義 Macro PDF417 檔案層級資訊

Macro PDF417 在標準 PDF417 格式上擴充了描述大型檔案如何分割成多個條碼段的欄位。提供這些欄位可確保下游掃描器能重建原始檔案。

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` 必須在屬於同一邏輯檔案的所有段落中保持相同。  
* `MacroPdf417SegmentID` 從 **0** 依序遞增至 `SegmentsCount‑1`。  
* `MacroPdf417SegmentsCount` 告訴解碼器預期的段落總數。  
* `MacroPdf417FileName` 為可選項，但有助於人類可讀的辨識。

## 步驟 4：設定其他宏中繼資料

除了核心檔案資訊外，規範還允許額外欄位，如 checksum、file size、timestamp、addressee、sender 以及 terminator 旗標。填寫這些欄位可提升資料完整性與可追溯性。

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` 為整個檔案提供 16 位元 CCITT checksum；解碼器可在重建後驗證完整性。  
* `MacroPdf417FileSize` 應反映原始檔案的精確位元組數；若值大於 `2^31‑1`，需使用 64 位元欄位，Aspose 會自動處理。  
* `MacroPdf417TimeStamp` 記錄條碼產生的時間。請使用 UTC 以避免時區歧義。  
* `MacroPdf417Addressee` 與 `MacroPdf417Sender` 為自由格式字串，可存放路由資訊。  
* `MacroPdf417Terminator` 表示此為最後段落；最後一段請設為 `Set`，否則保留預設 (`NotSet`)。

**邊緣情況提示** – 若檔案大小超過 4 GB，請將內容分割成多個宏段，並相應調整 `SegmentsCount`。函式庫會在不發生溢位的情況下處理大型尺寸欄位。

## 步驟 5：將條碼儲存為 PNG 圖片

最後一步將產生的符號寫入磁碟。PNG 能保留精確的像素尺寸，且被掃描硬體廣泛支援。

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

將 `YOUR_DIRECTORY` 替換為執行程序可寫入的絕對或相對路徑。`BarCodeImageFormat.Png` 列舉確保無損輸出。

**為什麼選擇 PNG？** – PNG 等點陣格式能保持模組邊緣銳利，這對依賴高對比度邊緣的掃描器至關重要。若需要向量格式，Aspose 亦支援 `Pdf` 與 `Svg`。

## 完整可執行範例

以下是完整程式碼，您可將其複製到主控台應用程式中。它包含必要的 `using` 指令與 `Main` 方法。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### 預期輸出

執行程式會在專案的工作目錄中產生名為 **MacroPdf417.png** 的檔案。開啟圖片會看到帶有嵌入宏欄位的緊湊 PDF417 條碼。使用支援 PDF417 的讀取器（例如 ZXing、Aspose.BarCode 解碼器）掃描此圖像，可取得原始的 `"Sample text"` payload 以及宏中繼資料。

## 常見問題與故障排除

| Question | Answer |
|----------|--------|
| *如果條碼對目標標籤來說太大怎麼辦？* | 降低 `XDimension.Pixels` 或增加 `Pdf417.Columns`。兩個參數皆會影響整體尺寸。 |
| *我可以產生向量圖像而非 PNG 嗎？* | 可以。呼叫 `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` 以取得可縮放的輸出。 |
| *掃描後如何驗證 checksum？* | Aspose.BarCode 解碼器會自動驗證 `MacroPdf417Checksum`，並在 `MacroPdf417Result` 物件中回報不匹配情況。 |
| *此函式庫是否相容 .NET Core？* | NuGet 套件支援 .NET Standard 2.0+，涵蓋 .NET Core、.NET 5、.NET 6 及之後的版本。 |
| *如果需要嵌入二進位資料而非文字該怎麼辦？* | 將二進位 payload 轉為 Base64，或使用接受 byte 陣列的 `EncodeTypes.MacroPdf417` 重載。 |

## 生產環境的專業提示

* **Cache the generator** –

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎延伸。每個資源皆包含完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何使用 Aspose.BarCode 建立條碼 – 緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何在 Java 中使用 Aspose.BarCode 從 PDF 讀取條碼](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [使用 Aspose.Barcode 建立 Codabar 條碼 – 產生器與讀取器 API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}