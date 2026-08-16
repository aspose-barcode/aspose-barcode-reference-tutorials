---
category: general
date: 2026-08-15
description: C# 中的條碼 PNG 圖像 – 學習如何產生郵政條碼、建立 Planet 條碼，並使用簡易產生器調整條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode image png
- barcode generator c#
- generate postal barcode
- create planet barcode
- change barcode height
language: zh-hant
lastmod: 2026-08-15
og_description: C# 教學中的條碼 PNG 圖像示範如何產生郵政條碼、建立 Planet 條碼，並使用 BarcodeGenerator API 調整條碼高度。
og_image_alt: Screenshot of generated PNG barcode with custom height using C# BarcodeGenerator
og_title: 條碼圖像 PNG（C#）– 產生及調整條碼
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: Barcode image PNG in C# – learn how to generate postal barcodes, create
    a Planet barcode, and change barcode height with a simple generator.
  headline: Barcode image PNG in C# generate barcodes, change height
  type: TechArticle
tags:
- barcode
- C#
- PNG
- postal
- generator
title: C# 產生條碼 PNG 圖像，變更高度
url: /zh-hant/python-java/general/barcode-image-png-in-c-generate-barcodes-change-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# C# 中的條碼 PNG 圖像 – 產生條碼，變更高度

如果您需要在 C# 中的 **barcode image PNG**，本指南將帶您完成完整的流程。您將學習如何產生郵政條碼、建立 Planet 條碼，並在不離開 IDE 的情況下變更條碼高度。

產生可靠的 PNG 條碼是運送標籤、庫存系統和自動郵寄解決方案的常見需求。完成本教學後，您將擁有可重複使用的程式碼片段，能產生高品質的 PNG 檔案，支援 Planet 與 RM4SCC 兩種格式，並了解如何調整條碼高度以符合郵政規範。

## 您需要的條件

- .NET 6+ 或 .NET Framework 4.7.2（BarcodeGenerator API 可在任何近期的 .NET 執行環境上運作）  
- 參考 **Aspose.BarCode for .NET** NuGet 套件（或任何提供 `BarcodeGenerator`、`EncodeTypes` 與 `BarCodeImageFormat` 的相容函式庫）  
- 基本熟悉 C# 語法與檔案 I/O  

不需要額外工具；程式碼可在 Visual Studio、Rider 或 `dotnet` CLI 中執行。

## 條碼 PNG 圖像 – 基本產生

第一步是使用預設尺寸建立 **barcode image PNG**。這會產生一個基礎檔案，之後您可以自行客製化。

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define the output folder (replace with your own path)
string outputFolder = @"C:\Barcodes";

// Ensure the folder exists
Directory.CreateDirectory(outputFolder);

// 1️⃣ Create a Planet barcode generator with default height
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Set the module width (X‑dimension) to 4 pixels – this defines the thin bar size
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the image as PNG; this is the first **barcode image PNG** you’ll produce
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

**Why this works:**  
- `EncodeTypes.Planet` 告訴產生器使用 Planet 符號，這是許多郵政服務所要求的。  
- `XDimension.Pixels` 控制最小條的寬度；設定為 4 px 可在一般標籤尺寸下產生可讀的條碼。  
- `Save` 方法將 **barcode image PNG** 檔案寫入磁碟，將所有向量資訊以點陣像素保存。

## 變更條碼高度 – 自訂視覺重量

郵政指南常規要求特定的條碼高度。以下程式碼示範如何為相同的 Planet 條碼設定自訂的 100 像素高度。

```csharp
// 2️⃣ Apply a custom 100‑pixel bar height
planetGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Overwrite or save as a new file to keep both versions
planetGenerator.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

**Why you change the height:**  
- 較高的條碼在低解析度印表機上提升掃描可靠性，而較低的條碼則可節省標籤空間。`BarHeight.Pixels` 屬性讓您在不影響 X‑dimension 的情況下微調此屬性。

## 產生郵政條碼 – 建立 RM4SCC 範例

RM4SCC 格式是英國常用的另一種郵政條碼。產生步驟與 Planet 範例相同，進一步鞏固 **barcode generator c#** 的使用模式。

```csharp
// 3️⃣ Create an RM4SCC barcode generator with default height
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Keep the same module width for consistency
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the default‑height PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                     BarCodeImageFormat.Png);
```

## 變更條碼高度 – RM4SCC 變體

就像 Planet 條碼一樣，您也可以調整 RM4SCC 的條碼高度。以下程式碼將高度設定為 100 px，為相同的資料字串產生第二個 **barcode image PNG**。

```csharp
// 4️⃣ Set a custom 100‑pixel bar height for RM4SCC
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the customized PNG
rm4sccGenerator.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                     BarCodeImageFormat.Png);
```

## 完整、可執行的範例

將所有步驟結合即可得到一個單一、獨立的程式，會產生四個 PNG 檔案：

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        string outputFolder = @"C:\Barcodes";
        Directory.CreateDirectory(outputFolder);

        // Planet barcode – default height
        var planet = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planet.Parameters.Barcode.XDimension.Pixels = 4;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // Planet barcode – custom 100‑pixel height
        planet.Parameters.Barcode.BarHeight.Pixels = 100;
        planet.Save(Path.Combine(outputFolder, "PlanetBarHeight100.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – default height
        var rm4scc = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4scc.Parameters.Barcode.XDimension.Pixels = 4;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeightDefault.png"),
                    BarCodeImageFormat.Png);

        // RM4SCC barcode – custom 100‑pixel height
        rm4scc.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4scc.Save(Path.Combine(outputFolder, "RM4SCCBarHeight100.png"),
                    BarCodeImageFormat.Png);

        Console.WriteLine("All barcode PNG files have been generated in " +


## 接下來您應該學習什麼？

以下教學涵蓋與本指南密切相關的主題，進一步延伸所示技巧。每個資源皆提供完整可執行的程式碼範例，並以步驟說明協助您精通其他 API 功能，或在自己的專案中探索替代實作方式。

- [建立條碼自訂高度 – 一維條碼](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [建立條碼圖像 C# – GS1 DataMatrix 範例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}