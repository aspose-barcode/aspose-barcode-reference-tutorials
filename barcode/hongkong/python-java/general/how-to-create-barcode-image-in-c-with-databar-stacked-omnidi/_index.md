---
category: general
date: 2026-11-17
description: 使用 Barcode Generator 函式庫於 C# 建立條碼圖像。請依照本指南逐步學習如何產生 DataBar 堆疊全方向碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- how to generate databar
language: zh-hant
lastmod: 2026-11-17
og_description: 使用 C# 建立條碼圖像，提供簡潔範例。學習如何使用 Barcode Generator 函式庫產生 DataBar 堆疊全方向條碼。
og_image_alt: Screenshot showing a generated barcode image created with C# code
og_title: 在 C# 中建立條碼圖像 – DataBar 條碼完整指南
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Create barcode image in C# using the Barcode Generator library. Follow
    this guide to learn how to generate DataBar stacked omnidirectional codes step‑by‑step.
  headline: How to create barcode image in C# with DataBar stacked omnidirectional
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 DataBar 堆疊全向式建立條碼圖像
url: /zh-hant/python-java/general/how-to-create-barcode-image-in-c-with-databar-stacked-omnidi/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 DataBar 堆疊全向條碼建立條碼圖像

如果您需要在 .NET 應用程式中 **建立條碼圖像**，本教學提供完整、可直接執行的解決方案。您將會看到如何使用 **Barcode Generator C#** API 產生堆疊全向 DataBar，這正是 *how to generate databar* 查詢所涵蓋的格式。

本指南會一步步說明所有必要步驟——從安裝函式庫到微調長寬比——讓您可以複製程式碼、執行它，並立即取得 PNG 檔案。無需查閱外部文件。

## 前置條件

在開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本（範例同樣適用於 .NET Framework 4.7+）
* 如 Visual Studio 2022 或 VS Code 等開發環境
* **Aspose.BarCode for .NET** NuGet 套件（提供 `BarcodeGenerator` 的函式庫）

您可以使用以下指令加入套件：

```bash
dotnet add package Aspose.BarCode
```

> **小技巧：** 使用 `--version` 參數鎖定套件至最新穩定版，例如 `dotnet add package Aspose.BarCode --version 23.9`。

## 步驟 1：建立專案並匯入命名空間

建立一個新的 console 專案，並參考所需的命名空間。此步驟為接下來的 **barcode generator c#** 程式碼做好環境準備。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // All barcode generation logic lives here
```

`Aspose.BarCode.Generation` 命名空間內的 `BarcodeGenerator` 類別是 **create barcode image** 工作流程的核心。

## 步驟 2：為堆疊全向 DataBar 初始化 BarcodeGenerator

產生器需要兩項資訊：條碼類型與要編碼的資料。`EncodeTypes.DatabarStackedOmniDirectional` 列舉值會選取 *how to generate databar* 情境所需的確切 DataBar 變體。

```csharp
            // Step 2: Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231"); // Example GTIN-14 payload
```

*為什麼重要：* 正確選擇 `EncodeTypes` 值可確保產生的圖像符合零售掃描的產業規範。

## 步驟 3：以像素定義模組大小（X‑dimension）

條碼的視覺密度由 X‑dimension 控制。將其設定為合理的像素值，可保證圖像在螢幕與列印時皆可辨識。

```csharp
            // Step 3: Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

若需為低解析度列印製作較大的條碼，請相應提升像素值。

## 步驟 4：調整 DataBar 長寬比以使列更高

堆疊全向 DataBar 由兩列組成。修改 `AspectRatio` 可控制每列的高度，當預設尺寸顯得擁擠時此設定相當有用。

```csharp
            // Step 4: Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

`15` 的長寬比是零售標籤的常見選擇；您可以在 `10` 到 `20` 之間嘗試，以符合特定版面需求。

## 步驟 5：將產生的條碼儲存為 PNG 圖像

最後，將圖像寫入磁碟。PNG 為無損格式，適合後續處理或嵌入 PDF。

```csharp
            // Step 5: Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

執行程式後，會在專案的輸出目錄產生名為 **DatabarAspectRatio15.png** 的檔案。開啟該檔案即可看到乾淨、高對比度、可供掃描的條碼。

### 預期輸出

儲存的圖像與下圖示意相似（此處省略實際圖示）。

*範例圖像的替代文字：* **create barcode image** – 顯示堆疊全向 DataBar、長寬比為 15 的 PNG 檔案。

## 常見變化與邊緣案例

| 情境 | 調整方式 |
|-----------|------------|
| **不同的資料長度** | 將 GTIN 字串換成任何有效的 DataBar 內容（例如 `(01)01234567890123`）。 |
| **大型列印的較高解析度** | 將 `XDimension.Pixels` 提升至 4 或 5，並可選擇在 `Parameters.Image` 中設定 `Resolution`。 |
| **其他 DataBar 格式** | 使用 `EncodeTypes.DatabarStacked` 取得不具全向功能的兩列堆疊變體。 |
| **儲存為 JPEG** | 將 `BarCodeImageFormat.Png` 改為 `BarCodeImageFormat.Jpeg`，並可選擇設定 `Quality`。 |

這些變化說明了同一個 *how to generate databar* 問題的多種解法，展示了同一產生器可重新配置以支援多種 DataBar 系列。

## 完整程式碼回顧

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for a stacked omnidirectional DataBar
            BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // Define the module size (X‑dimension) in pixels
            barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

            // Adjust the DataBar aspect ratio to make rows taller
            barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;

            // Save the generated barcode as a PNG image
            string outputPath = "DatabarAspectRatio15.png";
            barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to {outputPath}");
        }
    }
}
```

將程式碼貼入 `Program.cs`、還原 NuGet 套件，然後執行 `dotnet run`。主控台會顯示圖像位置，您即可開啟 PNG 以驗證 **create barcode image** 的結果。

## 結論

現在您已掌握如何在 C# 中使用 Barcode Generator 函式庫 **create barcode image**，以及如何以精確的尺寸與長寬比 **generate DataBar**。完整範例示範了所有必要設定——從初始化 `BarcodeGenerator` 到匯出 PNG 檔案——讓您能在任何 .NET 應用程式中整合條碼產生功能，無需額外研究。

### 接下來可以做什麼？

* 探索 `EncodeTypes` 支援的其他條碼符號（例如 QR、Code128）——這是 **barcode generator c#** 工作流程的自然延伸。
* 結合產生的圖像與 Aspose.PDF 或 Aspose.Cells，製作 PDF 或 Excel 報表。
* 調整顏色、加入邊距，或將條碼嵌入 Web API，以實現即時產生。

歡迎自行實驗各項參數，讓此程式碼成為您未來所有條碼相關專案的可靠基礎。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並探索在實際專案中的其他實作方式。

- [How to use a barcode generator C# to create DataBar barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-barcodes/)
- [How to use a barcode generator C# to create DataBar Omni‑directional barcodes](/barcode/english/python-java/general/how-to-use-a-barcode-generator-c-to-create-databar-omni-dire/)
- [How to create databar stacked barcode in C# – step‑by‑step guide](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-step-by-step-guid/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}