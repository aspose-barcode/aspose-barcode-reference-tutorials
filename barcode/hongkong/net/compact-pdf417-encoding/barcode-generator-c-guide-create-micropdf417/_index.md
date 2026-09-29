---
category: general
date: 2026-09-29
description: Barcode 產生器 C# 教學示範如何產生 MicroPdf417 條碼、調整尺寸、設定欄位，並僅用幾行程式碼自訂條碼大小。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- how to generate barcode
- how to change dimensions
- how to set columns
- customize barcode size
language: zh-hant
lastmod: 2026-09-29
og_description: 條碼產生器 C# 指南顯示如何產生 MicroPdf417 條碼、更改尺寸、設定欄位，並只需幾行程式碼即可自訂條碼大小。
og_image_alt: Screenshot of a MicroPdf417 barcode generated with a C# barcode generator
og_title: 條碼產生器 C# 指南 – 建立與自訂 MicroPdf417
schemas:
- author: GroupDocs
  dateModified: '2026-09-29'
  description: Barcode generator C# guide shows how to generate a MicroPdf417 barcode,
    change dimensions, set columns, and customize barcode size in just a few lines.
  headline: 'Barcode generator C# guide: create MicroPdf417'
  type: TechArticle
tags:
- barcode
- C#
- MicroPdf417
- barcode generation
title: 條碼產生器 C# 指南：建立 MicroPdf417
url: /zh-hant/net/compact-pdf417-encoding/barcode-generator-c-guide-create-micropdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 條碼產生器 C# 指南：建立 MicroPdf417

如果你需要在 .NET 專案中使用 **barcode generator C#**，本教學將一步步帶你從頭建立 MicroPdf417 條碼。你將學會 **如何產生條碼**、調整尺寸、設定欄位，並且輕鬆 **自訂條碼大小**。

MicroPdf417 是一種緊湊的 2‑D 符號，適合用於標示小零件、票券或庫存標籤。完成本指南後，你將擁有一個完整、可執行的 console 應用程式，輸出條碼的 PNG 圖片，並了解每個參數如何影響最終尺寸。

## 前置條件

在開始之前，請確保你已具備：

* .NET 6.0 SDK 或更新版本（此程式碼亦相容 .NET Framework 4.7+）
* 支援 C# 的 IDE（Visual Studio、VS Code、Rider 等）
* **GroupDocs.Barcode** NuGet 套件 – 使用以下指令安裝  

  ```bash
  dotnet add package GroupDocs.Barcode
  ```

不需要額外的外部工具；此函式庫會處理編碼、渲染與檔案儲存。

## Barcode generator C#：初始化產生器

第一步是建立 `BarcodeGenerator` 的實例，並指定符號類型 (`EncodeTypes.MicroPdf417`) 以及要編碼的資料。

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1 – create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // Subsequent configuration steps go here...

            // Save the final image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

**為什麼這很重要：**  
`BarcodeGenerator` 是所有條碼操作的入口點。建構子會將選擇的 **EncodeTypes**（MicroPdf417）與原始資料字串綁定。函式庫會自動處理 Unicode 字元，例如 “Å” 與 “©”，不需要額外的編碼邏輯。

## 如何變更條碼的尺寸

條碼的可讀性高度依賴模組寬度（X‑dimension）。將其設定為較大的像素數會使條紋變寬，圖像在低解析度螢幕上也更易掃描。

```csharp
// Step 2 – adjust the X‑dimension (module width) to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**說明：**  
`XDimension.Pixels` 控制單一條碼模組的寬度。預設為 1 pixel，在高 DPI 螢幕上可能顯得過細。將其提升至 2 pixels 會使整體寬度加倍，且不影響編碼資料。

**小技巧：** 若你打算以 300 dpi 列印條碼，設定為 3 或 4 pixels 往往能在尺寸與掃描可靠性之間取得最佳平衡。

## 如何設定欄位以控制大小

MicroPdf417 允許你指定欄位數量（最高 4 欄）。欄位較少時條碼較高；欄位較多則寬度增加但高度降低。調整此值是 **自訂條碼大小** 的主要方式。

```csharp
// Step 3 – set the maximum number of columns (4 is the limit for MicroPdf417)
generator.Parameters.Barcode.Pdf417.Columns = 4;
```

**為什麼會這樣運作：**  
`Pdf417.Columns` 屬性在所有基於 PDF417 的符號（包括 MicroPdf417）中皆共享。將其設為最大值（4）會將資料分散至最寬的版面，從而降低整體高度。若需要更緊湊的高度，可將欄位數降至 2 或 3。

**邊緣情況：** 當資料字串過長時，函式庫可能會自動增加列數以容納內容，與欄位數無關。建議將有效負載控制在 50 個字元以獲得可預測的尺寸。

## 為不同輸出自訂條碼大小

除了 X‑dimension 與欄位之外，你還可以透過選擇適當的影像格式與 DPI 來影響最終圖像大小。PNG 為無損格式，最適合網路顯示；BMP 或 TIFF 則可能較適合高品質列印。

```csharp
// Step 4 – save as PNG (lossless) with default 96 dpi
generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);
```

若需更高 DPI，可明確設定：

```csharp
generator.Parameters.Image.DpiX = 300;
generator.Parameters.Image.DpiY = 300;
generator.Save("MicroPdf417_300dpi.png", BarCodeImageFormat.Png);
```

**結果：** 儲存的 PNG 檔案會包含一個符合你設定尺寸的清晰 MicroPdf417 條碼。使用任何影像檢視器開啟檔案，即可驗證視覺大小。

### 預期輸出

執行程式後會產生名為 **MicroPdf417.png**（若設定 DPI，則為 **MicroPdf417_300dpi.png**）的檔案。條碼外觀類似下圖：

![條碼產生器 C# 輸出示例，顯示 MicroPdf417 PNG](barcode-micro-pdf417.png)

*Alt text:* *條碼產生器 C# 輸出示例，顯示 MicroPdf417 PNG*

使用標準 2‑D 條碼讀取器掃描此圖像，即可取得原始字串 `Åspóse.Barcóde©`。

## 完整原始碼，快速複製貼上

```csharp
using System;
using GroupDocs.Barcode;
using GroupDocs.Barcode.Enums;
using GroupDocs.Barcode.Common;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create the generator with the desired text
            var generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417,
                "Åspóse.Barcóde©"
            );

            // 2️⃣ Change dimensions – make modules 2 pixels wide
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Set columns – use the maximum of 4 for a wider, shorter barcode
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // (Optional) Increase DPI for high‑resolution output
            // generator.Parameters.Image.DpiX = 300;
            // generator.Parameters.Image.DpiY = 300;

            // 4️⃣ Save the barcode as a PNG image
            generator.Save("MicroPdf417.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode saved as MicroPdf417.png");
        }
    }
}
```

將程式碼貼入新的 console 專案，還原 NuGet 套件，然後執行 `dotnet run`。主控台會顯示圖像位置，並在專案資料夾中看到產生的條碼。

## 常見問題與故障排除

| 問題 | 解答 |
|----------|--------|
| **條碼看起來模糊怎麼辦？** | 增加 `XDimension.Pixels` 或 DPI（`Parameters.Image.DpiX/Y`）。兩者皆會放大模組，提升視覺清晰度。 |
| **可以使用其他影像格式嗎？** | 可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Tiff`。PNG 仍是最安全的無損選擇。 |
| **我的資料包含表情符號——能編碼嗎？** | MicroPdf417 支援 UTF‑8，大多數表情符號皆可正確編碼。若發生錯誤，請確認字串已正確正規化（`System.Text.Encoding.UTF8`）。 |
| **如何產生其他符號類型？** | 將 `EncodeTypes.MicroPdf417` 改為 `EncodeTypes` 中的其他值 ( |

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化你對 API 功能的掌握，並探索在專案中實作的其他方式。

- [How to Generate Barcode Image in C# – MicroPdf417 Guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)
- [How to generate PDF417 barcode in C# with custom dimensions](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}