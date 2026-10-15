---
category: general
date: 2026-10-08
description: 在 C# 中產生 PDF417 條碼，並學習如何使用 Aspose.BarCode 高效產生 PDF417 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417
- create barcode image c#
language: zh-hant
lastmod: 2026-10-08
og_description: 在 C# 中產生 PDF417 條碼，提供逐步教學。學習如何產生 PDF417 並將條碼圖像儲存為 PNG。
og_image_alt: Generated PDF417 barcode saved as a PNG image
og_title: 產生 PDF417 條碼並在 C# 中建立條碼圖像
schemas:
- author: Aspose
  dateModified: '2026-10-08'
  description: Generate PDF417 barcode in C# and learn how to generate PDF417 images
    efficiently with Aspose.BarCode.
  headline: Generate PDF417 barcode and create barcode image C#
  type: TechArticle
tags:
- barcode
- pdf417
- csharp
title: 產生 PDF417 條碼並建立條碼圖像 C#
url: /zh-hant/net/compact-pdf417-encoding/generate-pdf417-barcode-and-create-barcode-image-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生 PDF417 條碼並建立條碼影像 C#

如果您需要在 .NET 應用程式中 **產生 PDF417 條碼**，本教學將完整示範如何操作。您將看到一個可執行的完整範例，該範例會建立條碼、客製化其版面配置，並將結果儲存為 PNG 影像。

產生 PDF417 條碼是運輸標籤、登機證與庫存系統的常見需求。完成本指南後，您將能夠 **how to generate PDF417** 並對尺寸與版面進行精細控制，同時也會學會 **create barcode image C#** 檔案，這些檔案可在 UI 中顯示或傳送至印表機。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦可在 .NET Framework 4.7.2+ 上執行）
- Visual Studio 2022 或任何相容 C# 的 IDE
- Aspose.BarCode for .NET（免費試用版或授權版）  
  透過 NuGet 安裝：

```bash
dotnet add package Aspose.BarCode
```

不需要額外的設定；此函式庫會在內部處理 PNG 編碼。

## 步驟 1：設定專案並匯入命名空間

建立一個新的 console 專案，並加入必要的 `using` 指令。此區塊包含了編譯範例所需的全部內容。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation code lives here
        }
    }
}
```

*此步驟的重要性*：匯入 `Aspose.BarCode.Generation` 命名空間可讓您存取 `BarcodeGenerator`、`EncodeTypes`，以及用於客製化條碼的參數物件。

## 步驟 2：以指定文字產生 PDF417 條碼

在 `Main` 方法中，使用 `EncodeTypes.Pdf417` 建立 `BarcodeGenerator` 實例。建構子會接受條碼類型與您想要編碼的文字。

```csharp
// Step 2: Create a PDF417 barcode generator with the desired text
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");
```

*說明*：`EncodeTypes.Pdf417` 告訴函式庫產生 PDF417 符號。字串 `"Layout demo"` 會成為條碼中編碼的資料負載。

## 步驟 3：使用 X‑dimension 微調條碼尺寸

X‑dimension 控制單一模組（最小的黑白方格）的寬度。以像素設定可精確控制最終影像的大小。

```csharp
// Step 3: Define the module (X) dimension in pixels for finer control over barcode size
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*此設定的意義*：較小的 X‑dimension 會產生更緊湊的條碼，適用於標籤或 UI 元件空間受限的情況。

## 步驟 4：自訂 PDF417 版面（欄與列）

PDF417 允許您指定欄數與列數。調整這些數值會改變條碼的長寬比。

```csharp
// Step 4: Set the layout – 4 columns and 9 rows for this example
barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;
```

*說明*：使用 4 欄 9 列時，條碼的高度大於寬度，符合許多票證列印格式。

## 步驟 5：將產生的條碼儲存為 PNG 影像

最後，將條碼寫入檔案。`BarCodeImageFormat.Png` 列舉確保無損壓縮。

```csharp
// Step 5: Save the generated barcode as a PNG image
string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
Console.WriteLine($"Barcode saved to {outputPath}");
```

*此處的作用*：`Save` 會在磁碟上建立影像檔。若需其他格式，可將 `BarCodeImageFormat.Png` 替換為 `Jpeg` 或 `Bmp`。

### 完整範例（單一區塊）

以下為完整、可直接執行的程式。請將 `YOUR_DIRECTORY` 替換為您機器上的實際資料夾路徑。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a PDF417 barcode generator with the desired text
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Pdf417, "Layout demo");

            // Define the module (X) dimension in pixels for finer control over barcode size
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set the layout – 4 columns and 9 rows for this example
            barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
            barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9;

            // Save the generated barcode as a PNG image
            string outputPath = @"YOUR_DIRECTORY\LayoutPdf417.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

執行程式 (`dotnet run`) 並開啟產生的 `LayoutPdf417.png`。您應該會看到一個乾淨的 PDF417 條碼，編碼的文字為 *Layout demo*。

![已儲存為 PNG 的產生 PDF417 條碼範例](image-placeholder.png){: .responsive-img alt="已儲存為 PNG 的產生 PDF417 條碼範例"}

*預期輸出*：一個 PNG 檔案，尺寸約為 150 × 300 像素（大小會隨 X‑dimension 而變），內含可掃描的 PDF417 條碼。

## 常見變化與邊緣案例

| Scenario | How to adapt the code |
|----------|----------------------|
| **不同的資料負載** | 將 `BarcodeGenerator` 的第二個參數（`"Layout demo"`）改為任意字串，最多 1 800 個字元。 |
| **更高解析度** | 將 `XDimension.Pixels` 提升（例如 `4`），或透過 `barcodeGenerator.Parameters.ImageResolution.Dpi = 300;` 設定 `Resolution`。 |
| **透明背景** | 使用 `barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png, new ImageOptions { BackgroundColor = Color.Transparent });`。 |
| **嵌入 Windows Forms PictureBox** | 改為呼叫 `barcodeGenerator.Save(pictureBox1.CreateGraphics(), BarCodeImageFormat.Png);`，而非 `Save`。 |
| **錯誤處理** | 將產生條碼的程式碼包在 `try…catch` 區塊中，以捕捉不支援字元的 `BarCodeException`。 |

## 專業提示

- **Validate the barcode**：儲存後，您可以使用條碼掃描器 SDK 載入 PNG，確認資料與原始字串相符。
- **Performance**：重複使用同一個 `BarcodeGenerator` 實例產生多個條碼，可減少分配開銷。
- **Security**：若編碼資料包含敏感資訊，請考慮在傳遞給產生器之前先加密。

## 結論

您現在已了解如何在 C# 中 **generate PDF417 barcode**，以及如何建立符合自訂版面需求的 **create barcode image C#** 檔案。完整範例示範了初始化產生器、微調尺寸與版面，並將結果儲存為 PNG。接下來，您可以探索其他功能，例如顏色客製化、嵌入商標，或批次產生多個條碼以供大量列印。

---

*Next steps*：  
- 使用相同的 `BarcodeGenerator` 類別嘗試其他符號（Code128、QR）。  
- 了解如何使用 Aspose.BarCode 的 `BarCodeReader` 讀取 PDF417 條碼。  
- 將產生的 PNG 整合至 ASP.NET Core MVC 視圖，以即時產生條碼。

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何在 C# 中使用 Aspose 儲存條碼並產生 PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [如何使用 Aspose 產生 PDF417 條碼 – 完整指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [如何在 C# 中使用自訂尺寸產生 PDF417 條碼](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}