---
category: general
date: 2026-09-26
description: 學習如何在 C# 中使用 Aspose.BarCode 建立條碼。此一步一步的指南包含條碼產生器範例，並說明如何調整條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode c#
- barcode generator example
- how to adjust bar height
- change barcode height
- generate barcode aspose
language: zh-hant
lastmod: 2026-09-26
og_description: 在 C# 中使用 Aspose.BarCode 建立條碼。按照本指南生成條碼、調整條碼高度，並儲存為 PNG 圖像。
og_image_alt: Diagram illustrating how to create barcode in C# using Aspose.BarCode
og_title: 使用 Aspose.BarCode 在 C# 中建立條碼 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-09-26'
  description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  headline: How to create barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode in C# using Aspose.BarCode. This step‑by‑step
    guide includes a barcode generator example and shows how to adjust bar height.
  name: How to create barcode in C# with Aspose.BarCode
  steps:
  - name: Import required namespaces
    text: '```csharp using System; using Aspose.BarCode.Generation; using Aspose.BarCode;
      ```'
  - name: Initialise the barcode generator
    text: We’ll generate a **Databar Omni‑Directional** symbol that encodes a GTIN‑14
      value. The constructor takes the symbology and the raw data string.
  - name: Set common barcode parameters
    text: 'Two visual parameters are most often tweaked: the X‑dimension (the narrow
      bar width) and the overall bar height.'
  - name: Save the first image (30‑pixel height)
    text: '```csharp // Save the barcode as a 30‑pixel‑high PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: Change the bar height to 60 pixels
    text: Now we demonstrate **how to adjust bar height** at runtime. The same `generator`
      instance is reused; only the `BarHeight` property changes.
  - name: Full source code
    text: 'Putting everything together yields a concise, runnable program:'
  - name: Switching to a different symbology
    text: 'If you need a QR code instead of a Databar, replace the `EncodeTypes` value:'
  - name: Using `BarHeight` in millimetres
    text: 'Aspose.BarCode also supports physical units. To set a height of 10 mm:'
  - name: Handling errors
    text: 'If the data string does not conform to the selected symbology, `BarcodeGenerator`
      throws an `ArgumentException`. Wrap the generation logic in a try‑catch block
      to provide a friendly message:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中使用 Aspose.BarCode 建立條碼
url: /zh-hant/python-java/general/how-to-create-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 建立條碼  

如果您需要快速建立 **create barcode c#** 專案，Aspose.BarCode 提供了流暢的 API 來處理繁重的工作。在本教學中，您將看到完整的 **barcode generator example**，學習 **how to adjust bar height**，並將結果匯出為 PNG 檔案。  

無論您是構建零售結帳系統、產生庫存標籤，或是自動化運送標籤，程式化調整條碼視覺尺寸的能力都是必須的。本指南假設您具備 C# 的基本知識，並已安裝如 Visual Studio 2022 等開發環境。  

## 前置條件  

* .NET 6.0 SDK 或更新版本已安裝。  
* Visual Studio 2022（或任何 C# IDE）。  
* 有效的 Aspose.BarCode 授權（免費試用版可用於學習）。  

您還需要將 Aspose.BarCode NuGet 套件加入您的專案：

```bash
dotnet add package Aspose.BarCode
```

> **專業提示：** 如果您打算在迴圈中產生大量條碼，請重複使用同一個 `BarcodeGenerator` 實例，僅修改變動的參數。這樣可減少記憶體分配並提升效能。

## 如何在 C# 中使用 Aspose.BarCode 建立條碼  

以下各節將逐步說明 **barcode generator example** 的每一步。程式碼是自包含的；只要將其複製到新的主控台應用程式中並執行即可。  

### 步驟 1：匯入必要的命名空間  

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

這些命名空間讓您可以使用 `BarcodeGenerator` 類別與 `EncodeTypes` 列舉。  

### 步驟 2：初始化條碼產生器  

我們將產生一個 **Databar Omni‑Directional** 符號，編碼 GTIN‑14 值。建構函式接受條碼類型與原始資料字串。  

```csharp
// Initialise a generator for Databar Omni‑Directional
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

`EncodeTypes.DatabarOmniDirectional` 參數告訴 Aspose.BarCode 使用哪種條碼標準。資料字串遵循 GS1 應用識別碼格式，這在零售條碼中很常見。  

### 步驟 3：設定常用條碼參數  

最常調整的兩個視覺參數是 X‑dimension（窄條寬度）與整體條碼高度。  

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;

// Set the initial bar height to 30 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

**X‑dimension** 控制條碼的密度，而 **BarHeight** 決定每條的垂直尺寸。當您需要為不同的列印媒介 **change barcode height** 時，調整 **BarHeight** 正是所需的操作。  

### 步驟 4：儲存第一張影像（30 像素高度）  

```csharp
// Save the barcode as a 30‑pixel‑high PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

`Save` 方法會將渲染後的影像寫入磁碟。檔名清楚標示使用的高度，方便比較不同的輸出結果。  

### 步驟 5：將條碼高度變更為 60 像素  

現在示範在執行時 **how to adjust bar height**。同一個 `generator` 實例被重複使用；僅修改 `BarHeight` 屬性。  

```csharp
// Increase the bar height to 60 pixels
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the larger barcode
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

由於產生器保留了其他所有設定（條碼類型、資料、X‑dimension），兩個 PNG 檔案唯一的視覺差異就是條碼的垂直尺寸。  

### 完整原始碼  

將所有程式碼整合在一起，即可得到簡潔且可執行的程式：  

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
            // 1️⃣ Initialise the generator for Databar Omni‑Directional
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Configure visual parameters
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // narrow bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // first height

            // 3️⃣ Save the 30‑pixel‑high image
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 30‑pixel barcode.");

            // 4️⃣ Change the bar height to 60 pixels (how to adjust bar height)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;

            // 5️⃣ Save the 60‑pixel‑high image
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved 60‑pixel barcode.");

            // Optional: clean up resources
            generator.Dispose();
        }
    }
}
```

**預期輸出**  

執行程式後，會在執行檔的工作目錄中產生兩個 PNG 檔案：

* `DatabarBarHeight30Pixels.png` – 條碼的 BarHeight 為 30 像素。  
* `DatabarBarHeight60Pixels.png` – 同樣的條碼，但每條的高度是前者的兩倍。  

在任何檢視器中開啟這些影像；您會看到整體圖樣保持相同，僅垂直尺寸改變，證實 **change barcode height** 操作成功。  

## 進階變化  

### 切換至其他條碼類型  

如果您需要 QR code 而非 Databar，只需更換 `EncodeTypes` 的值：  

```csharp
generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

其他參數設定（X‑dimension、BarHeight）仍然適用於相應的情況。  

### 使用 `BarHeight` 設定為毫米  

Aspose.BarCode 亦支援實體單位。若要設定 10 mm 的高度：  

```csharp
generator.Parameters.Barcode.BarHeight.Millimeters = 10;
```

當您為需要精確尺寸的列印版面產生條碼時，這非常方便。  

### 錯誤處理  

如果資料字串不符合所選條碼類型，`BarcodeGenerator` 會拋出 `ArgumentException`。請將產生邏輯包在 try‑catch 區塊中，以提供友善的訊息：  

```csharp
try
{
    generator.Save("output.png", BarCodeImageFormat.Png);
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## 常見問題解答  

* **Does changing BarHeight affect scanability?**  
  條碼只要符合 X‑dimension 與整體靜區的規範，仍然可被掃描。僅提升高度會使條碼變長，並不會降低對比度。  

* **Can I set different heights for individual bars?**  
  不行。`BarHeight` 屬性會均勻套用於整個符號。若需變高設計，必須在 Aspose.BarCode 範圍之外自行實作自訂渲染程序。  

* **Is PNG the best format for printing?**  
  PNG 保留無損像素資料，適合螢幕顯示。若是高解析度列印，建議使用 `BarCodeImageFormat.Tiff` 或 `Pdf` 以保留向量資訊。  

## 結論  

現在您已了解如何使用 Aspose.BarCode **create barcode c#** 應用程式，看到完整的 **barcode generator example**，並掌握 **how to adjust bar height** 以符合不同版面需求。透過重複使用同一個產生器實例，僅修改 `BarHeight`，即可有效 **change barcode height**，而無需重新建立整個物件。  

接下來您可以探索：

* 產生其他條碼類型（`EncodeTypes.Code128`、`EncodeTypes.EAN13`）。  
* 匯出為 SVG 或 PDF 以取得可縮放的圖形。  
* 使用 Aspose.Words 或 Aspose.Cells 將條碼直接嵌入 Word 或 Excel 文件中。  

祝程式開發順利，盡情體驗 Aspose.BarCode 為您的 C# 條碼專案帶來的彈性！  

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [How to create a barcode PNG file with adjustable height in C#](/barcode/english/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/)
- [How to Generate Barcode in C# – Complete Aspose.BarCode Guide](/barcode/english/python-java/general/how-to-generate-barcode-in-c-complete-aspose-barcode-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}