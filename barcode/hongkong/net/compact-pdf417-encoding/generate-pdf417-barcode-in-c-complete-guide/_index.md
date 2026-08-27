---
category: general
date: 2026-07-15
description: 快速產生 PDF417 條碼，並學習如何在 C# 中設定欄位以產生緊湊的 PDF417 條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to set columns
- pdf417 barcode image
- Aspose.BarCode PDF417
- C# barcode generation
- compact PDF417
language: zh-hant
lastmod: 2026-07-15
og_description: 使用 Aspose.BarCode 產生 PDF417 條碼，並了解如何設定列數以建立緊湊的 PDF417 條碼圖像。
og_image_alt: Screenshot of a compact PDF417 barcode saved as PNG
og_title: 在 C# 中產生 PDF417 條碼 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-07-15'
  description: Generate PDF417 barcode quickly and learn how to set columns for a
    compact PDF417 barcode image in C#.
  headline: Generate PDF417 Barcode in C# – Complete Guide
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: 生成 PDF417 條碼（C#） – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中產生 PDF417 條碼 – 完整指南

是否曾經需要在 .NET 專案中 **generate PDF417 barcode**，卻不知從何開始？您並不孤單。在許多企業應用程式中——例如登機證印表機、庫存標籤或行動票證——PDF417 是能在小小視覺空間內容納大量資料的主力條碼。

事實上，Aspose.BarCode 函式庫讓整個流程幾乎毫不費力，您甚至可以控制 **how to set columns**，讓條碼盡可能緊湊。完成本教學後，您將擁有一個可直接使用的 PNG 圖片，內容為 **PDF417 barcode image**，可嵌入任何 UI、電子郵件或列印工作中。

## 您將學到的內容

- 一個完整功能的 C# 主控台應用程式，可產生 PDF417 條碼。
- 清楚了解 *X‑Dimension*（模組大小）以及其重要性。
- 逐步說明 **how to set columns** 以產生更緊湊的條碼。
- 一個已儲存的 `PNG` 檔案，您可立即開啟以驗證結果。
- 針對常見問題的排除技巧（例如，條碼無法辨識、圖像格式錯誤）。

> **先決條件** – .NET 6+ SDK、Visual Studio 2022（或任何您喜歡的編輯器），以及對 `Aspose.BarCode` 的 NuGet 參考。除此之外無需其他。

---

## 第一步：安裝 Aspose.BarCode NuGet 套件

在我們能夠 *generate PDF417 barcode* 之前，必須先在專案中加入此函式庫。

```bash
dotnet add package Aspose.BarCode
```

那一行指令會將您所需的所有類型引入，包括 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 列舉。

> **專業提示：** 若您針對 .NET Framework 而非 .NET 6，請在套件管理員主控台中使用傳統的 `Install-Package Aspose.BarCode` PowerShell 指令。

---

## 第二步：建立最小化的主控台應用程式

讓我們快速建立一個只負責產生條碼的簡易程式。開啟新資料夾，執行 `dotnet new console`，然後將自動產生的 `Program.cs` 替換為以下程式碼。

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
- `EncodeTypes.Pdf417` 告訴函式庫我們需要 PDF417 條碼，而非 QR 或 Code128。  
- `XDimension.Pixels` 控制每個微小黑白模組的解析度。  
- **how to set columns** 區塊直接影響 **PDF417 barcode image** 的形狀。  
- `Truncate = true` 會移除任何不必要的空白列，讓條碼呈現許多掃描器喜愛的「緊湊」外觀。

---

## 第三步：深入探討 – 了解欄位與截斷

### 如何設定欄位

PDF417 以 *rows* × *columns* 的矩陣排列資料。函式庫預設為 5 欄，適用於大多數情況。然而，您可能需要更窄的條碼以適配標籤，或更寬的條碼以提升掃描可靠度。此屬性：

```csharp
generator.Parameters.Barcode.Pdf417.Columns = <desiredColumnCount>;
```

接受 **1** 到 **30** 的值（具體上限取決於資料長度）。以下是一張快速參考表：

| 欄位 | 大約寬度 (mm) | 適用情況 |
|------|--------------|----------|
| 1‑3 | 非常窄 | 小標籤、空間受限 |
| 4‑6 | 標準 | 大多數收據、票證 |
| 7‑10 | 較寬 | 高密度資料、較佳可讀性 |

### 截斷（緊湊模式）

設定 `Truncate = true` 會指示編碼器切除底部所有不必要的空白列。結果會產生 **compact PDF417 barcode image**，佔用最小的區域，同時仍保留全部資料。若遇到「條碼過大無法貼標籤」的錯誤，請切換此旗標。

---

## 第四步：執行應用程式並驗證輸出

編譯並執行：

```bash
dotnet run
```

您應該會在主控台看到確認儲存位置的訊息。前往該資料夾並開啟 `CompactPdf417.png`。圖像大致如下：

![產生的 PDF417 條碼圖像](./CompactPdf417.png "產生的 PDF417 條碼圖像 – 由 Aspose.BarCode 建立的緊湊 PNG")

*圖片替代文字：* **Generated PDF417 barcode image** – 由本教學程式碼產生的緊湊 PNG 檔案。

如果您的掃描器能讀取它，恭喜您——您已成功 **generate PDF417 barcode**，並掌握 **how to set columns** 以產生整潔的 **PDF417 barcode image**。

---

## 第五步：常見問題與解決方法

| 症狀 | 可能原因 | 快速解決方案 |
|------|----------|--------------|
| 條碼看起來模糊 | `XDimension.Pixels` 太低（例如 1） | 提升至 2‑3 像素以獲得更清晰的圖像。 |
| 掃描器無法讀取 | 對於給定資料而言欄位過多 | 減少 `Columns` 或啟用 `Truncate`。 |
| 檔案格式錯誤 | 誤以 `BarCodeImageFormat.Jpeg` 儲存 | 使用 `BarCodeImageFormat.Png` 以取得無損結果。 |
| 例外 `ArgumentOutOfRangeException` | 欄位數超出允許範圍 | 將欄位數維持在 1‑30 之間，並確保資料能容納。 |

---

## 第六步：更進一步 – 自訂顏色與加入文字

如果您想讓條碼符合品牌配色，您可以調整前景與背景顏色：

```csharp
generator.Parameters.Barcode.BarcodeColor = System.Drawing.Color.DarkBlue;
generator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
```

或在條碼下方疊加可供人類閱讀的文字：

```csharp
generator.Parameters.Barcode.CodeText = data; // shows the raw string
generator.Parameters.Barcode.CodeLocation = CodeLocation.Below;
```

這些附加功能屬於選用項目，但它們說明了 **generate PDF417 barcode** 工作流程的彈性。

---

## 結論

我們已完整示範一個從頭到尾的範例，使用 Aspose.BarCode **generate PDF417 barcode**，說明 **how to set columns** 以控制條碼尺寸，並將結果以 PNG 格式儲存為清晰的 **PDF417 barcode image**。此程式碼自足、相容 .NET 6+，且可輕鬆嵌入任何現有專案。

接下來可以嘗試編碼更大的資料負載（例如 JSON），實驗不同的圖像格式，或將產生器整合至即時提供條碼的 Web API。沒有任何限制，而您已擁有堅實的基礎可供構建。

祝程式開發順利，願您的條碼總能一次即被掃描！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，建立於本教學所示技巧之上。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何建立條碼 – 使用 Aspose.BarCode 的緊湊 PDF417](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何在 Java 中產生條碼圖像 – 使用 Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)
- [在 Java 中產生條碼 – 使用 Aspose.BarCode 設定圖像解析度](/barcode/english/java/advanced-settings-and-optimization/setting-image-resolution-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}