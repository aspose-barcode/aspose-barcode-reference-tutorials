---
category: general
date: 2026-07-18
description: 如何使用 Aspose.BarCode 設定 PDF417 條碼的錯誤等級。學習在幾分鐘內產生帶自訂文字的 PDF417 條碼並微調錯誤更正。
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set error
- generate pdf417 barcode
- how to generate pdf417
- barcode with custom text
language: zh-hant
lastmod: 2026-07-18
og_description: 快速設定 PDF417 條碼的錯誤層級。本教學將指引您生成帶有自訂文字及不同錯誤更正層級的 PDF417 條碼。
og_image_alt: how to set error level in PDF417 barcode example
og_title: 如何設定 PDF417 條碼的錯誤等級 – 步驟說明
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  headline: How to Set Error Level in PDF417 Barcode – Complete Guide
  type: TechArticle
- description: how to set error level in PDF417 barcode using Aspose.BarCode. Learn
    to generate PDF417 barcode with custom text and tweak error correction in minutes.
  name: How to Set Error Level in PDF417 Barcode – Complete Guide
  steps:
  - name: What if my text contains line breaks?
    text: 'PDF417 automatically encodes line‑feed (`

      `) characters. Just include them in the string:'
  - name: Can I use a different image format?
    text: Absolutely. Replace `BarCodeImageFormat.Png` with `Jpeg`, `Bmp`, or `Svg`
      depending on your downstream workflow.
  - name: Does changing the X‑dimension affect error correction?
    text: Indirectly, yes. A larger X‑dimension yields bigger modules, which can improve
      scanning reliability but does **not** alter the logical error‑correction level.
      Adjust both parameters independently for best results.
  - name: How to generate PDF417 barcode in a web API?
    text: Wrap the same code in an ASP.NET Core controller and stream the PNG back
      as a `FileResult`. The core logic stays unchanged, which means **how to generate
      PDF417** remains consistent across desktop and web environments.
  type: HowTo
tags:
- PDF417
- barcode
- error correction
title: 如何設定 PDF417 條碼的錯誤等級 – 完整指南
url: /zh-hant/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 PDF417 條碼設定錯誤等級 – 完整指南

有沒有想過 **如何設定錯誤**，在產生 PDF417 條碼時？你並不孤單——大多數開發者在需要更強韌的條碼以應付惡劣環境時，都會碰到這個問題。好消息是：使用 Aspose.BarCode 調整錯誤更正等級非常簡單，同時你還會學會 **如何產生 PDF417** 並自訂文字內容。

在本教學中，我們將一步步說明，從建立帶有特殊字元的條碼產生器，到儲存兩個展示不同錯誤更正等級的 PNG 檔案。完成後，你將能熟練 **產生 PDF417 條碼**、調整 X‑dimension、欄位數量，以及最重要的 **設定錯誤** 等級，以符合你的使用情境。

## 前置條件

- .NET 6.0 或更新版本（此程式碼亦可於 .NET Framework 使用）
- 已安裝 Aspose.BarCode for .NET（透過 NuGet 執行 `Install-Package Aspose.BarCode`）
- 磁碟上有可寫入影像的資料夾（請將範例中的 `YOUR_DIRECTORY/` 替換為實際路徑）
- 基本的 C# 知識——只要寫過一次 `Console.WriteLine` 就足夠

> **專業小技巧：** 若你的目標是行動裝置掃描，建議使用較高的錯誤等級（Level 5），以抵抗污垢、刮痕或低光環境。

## 第一步：建立帶有自訂文字的條碼產生器

首先，你需要一個 `BarcodeGenerator` 實例，告訴它要產生 **PDF417 條碼**，並攜帶你想編碼的文字。留意範例中使用了重音字元與版權符號——這證明產生器能直接處理 Unicode。

```csharp
using Aspose.BarCode.Generation;

// Step 1: Create a PDF417 barcode generator with the desired text
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, "Åspóse.Barcóde©");
```

*為什麼這很重要：* `EncodeTypes.Pdf417` 旗標告訴 Aspose 你正在處理 2‑D 堆疊條碼，而字串參數則成為資料負載。若省略此步，最終會得到預設的 Code128 條碼，而非你需要的高容量 PDF417。

## 第二步：微調視覺參數

PDF417 條碼不只是資料，亦是一種視覺圖樣。調整 **X‑dimension**（最小條寬）與 **欄位數量**，即可控制條碼的實體尺寸與可讀性。

```csharp
// Step 2: Adjust visual parameters – set the X‑dimension and number of columns
generator.Parameters.Barcode.XDimension.Pixels = 2;   // each module is 2 pixels wide
generator.Parameters.Barcode.Pdf417.Columns = 3;    // three columns across the page
```

*為什麼這很重要：* 較小的 X‑dimension 會產生更緊湊的影像，但在低解析度掃描器上可能變得難以辨識。三欄的設定則在大多數標籤尺寸下提供平衡的長寬比。

## 第三步：設定錯誤更正等級為 2 並儲存

錯誤更正是 **如何設定錯誤** 的核心。`Pdf417ErrorLevel` 列舉從 `Level0`（無額外資料）到 `Level5`（最高冗餘）不等。此處我們從 **Level 2** 開始，提供適度的錯誤韌性，同時不會讓影像過大。

```csharp
// Define the output folder (replace with your actual path)
string outputFolder = "YOUR_DIRECTORY/";

// Step 3: Set error correction level to 2 and save the image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level2;
generator.Save($"{outputFolder}Pdf417ErrorLevel2.png", BarCodeImageFormat.Png);
```

執行此程式碼後，你會在資料夾中看到 `Pdf417ErrorLevel2.png`。打開它，你應該會看到一個乾淨的三欄條碼，且仍保有相當的冗餘資訊。

## 第四步：提升錯誤更正至 Level 5 再次儲存

有時條碼需要抵禦更激烈的損壞——例如倉庫地板上標籤被磨損的情況。切換至 **Level 5** 會在稍微增大影像尺寸的代價下，最大化錯誤更正。

```csharp
// Step 4: Change error correction level to 5 and save the second image
generator.Parameters.Barcode.Pdf417.ErrorLevel = Pdf417ErrorLevel.Level5;
generator.Save($"{outputFolder}Pdf417ErrorLevel5.png", BarCodeImageFormat.Png);
```

現在你會同時擁有兩個 PNG 檔案：一個具中等錯誤更正，另一個則是最高等級。比較兩者，你會發現 Level 5 版本的暗模組較多，這正是演算法為保護資料所加入的。

![如何在 PDF417 條碼設定錯誤等級範例](image.png)

*圖片說明（alt text）：如何在 PDF417 條碼設定錯誤等級範例 – 顯示兩個具有不同錯誤更正等級的 PNG 檔案。*

## 預期輸出

| 檔案名稱                     | 錯誤等級 | 近似尺寸 (px) |
|-----------------------------|----------|----------------|
| `Pdf417ErrorLevel2.png`     | Level 2  | 150 × 80       |
| `Pdf417ErrorLevel5.png`     | Level 5  | 180 × 95       |

兩張影像皆編碼字串 **“Åspóse.Barcóde©”**，可使用任何標準 PDF417 讀取器（如 ZXing、Scandit）掃描。Level 5 影像可容忍約 30 % 的損壞，而 Level 2 約 15 %。

## 常見問題與邊緣案例

### 若文字中包含換行符號怎麼辦？
PDF417 會自動編碼換行 (`\n`) 字元。只要在字串中加入即可：

```csharp
new BarcodeGenerator(EncodeTypes.Pdf417, "Line1\nLine2\nLine3");
```

### 可以使用其他影像格式嗎？
當然可以。將 `BarCodeImageFormat.Png` 替換為 `Jpeg`、`Bmp` 或 `Svg`，依照下游工作流程選擇。

### 改變 X‑dimension 會影響錯誤更正嗎？
間接會有影響。較大的 X‑dimension 產生較大的模組，能提升掃描可靠性，但 **不會** 改變邏輯上的錯誤更正等級。建議兩個參數分別調整，以取得最佳效果。

### 如何在 Web API 中產生 PDF417 條碼？
只要把相同程式碼包在 ASP.NET Core 控制器裡，並以 `FileResult` 回傳 PNG 串流即可。核心邏輯保持不變，亦即 **如何產生 PDF417** 在桌面與 Web 環境中皆一致。

## 重點回顧

我們已說明 **如何設定錯誤** 於 PDF417 條碼，示範 **如何產生 PDF417** 並使用自訂 Unicode 文字，並教你如何微調 X‑dimension 與欄位數。只要將 `Pdf417ErrorLevel.Level2` 換成 `Level5`，即可在影像大小與韌性之間取得平衡。

## 後續步驟

- 嘗試 **帶有自訂文字的條碼**，內容可包含 URL 或商品編號。
- 調整欄位數 (`generator.Parameters.Barcode.Pdf417.Columns = 5`) 觀察形狀變化。
- 在同一文件中結合 PDF417 與其他條碼類型，打造多模態掃描解決方案。
- 深入閱讀 Aspose 的[官方文件](https://docs.aspose.com/barcode/net/)，了解如 macro PDF417 或 compact mode 等進階功能。

如有任何問題或想分享掃描結果，歡迎留言。祝你條碼開發順利！

## 接下來該學什麼？

以下教學與本指南緊密相關，能進一步擴展你在本篇示範中學到的技巧。每篇資源皆提供完整可執行的程式碼範例與逐步說明，協助你掌握更多 API 功能，並在自己的專案中探索其他實作方式。

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to create Aztec barcode with error correction in .NET](/barcode/english/net/aztec-barcode-encoding/aztec-error-level-example/)
- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}