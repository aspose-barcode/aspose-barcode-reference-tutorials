---
category: general
date: 2026-09-10
description: 學習如何使用簡潔的 C# 條碼讀取器範例，從圖像中解碼條碼，僅需幾行程式碼即可讀取 Macro PDF417 代碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- decode barcode from image
- c# barcode reader example
- read barcode C#
- barcode decoding tutorial
- Macro PDF417 C#
language: zh-hant
lastmod: 2026-09-10
og_description: 使用簡短的 C# 條碼讀取器範例，從圖像解碼條碼。遵循一步一步的指南，即時讀取 Macro PDF417 資料。
og_image_alt: Screenshot of console output showing decoded Macro PDF417 barcode information
og_title: 使用 C# 條碼讀取器範例，從圖像解碼條碼
schemas:
- author: Aspose
  dateModified: '2026-09-10'
  description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  headline: Decode barcode from image with a C# barcode reader example
  type: TechArticle
- description: Learn how to decode barcode from image using a concise C# barcode reader
    example that reads Macro PDF417 codes in just a few lines.
  name: Decode barcode from image with a C# barcode reader example
  steps:
  - name: '**Initialize** a `BarCodeReader` for the target image.'
    text: '**Initialize** a `BarCodeReader` for the target image.'
  - name: '**Iterate** over every detected barcode.'
    text: '**Iterate** over every detected barcode.'
  - name: '**Print** the standard and extended Macro PDF417 data.'
    text: '**Print** the standard and extended Macro PDF417 data.'
  type: HowTo
tags:
- barcode
- C#
- image processing
title: 使用 C# 條碼閱讀器範例從圖像解碼條碼
url: /zh-hant/net/compact-pdf417-encoding/decode-barcode-from-image-with-a-c-barcode-reader-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 條碼閱讀器範例從影像解碼條碼

如果您需要 **從影像解碼條碼**，本指南將一步步示範如何在 C# 中完成。透過簡潔的 **C# 條碼閱讀器範例**，您只需幾行程式碼即可讀取 Macro PDF417 資料。

您將看到完整、可執行的程式、了解每個部分的意義，並學習避免常見陷阱的技巧。無需外部文件說明——所有資訊皆在此處。

## 您將學會

- 設定條碼解碼所需的 NuGet 套件。  
- 撰寫 **C# 條碼閱讀器範例**，開啟影像檔並擷取所有條碼。  
- 取得 Macro PDF417 的延伸欄位，例如檔案 ID。  
- 驗證輸出結果，並將程式碼套用到其他條碼類型。

### 前置條件

- .NET 6.0 SDK 或更新版本（程式碼亦相容 .NET Core 3.1 與 .NET Framework 4.7+）。  
- 具備 C# 主控台應用程式的基本概念。  
- 一張包含 Macro PDF417 條碼的影像檔（例如 `MacroPdf417.png`）。  

## 步驟 1：安裝條碼函式庫

此範例使用 **Aspose.BarCode for .NET**，這是一套廣受使用、支援 Macro PDF417 解碼的函式庫。

```bash
dotnet add package Aspose.BarCode
```

> **為何選擇此函式庫？**  
> 它提供單一的 `BarCodeReader` 類別即可處理多種格式，具備高精度，且會回傳 Macro PDF417 代碼的延伸資訊——全部不需額外設定。

## 步驟 2：建立 C# 條碼閱讀器範例

建立新的主控台專案，並將產生的 `Program.cs` 替換為以下程式碼。範例分為三個明確步驟：

1. **初始化** `BarCodeReader` 以讀取目標影像。  
2. **遍歷** 每一個偵測到的條碼。  
3. **輸出** 標準與延伸的 Macro PDF417 資料。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Path to the image that contains the Macro PDF417 barcode
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // 1️⃣ Create a BarCodeReader configured for Macro PDF417 decoding
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Read all barcodes found in the image
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Display basic information
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    // 3️⃣ Display Macro PDF417 extended fields (if available)
                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

### 各段落說明

- **`BarCodeReader` 建構子** – 第一個參數為影像路徑；第二個參數指示函式庫僅搜尋 Macro PDF417 代碼。此聚焦解碼較掃描所有格式更有效率。  
- **`ReadBarCodes()`** – 回傳影像中偵測到的所有條碼集合，讓您一次處理多個代碼。  
- **`result.Extended.Pdf417.MacroPdf417FileID`** – Macro PDF417 會儲存額外的中繼資料（檔案 ID、段落數等）。範例會先檢查是否為 null，以避免在非 Macro 條碼時拋出 `NullReferenceException`。

## 步驟 3：執行程式並驗證輸出

編譯並執行主控台應用程式：

```bash
dotnet run
```

您應該會看到類似以下的輸出：

```
Code Type: MacroPdf417
Code Text: 1234567890ABCDEF
Macro PDF417 File ID: 42
----------------------------------------
```

若影像未包含 Macro PDF417 條碼，程式仍會列出其他偵測到的格式，只是不會顯示延伸欄位。

## 專業提示：以最小變更解碼其他條碼類型

若要 **從影像解碼條碼** 為其他格式，只需更改 `DecodeType` 列舉值：

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.QR))
```

亦可傳入 `DecodeType.AllSupportedTypes`，讓函式庫自動偵測所有支援的條碼。

## 常見陷阱與避免方式

| 症狀 | 原因 | 解決方法 |
|------|------|----------|
| 完全沒有輸出 | 影像路徑錯誤或檔案格式不支援 | 核對路徑，確保檔案為支援的影像格式（PNG、JPEG、BMP） |
| `result.Extended` 為 null（Macro PDF417） | 條碼不是 Macro PDF417 變體 | 確認來源影像確實包含 Macro PDF417 代碼 |
| 例外 `System.IO.FileNotFoundException` | 執行時缺少 NuGet 套件 | 執行 `dotnet restore`，並確保 `Aspose.BarCode.dll` 已複製至輸出資料夾 |

## 完整程式碼供快速複製

以下即為完整程式，直接貼入 `Program.cs` 即可使用，無需其他檔案。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            const string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"Code Type: {result.CodeTypeName}");
                    Console.WriteLine($"Code Text: {result.CodeText}");

                    if (result.Extended?.Pdf417?.MacroPdf417FileID != null)
                    {
                        Console.WriteLine($"Macro PDF417 File ID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    }

                    Console.WriteLine(new string('-', 40));
                }
            }
        }
    }
}
```

## 後續步驟

- **探索其他延伸欄位** 如 `MacroPdf417SegmentID` 或 `MacroPdf417FileSize`，以建構完整文件重組工作流程。  
- **將閱讀器整合至 Web API**，讓客戶端上傳影像即時取得解碼結果。  
- **效能基準測試**：對大量影像批次解碼；新版 Aspose 支援非同步處理，可進一步提升效能。

---

透過本 **C# 條碼閱讀器範例**，您已掌握可靠的 **從影像解碼條碼** 方法，並能擷取豐富的 Macro PDF417 資訊。嘗試不同的 `DecodeType` 值，結合檔案監控或行動後端，即可讓您的條碼處理能力隨需求擴展。

## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您在本主題的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能與替代實作方式。

- [如何在 C# 中讀取 PDF417 – 完整條碼閱讀器範例](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-example/)
- [產生帶文字的條碼 – 完整 PDF417 Macro 教學](/barcode/english/net/compact-pdf417-encoding/generate-barcode-with-text-full-pdf417-macro-guide/)
- [如何使用 Aspose 建立 PDF417 條碼 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}