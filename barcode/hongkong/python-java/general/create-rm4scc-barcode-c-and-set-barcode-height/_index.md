---
category: general
date: 2026-08-25
description: 使用 C# 建立 RM4SCC 條碼，提供逐步程式碼，並學習如何設定條碼高度以精確調整尺寸。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create rm4scc barcode c#
- how to set barcode height
language: zh-hant
lastmod: 2026-08-25
og_description: 使用 Aspose.BarCode 在 C# 中建立 RM4SCC 條碼，並學習如何設定條碼高度，以在 .NET 應用程式中實現精確控制。
og_image_alt: Screenshot of an RM4SCC barcode generated with C#
og_title: 在 C# 中建立 RM4SCC 條碼 – 設定條碼高度指南
schemas:
- author: Aspose
  dateModified: '2026-08-25'
  description: Create RM4SCC barcode C# with step‑by‑step code and learn how to set
    barcode height for precise sizing.
  headline: Create RM4SCC barcode C# and set barcode height
  type: TechArticle
tags:
- barcode
- C#
- RM4SCC
- Aspose.BarCode
title: 建立 RM4SCC 條碼 C# 並設定條碼高度
url: /zh-hant/python-java/general/create-rm4scc-barcode-c-and-set-barcode-height/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 RM4SCC 條碼 C# 並設定條碼高度

快速使用 Aspose.BarCode 函式庫建立 RM4SCC 條碼 C#。本教學說明 **如何設定條碼高度** 以及自訂其他視覺屬性，讓條碼精確符合您的版面配置。

您將看到一個完整、可直接執行的主控台程式，會產生三個 PNG 檔案：

* 預設高度的 Planet 條碼（供比較用）  
* 手動高度為 100 像素的 RM4SCC 條碼  
* 條碼條為空白（未填滿）的 Planet 條碼  

此範例假設您已安裝 Visual Studio 2022（或任何 .NET 6+ 開發環境）以及有效的 Aspose.BarCode for .NET 授權或評估版。

## 先決條件

| 需求 | 原因 |
|-------------|--------|
| .NET 6 SDK (or later) | 提供主控台應用程式的執行環境 |
| Aspose.BarCode for .NET NuGet package | 提供 `BarcodeGenerator`、`EncodeTypes` 以及影像匯出 API |
| Basic C# knowledge | 需要了解程式流程 |

使用以下指令安裝 NuGet 套件：

```bash
dotnet add package Aspose.BarCode
```

> **專業提示：** 若在未授權的情況下執行程式，產生的影像會包含小型 Aspose 水印。

## 步驟 1：設定專案結構

建立新的主控台專案並加入必要的 `using` 指令：

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat; // optional, you can use the enum directly
```

## 步驟 2：定義輸出資料夾

選擇一個用於儲存 PNG 檔案的資料夾。必須先確保該資料夾已存在，才能呼叫 `Save`。

```csharp
// Step 1: Define the output folder
string outputFolder = "GeneratedBarcodes/";

// Ensure the directory exists
System.IO.Directory.CreateDirectory(outputFolder);
```

以程式方式建立目錄可避免在全新機器上執行程式時發生 *FileNotFoundException*。

## 步驟 3：產生預設高度的 Planet 條碼（基準線）

Planet 條碼並非本指南的重點，但它提供了一個視覺基準，可用於與手動設定尺寸的 RM4SCC 條碼進行比較。

```csharp
// Step 2: Generate a Planet barcode with the default (auto) height
BarcodeGenerator planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetAuto.Parameters.Barcode.XDimension.Pixels = 4; // controls bar width
planetAuto.Save($"{outputFolder}PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

*為何這很重要：*  
`XDimension` 決定單根條的寬度。保持此值不變，同時變更 `BarHeight`，即可僅觀察高度的影響。

## 步驟 4：**建立 RM4SCC 條碼 C#** – 設定手動高度

現在我們來處理主要任務：**建立 RM4SCC 條碼 C#**，並明確控制其高度。

```csharp
// Step 3: Generate an RM4SCC barcode with a manual height of 100 px
BarcodeGenerator rm4sccManual = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
rm4sccManual.Parameters.Barcode.XDimension.Pixels = 4;           // same bar width as Planet example
rm4sccManual.Parameters.Barcode.BarHeight.Pixels = 100;          // <-- how to set barcode height
rm4sccManual.Save($"{outputFolder}PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

### 如何設定條碼高度

`BarHeight` 屬性位於 `Parameters.Barcode` 下。它接受以 **像素**、**點** 或 **毫米** 為單位的 `float` 值，取決於您選擇的 `Unit`（`Pixels`、`Points`、`Millimeters`）。本範例使用 `Pixels`，因為輸出格式為 PNG。

如果需要以毫米為單位的高度，請先切換單位：

```csharp
rm4sccManual.Parameters.Barcode.BarHeight.Unit = BarHeightUnit.Millimeters;
rm4sccManual.Parameters.Barcode.BarHeight.Value = 25; // 25 mm tall
```

## 步驟 5：產生條碼條為空白（未填滿）的 Planet 條碼

此步驟示範另一個實用屬性——`FilledBars`。將其設為 `false` 會產生「空心」條碼，對於設計需求相當有用。

```csharp
// Step 4: Generate a Planet barcode with empty (unfilled) bars
BarcodeGenerator planetEmptyBars = new BarcodeGenerator(EncodeTypes.Planet, "123456");
planetEmptyBars.Parameters.Barcode.XDimension.Pixels = 4;
planetEmptyBars.Parameters.Barcode.FilledBars = false; // makes bars transparent
planetEmptyBars.Save($"{outputFolder}PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

## 完整、可執行的程式

將以下程式碼複製到 `Program.cs`。建置並執行專案後，三個 PNG 檔案會出現在 `GeneratedBarcodes` 資料夾中。



## 接下來該學什麼？

以下教學涵蓋與本指南密切相關的主題，並以此為基礎延伸技術。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [如何在 Java 中建立 Code128 條碼並設定條碼高度](/barcode/english/java/barcode-configuration/setting-bars-height/)
- [如何在 .NET 中使用 Aspose.BarCode 為 Code 16K 建立條碼靜區](/barcode/english/net/code-16k-encoding/code-16k-quiet-zone-settings/)
- [如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}