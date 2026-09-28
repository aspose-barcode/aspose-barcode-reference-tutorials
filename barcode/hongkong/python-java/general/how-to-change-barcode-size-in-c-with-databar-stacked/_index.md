---
category: general
date: 2026-08-22
description: 如何在 C# 中使用 DataBar 堆疊全方向產生器更改條碼尺寸。學習設定 X 方向尺寸與長寬比以產生 PNG 輸出。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to change barcode size
- DataBar Stacked Omni‑Directional barcode
- C# barcode generator
- barcode aspect ratio
- X‑dimension pixels
- BarCodeImageFormat PNG
language: zh-hant
lastmod: 2026-08-22
og_description: 如何在 C# 中使用 DataBar 堆疊全方向產生器更改條碼尺寸。請依循步驟指南調整 X 方向尺寸與長寬比。
og_image_alt: Screenshot showing how to change barcode size in C#
og_title: 如何在 C# 中更改條碼大小 – 完整指南
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  headline: How to change barcode size in C# with DataBar Stacked
  type: TechArticle
- description: How to change barcode size in C# using the DataBar Stacked Omni‑Directional
    generator. Learn to set X‑dimension and aspect ratio for PNG output.
  name: How to change barcode size in C# with DataBar Stacked
  steps:
  - name: Create a DataBar Stacked Omni‑Directional barcode generator
    text: The generator object holds all barcode settings. By passing `EncodeTypes.DatabarStackedOmniDirectional`
      and sample data, you create a valid barcode ready for further customization.
  - name: Set the basic module size (X‑dimension) in pixels
    text: The X‑dimension defines the width of a single barcode module. Adjusting
      it changes the overall width and height proportionally.
  - name: Change the barcode aspect ratio to 15 and save the image
    text: The **barcode aspect ratio** controls the height‑to‑width relationship.
      An aspect ratio of 15 yields a relatively tall barcode.
  - name: Change the barcode aspect ratio to 30 and save the new image
    text: Increasing the aspect ratio to 30 makes the barcode even taller, illustrating
      the flexibility of size adjustments.
  - name: Verify the generated images
    text: Open the PNG files in any image viewer. You should see two barcodes with
      identical width (controlled by the X‑dimension) but different heights (controlled
      by the aspect ratio). If the images appear blurry, increase the X‑dimension
      pixels; if they are too tall, lower the aspect ratio.
  - name: What to explore next
    text: '* **Custom colors** – experiment with `barcodeGenerator.Parameters.Barcode.ForeColor`
      and `BackColor` to match brand guidelines. * **Different barcode types** – replace
      `EncodeTypes.DatabarStackedOmniDirectional` with `EncodeTypes.QR` or `EncodeTypes.Code128`
      to see how size parameters differ across'
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: 如何在 C# 中使用 DataBar Stacked 更改條碼大小
url: /zh-hant/python-java/general/how-to-change-barcode-size-in-c-with-databar-stacked/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 C# 中使用 DataBar Stacked 調整條碼大小

如果您需要在 .NET 應用程式中 **如何調整條碼大小**，本指南將示範使用 DataBar Stacked Omni‑Directional 條碼產生器的完整步驟。您將了解如何以像素為單位控制 X‑dimension、調整條碼的長寬比，並將結果儲存為 PNG 檔案。

在列印標籤空間受限或需要更高解析度影像以供數位渠道使用時，常會需要變更條碼大小。本教學涵蓋從初始化產生器到產生兩張不同尺寸影像的全部流程。

## 前置條件

開始之前，請確保您已具備：

* 已安裝 .NET 6.0 SDK 或更新版本  
* 參考 **Aspose.BarCode for .NET** NuGet 套件  
* 具備基本的 C# 語法概念  

不需要額外設定；程式碼可在 Windows、Linux 或 macOS 上執行。

## 如何在 C# 中調整條碼大小 – 步驟說明

以下章節將流程切分為可重複使用的步驟。每一步都說明 **為什麼** 需要此程式碼，而不僅是 **做什麼**。

### 步驟 1：建立 DataBar Stacked Omni‑Directional 條碼產生器

產生器物件負責保存所有條碼設定。傳入 `EncodeTypes.DatabarStackedOmniDirectional` 以及樣本資料，即可建立可供後續客製化的有效條碼。

```csharp
// Step 1: Create a DataBar Stacked Omni‑Directional barcode generator with sample data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional, "(01)12345678901231");
```

*為什麼重要* – **C# 條碼產生器** 類別封裝了編碼演算法。從有效的產生器開始，可確保之後的尺寸變更會正確套用於此條碼類型。

### 步驟 2：以像素設定基本模組大小（X‑dimension）

X‑dimension 定義單一條碼模組的寬度。調整它會成比例改變條碼的整體寬度與高度。

```csharp
// Step 2: Define the basic module size (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*為什麼重要* – 較大的 X‑dimension 會產生較大的條碼，適合低解析度印表機；相反，較小的數值則產生緊湊的條碼，適用於小尺寸標籤。

### 步驟 3：將條碼長寬比設定為 15 並儲存影像

**條碼長寬比** 控制高度與寬度的比例。長寬比為 15 時，條碼會相對較高。

```csharp
// Step 3: Set the DataBar aspect ratio to 15 and save the image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

*為什麼重要* – 不同的掃描設備對長寬比有最佳需求。將長寬比設定為 15，即示範了透過調整高度（而寬度仍由 X‑dimension 定義）**如何調整條碼大小**。

#### 預期輸出

`DatabarAspectRatio15.png` 會顯示一個比預設更高的 DataBar Stacked Omni‑Directional 條碼。條碼寬度反映 2 像素的 X‑dimension，且高度遵循 15 的比例。

### 步驟 4：將條碼長寬比設定為 30 並儲存新影像

將長寬比提升至 30，條碼會更高，進一步說明尺寸調整的彈性。

```csharp
// Step 4: Change the DataBar aspect ratio to 30 and save the new image
barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
barcodeGenerator.Save("YOUR_DIRECTORY/DatabarAspectRatio30.png", BarCodeImageFormat.Png);
```

*為什麼重要* – 只要交換 **條碼長寬比** 的數值，即可立即看到 **如何調整條碼大小**，而不必重新建立產生器。這在批次處理情境下可節省大量時間。

#### 預期輸出

`DatabarAspectRatio30.png` 明顯比前一張圖更高，證實長寬比直接影響條碼高度。

### 步驟 5：驗證產生的影像

使用任何影像檢視器開啟 PNG 檔案。您應該會看到兩個條碼寬度相同（受 X‑dimension 控制），但高度不同（受長寬比控制）。若影像模糊，可提升 X‑dimension 像素；若過高，則降低長寬比。

```csharp
// Optional verification code – load images and print dimensions
using (var img15 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio15.png"))
using (var img30 = Image.Load("YOUR_DIRECTORY/DatabarAspectRatio30.png"))
{
    Console.WriteLine($"15‑ratio size: {img15.Width}×{img15.Height}");
    Console.WriteLine($"30‑ratio size: {img30.Width}×{img30.Height}");
}
```

*為什麼重要* – 程式化驗證可確保尺寸變更正確套用，這對自動化建置流程尤為關鍵。

## 常見變化與例外情況

| 情境 | 調整方式 | 原因 |
|-----------|------------|--------|
| **非常小的標籤** | 設定 `XDimension.Pixels = 1` 並 `AspectRatio = 10` | 在保持可讀性的同時減少整體佔位 |
| **高解析度列印** | 設定 `XDimension.Pixels = 4` 並 `AspectRatio = 20` | 提升像素密度以獲得更清晰的輸出 |
| **不同影像格式** | 將 `BarCodeImageFormat.Png` 換成 `BarCodeImageFormat.Jpeg` | PNG 支援受限時的替代方案 |
| **動態資料** | 將變數字串傳入 `BarcodeGenerator` 建構子 | 為每個商品自動產生條碼 |

若需大量產生不同尺寸的條碼，可將上述步驟封裝成方法：

```csharp
void GenerateDatabar(string data, int xDim, int aspectRatio, string filePath)
{
    var generator = new BarcodeGenerator(EncodeTypes.DatabarStackedOmniDirectional, data);
    generator.Parameters.Barcode.XDimension.Pixels = xDim;
    generator.Parameters.Barcode.DataBar.AspectRatio = aspectRatio;
    generator.Save(filePath, BarCodeImageFormat.Png);
}
```

呼叫 `GenerateDatabar("(01)98765432109876", 3, 25, "output.png")` 即可在單行程式碼內產生自訂尺寸的條碼。

## 可靠調整尺寸的專業提示

* **務必先設定 X‑dimension 再設定長寬比。** 先變更長寬比可能因 X‑dimension 預設值不理想而導致意外的縮放。  
* **使用一致的輸出資料夾。** 示範中硬寫 `"YOUR_DIRECTORY"` 可行，但正式環境建議使用 `Path.Combine(Environment.CurrentDirectory, "Barcodes")`。  
* **驗證產生的影像尺寸。** X‑dimension 的微小變動在螢幕上可能不易察覺，檢查像素尺寸可保證變更已生效。  

## 結論

您現在已掌握 **如何在 C# 中使用 DataBar Stacked Omni‑Directional 條碼產生器調整條碼大小**。只要調整 **X‑dimension 像素** 與 **條碼長寬比**，即可產生符合任何標籤尺寸或解析度需求的 PNG 影像。上方完整、可執行的範例示範了從產生器建立到尺寸驗證的完整工作流程。

### 接下來可以探索的主題

* **自訂顏色** – 嘗試 `barcodeGenerator.Parameters.Barcode.ForeColor` 與 `BackColor` 以符合品牌指南。  
* **其他條碼類型** – 將 `EncodeTypes.DatabarStackedOmniDirectional` 換成 `EncodeTypes.QR` 或 `EncodeTypes.Code128`，觀察不同符號的尺寸參數差異。  
* **批次處理** – 結合 `GenerateDatabar` 方法與 CSV 匯入，自動產生數千筆條碼。

歡迎將程式碼片段套用到您的專案架構，讓條碼尺寸調整提升掃描可靠性與視覺設計。祝開發順利！

## 下一步該學什麼？

以下教學與本指南緊密相關，能進一步深化您對 API 功能的掌握，並探索在實務專案中的其他實作方式。

- [How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode for .NET](/barcode/english/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}