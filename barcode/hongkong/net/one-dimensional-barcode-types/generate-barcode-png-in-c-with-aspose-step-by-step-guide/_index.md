---
category: general
date: 2026-11-27
description: 使用 Aspose.BarCode 在 C# 中快速產生條碼 PNG。了解如何使用 C# 程式碼建立條碼圖像、設定尺寸、選擇列數，並儲存為
  PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode png
- create barcode image c#
- generate barcode with aspose
language: zh-hant
lastmod: 2026-11-27
og_description: 使用 Aspose.BarCode 在 C# 中產生條碼 PNG。參考本指南，可在 C# 中建立條碼圖像、調整尺寸，並儲存為 PNG
  檔案。
og_image_alt: Screenshot of a generated MicroPdf417 barcode PNG
og_title: 使用 Aspose 在 C# 中生成條碼 PNG – 完整教學
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Generate barcode PNG in C# quickly using Aspose.BarCode. Learn how
    to create barcode image C# code, set dimensions, choose columns, and save as PNG.
  headline: Generate barcode PNG in C# with Aspose – step‑by‑step guide
  type: TechArticle
- description: Generate barcode PNG in C# quickly using Aspose.BarCode. Learn how
    to create barcode image C# code, set dimensions, choose columns, and save as PNG.
  name: Generate barcode PNG in C# with Aspose – step‑by‑step guide
  steps:
  - name: Why each step matters
    text: '* **Step 1** – Instantiating `BarcodeGenerator` ties the text you want
      to encode to a specific barcode type. If you need a different symbology (e.g.,
      QR, Code128), you only change `EncodeTypes`. * **Step 2** – The X‑dimension
      controls the smallest bar width. Adjusting this value influences both read'
  - name: Expected output
    text: 'Below is a textual representation of the generated PNG (the actual image
      will be visual, not text):'
  - name: Generating other barcode formats
    text: To **generate barcode with Aspose** for a different symbology, replace `EncodeTypes.MicroPdf417`
      with another enum value, such as `EncodeTypes.QR` or `EncodeTypes.Code128`.
      The rest of the code remains identical.
  - name: Changing image format
    text: 'Aspose supports several raster formats (`Png`, `Jpeg`, `Bmp`, `Gif`). To
      save as JPEG, modify the `Save` call:'
  - name: Handling large text payloads
    text: MicroPdf417 has a limited data capacity. If your text exceeds this limit,
      Aspose throws an `ArgumentException`. In such cases, switch to the full `Pdf417`
      symbology, which supports longer strings.
  - name: Running in a web application
    text: 'When generating a barcode image on the fly in ASP.NET Core, you can write
      the PNG directly to the response stream:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 使用 Aspose 在 C# 中產生條碼 PNG – 步驟指南
url: /zh-hant/net/one-dimensional-barcode-types/generate-barcode-png-in-c-with-aspose-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose 於 C# 產生條碼 PNG – 步驟教學

如果您需要在 .NET 應用程式中 **產生條碼 PNG**，本教學將示範如何使用 Aspose.BarCode 完成。您將學會 **建立條碼影像 C#** 程式碼、調整尺寸、指定欄位數，並將結果儲存為 PNG 檔案。

條碼產生是庫存系統、票券平台與行動應用程式的常見需求。使用 Aspose 可免除外部服務或複雜影像處理函式庫的需求。完成本教學後，您將擁有一個自包含、可執行的程式，能在磁碟上產生 MicroPdf417 條碼 PNG。

## 前置條件

開始之前，請確保您已具備：

* **.NET 6.0** 或更新版本（此程式碼亦相容 .NET Framework 4.7 以上）。  
* 有效的 **Aspose.BarCode for .NET** 授權或暫時的評估金鑰。  
* 如 **Visual Studio 2022** 或 **VS Code**（安裝 C# 擴充功能）的開發環境。  

除 `Aspose.BarCode` 之外，無需其他 NuGet 套件。

## 步驟 1：安裝 Aspose.BarCode NuGet 套件

在專案資料夾的終端機中執行：

```bash
dotnet add package Aspose.BarCode
```

此指令會將最新的 Aspose.BarCode 程式庫加入您的專案，讓您可以使用教學中會用到的 `BarcodeGenerator` 類別。

## 步驟 2：建立基本的主控台應用程式

如果尚未有專案，請建立新的主控台專案：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
```

將 `Program.cs` 內容替換為下列骨架程式碼。骨架已包含必要的 `using` 指示詞與 `Main` 方法，我們將在此加入條碼產生的邏輯。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The barcode generation code will be inserted here.
        }
    }
}
```

## 步驟 3：使用 Aspose.BarCode 產生條碼 PNG

以下為完整程式碼，**產生條碼 PNG** 使用 MicroPdf417 符號。每一行都有註解說明其意義，方便您將範例套用至其他條碼類型。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // 1️⃣ Create a barcode generator for MicroPdf417 with the desired text.
            //    EncodeTypes.MicroPdf417 tells Aspose which symbology to use.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.MicroPdf417, "Sample text");

            // 2️⃣ Set the X‑dimension (module width) in pixels.
            //    A smaller value yields a more compact barcode; 2 pixels works well for most screens.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ Define the number of columns for the MicroPdf417 barcode.
            //    Valid values are 1‑4. More columns reduce the height but increase width.
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // 4️⃣ Choose the output path. Ensure the directory exists or Aspose will throw an exception.
            string outputPath = "MicroPdf417.png";

            // 5️⃣ Save the generated barcode as a PNG image.
            //    BarCodeImageFormat.Png is the most widely supported raster format.
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode PNG generated at: {outputPath}");
        }
    }
}
```

### 為何每一步都很重要

* **步驟 1** – 建立 `BarcodeGenerator` 時會將欲編碼的文字與特定條碼類型關聯。若需其他符號（例如 QR、Code128），只要更改 `EncodeTypes` 即可。  
* **步驟 2** – X‑dimension 控制最小條寬。調整此值會影響條碼的可讀性與實體尺寸。  
* **步驟 3** – MicroPdf417 允許透過設定欄位數來平衡高度與寬度。對於行動螢幕而言，較寬但較短的條碼通常較好看。  
* **步驟 5** – 以 PNG 儲存可保留無損影像品質，對掃描準確度相當重要。

## 步驟 4：執行程式並驗證輸出

編譯並執行專案：

```bash
dotnet run
```

您應該會在主控台看到訊息：

```
Barcode PNG generated at: MicroPdf417.png
```

前往專案資料夾並開啟 `MicroPdf417.png`。此影像包含一個清晰的 MicroPdf417 條碼，編碼文字為 *Sample text*。大多數條碼掃描器與行動應用程式皆能直接讀取此檔案，無需額外設定。

### 預期輸出

以下為產生的 PNG 之文字化表示（實際圖像會是視覺圖形，而非文字）：

```
┌─────────────────────────────────────┐
│ █ █ █ █   █ █ █ █   █ █ █ █ █ █ █   │
│ █   █ █ █ █   █ █ █ █ █   █ █ █ █   │
│ ... (barcode pattern)               │
└─────────────────────────────────────┘
```

若您在圖像檢視器中開啟 PNG，會看到一個四欄、每個模組寬度為兩像素的清晰條碼。

## 步驟 5：常見變化與例外情況

### 產生其他條碼格式

若要 **使用 Aspose 產生其他條碼**，只需將 `EncodeTypes.MicroPdf417` 改為其他列舉值，例如 `EncodeTypes.QR` 或 `EncodeTypes.Code128`。其餘程式碼保持不變。

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.QR, "https://example.com");
```

### 更換影像格式

Aspose 支援多種點陣圖格式（`Png`、`Jpeg`、`Bmp`、`Gif`）。若要儲存為 JPEG，只需修改 `Save` 呼叫：

```csharp
generator.Save("barcode.jpg", BarCodeImageFormat.Jpeg);
```

### 處理大型文字內容

MicroPdf417 的資料容量有限。若文字超過此上限，Aspose 會拋出 `ArgumentException`。此時可改用完整的 `Pdf417` 符號，以支援較長的字串。

```csharp
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, longText);
```

### 在 Web 應用程式中使用

若在 ASP.NET Core 中即時產生條碼影像，可直接將 PNG 寫入回應串流：

```csharp
byte[] pngBytes = generator.GenerateBarCodeImage(BarCodeImageFormat.Png);
return File(pngBytes, "image/png");
```

## 生產環境使用小技巧

* **提前授權** – 使用評估版會在影像上加上浮水印。請在第一次 `Save` 前套用授權，以免出現水印。  
* **驗證輸入** – 確保傳入的文字符合所選條碼的字元集，否則 Aspose 會拋出例外。  
* **快取產生的影像** – 若相同條碼被頻繁請求，請將 PNG 存於磁碟或記憶體，以減少 CPU 負載。  
* **執行緒安全** – `BarcodeGenerator` 實例非執行緒安全。請於每次請求建立新實例，或自行同步存取。

## 結論

現在您已掌握如何在 C# 中使用 Aspose.BarCode **產生條碼 PNG**，從安裝套件、調整尺寸到儲存影像的完整流程。完整範例示範了 **建立條碼影像 C#** 程式的標準工作流程，且可延伸至其他條碼類型、影像格式與部署情境。

接下來，您可以探索如 **使用 Aspose 於 PDF 文件產生條碼**、為 QR 代碼加入錯誤更正等相關主題，或結合 Aspose.OCR 進行條碼掃描。嘗試不同的 `EncodeTypes` 與參數設定，找出最適合您應用程式的配置。

祝開發順利！

## 接下來該學什麼？

以下教學與本指南的技術緊密相關，能進一步深化您的實作技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能與替代實作方式。

- [How to generate barcode set custom size and save image in C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Barcode image PNG in C# generate barcodes, change height](/barcode/english/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/)
- [How to create barcode PNG in C# using Aspose.Barcode](/barcode/english/python-java/general/how-to-create-barcode-png-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}