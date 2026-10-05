---
category: general
date: 2026-09-18
description: 快速學習如何在 C# 中建立 PDF417 條碼圖像，並設定欄位以產生緊湊條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create pdf417 barcode image
- compact pdf417 barcode
- Aspose.BarCode PDF417
- C# barcode generation
- set barcode columns
lastmod: 2026-09-18
og_description: 快速學習如何在 C# 中建立 PDF417 條碼圖像，並設定欄位以產生緊湊條碼。Aspose.BarCode 讓此過程變得簡單。
og_image_alt: Developer guide showing a compact PDF417 barcode PNG generated with
  Aspose.BarCode
og_title: 建立 PDF417 條碼圖像 – 逐步 C# 指南
schemas:
- author: Aspose
  dateModified: '2026-09-18'
  description: Learn how to create PDF417 barcode image in C# quickly and set columns
    for a compact barcode.
  headline: Create PDF417 barcode image – complete guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
- Aspose.BarCode
title: 如何在 C# 中建立 PDF417 條碼圖像 – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立 PDF417 條碼影像 – 完整指南

如果您需要在 .NET 應用程式中 **建立 PDF417 條碼影像**，您來對地方了。無論是列印登機證標籤、編碼庫存資料，或是建置行動票務系統，PDF417 都能提供高容量的二維條碼。本指南將示範如何使用 Aspose.BarCode 產生影像，並說明如何設定欄位（Columns）以讓條碼盡可能緊湊。

## 快速解答
- **哪個函式庫能產生 PDF417 條碼？** Aspose.BarCode for .NET。
- **需要多少行程式碼？** 在主控台應用程式中約 10 行。
- **我可以控制條碼寬度嗎？** 可以，透過設定 `Columns` 屬性。
- **建議使用哪種影像格式？** PNG，提供無損品質。
- **支援 .NET 6 嗎？** 完全支援——此函式庫可在 .NET 6、.NET 7 以及更高版本上執行。

## 什麼是 PDF417 條碼影像？
PDF417 條碼影像是一種二維矩陣，每列可儲存多達 1 700 個字元，利用列與欄緊密打包資料。Aspose.BarCode 可將此矩陣渲染為 PNG、JPEG、BMP 等標準影像格式，並可儲存於各種檔案類型，適合列印於標籤、票券或行動裝置螢幕上。

## 為什麼要設定欄位以取得緊湊的 PDF417 條碼影像？
設定欄位可縮減條碼寬度，對於窄標籤或空間受限的 UI 元件尤為重要。Aspose.BarCode 支援 1‑30 欄，選擇較低的欄位數可將整體影像寬度降低最多 40 %，同時保持資料完整性。此調整有助於在小型標籤上放置條碼而不犧牲可讀性。

## 如何在 C# 中建立 PDF417 條碼影像？
載入 `Aspose.BarCode` 函式庫，使用 `EncodeTypes.Pdf417` 建立 `BarcodeGenerator`，設定 `Columns` 與 `Truncate`，最後以 PNG 儲存。整個流程只需兩個方法呼叫，即可產生可直接使用的影像檔。您亦可自訂尺寸、顏色，並加入可讀文字以符合應用需求。

### 前置需求
- .NET 6+ SDK（或更新版本）
- Visual Studio 2022 或任何 C# 編輯器
- NuGet 套件 `Aspose.BarCode`

### 步驟說明實作

## Step 1: Install the Aspose.BarCode NuGet package
`Aspose.BarCode` 是用於產生與讀取各種條碼符號的 .NET 函式庫。

```bash
dotnet add package Aspose.BarCode
```

只要這一行指令即可取得所有必要類型，包括 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 列舉。

> **專業提示：** 若您目標是 .NET Framework 而非 .NET 6，請在套件管理員主控台中使用傳統的 `Install-Package Aspose.BarCode` PowerShell 指令。

## Step 2: Create a minimal console application
`BarcodeGenerator` 依據指定設定產生條碼影像。`EncodeTypes` 列舉支援的條碼符號。`BarCodeImageFormat` 列舉影像格式。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Define the data you want to encode.
            string data = "SampleBarcode©";

            // 2️⃣ Instantiate the generator for PDF417.
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);

            // 3️⃣ Set the size of a single barcode module (pixel dimension).
            //    This is the “X‑Dimension” – smaller values yield a finer image.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 4️⃣ **How to set columns** – configure the matrix layout.
            //    Fewer columns = taller barcode; more columns = wider barcode.
            generator.Parameters.Barcode.Pdf417.Columns = 3;   // 👈 primary levers
            generator.Parameters.Barcode.Pdf417.Truncate = true; // compact mode

            // 5️⃣ Choose where the PNG will be saved.
            string outputPath = @"./CompactPdf417.png";

            // 6️⃣ Save the generated barcode as a PNG image.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"✅ Barcode saved to {outputPath}");
        }
    }
}
```

**為什麼這很重要：**  
- `EncodeTypes.Pdf417` 告訴函式庫我們要產生 PDF417 條碼，而非 QR 或 Code128。  
- `XDimension.Pixels` 控制每個微小黑白模組的解析度。  
- **設定欄位** 的程式碼直接影響 **PDF417 條碼影像** 的形狀。  
- `Truncate = true` 會移除任何不必要的空白列，呈現許多掃描器喜愛的「緊湊」外觀。

## Step 3: Dive deeper – understanding columns and truncation

### How to set columns
PDF417 以 *列* × *欄* 的矩陣排列資料。函式庫預設 5 欄，適用於大多數情況。但若需更窄的條碼以適配標籤，或需要更寬的條碼以提升掃描可靠度，可調整此屬性：

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

可接受的值介於 **1** 到 **30**（實際上限取決於資料長度）。以下是快速參考表：

| 欄位數 | 約寬度 (mm) | 使用情況 |
|--------|------------|----------|
| 1‑3    | 非常窄     | 小標籤，空間受限 |
| 4‑6    | 標準       | 大多數收據、票券 |
| 7‑10   | 較寬       | 高密度資料，較佳可讀性 |

### Truncate (compact mode)
設定 `Truncate = true` 會指示編碼器在底部裁切所有不必要的空白列。結果是一個 **緊湊的 PDF417 條碼影像**，佔用最小面積，同時保留全部資料。若遇到「條碼過大無法貼標」的錯誤，請切換此旗標。

## Step 4: Run the app and verify the output
編譯並執行：

```bash
dotnet run
```

您應該會在主控台看到確認儲存位置的訊息。前往該資料夾並開啟 `CompactPdf417.png`。影像大致如下：

![產生的 PDF417 條碼影像](./CompactPdf417.png "產生的 PDF417 條碼影像 – 由 Aspose.BarCode 建立的緊湊 PNG")

[產生的 PDF417 條碼影像](./CompactPdf417.png "產生的 PDF417 條碼影像 – 由 Aspose.BarCode 建立的緊湊 PNG")

*影像替代文字:* **產生的 PDF417 條碼影像** – 由本教學程式碼產生的緊湊 PNG 檔案。

如果您的掃描器能讀取，恭喜您已成功 **產生 PDF417 條碼**，並掌握 **如何設定欄位** 以取得整潔的 **PDF417 條碼影像**。

## Step 5: Common pitfalls & how to fix them

| 症狀 | 可能原因 | 快速解決 |
|------|----------|----------|
| 條碼看起來模糊 | `XDimension.Pixels` 太低（例如 1） | 提升至 2‑3 像素以獲得更清晰的影像。 |
| 掃描器無法讀取 | 對於給定資料欄位過多 | 減少 `Columns` 或啟用 `Truncate`。 |
| 檔案格式錯誤 | 誤以 `BarCodeImageFormat.Jpeg` 儲存 | 使用 `BarCodeImageFormat.Png` 以獲得無損結果。 |
| 例外 `ArgumentOutOfRangeException` | 欄位數超出允許範圍 | 將欄位數維持在 1‑30 之間，並確保資料適合。 |

## Step 6: Going further – customizing colors and adding text

如果想讓條碼符合品牌配色，可調整前景與背景顏色：

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

或在條碼下方加入可讀文字：

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

這些額外功能屬於選用項目，但能說明 **產生 PDF417 條碼** 工作流程的彈性。

## 結論
我們已完整示範如何使用 Aspose.BarCode **產生 PDF417 條碼**，說明 **如何設定欄位** 以控制條碼尺寸，並將結果以 PNG 格式儲存為清晰的 **PDF417 條碼影像**。程式碼自包含、相容 .NET 6+，可輕鬆嵌入任何現有專案。

接下來可以嘗試編碼更大的資料負載（例如 JSON 字串）、實驗不同影像格式，或將產生器整合至即時提供條碼的 Web API。只要有想像力，您就能在此基礎上構建更多應用。

祝程式開發順利，條碼一次即掃！

## What should you learn next?
以下教學與本指南緊密相關，提供完整範例與逐步說明，協助您掌握更多 API 功能或探索替代實作方式。

- [如何建立條碼 – 緊湊 PDF417 與 Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何在 Java 中使用 Aspose.BarCode 產生條碼影像](/barcode/english/java/barcode-rendering-techniques/)
- [在 Java 中產生條碼 – 使用 Aspose.BarCode 設定影像解析度](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

## Frequently asked questions

**Q: 我可以直接在網頁中使用產生的 PNG，無需額外轉換嗎？**  
A: 可以，PNG 受到所有現代瀏覽器原生支援，您只需使用 `<img>` 標籤直接嵌入檔案即可。

**Q: PDF417 條碼最多能容納多少字元？**  
A: 每列最多 1 700 個字元，最多 30 列，理論上可容納約 51 000 個字元，實際上限取決於掃描器的能力。

**Q: Aspose.BarCode 開發時需要授權嗎？**  
A: 提供免費評估授權供測試使用；正式上線則需購買商業授權。

**Q: 能否在背景服務中產生 PDF417 條碼？**  
A: 完全可以。此函式庫對唯讀操作具備執行緒安全性，您可在 ASP.NET Core 或 Windows 服務中產生條碼，無需 UI 互動。

**Q: 除了 PNG，還支援哪些影像格式？**  
A: 透過 `BarCodeImageFormat` 列舉，支援 BMP、JPEG、GIF、TIFF 以及 SVG。

---

**最後更新：** 2026-09-18  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

```bash
dotnet add package Aspose.BarCode
```

## Related Tutorials
- [使用 Aspose 完整指南建立 Pdf417 條碼](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-with-aspose-complete-guide/)
- [如何在 C 中使用 Aspose 產生 Pdf417 條碼影像](/barcode/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-image-in-c-with-aspose/)
- [在 C 中建立 Pdf417 條碼的逐步指南](/barcode/net/compact-pdf417-encoding/create-pdf417-barcode-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}