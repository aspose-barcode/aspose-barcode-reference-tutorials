---
category: general
date: 2026-09-13
description: 學習如何在 C# 中產生條碼、客製化條碼尺寸，並使用 Aspose.BarCode 將條碼圖像儲存為 PNG。完整的逐步指南。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- custom barcode size
- save barcode image
- Aspose.BarCode C#
- barcode image format
language: zh-hant
lastmod: 2026-09-13
og_description: 如何在 C# 中生成自訂尺寸的條碼並將條碼圖像儲存為 PNG。請參考 Aspose.BarCode 的完整指南。
og_image_alt: Screenshot of a DataBar stacked omnidirectional barcode generated in
  C#
og_title: 如何在 C# 中產生條碼、設定自訂尺寸並儲存圖片
schemas:
- author: Aspose
  dateModified: '2026-09-13'
  description: Learn how to generate barcode in C#, customize barcode size, and save
    barcode image as PNG using Aspose.BarCode. Complete step‑by‑step guide.
  headline: How to generate barcode set custom size and save image in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中產生條碼、設定自訂尺寸並儲存圖像
url: /zh-hant/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中產生條碼、設定自訂尺寸並儲存圖像

如果您需要在 .NET 應用程式中 **產生條碼**，本教學將提供完整解決方案。您將看到如何調整 **自訂條碼尺寸** 以及 **儲存條碼圖像** 檔案，只需幾行 C# 程式碼。

產生條碼是庫存系統、運送標籤及銷售點應用程式的常見需求。完成本指南後，您將擁有一個可執行的程式，能產生兩個 DataBar‑Stacked‑Omnidirectional 條碼，每個條碼具有不同的長寬比，並將它們寫入磁碟上的 PNG 檔案。

**Prerequisites**

- .NET 6.0 或更新版本（程式碼亦相容 .NET Framework 4.7+）
- Visual Studio 2022 或任何 C# IDE
- Aspose.BarCode for .NET（免費試用或授權的 NuGet 套件）

---

## 使用 Aspose.BarCode 產生條碼

Aspose.BarCode 函式庫抽象化條碼標準的底層細節，讓您專注於要編碼的資料以及所需的視覺外觀。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar stacked omnidirectional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231"); // GS1‑128 format example

        // 2️⃣ Set a basic module width – this influences the overall **custom barcode size**
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First aspect ratio (15) → save the image
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 15.");

        // 4️⃣ Change aspect ratio to 30 → **save barcode image** again
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved barcode with aspect ratio 30.");
    }
}
```

### 為何每一行都很重要

| Step | Explanation |
|------|-------------|
| **1️⃣ Create a generator** | `EncodeTypes.DatabarStackedOmniDirectional` 列舉告訴 Aspose 使用哪種條碼符號。字串 `"(01)12345678901231"` 符合 GS1‑128 資料格式，其中 `(01)` 為 GTIN 的應用識別碼 (Application Identifier)。 |
| **2️⃣ Set X‑dimension** | `XDimension.Pixels` 定義單一條碼模組（最小條）的寬度。變更此值是實現 **自訂條碼尺寸** 的主要方式，且不會改變編碼資料。 |
| **3️⃣ Set aspect ratio & save** | `DataBar.AspectRatio` 控制 DataBar 符號的高寬比。長寬比為 15 時產生相對較短且寬的條碼，而 30 則使其較高。`Save` 將視覺呈現寫入 PNG 檔案，滿足 **儲存條碼圖像** 的需求。 |
| **4️⃣ Change aspect ratio & save again** | 重新使用相同的產生器實例，可在保持資料不變的情況下產生具有不同視覺特性的多張圖像。 |

---

## 調整自訂條碼尺寸（超越 X‑dimension）

雖然 `XDimension.Pixels` 設定模組寬度，您亦可透過結合兩個屬性來微調條碼的整體尺寸：

1. **`BarHeight`** – 以像素為單位的明確高度。  
2. **`BarWidth`** – 以像素為單位的明確寬度（會覆寫 X‑dimension）。

```csharp
// Example: make a larger, more readable barcode
generator.Parameters.Barcode.XDimension.Pixels = 4;      // wider modules
generator.Parameters.Barcode.BarHeight.Pixels = 120;    // taller bars
generator.Parameters.Barcode.DataBar.AspectRatio = 20; // balanced ratio
generator.Save("LargeCustomSize.png", BarCodeImageFormat.Png);
Console.WriteLine("Saved large custom size barcode.");
```

> **專業提示：**列印條碼時，務必在最終列印尺寸下測試產生的圖像。2 px 的模組寬度適合螢幕顯示，但列印標籤通常需要至少 4 px 才能保持可掃描性。

---

## 為儲存條碼圖像選擇適當的影像格式

Aspose.BarCode 支援 PNG、JPEG、BMP、GIF 與 TIFF。PNG 為無損格式，能保留清晰的邊緣，是大多數應用程式最安全的選擇。若需較小的檔案供網路使用，品質設定為 90 的 JPEG 亦可，但需留意壓縮雜訊可能影響掃描可靠性。

```csharp
generator.Save("DatabarAspectRatio15.jpg", BarCodeImageFormat.Jpeg, 90);
Console.WriteLine("Saved JPEG version with quality 90.");
```

---

## 完整、可執行的範例

以下是一個獨立的主控台應用程式，您可以直接複製、貼上並執行。它示範了 **產生條碼**、修改 **自訂條碼尺寸**，以及以兩種不同格式 **儲存條碼圖像** 的方法。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator with the desired symbology and data
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // ---- Custom size configuration ----
            generator.Parameters.Barcode.XDimension.Pixels = 2;      // module width
            generator.Parameters.Barcode.BarHeight.Pixels = 80;    // optional explicit height
            generator.Parameters.Barcode.DataBar.AspectRatio = 15; // first aspect ratio

            // Save first image as PNG
            string pngPath1 = "DatabarAspectRatio15.png";
            generator.Save(pngPath1, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath1}");

            // Change aspect ratio for a taller barcode
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;
            string pngPath2 = "DatabarAspectRatio30.png";
            generator.Save(pngPath2, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {pngPath2}");

            // ---- Larger custom size example ----
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.BarHeight.Pixels = 120;
            generator.Parameters.Barcode.DataBar.AspectRatio = 20;
            string largePath = "LargeCustomSize.png";
            generator.Save(largePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved {largePath}");

            // ---- Save as JPEG for web use ----
            string jpegPath = "DatabarAspectRatio15.jpg";
            generator.Save(jpegPath, BarCodeImageFormat.Jpeg, 90);
            Console.WriteLine($"Saved {jpegPath}");
        }
    }
}
```

**預期的主控台輸出**

```
Saved DatabarAspectRatio15.png
Saved DatabarAspectRatio30.png
Saved LargeCustomSize.png
Saved DatabarAspectRatio15.jpg
```

四個圖像檔案將會出現在程式的執行目錄中

## 接下來您可以學習什麼？

以下教學涵蓋與本指南密切相關的主題，並以步驟說明的方式提供完整的程式碼範例，協助您精通其他 API 功能，並在自己的專案中探索替代實作方式。

- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟說明指南](/barcode/english/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose 產生 PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [如何使用 Aspose.BarCode for .NET 產生具有自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}