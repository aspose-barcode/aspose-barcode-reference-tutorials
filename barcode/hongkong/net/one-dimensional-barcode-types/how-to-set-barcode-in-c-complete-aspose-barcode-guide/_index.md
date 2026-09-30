---
category: general
date: 2026-08-06
description: 如何在 C# 中使用 Aspose.BarCode 設定條碼。學習如何變更宏字元並以逐步程式碼建立條碼圖像（C#）。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to change macro
- barcode generator c#
- create barcode image c#
language: zh-hant
lastmod: 2026-08-06
og_description: 如何在 C# 中使用 Aspose.BarCode 設定條碼。本指南快速示範如何變更宏字符並建立條碼圖像。
og_image_alt: Screenshot of a MicroPDF417 barcode generated with C# code
og_title: 如何在 C# 中設定條碼 – Aspose.BarCode 教學
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: How to set barcode using Aspose.BarCode in C#. Learn how to change
    macro characters and create barcode image C# with step‑by‑step code.
  headline: How to set barcode in C# – complete Aspose.BarCode guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中設定條碼 – 完整的 Aspose.BarCode 指南
url: /zh-hant/net/one-dimensional-barcode-types/how-to-set-barcode-in-c-complete-aspose-barcode-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中設定條碼 – 完整 Aspose.BarCode 指南

如果您需要在 .NET 應用程式中 **設定條碼**，本教學將示範使用 Aspose.BarCode 的完整步驟。您將看到如何變更宏字元、調整視覺參數，以及 **建立條碼影像 C#** 檔案，直接儲存至磁碟。

本指南涵蓋從安裝函式庫到產生兩個具有不同宏值的 MicroPDF417 條碼的全部內容。無需外部文件——您只要複製程式碼、執行，即可立即驗證 PNG 輸出。

## 前置條件

* .NET 6.0 或更新版本（範例使用主控台專案）
* Visual Studio 2022 或任何 C# IDE
* 有效的 Aspose.BarCode 授權（免費評估版可用於測試）
* 基本的 C# 語法知識

您還需要 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

## 設定條碼參數 – 步驟 1：建立產生器

第一步是以所需的條碼類型與資料實例化 `BarcodeGenerator`。使用 `EncodeTypes.MicroPdf417` 可讓 Aspose.BarCode 產生緊湊的 PDF417 變體。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    internal class Program
    {
        private static void Main()
        {
            // Step 1: Create a MicroPDF417 barcode generator with the desired text
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, // symbology
                "12345ABC");             // data to encode
```

**為什麼這很重要：** `BarcodeGenerator` 是核心物件；之後的所有設定皆會修改其 `Parameters` 屬性。選擇正確的 `EncodeTypes` 可確保條碼符合 MicroPDF417 規範。

## 變更宏字元 – 步驟 2：調整視覺參數

宏字元是可選的控制碼，可讓您串接多個 PDF417 符號。範例在 `Macro05` 與 `Macro06` 之間切換。同時您還會設定模組寬度（`XDimension`）以及欄位數量，以控制條碼大小。

```csharp
            // Step 2: Adjust visual parameters – set the X‑dimension (module width) and number of columns
            generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width in pixels
            generator.Parameters.Barcode.Pdf417.Columns = 4;           // number of data columns

            // Encode the first macro character (Macro05) and save the image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro05;
            generator.Save("MicroPdf417_Macro05.png", BarCodeImageFormat.Png);
```

**為什麼要變更宏字元：** 宏字元告訴掃描器此條碼屬於較大資料集的一部份。切換它可示範相同資料如何連結至不同的宏識別碼。

## 設定條碼 – 步驟 3：產生具有不同宏的第二個條碼

現在我們重複使用相同的 `generator` 實例，只是更換宏值。這樣可避免重新建立物件，並示範 **設定條碼** 參數可以在執行時動態變更。

```csharp
            // Step 3: Switch to the second macro character (Macro06) and save the new image
            generator.Parameters.Barcode.Pdf417.MacroCharacters = MacroCharacter.Macro06;
            generator.Save("MicroPdf417_Macro06.png", BarCodeImageFormat.Png);
        }
    }
}
```

### 預期輸出

執行程式會在專案資料夾產生兩個 PNG 檔案：

* `MicroPdf417_Macro05.png` – 含 Macro05 的條碼
* `MicroPdf417_Macro06.png` – 含 Macro06 的條碼

兩張影像皆顯示編碼為 `12345ABC` 的緊湊 MicroPDF417 符號。您可使用任何影像檢視器開啟 PNG 檔案，以驗證視覺品質。

## Barcode generator C# 最佳實踐

* **重複使用產生器：** 在現有實例上變更 `Parameters` 比為每個條碼建立新產生器更有效率。
* **提前設定 X‑dimension：** 模組寬度會影響整體影像大小；請在儲存前先調整。
* **驗證宏使用情形：** 並非所有掃描器皆支援宏字元。若在正式環境使用，請以目標硬體測試。
* **釋放資源：** `BarcodeGenerator` 實作 `IDisposable`。在長時間執行的服務中，請使用 `using` 區塊或在完成後呼叫 `Dispose()`。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "12345ABC"))
{
    // configure parameters...
}
```

## 建立條碼影像 C# – 疑難排解技巧

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 空白 PNG 檔案 | `XDimension` 設為 0 或過高的值 | 使用合理的像素寬度 (1‑5) |
| 掃描器無法辨識條碼 | 錯誤的宏字元設定 | 檢查掃描器文件說明；若不需要可使用 `MacroNone` |
| 例外 `ArgumentOutOfRangeException` | 欄位數超出允許範圍 (1‑30) | 將 `Columns` 設為 1 到 30 之間 |

## 結論

您現在已了解如何 **設定條碼** 屬性、**變更宏** 字元，以及如何使用 Aspose.BarCode **建立條碼影像 C#** 檔案。完整且可執行的範例示範了從產生器建立到影像匯出的完整工作流程。

接下來，您可以探索其他條碼類型（`EncodeTypes.QR`、`EncodeTypes.Code128`）或使用 Aspose.PDF 將條碼直接嵌入 PDF。這兩個主題皆屬於更廣泛的 **barcode generator c#** 生態系，且可透過少量程式碼變更加入此專案。

祝程式開發順利，歡迎隨意嘗試不同的宏值、尺寸與輸出格式！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立在所示技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 為 Code 16K 建立條碼安靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 建立 dotcode 延伸代碼文字](/barcode/english/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [如何設定 ITF-14 條碼的邊框客製化](/barcode/english/net/itf-14-barcode-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}