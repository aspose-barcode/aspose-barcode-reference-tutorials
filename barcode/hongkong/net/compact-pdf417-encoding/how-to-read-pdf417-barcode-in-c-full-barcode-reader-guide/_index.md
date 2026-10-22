---
category: general
date: 2026-10-21
description: 如何在 C# 中使用條碼讀取器從圖片讀取 PDF417 條碼。請參考此逐步 C# 條碼讀取器範例，以獲得可靠的解碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417 barcode
- read barcode from image c#
- c# barcode reader example
- macro pdf417 decoding
- barcode extended fields c#
language: zh-hant
lastmod: 2026-10-21
og_description: 如何在 C# 中讀取 PDF417 條碼，並提供完整的條碼閱讀器範例。學習解碼 Macro PDF417 圖像，並存取所有擴充欄位。
og_image_alt: Console output showing decoded PDF417 barcode fields in a C# application
og_title: 如何在 C# 中讀取 PDF417 條碼 – 詳細指南
schemas:
- author: Aspose
  dateModified: '2026-10-21'
  description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  headline: How to read PDF417 barcode in C# – full barcode reader guide
  type: TechArticle
- description: How to read PDF417 barcode in C# using a barcode reader from image.
    Follow this step‑by‑step C# barcode reader example for reliable decoding.
  name: How to read PDF417 barcode in C# – full barcode reader guide
  steps:
  - name: Initialise the `BarCodeReader` for the specific `DecodeType`.
    text: Initialise the `BarCodeReader` for the specific `DecodeType`.
  - name: Iterate through the returned `BarCodeResult` collection.
    text: Iterate through the returned `BarCodeResult` collection.
  - name: Access both basic and extended PDF417 fields.
    text: Access both basic and extended PDF417 fields.
  - name: '**Create a new console project**'
    text: '**Create a new console project**'
  - name: '**Add the Aspose.BarCode package** (as shown earlier).'
    text: '**Add the Aspose.BarCode package** (as shown earlier).'
  - name: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
    text: '**Copy the image file** into the project folder or reference it with an
      absolute path.'
  - name: '**Build and run**'
    text: '**Build and run**'
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中讀取 PDF417 條碼 – 完整條碼閱讀指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-barcode-in-c-full-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 條碼 – 完整條碼閱讀器指南

如果您需要在 .NET 應用程式中 **how to read PDF417 barcode**，本指南將為您展示一個即時可執行的解決方案。您將會看到如何使用流行的條碼函式庫 **read barcode from image C#**，並在不需額外工具的情況下取得所有 Macro PDF417 屬性。

本教學涵蓋 **C# barcode reader example** 所需的全部內容：專案設定、程式碼說明，以及處理邊緣情況的技巧。完成後，您即可將程式碼貼入主控台專案，即時開始解碼 PDF417 圖片。

## 您需要的條件

在開始之前，請確認以下先決條件：

| Prerequisite | Reason |
|--------------|--------|
| .NET 6.0 SDK or later | 為 C# 主控台應用程式提供執行環境 |
| Visual Studio 2022 (or any C# IDE) | 讓專案建立與除錯變得簡單 |
| Aspose.BarCode for .NET (NuGet package) | 提供 `BarCodeReader` 與 `DecodeType` 類別 |
| A Macro PDF417 image file (e.g., `MacroPdf417.png`) | 作為解碼的輸入檔案 |

您可以使用 dotnet CLI 安裝此函式庫：

```bash
dotnet add package Aspose.BarCode
```

## 如何在 C# 中從圖像讀取 PDF417 條碼

**read barcode from image C#** 工作流程的核心包含三個動作：

1. 初始化特定 `DecodeType` 的 `BarCodeReader`。
2. 遍歷返回的 `BarCodeResult` 集合。
3. 存取基本與擴充的 PDF417 欄位。

以下是完整且可執行的程式碼。請將其儲存為 `Program.cs`，放在主控台專案中。

```csharp
using System;
using Aspose.BarCode;               // Provides BarCodeReader, DecodeType, BarCodeResult
using Aspose.BarCode.BarCodeRecognition; // Contains extended PDF417 structures

class Program
{
    static void Main()
    {
        // Step 1: Initialise a BarCodeReader for a Macro PDF417 image
        // Replace the path with the location of your MacroPdf417.png file
        string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

        using (BarCodeReader barcodeReader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes present in the image
            foreach (BarCodeResult barcodeResult in barcodeReader.ReadBarCodes())
            {
                // Step 3: Display basic barcode information
                Console.WriteLine($"CodeType: {barcodeResult.CodeTypeName}");
                Console.WriteLine($"CodeText: {barcodeResult.CodeText}");

                // Step 4: Show Macro PDF417 specific extended fields
                Console.WriteLine($"File ID: {barcodeResult.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Segment ID: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Segments Count: {barcodeResult.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"File Name: {barcodeResult.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Checksum: {barcodeResult.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"File Size: {barcodeResult.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"TimeStamp: {barcodeResult.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Addressee: {barcodeResult.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Sender: {barcodeResult.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"Terminator: {barcodeResult.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### 各步驟說明

* **Step 1 – Initialise the reader**  
  `BarCodeReader` 建構子接受圖像檔案路徑與 `DecodeType`。`DecodeType.MacroPdf417` 告訴函式庫尋找 Macro PDF417 符號，這些符號包含比普通 PDF417 條碼更多的中繼資料。

* **Step 2 – ReadBarCodes()**  
  此方法回傳 `IEnumerable<BarCodeResult>`，若圖像中包含多個條碼，集合中可能會有多筆。`foreach` 迴圈確保每個偵測到的符號都會被處理。

* **Step 3 – Basic information**  
  `CodeTypeName` 用於辨識條碼格式（例如 “MacroPDF417”）。`CodeText` 保存符號中編碼的原始資料字串。

* **Step 4 – Extended fields**  
  Macro PDF417 在 `barcodeResult.Extended.Pdf417` 下加入一組擴充屬性。這些欄位揭露檔案層級的資料，如 `FileID`、`SegmentID` 與 `FileName`。直接存取它們可讓您重建多段文件或驗證完整性。

#### 預期的主控台輸出

```
CodeType: MacroPDF417
CodeText: 1234567890
File ID: 5
Segment ID: 1
Segments Count: 3
File Name: invoice_2024.pdf
Checksum: 0A3F
File Size: 254321
TimeStamp: 2024-03-15T10:45:12Z
Addressee: Acme Corp.
Sender: Warehouse 12
Terminator: END
----------------------------------------
```

實際數值會反映您 `MacroPdf417.png` 中編碼的內容。若圖像僅包含單一段，`SegmentsCount` 將為 1，`SegmentID` 為 0。

## 設定 C# 條碼閱讀器環境

可靠的 **C# barcode reader example** 取決於乾淨的專案設定：

1. **建立新的主控台專案**  
   ```bash
   dotnet new console -n Pdf417ReaderDemo
   cd Pdf417ReaderDemo
   ```
2. **加入 Aspose.BarCode 套件**（如前所示）。
3. **將影像檔案複製** 到專案資料夾，或以絕對路徑引用它。
4. **建置並執行**  
   ```bash
   dotnet run
   ```

如果建置失敗並顯示缺少參考錯誤，請確認 `using Aspose.BarCode;` 陳述式與已安裝的套件版本相符。此函式庫的 API 在 .NET 6 與 .NET 8 之間保持穩定，您可升級執行環境而無需修改程式碼。

## 解碼 Macro PDF417 條碼

當您呼叫 `ReadBarCodes()` 時，函式庫會在內部執行以下步驟：

* **Image preprocessing** – 將位圖轉換為二元矩陣，校正旋轉與雜訊。  
* **Pattern detection** – 掃描 PDF417 的起始/終止圖樣，並提取模組寬度。  
* **Error correction** – 套用 Reed‑Solomon 編碼以復原受損的碼字。  
* **Macro extraction** – 解析擴充的 PDF417 段標頭，並填充 `Extended.Pdf417` 物件。

了解此流程有助於您判斷何時調整解碼器選項。例如，若影像對比度低，您可以啟用 `BarCodeReader` 的 `ReadQuality` 屬性（在較新版本中提供），以提升偵測率。

## 解析擴充的 PDF417 欄位

這些擴充欄位直接對應至 Macro PDF417 規範：

| Field | Meaning |
|-------|---------|
| `MacroPdf417FileID` | 整個檔案在所有段落中的唯一識別碼 |
| `MacroPdf417SegmentID` | 目前段落的零基索引 |
| `MacroPdf417SegmentsCount` | 組成檔案的總段數 |
| `MacroPdf417FileName` | 編碼時儲存的原始檔案名稱 |
| `MacroPdf417Checksum` | 用於完整性驗證的 16 位元檢查碼 |
| `MacroPdf417FileSize` | 原始檔案的位元組大小 |
| `MacroPdf417TimeStamp` | 條碼產生時的 UTC 時間戳記 |
| `MacroPdf417Addressee` | 文件的預定收件人 |
| `MacroPdf417Sender` | 文件的發件人 |
| `MacroPdf417Terminator` | 表示最後一段的字面字串 “END” |

您可以利用這些值重建多段 PDF、驗證是否有遺漏段落，或為合規目的記錄稽核資訊。

## 常見問題與故障排除

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| No output appears | 圖像路徑不正確或格式不受支援 | 使用絕對路徑，並確保檔案為 Aspose.BarCode 支援的 PNG/JPEG |
| `CodeType` shows “PDF417” instead of “MacroPDF417” | 圖像包含一般 PDF417 符號，未使用宏變體 | 確認來源條碼已使用 Macro PDF417 擴充編碼 |
| Some fields are empty | 條碼在產生時未包含那些宏欄位 | 使用完整的宏負載編碼條碼，或在程式碼中處理 null 值 |
| Decoder throws `ArgumentException` | 指定了錯誤的 `DecodeType` | 若只需要標準 PDF417 資料，將 `DecodeType.MacroPdf417` 改為 `DecodeType.Pdf417` |

**小技巧：** 若預期會遇到非宏條碼，請將欄位存取包在 null 檢查中。當資料缺失時，`Extended.Pdf417` 物件會回傳預設值（例如數值欄位回傳 `0`）。

```csharp
int fileId = barcodeResult.Extended?.Pdf417?.MacroPdf417FileID ?? -1;
```

## 完整範例回顧

將所有內容整合後，最終程式由 using 指令、`Main` 方法以及前述的四步迴圈組成。無需額外的設定檔。編譯並執行專案，即可在主控台看到所有 Macro PDF417 屬性。

## 結論

您現在已了解如何在 C# 中 **how to read PDF417 barcode**，並使用簡潔的 **C# barcode reader example**。本指南帶您完成環境設定、程式碼實作，以及每個擴充 Macro PDF417 欄位的解讀。憑藉此基礎，您可將條碼掃描整合至庫存系統、文件管理工作流程或行動後端。

### 下一步

## 接下來您應該學習什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整的可執行程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中讀取 PDF417 – 完整條碼閱讀器指南](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [如何在 C# 中使用條碼閱讀器範例解碼 PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-in-c-with-a-barcode-reader-example/)
- [如何在 C# 中使用 Macro PDF417 選項建立 PDF417 條碼圖像](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}