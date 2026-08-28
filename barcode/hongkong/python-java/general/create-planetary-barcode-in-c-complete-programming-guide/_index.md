---
category: general
date: 2026-07-30
description: 使用 C# 快速建立行星條碼。了解如何產生行星條碼、設定自訂條碼高度，以及匯出條碼圖像。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create planetary barcode
- generate planet barcode
- custom barcode height
- export barcode image
- customize postal barcode
language: zh-hant
lastmod: 2026-07-30
og_description: 使用 C# 建立行星條碼，即時生成自訂高度的行星條碼，然後匯出條碼圖像以適用於任何郵遞系統。
og_image_alt: Screenshot showing a generated planetary barcode saved as a PNG file
og_title: 在 C# 中建立行星條碼 – 完整逐步教學
schemas:
- author: Aspose
  dateModified: '2026-07-30'
  description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  headline: Create planetary barcode in C# – Complete Programming Guide
  type: TechArticle
- description: Create planetary barcode quickly with C#. Learn how to generate planet
    barcode, set custom barcode height, and export barcode image.
  name: Create planetary barcode in C# – Complete Programming Guide
  steps:
  - name: 'Example 1: Default planetary barcode (auto height)'
    text: '```csharp using Aspose.Barcode; using Aspose.Barcode.Generation;'
  - name: 'Example 2: Planet barcode with a custom 100‑pixel bar height'
    text: 'Sometimes you need a taller barcode for a specific label printer. Here’s
      how to set a **custom barcode height**:'
  - name: 'Example 3: RM4SCC barcode with a custom 100‑pixel bar height'
    text: 'The Planet format isn’t the only postal symbology you might encounter.
      Let’s **customize postal barcode** for RM4SCC, which is popular in the UK and
      parts of Europe:'
  type: HowTo
tags:
- barcode
- C#
- planetary barcode
title: 在 C# 中建立行星條碼 – 完整程式設計指南
url: /zh-hant/python-java/general/create-planetary-barcode-in-c-complete-programming-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 C# 中建立行星條碼 – 完整程式指南

是否曾經需要**建立行星條碼**卻不確定要調整哪些屬性？你並不孤單；Planet 符號系統在實際看到之前可能會顯得有點神祕。在本指南中，我們將**產生 planet 條碼**物件、調整**自訂條碼高度**，最後**匯出條碼影像**檔案，讓它能在任何郵件工作流程中使用。

可以把行星條碼想像成郵政服務版的 QR Code——緊湊、機器可讀且出乎意料地彈性。完成本教學後，你將能夠**自訂郵件條碼**設定，而不必在無盡的 API 文件中搜尋，並且會擁有三段可直接放入專案的可執行程式碼片段。

---

## 前置條件 – 開始前需要的項目

| 需求 | 重要原因 |
|------|----------|
| .NET 6.0 or later | 現代執行環境，完整支援 Aspose.Barcode |
| Visual Studio 2022 (or any C# IDE) | 方便的除錯與 IntelliSense |
| **Aspose.Barcode for .NET** NuGet package | 提供 `BarcodeGenerator`、`EncodeTypes` 以及影像格式 |
| Write access to a folder on disk | `Save` 呼叫所需，以**匯出條碼影像** |

你可以透過套件管理員主控台加入此函式庫：

```powershell
Install-Package Aspose.Barcode
```

就是這樣——不需要額外的 DLL，也不需要外部服務。準備好了嗎？讓我們開始吧。

---

## 建立行星條碼 – 步驟說明

以下我們將逐步說明三個實用範例：

1. **預設高度行星條碼**（自動調整）
2. **具有自訂 100 像素條高的 Planet 條碼**
3. **具有自訂高度的 RM4SCC 條碼**（示範如何在 Planet 之外**自訂郵件條碼**）

每個範例皆以先前的程式碼為基礎，請隨意將整段程式碼複製貼上到新的 Console 應用程式中執行。

### 範例 1：預設行星條碼（自動高度）

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a generator for the Planet symbology and supply the data to encode
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Step 2: Define the module (X) size – 4 pixels per bar
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Step 3: Render the barcode to a PNG file (this will **export barcode image**)
        gen.Save(@"C:\Barcodes\PostalPlanetAuto.png", BarCodeImageFormat.Png);
    }
}
```

**剛剛發生了什麼？**  
`BarcodeGenerator` 是你的入口點；你告訴它*產生什麼*（Planet）以及*使用哪筆資料*（`"123456"`）。X‑dimension 控制每根條的寬度，因為我們沒有設定高度，函式庫會自動選擇符合郵件標準的合理尺寸。執行程式後，你會在 `C:\Barcodes` 中找到名為 **PostalPlanetAuto.png** 的 PNG 檔案。

> **專業提示：** 若你正在除錯，請使用任何影像檢視器開啟 PNG——留意條碼的線條清晰且間距均勻。這是可靠**產生 planet 條碼**操作的基礎。

### 範例 2：具有自訂 100 像素條高的 Planet 條碼

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Initialise the generator with the same data
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Override the default bar height to 100 pixels
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Save the customised barcode image
        gen.Save(@"C:\Barcodes\PostalPlanetHeight100.png", BarCodeImageFormat.Png);
    }
}
```

**為何要調整高度？**  
較高的條紋可以提升低解析度印表機的掃描可靠性，且部分郵政服務明確要求最低高度。透過調整 `BarHeight.Pixels`，我們在保持對符號視覺重量的完整控制的同時，仍能在底層**產生 planet 條碼**。

### 範例 3：具有自訂 100 像素條高的 RM4SCC 條碼

Planet 格式並非唯一可能遇到的郵件符號。讓我們為在英國及部分歐洲地區常見的 RM4SCC **自訂郵件條碼**：

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

class Program
{
    static void Main()
    {
        // Create a generator for the RM4SCC symbology
        BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.RM4SCC, "123456");

        // Set the X dimension (module width)
        gen.Parameters.Barcode.XDimension.Pixels = 4;

        // Specify a 100‑pixel bar height
        gen.Parameters.Barcode.BarHeight.Pixels = 100;

        // Export the barcode to a PNG file
        gen.Save(@"C:\Barcodes\PostalRM4SCCHeight100.png", BarCodeImageFormat.Png);
    }
}
```

請注意此程式碼與範例 2 幾乎相同——僅 `EncodeTypes` 列舉不同。這正是 Aspose.Barcode 的優點：你可以在不學習新 API 的情況下**自訂郵件條碼**格式。

## 了解關鍵屬性

| 屬性 | 說明 | 常見值 |
|------|------|--------|
| `XDimension.Pixels` | 單一模組（最小條）的寬度 | 大多數印表機為 2‑6 像素 |
| `BarHeight.Pixels` | 最高條的高度（以像素為單位） | 50‑150 像素，視標籤尺寸而定 |
| `EncodeTypes` | 要產生的符號系統（Planet、RM4SCC 等） | `EncodeTypes.Planet`, `EncodeTypes.RM4SCC` |
| `BarCodeImageFormat` | 輸出影像格式 | `.Png`, `.Jpeg`, `.Bmp` |

當你**匯出條碼影像**時，函式庫會將向量資料光柵化為所選格式。PNG 為無損格式，適合高品質標籤。若需較小的檔案供網路使用，可改用 `BarCodeImageFormat.Jpeg` 並調整壓縮率。

## 常見陷阱與避免方法

* **模組寬度不正確** – 將 `XDimension.Pixels` 設得過低會導致列印時條紋合併。請先以實體印表機測試，再進行大量生產。
* **缺少寫入權限** – 若目標資料夾不可寫入，`Save` 方法會拋出例外。請務必確認路徑，或在快速測試時使用 `Path.GetTempPath()`。
* **資料長度錯誤** – Planet 需要 6‑8 位數的數字字串。提供字母字元會導致驗證錯誤。
* **忘記釋放資源** – `BarcodeGenerator` 實作 `IDisposable`。在長時間執行的服務中，請使用 `using` 區塊以釋放原生資源。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(...))
{
    // configure and save...
}
```

## 預期輸出 – 你應該看到的結果

執行完三個範例後，`C:\Barcodes` 資料夾將包含以下檔案：

| 檔案 | 說明 |
|------|------|
| `PostalPlanetAuto.png` | 預設高度 Planet 條碼（自動調整） |
| `PostalPlanetHeight100.png` | 具有 **自訂條碼高度** 100 像素的 Planet 條碼 |
| `PostalRM4SCCHeight100.png` | RM4SCC 條碼，同樣 **自訂條碼高度** 100 像素 |

開啟任一 PNG，你會看到整齊的垂直條紋，且數字資料已編碼於條碼下方（或上方，視符號而定）。使用智慧手機條碼掃描應用程式掃描——若應用程式辨識出 “123456”，即表示你已成功**建立行星條碼**並**匯出條碼影像**。

## 更進一步 – 後續步驟與相關主題

* **批次產生** – 迭代 CSV 中的郵遞區號清單，並自動儲存每個條碼。
* **嵌入 PDF** – 使用 Aspose.PDF 的 `PdfDocument` 將 PNG 直接放置於運送標籤上。
* **動態尺寸** – 根據標籤 DPI 計算 `BarHeight.Pixels`，以確保實體尺寸一致。
* **其他郵件符號** – 探索 `EncodeTypes.Postnet`、`EncodeTypes.USPSIntelligentMail` 或 `EncodeTypes.Aztec` 以擴大支援範圍。

若你對 **自訂條碼高度** 計算方式感到好奇，請參閱官方 Aspose.Barcode 文件中關於 *模組尺寸* 的說明——公式簡單，且適用於所有支援的符號系統。

## 結論

我們已完整示範了在 C# 中**建立行星條碼**影像的實作流程。從簡易產生器開始，我們學會了如何**產生 planet 條碼**、套用**自訂條碼高度**，最後**匯出條碼影像**檔案以符合郵件標準。只要微調少數屬性，即可**自訂郵件條碼**，例如 RM4SCC 或其他支援的格式。

試試看吧：更改資料字串、嘗試不同的 `XDimension` 值，或將 PNG 換成 JPEG。此函式庫足夠彈性，能因應大多數實務情境，且你已擁有堅實的基礎可供延伸。

有任何問題或想分享自己的條碼技巧嗎？在下方留言吧，祝開發愉快！

## 接下來該學什麼？

以下教學涵蓋與本指南緊密相關的主題，並以此為基礎。每個資源皆提供完整可執行的程式碼範例與逐步說明，協助你精通更多 API 功能，並在自己的專案中探索其他實作方式。

- [建立條碼自訂高度 – 一維條碼](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/)
- [如何使用 Aspose.BarCode for .NET 產生具有自訂長寬比的 Aztec 條碼](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [建立條碼影像 C# – GS1 DataMatrix 範例](/barcode/english/net/gs1-barcode-encoding/gs1-datamatrix-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}