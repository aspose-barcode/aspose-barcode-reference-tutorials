---
category: general
date: 2026-09-07
description: 學習如何在 C# 中建立條碼圖像，並調整其高度、寬度及格式，以快速產生條碼 PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- how to set barcode
- how to adjust barcode
- generate barcode png
- change barcode height
language: zh-hant
lastmod: 2026-09-07
og_description: 在 C# 中建立條碼圖像，並學習如何設定條碼尺寸、調整條碼高度，以及為任何應用程式產生條碼 PNG 檔案。
og_image_alt: C# generated barcode image saved as PNG with custom height
og_title: 在 C# 中建立條碼圖像 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  headline: How to create barcode image in C# with adjustable height
  type: TechArticle
- description: Learn how to create barcode image in C# and adjust its height, width,
    and format to generate barcode PNG files quickly.
  name: How to create barcode image in C# with adjustable height
  steps:
  - name: 3.1 Adjust the narrow bar width (X‑dimension)
    text: The X‑dimension controls the thickness of the thinnest bar. A value of **2
      pixels** yields a finer appearance, useful when you need a compact label.
  - name: 3.2 Change barcode height for visual balance
    text: Bar height determines how tall the barcode appears. Below we show two common
      heights—30 pixels for a small label and 60 pixels for a larger visual. This
      demonstrates **how to adjust barcode** height programmatically.
  - name: 4.1 Save the first image (30 px height)
    text: '```csharp // Save a 30‑pixel‑high barcode as PNG generator.Save("DatabarBarHeight30Pixels.png",
      BarCodeImageFormat.Png); ```'
  - name: 4.2 Increase the height and save a second image
    text: '```csharp // Increase height to 60 pixels for a larger visual generator.Parameters.Barcode.BarHeight.Pixels
      = 60;'
  type: HowTo
tags:
- barcode
- C#
- image generation
title: 如何在 C# 中建立可調整高度的條碼圖像
url: /zh-hant/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立可調整高度的條碼圖像

如果您需要在 C# 中為銷售點系統或庫存追蹤器建立條碼圖像，本指南將展示完整的工作流程。您將會看到如何設定條碼參數、變更條碼高度，以及產生符合視覺需求的條碼 PNG 檔案。

產生條碼圖像是整合掃描硬體、列印標籤或建構報表儀表板時的常見任務。完成本教學後，您將擁有可重複使用的程式碼片段，讓您在不離開 IDE 的情況下調整條碼的 X‑dimension、高度與輸出格式。

## 前置條件

* 已安裝 .NET 6.0（或更新版本）— 程式碼可在任何近期的 .NET SDK 上編譯。
* 參考 **Aspose.BarCode** 函式庫（可透過 NuGet `Aspose.BarCode` 取得）。
* 具備 C# 主控台應用程式的基本知識。

這些需求確保範例可在 Windows、Linux 或 macOS 上即時執行。

## 步驟 1：設定專案並匯入函式庫

建立新的主控台專案並加入條碼套件：

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

接著開啟 *Program.cs*，加入必要的 `using` 指令：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;
```

這些匯入讓您能使用 `BarcodeGenerator`、`EncodeTypes` 以及產生 **create barcode image** 檔案所需的影像格式列舉型別。

## 步驟 2：以所需的符號系統初始化產生器

第一行程式碼會建立一個 `BarcodeGenerator`，讓它知道要編碼哪種條碼類型。在此範例中，我們使用 DataBar Omni‑Directional 符號系統，但您可以將 `EncodeTypes.DatabarOmniDirectional` 替換為 Aspose.BarCode 支援的其他類型。

```csharp
// Initialize a generator for a DataBar Omni‑Directional barcode
var generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

字串 `"(01)12345678901231"` 符合 GS1 應用程式識別碼格式，許多零售商都要求如此。初始化產生器是之後每個 **how to set barcode** 操作的基礎。

## 步驟 3：如何設定條碼尺寸 – X‑dimension 與高度

### 3.1 調整窄條寬度 (X‑dimension)

X‑dimension 控制最細條的寬度。設定為 **2 像素** 可產生較細緻的外觀，適合需要緊湊標籤的情況。

```csharp
// Set the narrow bar width to 2 pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

### 3.2 變更條碼高度以取得視覺平衡

條碼高度決定條碼的垂直長度。以下示範兩種常見高度——30 像素用於小標籤，60 像素用於較大的視覺效果。此範例說明了 **how to adjust barcode** 高度的程式化調整。

```csharp
// Height 30 pixels – suitable for compact labels
generator.Parameters.Barcode.BarHeight.Pixels = 30;
```

## 步驟 4：產生不同高度的條碼 PNG 檔案

### 4.1 儲存第一張影像（30 像素高度）

```csharp
// Save a 30‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

### 4.2 提高高度並儲存第二張影像

```csharp
// Increase height to 60 pixels for a larger visual
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save a 60‑pixel‑high barcode as PNG
generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

這兩個 `Save` 呼叫示範了在重複使用同一產生器實例的情況下，產生具有不同尺寸的 **generate barcode PNG** 檔案。影像格式明確設定為 PNG，可保留無損品質——非常適合列印或螢幕顯示。

## 步驟 5：完整、可執行的範例

將所有步驟整合後會得到一個可直接複製到任何 C# 主控台專案的 `Main` 方法：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.Encoding;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create a DataBar Omni‑Directional barcode generator
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set the narrow bar width (X‑dimension) to 2 pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ Create a 30‑pixel‑high barcode and save it as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Change barcode height to 60 pixels and save again
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

執行此程式會在專案的輸出資料夾產生兩個 PNG 檔案：

* `DatabarBarHeight30Pixels.png` – 緊湊的 30 像素條碼。
* `DatabarBarHeight60Pixels.png` – 較大的 60 像素條碼。

兩個檔案皆包含 **create barcode image**，可嵌入 HTML、列印於標籤上，或傳送至行動應用程式進行掃描。

## 常見問題與邊緣案例處理

| 問題 | 答案 |
|----------|--------|
| **如果需要不同的影像格式該怎麼辦？** | 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`、`Bmp` 或 `Gif`。函式庫會自動處理轉換。 |
| **我可以變更前景/背景顏色嗎？** | 可以。於呼叫 `Save` 前，使用 `generator.Parameters.Barcode.ForeColor` 與 `BackColor` 設定 `System.Drawing.Color` 值。 |
| **如何在不產生磁碟檔案的情況下產生條碼？** | 呼叫 `generator.GenerateBarCodeImage()` 取得 `System.Drawing.Image` 物件，然後直接串流至回應或資料庫。 |
| **如果資料字串超過符號系統的限制呢？** | 產生器會拋出 `ArgumentException`。請驗證輸入長度或依照符號系統規範截斷。 |
| **有沒有辦法批次處理多個條碼？** | 將步驟包在 `foreach` 迴圈中，為每個項目更新 `generator.CodeText` 與 `BarHeight`，然後以唯一檔名呼叫 `Save`。 |

處理上述情境可使本教學的 **how to adjust barcode** 邏輯在實務專案中更具韌性。

## 專業提示：可靠的條碼產生

* **快取產生器**：當您大量產生相同類型的條碼時，重複使用該物件可減少分配開銷。
* **設定 `Resolution`**（`generator.Parameters.ImageResolution.Dpi`），若需高解析度 PNG 以供列印。
* **驗證 GS1 資料** 在指派給 `CodeText` 前，以避免編碼錯誤導致掃描失敗。
* **在實體掃描器上測試** 變更高度或 X‑dimension 後——某些舊版設備對最小尺寸有要求。

## 結論

您現在已了解如何在 C# 中 **create barcode image**、**how to set barcode** 尺寸、**how to adjust barcode** 高度，以及為任何視覺需求 **generate barcode PNG** 檔案。只要微調 `XDimension` 與 `BarHeight`，即可在不更改底層資料的情況下產生緊湊或大型條碼。

接下來，您可以探索相關主題，例如根據使用者輸入動態 **change barcode height**、使用 Aspose.PDF 將條碼嵌入 PDF 報表，或改用 `EncodeTypes.QR` 產生 QR‑code。嘗試不同的符號系統與輸出格式，全面掌握 C# 條碼建立。

## 接下來該學什麼？

以下教學涵蓋與本指南技術密切相關的主題。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [在 C# 中建立 GS1 條碼圖像 – 快速產生條碼 C# 教學](/barcode/english/net/gs1-barcode-encoding/create-gs1-barcode-images-in-c-how-to-generate-barcode-c-qui/)
- [使用 Aspose.BarCode for .NET 產生與調整一維 Databar 條碼高度的方法](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [在 C# 中產生條碼圖像 – MicroPdf417 指南](/barcode/english/net/compact-pdf417-encoding/how-to-generate-barcode-image-in-c-micropdf417-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}