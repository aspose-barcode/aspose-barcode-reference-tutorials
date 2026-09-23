---
category: general
date: 2026-09-22
description: 使用 Aspose.BarCode 於 C# 建立宏式 PDF417 條碼。一步一步學習如何使用 Aspose 產生條碼、設定中繼資料，並儲存為
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- generate barcode with Aspose
- Aspose.BarCode PDF417
- C# barcode generation
- barcode metadata configuration
language: zh-hant
lastmod: 2026-09-22
og_description: 使用 Aspose.BarCode 在 C# 中建立宏 PDF417 條碼。本指南將示範如何使用 Aspose 產生條碼、設定宏中繼資料，並匯出圖像。
og_image_alt: Screenshot of a created macro PDF417 barcode using Aspose.BarCode in
  C#
og_title: 使用 Aspose.BarCode (C#) 建立宏 PDF417 條碼 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-22'
  description: Create macro PDF417 barcode using Aspose.BarCode in C#. Learn step‑by‑step
    how to generate barcode with Aspose, configure metadata, and save as PNG.
  headline: Create macro PDF417 barcode with Aspose.BarCode (C#)
  type: TechArticle
tags:
- Aspose
- PDF417
- C#
- Barcode
title: 使用 Aspose.BarCode (C#) 建立宏 PDF417 條碼
url: /zh-hant/net/compact-pdf417-encoding/create-macro-pdf417-barcode-with-aspose-barcode-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode (C#) 建立宏式 PDF417 條碼

如果您需要在 .NET 應用程式中 **建立宏式 PDF417 條碼**，本教學將會完整示範如何使用 Aspose.BarCode。您將看到一個完整、可執行的範例，**使用 Aspose 產生條碼**、設定所有宏專屬欄位，並將結果儲存為 PNG 圖片。

條碼常用於庫存、運輸或文件追蹤，而 Macro PDF417 變體允許您在條碼內嵌入額外的檔案層級中繼資料。完成本指南後，您將能產生符合 ISO/IEC 15438 標準的完整功能宏式 PDF417 條碼。

## 您需要的環境

* .NET 6.0 SDK 或更新版本（此程式碼適用於 .NET Core 與 .NET Framework）
* Visual Studio 2022（或任何 C# IDE）
* 具備可連線至 NuGet 的網路環境，以取得 Aspose.BarCode 套件
* 具備基本的 C# 語法知識

上述前置條件可確保程式碼在未額外設定的情況下順利編譯。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

Aspose.BarCode 函式庫提供了在本教學中全程使用的 `BarcodeGenerator` 類別。

```bash
dotnet add package Aspose.BarCode
```

執行此指令會將最新的穩定版加入您的專案檔案（`*.csproj`）。此套件支援 PDF417、Macro PDF417 以及其他多種條碼類型。

## 步驟 2：建立新的 Console 專案（可選）

如果您想從頭開始，請產生一個 console 應用程式：

```bash
dotnet new console -n MacroPdf417Demo
cd MacroPdf417Demo
```

產生的 `Program.cs` 會放置條碼產生的程式碼。

## 步驟 3：初始化條碼產生器

產生器使用 `EncodeTypes.MacroPdf417` 列舉值以及您欲編碼的文字建立。Aspose.BarCode 會自動處理 Unicode 字元，您可以直接加入帶重音的字母或符號。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using System;

class Program
{
    static void Main()
    {
        // Step 3: Create a Macro PDF417 barcode generator with the desired text
        using (var barcodeGenerator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
        {
            // The rest of the configuration follows...
```

### 為何這很重要
`EncodeTypes.MacroPdf417` 告訴函式庫使用 PDF417 的宏版，從而能在條碼內嵌入檔案層級的中繼資料（檔案 ID、段落數量等）。文字 `"Åspóse.Barcóde©"` 示範了產生器能正確編碼 UTF‑8 字元。

## 步驟 4：設定基本條碼尺寸

PDF417 允許您控制欄位數量與 X‑dimension（單一模組的寬度）。調整這些數值會影響條碼的實體大小與掃描可靠性。

```csharp
            // Step 4: Set basic barcode dimensions
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

* **XDimension** – 較小的值會產生較密集的條碼；較大的值則有助於低解析度掃描器。
* **Columns** – 控制資料欄位的數量；常見範圍為 1 至 30。

## 步驟 5：設定 Macro PDF417 中繼資料

Macro PDF417 包含描述條碼所代表檔案的額外欄位。每個欄位皆為選填，但設定後可提升與支援宏格式掃描器的相容性。

```csharp
            // Step 5: Configure Macro PDF417 metadata
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // demo checksum
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000; // bytes
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

### 各欄位說明

| 屬性 | 用途 | 典型範圍 |
|----------|---------|---------------|
| **MacroPdf417FileID** | 邏輯檔案的唯一識別碼，該檔案可能分割於多個條碼中。 | 0‑2³²‑1 |
| **MacroPdf417SegmentID** | 目前段落的索引（從 0 開始）。 | 0‑(SegmentsCount‑1) |
| **MacroPdf417SegmentsCount** | 構成完整檔案的段落總數。 | 1‑99 |
| **MacroPdf417FileName** | 檔案的可讀名稱。 | 最多 255 個字元 |
| **MacroPdf417Checksum** | 用於錯誤偵測的可選檢查碼。 | 0‑65535 |
| **MacroPdf417FileSize** | 原始檔案的位元組大小。 | 0‑2³²‑1 |
| **MacroPdf417TimeStamp** | 檔案建立或修改的時間戳記。 | 任意 `DateTime` |
| **MacroPdf417Addressee** | 目的地識別碼（例如部門或機器）。 | 自由格式字串 |
| **MacroPdf417Sender** | 來源識別碼（例如公司名稱）。 | 自由格式字串 |
| **MacroPdf417Terminator** | 指示此段是否為最後一段。 | `Set` or `Unset` |

**小技巧：** 若將大型檔案分割成多個條碼，請確保每個段落的 `SegmentID` 為連續編號，且 `SegmentsCount` 在所有段落中保持一致。掃描器會依賴這些值來重建原始檔案。

## 步驟 6：儲存條碼影像

Aspose.BarCode 支援多種輸出格式（PNG、JPEG、BMP、SVG 等）。PNG 提供無損品質，適合測試與文件說明。

```csharp
            // Step 6: Save the barcode image as PNG
            barcodeGenerator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
        }
    }
}
```

執行程式後會在專案的輸出目錄（`bin/Debug/net6.0/`）產生名為 `ExtPDF417Meta.png` 的檔案。使用任何影像檢視器開啟，即可驗證條碼是否正確呈現。

## 步驟 7：驗證產生的條碼（可選）

如果您有 PDF417 掃描應用程式（行動或桌面），掃描已儲存的 PNG。掃描器應回傳：

* 編碼文字 `"Åspóse.Barcóde©"`
* 您設定的所有宏欄位（檔案 ID、段落 ID 等）

若需自動化驗證，Aspose.BarCode 亦提供 `BarCodeReader` 類別：

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

using (var reader = new BarCodeReader("ExtPDF417Meta.png", DecodeType.Pdf417))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
    {
        Console.WriteLine($"Text: {result.CodeText}");
        Console.WriteLine($"Macro File ID: {result.GetMacroPdf417FileID()}");
        // Access other macro properties similarly
    }
}
```

此程式碼片段示範了如何以程式方式讀取宏中繼資料，確認 **使用 Aspose 產生條碼** 能端對端運作。

## 邊緣情況與最佳實踐

| 情況 | 建議處理方式 |
|-----------|----------------------|
| **Unicode 字元** | 確保來源字串為 UTF‑8（.NET 預設）。Aspose.BarCode 會自動編碼 Unicode，但請確認掃描器的字元集。 |
| **大型檔案** | Macro PDF417 可將檔案分割成最多 99 個段落。若檔案超過 400 KB，請增加 `SegmentsCount` 並產生多個條碼，每個條碼的 `SegmentID` 依序遞增。 |
| **時間戳記精度** | 使用 `DateTime.UtcNow` 取得 UTC 時間；部分掃描器預期使用 UTC。 |
| **檢查碼驗證** | 若在接收端需要驗證完整性，請提供正確的檢查碼。 |
| **不同影像格式** | 若需無限可縮放的條碼，請使用 `BarCodeImageFormat.Svg` 產生向量圖形。 |
| **效能** | 產生大量條碼時，重複使用同一個 `BarcodeGenerator` 實例；僅在每次迭代間變更 `Parameters`。 |

## 完整、可執行範例

以下為完整程式碼，您可直接複製、貼上並執行（前提是已安裝 NuGet 套件）。



## 接下來應該學什麼？

以下教學涵蓋與本指南緊密相關的主題，讓您進一步掌握 API 功能並探索其他實作方式：

- [Aspose 條碼範例：在 C# 中產生 Macro PDF417](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)
- [在 C# 中建立 PDF417 條碼中繼資料 – 完整步驟指南](/barcode/english/net/compact-pdf417-encoding/create-pdf417-barcode-metadata-in-c-complete-step-by-step-gu/)
- [如何使用 Aspose 在 C# 中產生 PDF417 條碼影像](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}