---
category: general
date: 2026-09-19
description: 條碼產生器範例，示範如何變更高度、建立 DataBar Omni‑Directional，並調整條碼尺寸以輸出 C# 圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: zh-hant
lastmod: 2026-09-19
og_description: 條碼產生器範例，教您如何變更高度、建立 DataBar Omni‑Directional，並調整 C# PNG 圖像的條碼尺寸
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: C# 條碼產生器範例 – 逐步指南
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中建立條碼產生器範例
url: /zh-hant/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 條碼產生器範例 – 完整程式教學

如果你需要一個 **條碼產生器範例** 用於 .NET 專案，本指南將一步步說明如何使用 C# 建立、設定並儲存 DataBar Omni‑Directional 條碼。你將學會如何調整高度、改變條碼尺寸，以及輸出高品質 PNG 圖片——全部在一個可執行的主控台應用程式中完成。

以下步驟涵蓋從安裝必要 SDK 到微調 X‑dimension 與條碼高度的全部內容。完成教學後，你將擁有一個可直接使用的條碼產生器，能整合至發票、庫存或任何掃描工作流程。

## 前置條件

開始之前，請確保你已具備：

* .NET 6.0 SDK 或更新版本  
* Visual Studio 2022（或任何支援 .NET 的 IDE）  
* 有效的 **Aspose.BarCode for .NET** 授權（免費試用版可用於測試）  

如果你改用其他函式庫，調整尺寸與儲存影像的概念仍然相同，只需相應替換 API 呼叫即可。

## 第一步：建立專案並加入 Aspose.BarCode 套件

建立一個新的主控台專案，並參考條碼函式庫。

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

`dotnet add package` 指令會下載最新穩定版的 Aspose.BarCode，該版本完整支援 DataBar Omni‑Directional 符號。

## 第二步：撰寫完整的條碼產生器範例

開啟 **Program.cs**，將內容全部取代為以下程式碼。此區塊即為完整的 **條碼產生器範例**，沒有遺漏任何部份。

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
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### 為何每一行都很重要

* **建立條碼產生器** – `BarcodeGenerator` 建構子將編碼類型（`EncodeTypes.DatabarOmniDirectional`）與欲嵌入的資料關聯起來，這是 **如何建立 databar** 步驟的核心。  
* **調整條碼尺寸** – `XDimension.Pixels` 屬性定義最窄條的寬度。變更此值會影響整體大小與掃描可靠度。  
* **如何變更高度** – `BarHeight.Pixels` 屬性控制垂直尺寸。提升高度可改善手持掃描器的可讀性，降低高度則可節省小標籤的空間。  
* **可選調整** – 設定前景/背景顏色或錯誤更正等級屬於可選項目，但可示範如何延伸 **調整條碼尺寸** 的概念。  
* **C# 建立條碼影像** – `Save` 方法將條碼寫入磁碟。使用 `BarCodeImageFormat.Png` 可確保無損壓縮，適合大多數應用。

## 第三步：建置並執行範例

編譯並執行程式：

```bash
dotnet run
```

你應該會在主控台看到以下輸出：

```
Barcode saved to DatabarOmniDirectional.png
```

專案資料夾中會產生一個名為 **DatabarOmniDirectional.png** 的檔案。開啟該影像即可看到清晰的 DataBar Omni‑Directional 條碼，已可供掃描使用。

## 事後變更高度的方法

若需產生不同高度的條碼，可將高度設定封裝於方法中：

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

在 `Save` 之前呼叫 `SetBarHeight(generator, 45);`。此做法讓你可以根據使用者輸入或設定檔 **動態變更高度**。

## 使用不同資料建立 DataBar Omni‑Directional 條碼

DataBar Omni‑Directional 符號支援 GTIN‑14、GTIN‑13 以及其他數字識別碼。若要編碼不同的值，只需在建構子中更換字串：

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

請確保資料為數字且格式正確，否則產生器會拋出 `BarcodeException`。

## 為不同列印情境調整條碼尺寸

不同的印表機與標籤尺寸需要不同的 X‑dimension 與高度。以下表格提供快速參考：

| 情境                         | X‑Dimension（像素） | 條碼高度（像素） |
|------------------------------|----------------------|------------------|
| 小標籤 (25 mm × 15 mm)       | 1                    | 20               |
| 中標籤 (50 mm × 30 mm)       | 2                    | 30               |
| 大標籤 (100 mm × 50 mm)      | 3                    | 45               |

依需求設定 `generator.Parameters.Barcode.XDimension.Pixels` 與 `BarHeight.Pixels` 即可。

## 專業提示：驗證產生的條碼

在出貨前，你可以以程式方式驗證條碼的可讀性：

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

此程式碼示範了一個快速的 **調整條碼尺寸** 檢查，確保條碼符合掃描要求。

## 常見陷阱與避免方式

| 陷阱                              | 為何會發生                                 | 解決方式                                                            |
|-----------------------------------|--------------------------------------------|---------------------------------------------------------------------|
| 為 DataBar 使用非數字資料          | DataBar 只接受數字 GTIN 格式                | 確認字串符合 `(01)XXXXXXXXXXXXX` 之模式。                         |
| 設定 X‑dimension 為 0 或負值       | 函式庫會拋出 `ArgumentOutOfRangeException`   | 最低使用 1 像素；先在目標印表機上測試。                             |
| 儲存至唯讀資料夾                  | `UnauthorizedAccessException` 於 `Save` 時 | 選擇可寫入的目錄，或以適當權限執行應用程式。                       |
| 忘記釋放 `BarCodeReader`          | 長時間服務會造成記憶體泄漏                | 使用 `using` 區塊或手動呼叫 `Dispose()`。                           |

提前處理這些問題可節省除錯時間，提升正式環境的穩定性。

## 完整程式碼回顧

以下即為完整、可直接複製的程式，實作了從頭到尾的 **條碼產生器範例**。

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

執行此程式會產生如下圖示的 PNG 檔（示意圖）：

![在 C# 中產生的 DataBar Omni‑Directional 條碼](https://example.com/og-image.png "在 C# 中產生的 DataBar Omni‑Directional 條碼")

*圖片替代文字*：**在 C# 中產生的 DataBar Omni‑Directional 條碼**（符合 `og_image_alt`）。

## 結論

現在你已擁有一個 **條碼產生器範例**，示範了如何變更高度、如何建立 DataBar Omni‑Directional 符號，以及如何 **調整條碼尺寸** 以獲得最佳掃描效果。完整的 C# 程式碼會儲存 PNG 圖片、驗證其可讀性，且可擴充為批次產生或整合至 Web 服務。

接下來，你可以探索以下相關主題，如 **使用 Aspose.BarCode 建立 QR Code**、**批次處理多筆條碼值**，或 **將條碼嵌入 PDF 文件**。這些主題皆建立在本指南所涵蓋的基礎上。

祝開發順利，願你的條碼永遠可被順利掃描！


## 接下來該學什麼？

以下教學與本指南緊密相關，進一步深化本章所示技巧。每篇資源皆提供完整可執行的程式範例與逐步說明，協助你掌握更多 API 功能，並在專案中探索其他實作方式。

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}