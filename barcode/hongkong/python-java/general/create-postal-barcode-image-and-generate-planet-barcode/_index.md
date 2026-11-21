---
category: general
date: 2026-11-20
description: 在 C# 中快速建立郵政條碼圖像。學習如何產生 Planet 條碼與 RM4SCC 條碼，並可自訂條紋樣式。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- postal barcode C#
- Aspose.BarCode example
- barcode image generation
language: zh-hant
lastmod: 2026-11-20
og_description: 使用 Aspose.BarCode 在 C# 中建立郵政條碼圖像。本教學示範如何產生 Planet 條碼、客製化條碼樣式，以及產生
  RM4SCC 圖像。
og_image_alt: Create postal barcode image example showing filled and empty bars
og_title: 在 C# 中建立郵政條碼圖像 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create postal barcode image in C# quickly. Learn how to generate planet
    barcode and RM4SCC barcodes with customizable bar styles.
  headline: Create postal barcode image and generate planet barcode
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: 建立郵政條碼圖像並生成星球條碼
url: /zh-hant/python-java/general/create-postal-barcode-image-and-generate-planet-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立郵政條碼圖像並產生 Planet 條碼

使用 Aspose.BarCode 函式庫在 C# 中建立郵政條碼圖像。如果您需要為郵寄應用產生 Planet 條碼或 RM4SCC 條碼，本教學提供完整、可直接執行的解決方案。

產生郵政服務條碼通常需要精確的尺寸，且需要在實心與空心條紋樣式之間切換。本指南將帶您設定輸出資料夾、建立實心與空心的 Planet 條碼，並以相同的視覺設定產生 RM4SCC 條碼。完成後，您將擁有四個可直接用於郵寄工作流程的 PNG 檔案。

## 先決條件

在開始之前，請確保您已具備：

* .NET 6.0 或更新版本  
* Visual Studio 2022（或任何您偏好的 C# IDE）  
* **Aspose.BarCode** NuGet 套件（`Install-Package Aspose.BarCode`）  

不需要額外的設定；程式碼僅使用預設字型與 PNG 編碼器。

## 建立郵政條碼圖像 – 概觀

此流程的核心是 `BarcodeGenerator` 類別。它接受一個 `EncodeTypes` 值，用以決定條碼的符號系統（例如 `EncodeTypes.Planet` 代表 Planet 條碼）。設定好產生器後，呼叫 `Save` 即可寫入圖像檔案。

![Create postal barcode image example](/images/postal_barcode_example.png)

*Alt text: 建立郵政條碼圖像範例，顯示實心與空心條紋。*

## 步驟 1：設定輸出資料夾

首先定義一個資料夾，用來儲存 PNG 檔案。使用絕對或相對路徑皆可，只要確保資料夾存在，或讓程式自行建立即可。

```csharp
using System.IO;
using Aspose.BarCode.Generation;

// Define the output folder (change to your own path)
string outputFolder = Path.Combine(Directory.GetCurrentDirectory(), "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
```

以程式方式建立資料夾可避免在全新機器上執行教學時拋出 `DirectoryNotFoundException`。

## 步驟 2：產生實心 Planet 條碼

實心條紋的 Planet 條碼是預設的視覺樣式。以下程式碼會建立條碼、將 X‑dimension 設為 4 像素（郵政應用常用尺寸），並儲存圖像。

```csharp
// Step 2: Generate a Planet barcode with filled bars
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save as PNG
string planetFilledPath = Path.Combine(outputFolder, "PostalPlanetFilledBars.png");
planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
```

**為什麼這樣有效：**  
* `EncodeTypes.Planet` 告訴產生器使用 Planet 符號系統，這是許多郵政服務的必備規格。  
* `XDimension.Pixels` 控制每條條紋的寬度；4 px 可產生清晰且易於掃描的圖像，同時保持檔案大小適中。  
* `Save` 方法會根據 `BarCodeImageFormat` 列舉自動選擇 PNG 編碼器。

## 步驟 3：產生空心 Planet 條碼

某些郵政規範偏好在深色背景上使用空白（白色）條紋。只要將 `FilledBars` 設為 `false` 即可達成。

```csharp
// Step 3: Generate a Planet barcode with empty bars
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Keep the same X‑dimension for consistency
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;

// Disable filled bars – the bars become transparent (empty)
planetEmpty.Parameters.Barcode.FilledBars = false;

// Save the result
string planetEmptyPath = Path.Combine(outputFolder, "PostalPlanetEmptyBars.png");
planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
```

**提示：** 當 `FilledBars` 為 `false` 時，產生器會將條紋繪製為背景色（預設為白色），而空白區域則使用前景色（黑色）。若需其他配色，請調整 `Parameters.Barcode.ForeColor` 與 `BackColor`。

## 步驟 4：產生實心 RM4SCC 條碼

RM4SCC 是英國使用的另一種郵政符號系統。建立步驟與 Planet 範例相同，唯一差異在於 `EncodeTypes` 的值。

```csharp
// Step 4: Generate an RM4SCC barcode with filled bars
BarcodeGenerator rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Reuse the same X‑dimension for a uniform look
rm4sccFilled.Parameters.Barcode.XDimension.Pixels = 4;

// Save the PNG file
string rm4sccPath = Path.Combine(outputFolder, "PostalRM4SCCFilledBars.png");
rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
```

**預期結果：** 產生的 PNG 會顯示符合英國郵政指南的緊湊 RM4SCC 條碼。由於 X‑dimension 相同，圖像尺寸與 Planet 條碼相近。

## 步驟 5：驗證產生的圖像

執行程式後，開啟 `Barcodes` 資料夾中的四個檔案，您應該會看到：

* `PostalPlanetFilledBars.png` – 深色條紋於淺色背景  
* `PostalPlanetEmptyBars.png` – 淺色條紋於深色背景（反相）  
* `PostalRM4SCCFilledBars.png` – 標準 RM4SCC 圖樣  

若任何圖像看起來失真，請檢查以下項目：

* **X‑dimension** – 小於 2 px 可能導致模糊；大於 10 px 可能超出標籤尺寸限制。  
* **資料字串** – 值 `"123456"` 必須符合所選符號系統的長度要求（Planet 需要 6 位數，RM4SCC 亦同）。  
* **資料夾權限** – 確保應用程式對輸出目錄具有寫入權限。

## 常見變化與邊緣情況

| 情境 | 調整 |
|----------|------------|
| **不同的條碼資料** | 將 `"123456"` 替換為任何有效的數字字串。對於 Planet，長度必須恰好為 6 位；RM4SCC 亦需 6 位。 |
| **自訂顏色** | 設定 `planetFilled.Parameters.Barcode.ForeColor = System.Drawing.Color.DarkBlue;` 並 `BackColor = System.Drawing.Color.LightYellow;`。 |
| **更高解析度** | 將 `XDimension.Pixels` 提升至 6 或 8，以獲得較大的列印尺寸。 |
| **其他圖像格式** | 在 `Save` 呼叫中使用 `BarCodeImageFormat.Jpeg` 或 `BarCodeImageFormat.Bmp`。 |
| **批次產生** | 針對字串集合進行迴圈，於迴圈內呼叫相同的產生器邏輯，並重複使用 `outputFolder` 路徑。 |

## 完整、可執行範例

將以下程式碼複製到新的 C# 主控台專案中。它可在 .NET 6.0 下編譯，並自動產生四個條碼圖像。



## 接下來應該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並提供完整的可執行程式碼範例與逐步說明，協助您掌握更多 API 功能，或在自己的專案中探索替代實作方式。

- [如何在 C# 中建立具有自訂高度的郵政條碼圖像](/barcode/english/python-java/general/how-to-create-postal-barcode-image-with-custom-heights-in-c/)
- [如何在 C# 中建立 RM4SCC 條碼並產生 Planet 條碼](/barcode/english/python-java/general/how-to-create-rm4scc-barcode-and-generate-planet-barcode-in/)
- [在 C# 中建立郵政條碼圖像 – 步驟說明指南](/barcode/english/python-java/general/create-postal-barcode-image-in-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}