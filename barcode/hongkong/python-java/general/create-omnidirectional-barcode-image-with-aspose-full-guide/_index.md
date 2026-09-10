---
category: general
date: 2026-07-27
description: 使用 Aspose.BarCode 建立全方向條碼圖像。了解如何使用 Aspose 產生條碼、調整長寬比，並儲存為 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: zh-hant
lastmod: 2026-07-27
og_description: 使用 Aspose 建立全方位條碼圖像。按照本指南使用 Aspose 生成條碼，調整長寬比，並匯出 PNG 圖檔。
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: 使用 Aspose 逐步創建全向條碼圖像
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: 使用 Aspose 創建全向條碼圖像 – 完整指南
url: /zh-hant/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose 建立全向條碼影像 – 完整指南

曾經需要**建立全向條碼影像**卻不確定該選哪個函式庫嗎？你並不是唯一的疑問者。在許多物流與零售專案中，DataBar Stacked Omnidirectional 格式是實現緊湊、高密度編碼的祕密武器。

好消息是？只要使用 **Aspose.BarCode**，你就能在幾行程式碼內產生條碼、調整長寬比，並直接將 PNG 檔寫入磁碟。以下將逐步說明**使用 Aspose 產生條碼**的完整流程、每個設定的意義，以及在變更長寬比時需要留意的地方。

---

## 本教學涵蓋內容

我們將完整走過以下生命週期：

1. 設定輸出資料夾。
2. 建立 DataBar Stacked Omnidirectional 產生器。
3. 設定像素尺寸與長寬比。
4. 將條碼儲存為 PNG 檔。
5. 延伸範例以支援其他格式與特殊情況。

完成後，你將擁有一個可直接執行的 C# 主控台應用程式，產出兩張不同長寬比的條碼影像。無需外部工具，純粹使用 Aspose 程式碼即可。

**先備條件**

- .NET 6.0 SDK 或更新版本（此程式碼亦可於 .NET Framework 4.7.2 執行）。
- Aspose.BarCode for .NET NuGet 套件（`Install-Package Aspose.BarCode`）。
- 磁碟上可寫入影像的資料夾。

如果你已備妥上述條件，讓我們開始吧。

---

## 步驟 1：準備輸出資料夾

首先告訴程式要把 PNG 檔寫到哪裡。硬編碼路徑適合示範用，但正式環境通常會從設定檔讀取。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*為什麼這很重要：* `Directory.CreateDirectory` 具備冪等性；若資料夾已存在不會拋出例外，省去 try‑catch 的麻煩。

---

## 步驟 2：建立 DataBar Stacked Omnidirectional 產生器

接著以特定的編碼類型與樣本資料啟動產生器。字串 `"(01)12345678901231"` 符合 GS1 應用識別碼語法，代表 14 位元的 GTIN。

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*說明：* `EncodeTypes.DatabarStackedOmniDirectional` 告訴 Aspose 使用全向變體，無論從哪個方向掃描都能辨識，特別適合可能被旋轉的小標籤。

---

## 步驟 3：設定共用條碼參數

在渲染之前，我們先定義最小元素大小（X‑Dimension）。**2 像素**的設定可產生清晰影像，同時不會讓檔案過大。

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*小技巧：* 若需更高解析度以供列印，可將數值調整為 3 或 4。但請記得 X‑Dimension 變大會等比例放大寬度與高度。

---

## 步驟 4：以長寬比 15 產生並儲存

DataBar 系列允許調整**長寬比**，即高度與寬度的比例。長寬比 **15** 是全向條碼的常見預設值。

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*你會看到的結果：* 條碼相對較高，仍能舒適放入 2 × 1 cm 標籤。PNG 格式保留無損品質，適合後續處理或列印。

---

## 步驟 5：將長寬比改為 30 再次儲存

想要更矮的條碼嗎？只要調整 `AspectRatio` 屬性再呼叫 `Save` 即可，無需重新建立產生器。

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*為什麼可以重複使用同一個產生器？* Aspose 物件相當輕量，變更屬性後重新儲存比重新建構實例更快，且可確保編碼設定（例如 X‑Dimension）保持一致。

---

## 完整範例程式

將上述步驟整合，以下是一個可直接貼到新主控台專案的完整自足程式。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**預期輸出**

執行程式後會在 `Barcodes` 子資料夾產生：

- `DatabarAspectRatio15.png` – 較高的經典外觀。
- `DatabarAspectRatio30.png` – 較平的寬標籤適用版本。

兩張影像皆編碼相同的 GTIN 資料，僅在視覺比例上有所差異。

---

## 延伸範例（邊緣案例與變化）

### 1. 不同影像格式

Aspose 除 PNG 外亦支援 BMP、JPEG、TIFF 與 SVG。只要替換列舉值即可：

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG 為向量格式，意味著可無損縮放，非常適合響應式網站應用。

### 2. 自訂顏色

若需在深色背景上呈現白色條碼，可設定 `ForeColor` 與 `BackColor`：

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. 處理無效長寬比

Aspose 會驗證長寬比範圍（通常為 5‑50）。若傳入超出範圍的值，會拋出 `ArgumentException`。可將儲存動作包在 try‑catch 中，提供友善訊息：

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. 批次產生

當有多筆 GTIN 清單時，可迴圈處理，更新 `CodeText`，並以唯一檔名儲存每張影像。產生器物件可重複使用，降低記憶體占用。

---

## 常見陷阱與進階技巧

- **務必在儲存前設定 `XDimension`**；預設值 (0.33 mm) 在低解析度顯示器上會產生模糊影像。
- **長寬比是高度對寬度**，而非相反。數值越大，條碼在垂直方向上會*變短*。
- **檔案路徑**：使用 `Path.Combine` 可避免平台特定的分隔符問題，特別是程式在 Linux 容器中執行時。
- **授權**：Aspose.BarCode 為商業授權。試用模式下影像會出現浮水印，請盡早註冊授權以免上線後出現意外。

---

## 結論

現在你已掌握如何使用 Aspose **建立全向條碼影像**、調整長寬比，並以 PNG 格式匯出——全程不到 30 行 C# 程式碼。本教學逐步說明每個設定的意義，並提供了格式、顏色與批次處理等延伸應用。

準備好迎接下一個挑戰了嗎？試著產生 QR Code、將條碼嵌入 PDF，或在 ASP.NET Core API 中整合輸出。**使用 Aspose 產生條碼**的原則在所有條碼類型上皆通用，讓你能將今天學到的技巧靈活運用。

有任何問題或想分享自己的調整嗎？歡迎在下方留言——祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化你對 API 功能的掌握，並探索在專案中實作的其他方式。每篇資源皆提供完整可執行的程式碼範例與逐步說明。

- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Create Barcode Aspose Java - Adjust Image Quality](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [How to Generate Barcode Image in Java with Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}