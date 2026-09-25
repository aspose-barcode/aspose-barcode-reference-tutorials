---
category: general
date: 2026-08-19
description: 學習如何使用 Aspere.BarCode 在 C# 中產生郵政條碼。本分步指南說明如何產生 Planet 與 RM4SCC 格式的條碼。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- how to generate barcode
language: zh-hant
lastmod: 2026-08-19
og_description: 使用 Aspose.BarCode 在 C# 中生成郵政條碼。請參考本指南，了解如何以自訂尺寸生成 Planet 與 RM4SCC
  條碼。
og_image_alt: Generated postal barcode image using Aspose.BarCode
og_title: 在 C# 中生成郵政條碼 – 完整的 Aspose.BarCode 指南
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  headline: How to generate postal barcode in C# with Aspose.BarCode
  type: TechArticle
- description: Learn how to generate postal barcode in C# using Aspere.BarCode. This
    step‑by‑step guide shows how to generate barcode for Planet and RM4SCC formats.
  name: How to generate postal barcode in C# with Aspose.BarCode
  steps:
  - name: Create a Planet barcode (automatic height)
    text: Planet is a postal barcode used in many countries for mail sorting. When
      you create a Planet barcode, the library automatically determines the optimal
      bar height based on the encoded data.
  - name: Create an RM4SCC barcode with explicit height
    text: RM4SCC is another postal symbology that often requires a specific bar height
      for scanner compatibility. The following code shows how to set that height manually.
  - name: Verify the output
    text: 'After running the program, open the two PNG files located in `YOUR_DIRECTORY`.
      You should see two distinct barcodes:'
  type: HowTo
tags:
- barcode
- Aspose.BarCode
- C#
title: 如何在 C# 中使用 Aspose.BarCode 產生郵政條碼
url: /zh-hant/python-java/general/how-to-generate-postal-barcode-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 Aspose.BarCode 產生郵政條碼

如果您需要 **產生郵政條碼** 以供郵寄應用程式使用，本指南將一步步示範如何使用 Aspose.BarCode 函式庫產生條碼。您將看到完整、可執行的範例，建立自動計算高度的 Planet 條碼以及具有明確條碼高度的 RM4SCC 條碼。

產生郵政條碼是物流軟體、自動標籤印表機與大量郵寄系統的常見需求。完成本教學後，您將能在任何 .NET 專案中整合條碼產生、調整 X‑dimension（模組寬度），以及在標準格式允許的情況下控制條碼高度。

**您將學到的內容**

* 如何在 C# 專案中設定 Aspose.BarCode。  
* 如何產生 Planet 與 RM4SCC 郵政條碼。  
* 如何調整 X‑dimension（模組寬度）與條碼高度。  
* 如何將結果儲存為 PNG 圖片。  

不需要任何外部服務——只要引用 Aspose.BarCode NuGet 套件，即可在本機執行。

## 前置條件

* .NET 6.0 SDK 或更新版本（此程式碼亦支援 .NET Framework 4.7+）。  
* Visual Studio 2022、Visual Studio Code，或您慣用的任何 C# IDE。  
* Aspose.BarCode for .NET 套件 – 透過 NuGet 安裝：

```bash
dotnet add package Aspose.BarCode
```

## 使用 Aspose.BarCode 產生郵政條碼

以下各節將逐步說明，從建立產生器物件到儲存最終 PNG 檔案。

### 步驟 1：建立 Planet 條碼（自動高度）

Planet 是許多國家用於郵件分揀的郵政條碼。建立 Planet 條碼時，函式庫會自動根據編碼資料決定最佳條碼高度。

```csharp
using Aspose.BarCode.Generation;

// Create a Planet barcode generator with the data you want to encode.
BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

// Define the X‑dimension (module width) in pixels. A value of 4 pixels is a good default.
planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;

// Save the barcode as a PNG image. The height is calculated automatically.
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);
```

**為什麼這樣寫** – `EncodeTypes.Planet` 告訴 Aspose.BarCode 使用 Planet 符號。`XDimension` 屬性控制最小條的寬度（模組寬度）。因為 Planet 不需要固定條碼高度，函式庫會自動計算合適的高度，讓程式碼更簡潔。

### 步驟 2：建立具有明確高度的 RM4SCC 條碼

RM4SCC 是另一種郵政符號，通常需要特定的條碼高度以符合掃描器規格。以下程式碼示範如何手動設定該高度。

```csharp
// Create an RM4SCC barcode generator.
BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

// Set the X‑dimension (module width) and the desired bar height in pixels.
rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;

// Save the barcode as a PNG image.
rm4sccGenerator.Save("YOUR_DIRECTORY/PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);
```

**為什麼要設定高度** – 某些郵政掃描器要求最小條碼高度。將 `BarHeight.Pixels = 100` 後，即可保證產生的圖像符合此需求。X‑dimension 與 Planet 條碼保持一致，讓兩張圖的視覺密度相同。

### 步驟 3：驗證輸出

執行程式後，開啟 `YOUR_DIRECTORY` 中的兩個 PNG 檔案。您應該會看到兩個不同的條碼：

* `PostalPlanetBarHeightNone.png` – 以自動計算高度的 Planet 條碼。  
* `PostalRM4SCCBarHeight100Pixels.png` – 條碼高度為 100 像素的 RM4SCC 條碼。

兩張圖皆可直接送入標籤印表機或在 Web 應用程式中顯示。

![使用 Aspose.BarCode 產生的郵政條碼圖像](generated-postal-barcode.png)

*圖片說明：* **產生的郵政條碼** 圖像，使用 Aspose.BarCode（示範如何產生郵政條碼）。

## 如何使用自訂尺寸產生條碼（進階）

若您需要微調其他參數——例如邊距、文字位置或顏色——Aspose.BarCode 提供功能豐富的 `Parameters` 物件。以下範例示範如何加入白色背景並停用可讀文字。

```csharp
planetGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.White;
planetGenerator.Parameters.Barcode.CodeTextVisible = false;
planetGenerator.Save("YOUR_DIRECTORY/PostalPlanetNoText.png", BarCodeImageFormat.Png);
```

**何時使用** – 在自動分揀只需機器可讀圖樣時，常會停用可讀文字。設定背景顏色可確保條碼在透明介質上正確列印。

## 常見問題與專業技巧

| 問題 | 為什麼會發生 | 解決方式 |
|------|--------------|----------|
| 條碼看起來被拉伸 | X‑dimension 相對於圖像尺寸過大 | 大多數郵政條碼將 `XDimension.Pixels` 保持在 2 到 5 之間 |
| 掃描器拒絕圖像 | 條碼高度低於郵政服務規定的最小值 | 對 RM4SCC 使用 `BarHeight.Pixels` ≥ 80，除非規範另有說明 |
| PNG 檔案太大 | 圖像解析度高於需求 | 使用 PNG‑8 (`BarCodeImageFormat.Png8`) 或降低像素尺寸 |

**專業技巧：** 在投入正式環境前，務必使用實體掃描器測試產生的條碼。細微的視覺差異可能影響可讀性。

## 完整原始碼

將下列程式碼完整複製到新的主控台應用程式 (`Program.cs`) 中。請將輸出路徑調整為您的程式可寫入的資料夾。

```csharp
using System;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // ------------------------------
        // Generate Planet barcode (auto height)
        // ------------------------------
        BarcodeGenerator planetGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");
        planetGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        planetGenerator.Save("PostalPlanetBarHeightNone.png", BarCodeImageFormat.Png);

        // ------------------------------
        // Generate RM4SCC barcode (explicit height)
        // ------------------------------
        BarcodeGenerator rm4sccGenerator = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");
        rm4sccGenerator.Parameters.Barcode.XDimension.Pixels = 4;
        rm4sccGenerator.Parameters.Barcode.BarHeight.Pixels = 100;
        rm4sccGenerator.Save("PostalRM4SCCBarHeight100Pixels.png", BarCodeImageFormat.Png);

        Console.WriteLine("Barcodes generated successfully.");
    }
}
```

執行程式後會在執行目錄印出 *“Barcodes generated successfully.”*，並產生兩個 PNG 檔案。

## 結論

您現在已掌握如何在 C# 中使用 Aspose.BarCode **產生郵政條碼**，包括自動高度的 Planet 條碼與固定高度的 RM4SCC 條碼。本指南亦示範了如何以自訂 X‑dimension、條碼高度與視覺選項產生條碼，為任何郵寄自動化專案奠定堅實基礎。

接下來可以探索的方向：

* 使用 Aspose.PDF 將產生的 PNG 嵌入 PDF 發票。  
* 將輸出格式切換為 SVG，以取得可縮放向量圖形。  
* 使用 `BarcodeReader` 類別以程式方式驗證編碼資料。

歡迎嘗試不同的符號（例如 `EncodeTypes.Postnet`），並將您的成果分享給社群。祝開發順利！


## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步深化您所學的技巧。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助您掌握更多 API 功能，並在自己的專案中探索替代實作方式。

- [How to Generate Barcode Image with Supplemental Space Customization using Aspose.BarCode](/barcode/english/net/supplemental-barcode-data/supplemental-barcode-space-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}