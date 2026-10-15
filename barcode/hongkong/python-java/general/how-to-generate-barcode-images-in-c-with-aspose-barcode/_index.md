---
category: general
date: 2026-10-12
description: 如何快速在 C# 中產生條碼。學習建立空白條碼並自訂條寬，以獲得清晰的郵政條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate barcode
- create empty barcode
language: zh-hant
lastmod: 2026-10-12
og_description: 如何在 C# 中使用 Aspose.BarCode 產生條碼。本指南將示範如何建立空白條碼以及調整條碼尺寸以符合郵政標準。
og_image_alt: Screenshot of generated barcode image created with how to generate barcode
  tutorial
og_title: 如何在 C# 中產生條碼圖像 – 一步一步指南
schemas:
- author: Aspose
  dateModified: '2026-10-12'
  description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  headline: How to generate barcode images in C# with Aspose.BarCode
  type: TechArticle
- description: How to generate barcode in C# quickly. Learn to create empty barcode
    and customize bar width for clear postal barcodes.
  name: How to generate barcode images in C# with Aspose.BarCode
  steps:
  - name: Why this step matters
    text: '* **Project scaffolding** ensures the tutorial is runnable without extra
      configuration. * The `using Aspose.BarCode.Generation;` and `using Aspose.BarCode;`
      namespaces expose the `BarcodeGenerator` class and image formats. * Creating
      the output folder programmatically avoids “directory not found” er'
  - name: Expected output
    text: Running the program will create an image similar to the one below (the actual
      image is not displayed here, but you’ll see a clear, 6‑digit barcode when you
      open the file).
  - name: Expected output
    text: 'The generated PNG contains only the bar outlines:'
  - name: Expected output
    text: '```text [PostalRM4SCCFilledBars.png] // solid bars representing "123456"
      ```'
  type: HowTo
tags:
- barcode generation
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 Aspose.BarCode 生成條碼圖像
url: /zh-hant/python-java/general/how-to-generate-barcode-images-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 產生條碼影像

如果您需要在 .NET 應用程式中從字串產生條碼影像，本指南提供完整、即時可執行的解決方案。您將會看到如何產生標準 Planet 與 RM4SCC 條碼、調整條寬以提升可讀性，以及 **create empty barcode** 變體（條碼未填滿）。此程式碼相容最新的 Aspose.BarCode for .NET（v.24.10），並可在 .NET 6 或更高版本上執行。

產生條碼是運送標籤、庫存系統與票務平台的常見需求。完成本教學後，您將能以程式方式產生實心與空心條碼，無需外部工具。

## 前置條件

* .NET 6 SDK（或任何較新版本的 .NET）
* Visual Studio 2022 或 VS Code
* 有效的 Aspose.BarCode for .NET 授權（免費評估版可用於測試）
* 具備 C# 主控台應用程式的基本知識

您可以使用以下指令安裝 Aspose.BarCode NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

## 步驟 1：建立最小化的主控台專案

建立一個新的主控台專案並加入所需的 `using` 指令。以下程式碼為完整範例；請將其複製到 `Program.cs` 後執行。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define output folder (adjust to your environment)
            string outputFolder = @"C:\Barcodes";

            // Ensure the folder exists
            System.IO.Directory.CreateDirectory(outputFolder);

            // Generate filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Generate empty Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Generate filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes have been saved to " + outputFolder);
        }

        /// <summary>
        /// Generates a Planet barcode and optionally disables bar filling.
        /// </summary>
        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            // Create generator for Planet symbology
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, data);

            // Set X dimension (bar width) to 4 pixels for better visibility
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // Control whether bars are filled or left empty
            generator.Parameters.Barcode.FilledBars = filled;

            // Choose a file name that reflects the filling mode
            string fileName = filled
                ? "PostalPlanetFilledBars.png"
                : "PostalPlanetEmptyBars.png";

            // Save the image as PNG
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }

        /// <summary>
        /// Generates an RM4SCC barcode with default filled bars.
        /// </summary>
        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);

            // Consistent bar width with Planet example
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName), BarCodeImageFormat.Png);
        }
    }
}
```

### 為何此步驟重要

* **Project scaffolding** 確保本教學可直接執行，無需額外設定。
* `using Aspose.BarCode.Generation;` 與 `using Aspose.BarCode;` 命名空間提供 `BarcodeGenerator` 類別與影像格式。
* 以程式方式建立輸出資料夾，可避免首次執行時出現「找不到目錄」錯誤。

## 步驟 2：產生實心 Planet 條碼

第一次呼叫 `GeneratePlanetBarcode` 時傳入 `filled: true`。這會產生標準的 Planet 條碼，且每根條紋皆以實心黑色矩形呈現。

* **Resulting file:** `PostalPlanetFilledBars.png`
* **Visual cue:** 條紋呈現黑色，符合郵件印刷的郵政規範。

### 預期輸出

執行程式後會產生如下圖所示的影像（此處不顯示實際圖片，開啟檔案時您會看到清晰的 6 位數條碼）。

```text
[PostalPlanetFilledBars.png]  // image shows solid black bars
```

## 步驟 3：建立空心條碼（Planet 未填滿的條紋）

若要 **create empty barcode**，以 `filled: false` 呼叫相同方法。`FilledBars` 屬性指示 Aspose.BarCode 只繪製條紋輪廓，內部保持透明。

* **Resulting file:** `PostalPlanetEmptyBars.png`
* **Use case:** 當您希望背景顯示標誌或顏色，同時保持條碼可讀性時，空心條碼相當有用。

### 預期輸出

產生的 PNG 僅包含條紋輪廓：

```text
[PostalPlanetEmptyBars.png]  // image shows hollow bar shapes
```

## 步驟 4：產生實心 RM4SCC 條碼

RM4SCC 為荷蘭郵政條碼標準。範例使用相同的 X‑dimension（4 像素），以保持與 Planet 條碼的視覺一致性。

* **Resulting file:** `PostalRM4SCCFilledBars.png`
* **Why RM4SCC?** 它以緊湊格式編碼數字資料，受到多數歐洲郵政服務的接受。

### 預期輸出

```text
[PostalRM4SCCFilledBars.png]  // solid bars representing "123456"
```

## 實用技巧與常見陷阱

| Tip | Explanation |
|-----|-------------|
| **Consistent X‑dimension** | 使用相同的 `XDimension.Pixels` 值於不同的符號集，可確保列印標籤上外觀一致。 |
| **Do not reuse the same generator instance** | 在已存在的產生器上變更 `FilledBars` 可能導致意外結果；對每個不同的條碼請重新實例化 `BarcodeGenerator`。 |
| **Verify image format** | PNG 為無損格式，最適合條碼；JPEG 壓縮可能使細條模糊，導致掃描失敗。 |
| **License handling** | 若未使用授權執行程式，產生的影像會帶有浮水印。請在 `Main` 早期加入授權程式碼，例如 `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`。 |
| **Thread safety** | `BarcodeGenerator` **非**執行緒安全。若平行產生條碼，請為每個執行緒建立獨立實例。 |

## 可能遇到的邊緣案例

* **Data length limits** – Planet 條碼最多接受 6 個數字字元。提供超過此長度會拋出 `ArgumentException`。請在呼叫產生器前驗證輸入長度。
* **Non‑numeric data** – RM4SCC 亦僅接受數字輸入。若需字母數字混合，必須使用其他符號集（例如 Code128）。設定 `FilledBars` 的相同模式適用於任何支援此屬性的條碼類型。
* **High‑resolution printing** – 若需要比螢幕顯示更大的條碼，請提升 `XDimension.Pixels`（例如 8 或 10），並可於 `generator.Parameters.Image` 中設定 `Resolution`。此作法可在 300 dpi 列印時保持條紋清晰。

## 完整原始檔回顧

以下為完整的原始檔，方便快速複製貼上。內含所有步驟、註解，以及可選的授權程式碼片段（已註解掉）。

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Optional: apply your Aspose.BarCode license here
            // var license = new License();
            // license.SetLicense("Aspose.BarCode.lic");

            string outputFolder = @"C:\Barcodes";
            System.IO.Directory.CreateDirectory(outputFolder);

            // Filled Planet barcode
            GeneratePlanetBarcode(outputFolder, "123456", filled: true);

            // Empty Planet barcode (create empty barcode)
            GeneratePlanetBarcode(outputFolder, "123456", filled: false);

            // Filled RM4SCC barcode
            GenerateRM4SCCBarcode(outputFolder, "123456");

            Console.WriteLine("All barcodes saved to " + outputFolder);
        }

        static void GeneratePlanetBarcode(string folder, string data, bool filled)
        {
            var generator = new BarcodeGenerator(EncodeTypes.Planet, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;
            generator.Parameters.Barcode.FilledBars = filled;

            string fileName = filled ? "PostalPlanetFilledBars.png"
                                     : "PostalPlanetEmptyBars.png";

            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }

        static void GenerateRM4SCCBarcode(string folder, string data)
        {
            var generator = new BarcodeGenerator(EncodeTypes.RM4SCC, data);
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            string fileName = "PostalRM4SCCFilledBars.png";
            generator.Save(System.IO.Path.Combine(folder, fileName),
                           BarCodeImageFormat.Png);
        }
    }
}
```

## 結論

您現在已了解如何在 C# 中使用 Aspose.BarCode **how to generate barcode** 影像，並可透過切換 `FilledBars` 屬性 **create empty barcode** 變體。本教學涵蓋：

* 建立主控台專案並安裝 Aspose.BarCode 套件
* 產生實心 Planet 與 RM4SCC 條碼
* 產生僅有輪廓的空心 Planet 條碼
* 調整條寬以提升可讀性並處理常見陷阱

接下來，您可以探索其他符號集（Code128、QR、DataMatrix），並嘗試不同的顏色、尺寸與影像格式。將條碼產生整合至 Web API 或 Windows 服務，只需將主控台的 `Main` 方法換成您應用程式的入口點，即可沿用相同模式。

祝程式開發順利，讓您的應用程式開始掃描！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並在此基礎上延伸技術。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在專案中探索其他實作方式。

- [How to create postal barcode image in C# using Aspose.BarCode](/barcode/english/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/)
- [How to generate postal barcode in C# with custom dimensions](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-custom-dimensions/)
- [How to generate barcode image with Aspose.BarCode in C#](/barcode/english/python-java/general/how-to-generate-barcode-image-with-aspose-barcode-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}