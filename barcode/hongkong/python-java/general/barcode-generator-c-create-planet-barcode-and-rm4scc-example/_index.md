---
category: general
date: 2026-08-03
description: 條碼產生器 C# 教學，示範如何使用 Aspose.BarCode 建立 Planet 條碼、設定 X 尺寸，並儲存為 PNG 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator c#
- create planet barcode
language: zh-hant
lastmod: 2026-08-03
og_description: 條碼產生器 C# 教學一步步教你建立 Planet 條碼、調整 X 尺寸，並使用 Aspose.BarCode 儲存為 PNG。
og_image_alt: Screenshot of generated Planet and RM4SCC barcodes in PNG format
og_title: 條碼產生器 C# – 一步一步建立 Planet 條碼
schemas:
- author: Aspose
  dateModified: '2026-08-03'
  description: Barcode generator C# tutorial showing how to create Planet barcode
    with Aspose.BarCode, set X‑dimension, and save as PNG images.
  headline: Barcode generator C# – create Planet barcode and RM4SCC example
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 條碼產生器 C# – 建立 Planet 條碼與 RM4SCC 範例
url: /zh-hant/python-java/general/barcode-generator-c-create-planet-barcode-and-rm4scc-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Barcode generator C# – create Planet barcode and RM4SCC example

如果你需要一個 **barcode generator C#** 能產生郵政專用符號，本教學將示範如何使用 Aspose.BarCode **建立 Planet barcode** 圖片。你會看到如何設定 X‑dimension、產生相對應的 RM4SCC 條碼，並將兩者儲存為 PNG 檔案——只需幾個簡潔步驟。

本教學涵蓋在 .NET 6 或更新版本上執行程式碼所需的一切，說明每個設定的意義，並指出常見的陷阱（例如模組寬度設定錯誤或目錄權限不足）。完成後，你將得到兩張符合 Planet 與 RM4SCC 標準的可直接列印條碼圖檔。

## Prerequisites

開始之前，請確保你已具備：

* .NET 6 SDK（或任何 Aspose.BarCode 支援的 .NET 版本）
* Visual Studio 2022 或你慣用的 C# IDE
* 已加入 **Aspose.BarCode** 的 NuGet 參考（`Install-Package Aspose.BarCode`）
* 對欲存放 PNG 檔案的資料夾具備寫入權限

不需要額外的外部服務；所有編碼皆在本機函式庫內完成。

## Step 1: Initialise the barcode generator C# object

第一步是建立 `BarcodeGenerator` 的實例。建構子接受條碼類型（`EncodeTypes.Planet`）與要編碼的資料。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

*Why this step?*  
`BarcodeGenerator` 是產生任何條碼的入口。選擇 `EncodeTypes.Planet` 會讓函式庫依照多數郵政服務使用的 ISO/IEC 24723 規範來產生條碼。

## Step 2: Set the X‑dimension (module width) for the Planet barcode

X‑dimension 定義單一條碼模組（最小的條或空白）的寬度。**4 像素** 的設定對大多數標籤印表機來說相當合適。

```csharp
// Step 2: Define the X‑dimension (module width) in pixels
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Why this matters*  
若模組太窄，條碼可能無法被辨識；若太寬則會不必要地增大標籤尺寸。調整 `Pixels` 可讓你依印表機解析度微調條碼。

## Step 3: Save the Planet barcode as a PNG image

Aspose.BarCode 會根據所選的條碼類型自動計算條碼高度，你只需要提供檔案路徑與格式。

```csharp
// Step 3: Save the Planet barcode as a PNG image (height is calculated automatically)
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*Tip*  
將 `YOUR_DIRECTORY` 替換為本機上已存在的絕對或相對路徑。若資料夾不存在，`Save` 方法會拋出 `DirectoryNotFoundException`。

**Expected output** – 一個 PNG 檔案，外觀類似下圖（此處不顯示實際圖像，但你會看到一個帶有數字 `123456` 的標準 Planet 條碼）。

## Step 4: Initialise a second generator for the RM4SCC barcode

許多郵政系統要求在同一封信件上同時印製 Planet 與 RM4SCC 符號。為 RM4SCC 類型再建立一個 `BarcodeGenerator` 實例。

```csharp
// Step 4: Create an RM4SCC barcode generator with the same data
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
```

*Why a separate instance?*  
每種條碼類型都有自己的參數集合。重複使用同一個產生器可能會不小心帶入不適用於第二條碼的設定（例如 X‑dimension）。

## Step 5: Configure the X‑dimension for the RM4SCC barcode

RM4SCC 同樣遵循 X‑dimension 設定，我們使用相同的像素寬度以保持視覺一致性。

```csharp
// Step 5: Set the X‑dimension for the RM4SCC barcode
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

*Pro tip*  
若需要較高的條碼（例如較大的標籤），也可以設定 `Height.Pixels`。不設定時，函式庫會自動計算最適高度。

## Step 6: Save the RM4SCC barcode as a PNG image

最後，將 RM4SCC 條碼寫入磁碟。

```csharp
// Step 6: Save the RM4SCC barcode as a PNG image (height is calculated automatically)
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeightNone.png", BarCodeImageFormat.Png);
```

現在你已擁有兩個 PNG 檔案——`PostalPlanetBarHeightNone.png` 與 `PostalRM4SCCBarHeightNone.png`——可嵌入郵件標籤、列印於信封，或交給第三方列印服務。

## Optional: Adjusting height or using other image formats

如果工作流程需要特定的條碼高度或其他影像格式（例如 JPEG 或 BMP），可在呼叫 `Save` 前調整參數：

```csharp
// Example: set a fixed height of 100 pixels and save as JPEG
planetGenerator.Parameters.Barcode.Height.Pixels = 100;
planetGenerator.Save("PostalPlanet.jpg", BarCodeImageFormat.Jpeg);
```

**Edge case** – 設定自訂高度時，請確保該值符合 ISO 標準規定的最小高度；否則條碼可能無法通過驗證。

## Common pitfalls and how to avoid them

| Pitfall | Why it happens | Fix |
|---------|----------------|-----|
| `DirectoryNotFoundException` | 目標資料夾不存在或拼寫錯誤。 | 先建立資料夾，或使用 `Path.Combine` 搭配 `Environment.CurrentDirectory`。 |
| Barcode unreadable on low‑resolution printers | X‑dimension 對印表機 DPI 來說太小。 | 將 `XDimension.Pixels` 提升至 5 – 6（適用於 203 dpi 印表機），或先用樣本標籤測試。 |
| Wrong symbology used | 傳入 `EncodeTypes.Code128` 而非 `EncodeTypes.Planet`。 | 再次確認 `EncodeTypes` 列舉值與所需的郵政標準相符。 |
| Null reference on `Parameters` | 使用較舊版本的 Aspose.BarCode，API 不同。 | 升級至最新的 NuGet 套件（v23.12 或以上）。 |

## Full runnable example

以下是完整程式碼，你可以直接複製、貼上並執行。程式碼包含 `using` 陳述式、錯誤處理與說明每一行功能的註解。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define the output directory (change as needed)
        string outputDir = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputDir);

        // -------- Planet barcode ----------
        var planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string planetPath = Path.Combine(outputDir, "PostalPlanetBarHeightNone.png");
        planetGenerator.Save(planetPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Planet barcode saved to: {planetPath}");

        // -------- RM4SCC barcode ----------
        var rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        string rm4sccPath = Path.Combine(outputDir, "PostalRM4SCCBarHeightNone.png");
        rm4sccGenerator.Save(rm4sccPath, BarCodeImageFormat.Png);
        Console.WriteLine($"RM4SCC barcode saved to: {rm4sccPath}");
    }
}
```

執行後會在執行檔旁建立 `Barcodes` 資料夾，並將兩個 PNG 檔案放入其中。使用任何影像檢視器開啟即可驗證結果。

## Conclusion

現在你已擁有一套 **barcode generator C#** 解決方案，能 **create Planet barcode** 圖片、調整 X‑dimension 以獲得最佳列印效果，並產生相對應的 RM4SCC 條碼——只需幾行程式碼。此方法適用於 .NET 6 以上版本，只需 Aspose.BarCode NuGet 套件，亦可透過更換 `EncodeTypes` 值擴充至 Code128、QR、DataMatrix 等其他條碼類型。

### What’s next?

* 嘗試不同的 `XDimension.Pixels` 數值，以配合你的印表機 DPI。
* 透過變更 `BarCodeImageFormat` 列舉，產生 PDF、SVG 等其他格式。
* 使用 **SkiaSharp** 等圖形函式庫將兩張 PNG 合併成單一標籤。
* 探索完整的 Aspose.BarCode API，了解校驗碼驗證或自訂字型等進階功能。

歡迎將程式碼改寫為批次處理，或整合至 ASP.NET Core Web 服務，讓它在需要時即時回傳條碼圖像。祝開發順利！

## What Should You Learn Next?

以下教學與本指南的技術緊密相關，能幫助你進一步掌握 API 功能並探索其他實作方式：

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [How to Save PNG using DataMatrix C40 with Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}