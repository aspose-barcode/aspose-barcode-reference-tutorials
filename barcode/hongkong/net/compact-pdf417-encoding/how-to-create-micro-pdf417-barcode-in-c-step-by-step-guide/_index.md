---
category: general
date: 2026-08-22
description: 學習如何在 C# 中建立微型 PDF417 條碼並產生條碼 PNG 圖像。包括設定條碼尺寸及儲存檔案。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create micro pdf417 barcode
- how to generate barcode png
- create barcode image c#
- how to set barcode dimensions
language: zh-hant
lastmod: 2026-08-22
og_description: 在 C# 中建立微型 PDF417 條碼並匯出為 PNG。請遵循本指南設定條碼尺寸，快速產生條碼圖像。
og_image_alt: Screenshot of a micro PDF417 barcode generated with C# code
og_title: 在 C# 中建立微型 PDF417 條碼 – 完整程式碼教學
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  headline: How to create micro PDF417 barcode in C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to create micro PDF417 barcode in C# and generate a barcode
    PNG image. Includes setting barcode dimensions and saving the file.
  name: How to create micro PDF417 barcode in C# – step‑by‑step guide
  steps:
  - name: 'Build the project: `dotnet build`.'
    text: 'Build the project: `dotnet build`.'
  - name: 'Execute: `dotnet run`.'
    text: 'Execute: `dotnet run`.'
  - name: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
    text: Open `MicroPdf417.png` on your desktop and scan it with a mobile barcode
      scanner app.
  type: HowTo
tags:
- barcode
- C#
- MicroPdf417
- image generation
title: 如何在 C# 中建立微型 PDF417 條碼 – 逐步指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中建立微型 PDF417 條碼 – 步驟指南

如果您需要為票務系統、庫存標籤或手機掃描 **建立微型 PDF417 條碼**，本教學將完整說明。您將看到產生條碼 PNG 的完整 C# 程式碼，學習如何設定條碼尺寸，並了解每個設定選項。

完成本指南後，您將能夠產生高解析度的條碼影像、客製化 X‑dimension、選擇欄位數，並將結果儲存為 PNG 檔案——只需幾行程式碼。

## 您需要的環境

- .NET 6.0 SDK 或更新版本（此程式碼可於 .NET Core 與 .NET Framework 使用）
- Visual Studio 2022 或任何相容 C# 的 IDE
- **Aspose.BarCode for .NET** NuGet 套件（或任何支援 `EncodeTypes.MicroPdf417` 的函式庫）
- 基本的 C# 語法熟悉度

> **專業提示：** Aspose.BarCode 的免費社群版已足夠開發與測試使用。正式上線時，請取得授權以移除評估水印。

## 步驟 1：安裝條碼函式庫

在專案資料夾中開啟終端機並執行以下指令：

```bash
dotnet add package Aspose.BarCode
```

此指令會加入 `Aspose.BarCode` 程式集，提供用於 **建立條碼影像 C#** 應用程式的 `BarcodeGenerator` 類別。

## 步驟 2：初始化產生器 – 建立微型 PDF417 條碼

第一行可執行的程式碼會建立一個 `BarcodeGenerator` 實例，設定為 Micro PDF417 符號，並提供您欲編碼的資料。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize a Micro PDF417 barcode generator with the data to encode
        BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");
```

*為什麼這很重要*：`EncodeTypes.MicroPdf417` 列舉告訴函式庫使用 PDF417 的緊縮版，適合小型標籤與手機螢幕。

## 步驟 3：在 C# 中設定條碼尺寸

微調模組寬度（X‑dimension）可控制條碼的視覺密度。較小的數值會產生較銳利的影像，而較大的數值則使條碼在遠距離時更易於掃描。

```csharp
        // Step 3: Set the X‑dimension (module width) to 2 pixels for finer resolution
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**為什麼要設定尺寸**：若未調整 X‑dimension，預設值在高 DPI 渲染時可能會使條碼看起來模糊。將其設定為 2 像素對大多數螢幕掃描而言是一個不錯的平衡。

## 步驟 4：選擇欄位數 – 控制條碼寬度

Micro PDF417 支援 1 至 4 欄。欄位數越多，資料水平壓縮越多，整體影像寬度亦會減少。

```csharp
        // Step 4: Define the number of columns (allowed values: 1‑4)
        generator.Parameters.Barcode.Pdf417.Columns = 4;
```

*邊緣情況*：若要求 5 欄，函式庫會拋出 `ArgumentOutOfRangeException`。請始終保持在文件規定的範圍內。

## 步驟 5：產生條碼 PNG – 儲存影像

現在您可以將產生的條碼匯出為 PNG 檔案。PNG 保留無損品質，對於可靠的掃描至關重要。

```csharp
        // Step 5: Save the generated barcode as a PNG image
        string outputPath = Path.Combine(
            Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
            "MicroPdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);
        Console.WriteLine($"Barcode saved to {outputPath}");
    }
}
```

執行程式時，您會在主控台看到確認檔案位置的訊息。產生的 `MicroPdf417.png` 如下所示：

![顯示使用 C# 產生的微型 PDF417 條碼的螢幕截圖](micro-pdf417-example.png "產生的微型 PDF417 條碼")

*圖片替代文字*：**使用 C# 產生的微型 PDF417 條碼** – 展示套用尺寸與欄位設定後的最終輸出。

## 步驟 6：執行並驗證輸出

1. 建置專案：`dotnet build`。
2. 執行：`dotnet run`。
3. 在桌面開啟 `MicroPdf417.png`，並使用手機條碼掃描應用程式掃描。

您應該會看到解碼後的文字 **“Sample text”**。若掃描器回報錯誤，請再次檢查 X‑dimension 與欄位數——極端值可能使條碼對某些裝置過於密集。

## 常見變化與故障排除

| Situation | Adjustment |
|-----------|------------|
| **需要較大的條碼以適應低解析度印表機** | 將 `XDimension.Pixels` 提升至 3 或 4。 |
| **想要更高的條碼而不改變寬度** | 設定 `generator.Parameters.Barcode.Pdf417.Rows`（列範圍 3‑90）。 |
| **在迴圈中產生多個條碼** | 重複使用相同的 `BarcodeGenerator` 實例，並在每次 `Save` 前僅更改 `CodeText`。 |
| **儲存為 JPEG 而非 PNG** | 將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。 |
| **在 .NET Framework 4.7 上執行** | 相同程式碼可執行；只需參考相應的 `Aspose.BarCode.dll`。 |

## 完整程式碼清單（可執行）

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MicroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialize a Micro PDF417 barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MicroPdf417, "Sample text");

            // Set the X‑dimension (module width) to 2 pixels for finer resolution
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns (allowed values: 1‑4)
            generator.Parameters.Barcode.Pdf417.Columns = 4;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(
                Environment.GetFolderPath(Environment.SpecialFolder.Desktop),
                "MicroPdf417.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

**預期輸出** – 一個 200 × 100 像素的 PNG 檔案，內含清晰的 Micro PDF417 條碼，解碼後為 “Sample text”。

## 結論

現在您已了解如何在 C# 中 **建立微型 PDF417 條碼**、**設定條碼尺寸**，以及 **產生條碼 PNG** 影像。完整範例示範了從函式庫安裝到儲存最終檔案的每一步，讓您能將條碼產生直接嵌入自己的應用程式中。

接下來，您可以探索相關主題，例如 **使用 Aspose.BarCode 建立 QR Code**、**自訂顏色**，或 **在 PDF 文件中嵌入條碼**。這些皆基於此處說明的 `BarcodeGenerator` 基礎。

歡迎嘗試不同的資料字串、欄位數與 X‑dimension 值，以符合您的特定掃描環境。祝開發愉快！

## 接下來您可以學習什麼？

以下教學涵蓋與本指南密切相關的主題，建立在此處示範的技巧之上。每個資源皆提供完整可執行的程式碼範例與步驟說明，協助您精通其他 API 功能，並在專案中探索替代實作方式。

- [如何建立條碼 – 緊縮 PDF417（使用 Aspose.BarCode）](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [如何產生 PDF417 條碼 – 緊縮 PDF417 編碼](/barcode/english/net/compact-pdf417-encoding/)
- [如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}