---
category: general
date: 2026-10-02
description: 使用 C# 及 Aspose.BarCode 建立郵政條碼圖像。學習產生 Planet 與 RM4SCC 條碼、客製化實心條，並將其儲存為
  PNG 檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode image
- generate planet barcode
- Aspose.BarCode C#
- postal barcode PNG
- barcode XDimension setting
language: zh-hant
lastmod: 2026-10-02
og_description: 使用 C# 與 Aspose.BarCode 建立郵政條碼圖像。本教學示範如何產生 Planet 與 RM4SCC 條碼、調整條紋填充，並匯出
  PNG 檔案。
og_image_alt: Postal barcode image generated with Aspose.BarCode (filled bars)
og_title: 使用 C# 建立郵政條碼圖像 – 步驟指南
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  headline: How to create postal barcode image in C# using Aspose.BarCode
  type: TechArticle
- description: Create postal barcode image in C# with Aspose.BarCode. Learn to generate
    Planet and RM4SCC barcodes, customize filled bars, and save PNG files.
  name: How to create postal barcode image in C# using Aspose.BarCode
  steps:
  - name: Why each line matters
    text: '* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – The `EncodeTypes.Planet`
      enum tells Aspose.BarCode to use the *Planet* symbology, which is a standard
      postal barcode in many countries. This is the core of how you **generate planet
      barcode** images. * **`XDimension.Pixels = 4`** – The wid'
  - name: Expected output
    text: 'After running the program, the `YOUR_DIRECTORY` folder contains three PNG
      files:'
  - name: Change image format
    text: If you need a different format (e.g., JPEG for web delivery), replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. Keep in mind that JPEG introduces compression
      artifacts, which can affect scanner performance.
  - name: Adjust image size without scaling
    text: Instead of changing `XDimension`, you can control the overall image dimensions
      via `Parameters.Image.Height` and `Parameters.Image.Width`. This is useful when
      you have a fixed label size.
  - name: Use a different barcode symbology
    text: Aspose.BarCode supports dozens of postal symbologies (e.g., **USPS Intelligent
      Mail**, **Japan Post**). To **generate planet barcode** alternatives, replace
      `EncodeTypes.Planet` with the desired enum value.
  - name: Handling invalid data
    text: Postal barcodes have strict data length rules. If you pass a string that
      does not meet the specification, Aspose.BarCode throws an `ArgumentException`.
      Wrap the generator creation in a `try/catch` block to provide a friendly error
      message.
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: 如何在 C# 中使用 Aspose.BarCode 建立郵政條碼圖像
url: /zh-hant/python-java/general/how-to-create-postal-barcode-image-in-c-using-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 建立郵政條碼圖像

如果您需要在 C# 中**建立郵政條碼圖像**，Aspose.BarCode 提供了簡潔的 API 來處理繁重的工作。無論您是構建郵件標籤系統或地址驗證服務，本指南將精確說明如何產生 Planet 與 RM4SCC 條碼、在實心與空心條之間切換，並將結果匯出為 PNG 檔案。

您將學會如何設定條碼尺寸、控制條形填充行為，並將圖像儲存至磁碟——全部在一個可執行的程式中完成。除了 Aspose.BarCode for .NET 函式庫外，無需任何外部工具。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼亦可於 .NET Framework 4.7+ 執行）
* Visual Studio 2022 或任何相容 C# 的 IDE
* 授權或評估版的 **Aspose.BarCode for .NET**（可透過 NuGet 取得）

```bash
dotnet add package Aspose.BarCode
```

## 解決方案概覽

本教學分為三個邏輯步驟：

1. **建立帶有預設（實心）條的 Planet 條碼** – 這展示了郵政服務的典型外觀。
2. **建立帶有空心條的 Planet 條碼** – 當印刷流程需要未填充的條時很有用。
3. **建立帶有實心條的 RM4SCC 條碼** – 這是許多國家常用的另一種郵政格式。

每個步驟皆遵循相同模式：實例化 `BarcodeGenerator`、設定 `XDimension`（單條的像素寬度）、可選地調整 `FilledBars`，最後呼叫 `Save` 以寫入 PNG 檔案。

---

## 使用 Aspose.BarCode 建立郵政條碼圖像

以下為完整、獨立的程式。將其儲存為 `Program.cs`，然後在命令列或 IDE 中執行。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Define the output folder – change this to a writable location on your machine
            string outputDir = @"YOUR_DIRECTORY";

            // -------------------------------------------------
            // Step 1: Generate a Planet barcode with filled bars
            // -------------------------------------------------
            var planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                // XDimension controls the width of a single bar in pixels.
                // A value of 4 gives a good balance between readability and file size.
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string planetFilledPath = System.IO.Path.Combine(outputDir, "PostalPlanetFilledBars.png");
            planetFilled.Save(planetFilledPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled Planet barcode saved to {planetFilledPath}");

            // -------------------------------------------------
            // Step 2: Generate a Planet barcode with empty bars
            // -------------------------------------------------
            var planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456")
            {
                Parameters = {
                    Barcode = {
                        XDimension = { Pixels = 4 },
                        // Setting FilledBars to false renders the bars as empty outlines.
                        FilledBars = false
                    }
                }
            };
            string planetEmptyPath = System.IO.Path.Combine(outputDir, "PostalPlanetEmptyBars.png");
            planetEmpty.Save(planetEmptyPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Empty Planet barcode saved to {planetEmptyPath}");

            // -------------------------------------------------
            // Step 3: Generate an RM4SCC barcode with filled bars
            // -------------------------------------------------
            var rm4sccFilled = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
            {
                Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
            };
            string rm4sccPath = System.IO.Path.Combine(outputDir, "PostalRM4SCCFilledBars.png");
            rm4sccFilled.Save(rm4sccPath, BarCodeImageFormat.Png);
            Console.WriteLine($"Filled RM4SCC barcode saved to {rm4sccPath}");

            // End of demo
            Console.WriteLine("All barcode images have been generated successfully.");
        }
    }
}
```

### 為何每一行都很重要

* **`new BarcodeGenerator(EncodeTypes.Planet, "123456")`** – `EncodeTypes.Planet` 列舉告訴 Aspose.BarCode 使用 *Planet* 符號，這是許多國家標準的郵政條碼。這是您**產生 planet 條碼**圖像的核心。
* **`XDimension.Pixels = 4`** – 單條的寬度會影響掃描可靠性與視覺尺寸。4 px 的數值對大多數標籤印表機而言表現良好；如需更高解析度可將其調高。
* **`FilledBars = false`** – 預設情況下條是實心的。將其設為 `false` 會產生某些郵寄規範所需的「空心條」樣式。
* **`Save(..., BarCodeImageFormat.Png)`** – PNG 保持無損品質，適合必須被掃描器讀取的條碼圖像。

### 預期輸出

執行程式後，`YOUR_DIRECTORY` 資料夾會包含三個 PNG 檔案：

| 檔案名稱 | 視覺說明 |
|----------|----------|
| `PostalPlanetFilledBars.png` | 實心黑條的 Planet 條碼 |
| `PostalPlanetEmptyBars.png` | 條線以輪廓呈現（空心）的 Planet 條碼 |
| `PostalRM4SCCFilledBars.png` | 實心條的 RM4SCC 條碼 |

您可以在圖像檢視器中開啟任一圖檔，或直接嵌入 PDF/HTML 標籤中。

## 進一步自訂條碼（可選）

### 更改圖像格式

如果您需要其他格式（例如用於網路傳輸的 JPEG），請將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。請注意 JPEG 會產生壓縮雜訊，可能影響掃描器效能。

### 在不縮放的情況下調整圖像尺寸

您可以不改變 `XDimension`，改透過 `Parameters.Image.Height` 與 `Parameters.Image.Width` 來控制整體圖像尺寸。當標籤尺寸固定時此方式很有用。

```csharp
planetFilled.Parameters.Image.Height = 150; // pixels
planetFilled.Parameters.Image.Width = 300;  // pixels
```

### 使用不同的條碼符號

Aspose.BarCode 支援數十種郵政符號（例如 **USPS Intelligent Mail**、**Japan Post**）。若要**產生 planet 條碼**的其他選項，請將 `EncodeTypes.Planet` 替換為所需的列舉值。

```csharp
var uspsBarcode = new BarcodeGenerator(EncodeTypes.USPSIntelligentMail, "123456789012");
```

### 處理無效資料

郵政條碼對資料長度有嚴格規範。若傳入不符合規範的字串，Aspose.BarCode 會拋出 `ArgumentException`。請將產生器的建立包在 `try/catch` 區塊中，以提供友善的錯誤訊息。

```csharp
try
{
    var invalid = new BarcodeGenerator(EncodeTypes.Planet, "ABC");
}
catch (ArgumentException ex)
{
    Console.Error.WriteLine($"Invalid barcode data: {ex.Message}");
}
```

## 常見陷阱與專業提示

| 陷阱 | 發生原因 | 專業提示 |
|------|----------|----------|
| **使用過小的 XDimension** | 條變得比掃描器的最小解析度還細，導致讀取錯誤。 | 從 `Pixels = 4` 開始，並在目標印表機上測試；如有需要請調高。 |
| **儲存至唯讀資料夾** | `Save` 會拋出 `UnauthorizedAccessException`。 | 確保 `outputDir` 指向可寫入的位置，或使用 `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`。 |
| **忽略釋放產生器** | 大型圖像可能佔用未受管理的資源。 | 將產生器包在 `using` 陳述式中，或在 `Save` 後呼叫 `Dispose()`。 |
| **在同一圖像中混合條碼格式** | 某些印表機要求每個標籤僅使用單一符號。 | 分別產生每個條碼，若需要可使用圖形函式庫將它們合成。 |

## 驗證產生的條碼

為了確認條碼是否有效，您可以使用免費的 **Aspose.BarCode Demo** 網站或任何標準條碼掃描應用程式。載入 PNG 檔案並掃描；解碼後的值應為 `123456`，適用於 Planet 與 RM4SCC 兩個範例。

## 結論

在本教學中，您學會了如何在 C# 使用 Aspose.BarCode **建立郵政條碼圖像**檔案。您了解了如何 **產生 planet 條碼** 圖像（包括實心與空心條），以及如何產生 RM4SCC 條碼，並學會自訂尺寸、格式與錯誤處理。透過完整且可執行的程式碼，您現在可以將郵政條碼產生整合至任何 .NET 應用程式中。

**下一步**

* 探索其他郵政符號，例如 `EncodeTypes.USPSIntelligentMail`（次要關鍵字：postal barcode PNG）。

## 接下來該學什麼？

以下教學涵蓋與本指南技術緊密相關的主題。每個資源皆提供完整可運作的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索替代實作方式。

- [在 C# 中建立郵政條碼圖像 – 完整逐步指南](/barcode/english/python-java/general/create-postal-barcode-image-in-c-full-step-by-step-guide/)
- [在 C# 中產生郵政條碼 – 完整指南（含 Planet 條碼）](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)
- [如何在 C# 中使用 Aspose.BarCode 產生郵政條碼](/barcode/english/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}