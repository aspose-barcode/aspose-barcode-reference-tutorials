---
category: general
date: 2026-09-07
description: 在 C# 中建立郵政條碼圖像，並透過簡潔的條碼產生器範例 C# 教學，學習如何調整條碼高度。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal barcode images
- barcode generator example c#
- change barcode height
language: zh-hant
lastmod: 2026-09-07
og_description: 使用 C# 建立郵政條碼圖像，並透過清晰的條碼產生器範例 C#，探索更改條碼高度的最簡單方法。
og_image_alt: Screenshot showing created postal barcode images with custom height
og_title: 建立郵政條碼圖像 – 在 C# 中設定條碼高度
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Create postal barcode images in C# and learn how to change barcode
    height with a concise barcode generator example C# tutorial.
  headline: Create postal barcode images and set barcode height in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: 在 C# 中建立郵政條碼圖像並設定條碼高度
url: /zh-hant/python-java/general/create-postal-barcode-images-and-set-barcode-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 C# 建立郵件條碼圖像並設定條碼高度

如果您需要 **建立郵件條碼圖像** 以用於寄件應用程式，本指南提供完整、可直接執行的解決方案。您將看到一個 **條碼產生器範例 C#**，可同時產生 Planet 與 RM4SCC 條碼，並學會 **變更條碼高度** 而不必離開程式碼。

本教學涵蓋您立即開始產生郵件條碼所需的一切：必備 NuGet 套件、資料夾準備、預設高度產生、固定高度客製化，以及常見的陷阱與避免方式。

## 前置條件

開始之前，請確保您已安裝：

- .NET 6.0 SDK 或更新版本  
- Visual Studio 2022（或任何 C# IDE）  
- **Aspose.BarCode** NuGet 套件（`Install-Package Aspose.BarCode`）  

這些元件會提供在範例中使用的 `BarcodeGenerator` 類別。

## 步驟 1：準備輸出資料夾

產生器會將 PNG 檔寫入磁碟，故資料夾必須已存在且可寫入。

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Define where the barcode images will be saved
string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");

// Ensure the directory exists
Directory.CreateDirectory(outputFolder);
Console.WriteLine($"Images will be saved to: {outputFolder}");
```

*為什麼需要這麼做*：若儲存至不存在的路徑會拋出 `DirectoryNotFoundException`。`Directory.CreateDirectory` 是安全的，因為資料夾已存在時不會執行任何操作。

## 步驟 2：產生預設高度的 Planet 與 RM4SCC 條碼

當您未設定 `BarHeight` 屬性時，函式庫會自動選擇最佳高度（自動模式）。這對快速原型開發非常有用。

```csharp
// Planet barcode – auto height
var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    // Set module width (X dimension) to 4 pixels for readability
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                BarCodeImageFormat.Png);

// RM4SCC barcode – auto height
var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
};
rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                BarCodeImageFormat.Png);
```

**結果**：在 `Barcodes/` 資料夾中會出現兩個 PNG 檔，條碼高度由函式庫自行決定。

## 步驟 3：設定明確的條碼高度（100 像素）

有時郵寄規範要求固定的條碼高度。您可以透過 `BarHeight.Pixels` 屬性加以控制。

```csharp
// Planet barcode – fixed 100‑pixel height
var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },   // module width
            BarHeight = { Pixels = 100 }   // explicit height
        }
    }
};
planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                 BarCodeImageFormat.Png);

// RM4SCC barcode – fixed 100‑pixel height
var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
{
    Parameters = {
        Barcode = {
            XDimension = { Pixels = 4 },
            BarHeight = { Pixels = 100 }
        }
    }
};
rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                 BarCodeImageFormat.Png);
```

**為什麼可能需要這樣做**：郵政服務常規會規定最小條碼高度以確保掃描可靠性。設定固定高度可保證所有產生的圖像皆符合規範。

## 步驟 4：驗證產生的圖像

您可以使用任何圖像檢視器開啟 PNG 檔。視覺上的差異在於條碼的長度：

- **自動高度** 檔案：條碼高度會依資料長度自動調整。  
- **固定高度** 檔案：條碼高度恆為 100 像素，與內容無關。

若需以程式方式確認高度，可使用 `System.Drawing` 載入圖像並檢查 `Bitmap.Height`。

```csharp
using System.Drawing;

void PrintBarHeight(string filePath)
{
    using var bmp = new Bitmap(filePath);
    Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
}

PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
```

## 專業小技巧：調整 DPI 以符合高解析度列印

當條碼需在標籤印表機上列印時，您可能想提升 DPI 設定。`Resolution` 屬性讓您在不改變像素尺寸的前提下調整解析度。

```csharp
planetFixed.Parameters.Resolution = 300; // 300 dpi for crisp prints
planetFixed.Save(Path.Combine(outputFolder, "Planet_300dpi.png"),
                 BarCodeImageFormat.Png);
```

## 常見陷阱與避免方法

| 問題 | 原因 | 解決方法 |
|------|------|----------|
| **未建立圖像** | 輸出資料夾不存在或沒有寫入權限 | 呼叫 `Directory.CreateDirectory`，並以足夠權限執行應用程式 |
| **條碼無法辨識** | X‑dimension 太小（例如 1 像素） | 使用至少 2 像素；4 像素在大多數掃描器上表現良好 |
| **條碼類型錯誤** | `EncodeTypes` 值不正確 | 核對郵件規範（Planet 或 RM4SCC），並使用對應的列舉值 |

## 完整原始碼（可直接複製）

```csharp
using System;
using System.IO;
using System.Drawing;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class PostalBarcodeDemo
{
    static void Main()
    {
        // -------------------------------------------------
        // Step 1 – Prepare output folder
        // -------------------------------------------------
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);
        Console.WriteLine($"Saving images to: {outputFolder}");

        // -------------------------------------------------
        // Step 2 – Auto‑height barcodes
        // -------------------------------------------------
        var planetAuto = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        planetAuto.Save(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        var rm4sccAuto = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = { Barcode = { XDimension = { Pixels = 4 } } }
        };
        rm4sccAuto.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeightAuto.png"),
                        BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 3 – Fixed 100‑pixel height barcodes
        // -------------------------------------------------
        var planetFixed = new BarcodeGenerator(EncodeTypes.Planet, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        planetFixed.Save(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"),
                         BarCodeImageFormat.Png);

        var rm4sccFixed = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456")
        {
            Parameters = {
                Barcode = {
                    XDimension = { Pixels = 4 },
                    BarHeight = { Pixels = 100 }
                }
            }
        };
        rm4sccFixed.Save(Path.Combine(outputFolder, "PostalRM4SCCBarHeight100.png"),
                         BarCodeImageFormat.Png);

        // -------------------------------------------------
        // Step 4 – Verify heights (optional)
        // -------------------------------------------------
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeightAuto.png"));
        PrintBarHeight(Path.Combine(outputFolder, "PostalPlanetBarHeight100.png"));
    }

    static void PrintBarHeight(string filePath)
    {
        using var bmp = new Bitmap(filePath);
        Console.WriteLine($"{Path.GetFileName(filePath)} – Height: {bmp.Height}px");
    }
}
```

執行程式後會產生四個 PNG 檔：

- `PostalPlanetBarHeightAuto.png`
- `PostalRM4SCCBarHeightAuto.png`
- `PostalPlanetBarHeight100.png`
- `PostalRM4SCCBarHeight100.png`

Each


## 接下來您可以學習什麼？

以下教學與本指南緊密相關，能進一步深化您對本技術的掌握。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您在專案中探索更多 API 功能與替代實作方式。

- [Create Postal Barcode in C# – Full Generator Example](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)
- [.net barcode generator – change barcode height](/barcode/english/python-java/general/net-barcode-generator-change-barcode-height/)
- [Create Barcode Custom Height – One-Dimensional Barcodes](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}