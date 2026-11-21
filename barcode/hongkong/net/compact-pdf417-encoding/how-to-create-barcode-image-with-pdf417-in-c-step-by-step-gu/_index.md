---
category: general
date: 2026-11-20
description: 使用 Aspose.BarCode 在 C# 中建立條碼圖像。了解如何使用自訂版面產生 PDF417 條碼並將其儲存為 PNG。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- generate pdf417 barcode
- how to generate pdf417
language: zh-hant
lastmod: 2026-11-20
og_description: 使用 Aspose.BarCode 在 C# 中建立條碼圖像。本指南說明如何產生 PDF417 條碼、自訂版面配置，並匯出為 PNG。
og_image_alt: Screenshot of generated barcode image created with PDF417 using C#
og_title: 使用 C# 產生 PDF417 條碼圖像 – 完整教學
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  headline: How to create barcode image with PDF417 in C# – step‑by‑step guide
  type: TechArticle
- description: Create barcode image in C# using Aspose.BarCode. Learn how to generate
    PDF417 barcode with a custom layout and save it as PNG.
  name: How to create barcode image with PDF417 in C# – step‑by‑step guide
  steps:
  - name: Why this code works
    text: '* **`BarcodeGenerator`** is the entry point for all barcode types. By passing
      `EncodeTypes.Pdf417` you tell the library to produce a PDF417 symbol. * **Columns
      and rows** are the primary levers for layout. Fewer columns produce a taller
      barcode; more columns make it wider. Adjust these values to fit'
  - name: Adjusting data length
    text: 'PDF417 can encode up to 1,850 characters. If you need to encode longer
      strings, consider splitting the data across multiple barcodes or using the **compact
      mode**:'
  - name: Controlling image size
    text: 'The default image size is calculated from the module size (the smallest
      square in the barcode). You can explicitly set the DPI or scale the image after
      generation:'
  - name: Handling special characters
    text: 'PDF417 supports the full ASCII set. If your data contains Unicode characters,
      ensure you encode the string as UTF‑8:'
  type: HowTo
tags:
- barcode
- PDF417
- C#
title: 如何在 C# 中使用 PDF417 建立條碼圖像 – 步驟教學
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-barcode-image-with-pdf417-in-c-step-by-step-gu/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 PDF417 建立條碼影像 – 步驟說明指南

如果您需要在 .NET 應用程式中 **建立條碼影像**，本指南將一步步示範 **如何產生 PDF417 條碼**，並以自訂版面配置儲存為 PNG 檔案。您將看到完整可執行的程式碼、了解每個設定的意義，並學會常見的陷阱，確保條碼在正式環境中可靠運作。

在本教學中您將會：

* 初始化 Aspose.BarCode 的 PDF417 產生器。
* 設定欄與列的數量以控制條碼形狀。
* 匯出高品質的 PNG 影像。
* 探索錯誤更正與資料長度的可選設定。

唯一的前置條件是近期的 .NET SDK（.NET 6 或更新）以及 **Aspose.BarCode for .NET** 的授權或免費試用版。

---

## 前置條件與設定

開始之前，請確保您具備以下項目：

| 前置條件 | 為何重要 |
|----------|----------|
| .NET 6 SDK 或更新版本 | 為 C# 主控台應用程式提供執行環境。 |
| Visual Studio 2022（或 VS Code） | 提供 Aspose API 的 IntelliSense 及完整 IDE 體驗。 |
| Aspose.BarCode for .NET NuGet 套件 | 提供 `BarcodeGenerator`、`EncodeTypes` 與影像匯出輔助功能。 |
| 輸出資料夾的寫入權限 | 產生器會將 PNG 檔寫入磁碟。 |

您可以使用以下指令加入 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

---

## 第一步：建立新的主控台專案

首先，建立一個簡易的主控台應用程式，以容納條碼產生的程式碼。

```csharp
using System;
using Aspose.BarCode.Generation;

namespace Pdf417Demo
{
    class Program
    {
        static void Main(string[] args)
        {
            // The full barcode generation flow is encapsulated in GeneratePdf417().
            GeneratePdf417();
            Console.WriteLine("Barcode image created successfully.");
        }

        // -----------------------------------------------------------------
        // Generates a PDF417 barcode with a custom layout and saves it as PNG.
        // -----------------------------------------------------------------
        static void GeneratePdf417()
        {
            // -------------------------------------------------------------
            // Step 2: Initialize the barcode generator for PDF417 with text.
            // -------------------------------------------------------------
            var generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Sample data for PDF417 barcode");

            // -------------------------------------------------------------
            // Step 3: Define a custom layout – set the number of columns and rows.
            // -------------------------------------------------------------
            generator.Parameters.Barcode.Pdf417.Columns = 4; // Controls horizontal density.
            generator.Parameters.Barcode.Pdf417.Rows = 9;    // Controls vertical density.

            // Optional: increase error correction level for noisy environments.
            // Values: 0 (no correction) to 8 (maximum correction).
            generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 2;

            // -------------------------------------------------------------
            // Step 4: Save the generated barcode as a PNG image.
            // -------------------------------------------------------------
            string outputPath = System.IO.Path.Combine(
                Environment.CurrentDirectory, "CustomPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);
        }
    }
}
```

### 為何這段程式碼可行

* **`BarcodeGenerator`** 是所有條碼類型的入口點。傳入 `EncodeTypes.Pdf417` 即告訴函式庫產生 PDF417 符號。
* **欄與列** 是版面配置的主要控制項。較少的欄會產生較高的條碼；較多的欄則使條碼變寬。依照影像顯示的場景（例如標籤印表機或網頁）調整這些數值。
* **錯誤更正** 能提升條碼在污損或低品質媒介上的掃描可靠度。預設等級為 0，適度提升（2–4）可在尺寸與韌性之間取得良好平衡。
* **`Save`** 會以 PNG 格式寫入磁碟，保留銳利的邊緣，且在瀏覽器與行動裝置上皆相容。

執行程式（`dotnet run`）後，會在專案資料夾產生 `CustomPdf417.png`。PNG 影像如下：

![Generated PDF417 barcode image](https://example.com/images/pdf417-sample.png "Screenshot of generated barcode image created with PDF417 using C#")

*Alt text:* **create barcode image** – 以 C# 產生 PDF417 條碼並儲存為 PNG。

---

## 第二步：微調條碼以因應實務情境

### 調整資料長度

PDF417 最多可編碼 1,850 個字元。若需編碼更長的字串，請考慮將資料分割至多個條碼，或使用 **compact mode**：

```csharp
generator.Parameters.Barcode.Pdf417.CompactMode = true;
```

緊縮模式會減少列數，但可能提升視覺密度，請以您的掃描器進行測試。

### 控制影像尺寸

預設影像大小是根據模組大小（條碼中最小的方格）計算。您可以明確設定 DPI，或在產生後縮放影像：

```csharp
generator.Parameters.ImageResolution = new Resolution(300); // 300 DPI for printing.
```

或是儲存後，使用 `System.Drawing` 產生縮圖。

### 處理特殊字元

PDF417 支援完整的 ASCII 集。若資料包含 Unicode 字元，請確保以 UTF‑8 編碼字串：

```csharp
var generator = new BarcodeGenerator(EncodeTypes.Pdf417, System.Text.Encoding.UTF8.GetString(bytes));
```

---

## 第三步：常見陷阱與避免方式

| 陷阱 | 症狀 | 解決方案 |
|------|------|----------|
| 欄數過多且資料不足 | 條碼被截斷或拋出例外。 | 減少 `Columns`，或省略此設定讓函式庫自動調整大小。 |
| 噪聲印表機的錯誤更正等級過低 | 掃描器間歇性讀取失敗。 | 將 `ErrorCorrectionLevel` 提升至至少 2。 |
| 儲存至唯讀目錄 | 執行時拋出 `UnauthorizedAccessException`。 | 改用可寫入的資料夾，例如 `Environment.CurrentDirectory` 或 `Path.GetTempPath()`。 |
| 使用過舊的 Aspose.BarCode 版本 | 缺少 `CompactMode` 等屬性。 | 更新 NuGet 套件至最新穩定版。 |

---

## 第四步：驗證結果

為確認條碼正確產生，您可以：

1. 用任意影像檢視器開啟 `CustomPdf417.png` – 條碼應該清晰、黑色模組在白色背景上呈現銳利。
2. 使用免費的 PDF417 掃描應用（iOS、Android 均有）掃描影像。應用程式應顯示 **“Sample data for PDF417 barcode”**。
3. （可選）在單元測試中以 `System.Drawing.Bitmap` 載入影像，並斷言座標 `(0,0)` 的像素為黑色，以確認影像非空白。

```csharp
using System.Drawing;

Bitmap bmp = new Bitmap("CustomPdf417.png");
bool topLeftIsBlack = bmp.GetPixel(0, 0).R == 0;
Console.WriteLine($"Top‑left pixel black? {topLeftIsBlack}");
```

若斷言通過，即表示您已成功 **create barcode image** 並以程式方式 **generate PDF417 barcode**。

---

## 結論

您現在已掌握如何在 C# 中 **create barcode image**，透過 **generating PDF417 barcode**、自訂版面、調整錯誤更正，並匯出為 PNG。完整範例示範了從初始化 `BarcodeGenerator` 到儲存最終影像的每一步，您可以直接複製、貼上並在自己的專案中執行。

接下來，您可以探索：

* **在 Web API 中嵌入 PNG**，讓客戶端即時請求條碼（將 PDF417 生成作為服務）。
* **批次產生** 大量資料 – 迭代字串清單，將每個 PNG 存入資料庫。
* **其他輸出格式**（SVG、JPEG），只需變更 `BarCodeImageFormat`。

歡迎自行實驗欄/列比例、錯誤更正等級與影像解析度，以符合掃描硬體或 UI 設計的精確需求。祝開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，提供完整可執行的程式碼範例與逐步說明，協助您深入掌握其他 API 功能或探索替代實作方式。

- [How to create PDF417 barcode image in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)
- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}