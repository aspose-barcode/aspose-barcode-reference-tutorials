---
category: general
date: 2026-10-02
description: 使用 Aspose.BarCode 在 C# 中從文字建立條碼。了解如何產生 PDF417 條碼，並查看如何在緊湊模式下產生 PDF417
  條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode from text
- generate pdf417 barcode
- how to generate pdf417 barcode
language: zh-hant
lastmod: 2026-10-02
og_description: 使用 Aspose.BarCode 在 C# 中從文字建立條碼。本指南說明如何產生 PDF417 條碼，以及如何在緊湊模式下產生 PDF417
  條碼。
og_image_alt: Screenshot showing create barcode from text output as a PNG image
og_title: 在 C# 中從文字建立條碼 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  headline: How to create barcode from text in C# with Aspose.BarCode
  type: TechArticle
- description: Create barcode from text in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode and see how to generate PDF417 barcode in compact mode.
  name: How to create barcode from text in C# with Aspose.BarCode
  steps:
  - name: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
    text: '**Invalid characters** – PDF417 supports Unicode, but some older scanners
      may reject non‑ASCII symbols. Test with your target hardware.'
  - name: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
    text: '**File path permissions** – Ensure the directory you write to is writable;
      otherwise `Save` throws an `UnauthorizedAccessException`.'
  - name: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
    text: '**Image size** – Very high `XDimension` values produce large PNG files.
      Keep the pixel size between 1 and 4 for most screen‑display scenarios.'
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: 如何在 C# 中使用 Aspose.BarCode 從文字建立條碼
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-barcode-from-text-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 從文字建立條碼

如果您需要在 .NET 應用程式中 **create barcode from text**，本指南將帶您完成整個流程。您將看到一個可直接執行的範例，該範例 **generates PDF417 barcode**，同時說明 **how to generate PDF417 barcode** 在緊湊布局中的做法。

以程式方式產生條碼可省去手動步驟，並確保所有文件的一致性。完成本教學後，您將擁有一個包含 PDF417 條碼的 PNG 檔案，可嵌入發票、票券或身分證等文件中。

## 您需要的環境

- .NET 6.0 SDK 或更新版本（此程式碼亦相容於 .NET Framework 4.7.2 以上）
- Visual Studio 2022 或任何支援 C# 的編輯器
- **Aspose.BarCode for .NET** 的 NuGet 授權（免費試用版可用於測試）

> **Pro tip:** 透過 CLI 新增 NuGet 套件，以保持專案整潔：  
> `dotnet add package Aspose.BarCode`

## 步驟 1：設定主控台專案

建立一個新的主控台應用程式，並參考 Aspose.BarCode 函式庫。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet new console` 指令會產生 `Program.cs` 檔案，我們將以以下完整範例取代它。

## 步驟 2：如何從文字建立條碼 – 核心程式碼

開啟 `Program.cs`，將其內容取代為以下程式碼。每一行皆有註解說明其用途。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Image;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Define the text that will be encoded.
            // The PDF417 symbology supports a wide range of Unicode characters.
            string textToEncode = "Åspóse.Barcóde©";

            // 2️⃣ Create a BarcodeGenerator for PDF417 using the desired text.
            // This object holds all settings and performs the rendering.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, textToEncode);

            // 3️⃣ Adjust module (X) dimension for better readability on screen.
            // XDimension defines the width of a single barcode column in pixels.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ Set the number of columns – a smaller column count yields a denser image.
            generator.Parameters.Barcode.Pdf417.Columns = 3;

            // 5️⃣ Enable compact mode by truncating the data.
            // Truncate = true removes padding, making the barcode smaller while preserving scannability.
            generator.Parameters.Barcode.Pdf417.Truncate = true;

            // 6️⃣ Choose the output path. Adjust the folder to match your environment.
            string outputPath = "CompactPdf417.png";

            // 7️⃣ Save the barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 為何每個設定都很重要

| Setting | Purpose |
|--------|----------|
| `EncodeTypes.Pdf417` | 選擇 PDF417 符號集，可在二維矩陣中儲存大量資料。 |
| `XDimension.Pixels = 2` | 控制每個模組的寬度；2 像素的值在可讀性與檔案大小之間取得平衡。 |
| `Pdf417.Columns = 3` | 減少欄位數，使條碼更緊湊且不失資料。 |
| `Pdf417.Truncate = true` | 啟用緊湊模式，移除不必要的填充，縮短條碼長度。 |
| `BarCodeImageFormat.Png` | PNG 保留無損品質，適合進一步處理或列印。 |

## 步驟 3：產生 PDF417 條碼 – 執行範例

建置並執行專案：

```bash
dotnet run
```

執行完成後您會看到：

```
Barcode saved to CompactPdf417.png
```

開啟 `CompactPdf417.png` 以檢視結果。此影像包含一個編碼字串 **Åspóse.Barcóde©** 的 PDF417 條碼。

![從文字建立條碼範例 – PDF417 條碼已儲存為 PNG](barcode-example.png)

*Alt text: 從文字建立條碼 – PDF417 條碼已儲存為 PNG*

## 步驟 4：如何使用自訂錯誤更正產生 PDF417 條碼（可選）

如果您的掃描環境較為嘈雜，可提升錯誤更正等級：

```csharp
generator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // Levels 0–5, higher = more redundancy
```

提升錯誤等級會使條碼變大，但可提升對損壞的抗性。

## 步驟 5：常見陷阱與邊緣案例處理

1. **Invalid characters** – PDF417 支援 Unicode，但某些較舊的掃描器可能會拒絕非 ASCII 符號。請以目標硬體進行測試。  
2. **File path permissions** – 確保寫入的目錄具有寫入權限；否則 `Save` 會拋出 `UnauthorizedAccessException`。  
3. **Image size** – 過高的 `XDimension` 會產生大型 PNG 檔案。大多數螢幕顯示情境下，請將像素大小維持在 1 到 4 之間。

## 重點回顧

現在您已了解如何在 C# 中使用 Aspose.BarCode **create barcode from text**，以及如何以緊湊布局 **generate PDF417 barcode**，並掌握 **how to generate PDF417 barcode** 的自訂設定步驟。上述完整可執行的程式碼可直接複製至任何 .NET 專案，並依需求調整文字輸入或輸出格式（例如 JPEG、BMP）。

## 往後步驟

- 透過變更 `EncodeTypes`，探索其他符號集，例如 QR Code 或 Code128。  
- 使用 Aspose.PDF 將產生的 PNG 整合至 PDF，實現端對端文件產生。  
- 嘗試調整 `generator.Parameters.Barcode.Pdf417.Rows` 以控制垂直密度。

歡迎自行修改範例，將條碼嵌入您的應用程式，並與社群分享成果。祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [如何在 C# 中產生 PDF417 條碼 – 緊湊範例](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-compact-example/)
- [如何在 C# 中以緊湊模式建立 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [如何在 C# 中產生 PDF417 條碼 – 步驟說明指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}