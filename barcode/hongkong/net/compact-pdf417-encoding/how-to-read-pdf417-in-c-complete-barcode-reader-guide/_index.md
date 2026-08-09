---
category: general
date: 2026-08-09
description: 如何在 C# 中使用 BarCodeReader 讀取 PDF417。學習讀取條碼 PNG 檔案、處理多條條碼，並提取擴充的元資料。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: zh-hant
lastmod: 2026-08-09
og_description: 如何在 C# 中使用 Aspose.BarCode 讀取 PDF417。本教學示範如何讀取條碼 PNG 檔案、在同一張圖片中處理多個條碼，以及取得擴充的
  PDF417 中繼資料。
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: 如何在 C# 中讀取 PDF417 – 條碼閱讀器教學
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: 如何在 C# 中讀取 PDF417 – 完整條碼閱讀器指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中讀取 PDF417 – 完整條碼閱讀器指南

如果您需要在 .NET 應用程式中 **how to read PDF417**，本指南提供即用的解決方案。您將會看到如何讀取條碼 PNG、在同一張影像中處理多個條碼，以及提取許多掃描器隱藏的擴充 PDF417 欄位。

在物流、票務與文件管理領域，讀取 PDF417 條碼相當常見。完成本教學後，您即可解碼 Macro PDF417 影像、顯示所有結果，並在自訂業務邏輯中使用額外資訊（檔案 ID、段落計數、時間戳記等）。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦相容於 .NET Framework 4.7+）
- Visual Studio 2022 或任何 C# IDE
- **Aspose.BarCode for .NET**（免費試用或授權 NuGet 套件）
- 包含 Macro PDF417 條碼的 PNG 影像（範例檔案名稱為 `ExtPDF417Meta.png`)

> **專業提示：** 使用 NuGet 主控台安裝此函式庫：  
> `dotnet add package Aspose.BarCode`

## 如何使用 BarCodeReader 在 C# 中讀取 PDF417

此解決方案的核心是 `BarCodeReader` 類別。它接受影像路徑以及一個 `DecodeType` 列舉，用以告訴引擎要尋找哪種符號。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### 為什麼這樣可行

- **`DecodeType.MacroPdf417`** 告訴讀取器尋找 Macro PDF417 變體，該變體會儲存您在第 4 步看到的額外欄位。
- `using` 區塊會自動釋放讀取器，釋放檔案句柄。
- `ReadBarCodes()` 會回傳 **所有** 符合請求類型的條碼，即使影像僅包含一個，也滿足 *read multiple barcodes* 的需求。

執行程式會輸出類似以下內容：

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## 使用 C# 條碼讀取器讀取多個條碼

如果影像包含多個 Macro PDF417 符號（例如，掃描的頁面上有一批票券），相同的 `foreach` 迴圈會處理每一個。無需額外程式碼；讀取器會在內部彙總結果。

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### 常見陷阱

- **影像格式：** 讀取器支援 PNG、JPEG、BMP 與 TIFF。若嘗試不支援的格式，將得到空集合。這也是教學強調 *read barcode PNG* 的原因。
- **解析度：** 低解析度影像（< 300 dpi）可能導致遺漏段落。盡可能升級解析度或要求較高品質的掃描。
- **Macro 標誌：** 若遺漏 `DecodeType.MacroPdf417`，引擎僅會解讀普通 PDF417，並捨棄擴充資料。需要 *read barcode extended* 欄位時，務必指定 macro 類型。

## 讀取條碼 PNG 檔案 – 最佳實踐

使用 PNG 檔案相當直接，因為此格式保留無損像素資料。以下是快速檢查清單：

1. 在建立讀取器之前，先確認檔案是否存在。  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. 僅在需要前置處理（旋轉、裁切）時才使用 `Image.FromFile`。`BarCodeReader` 可直接開啟檔案，避免額外的記憶體分配。
3. 若 PNG 含有透明度，讀取器仍能正常運作，因為條碼是繪製在不透明像素上。

## 取得擴充 PDF417 中繼資料

`Extended.Pdf417` 物件會公開 PDF417 規範中定義的所有可選欄位。您可以將這些欄位映射至領域模型、儲存至資料庫，或用於驗證。

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

填充模型：



## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 讀取 DataMatrix 條碼](/barcode/english/net/datamatrix-barcode-reading/)
- [如何使用 Aspose.BarCode 建立條碼 – 緊湊型 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [讀取 DataMatrix 條碼 C# – 產生 DataMatrix 模式（自動）](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}