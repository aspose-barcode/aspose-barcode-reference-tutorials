---
date: 2026-09-28
description: 了解如何使用 Aspose.BarCode for .NET 為 GS1 優惠券建立條碼自訂空間，提升條碼可讀性。請依照我們的逐步指南操作。
keywords:
- create barcode custom space
- GS1 coupon supplement
- Aspose.BarCode .NET
- increase barcode readability
lastmod: 2026-09-28
linktitle: GS1 優惠券補充空間設定
og_description: 了解如何使用 Aspose.BarCode for .NET 為 GS1 優惠券建立條碼自訂空間，提升條碼可讀性。內含逐步程式碼與技巧說明。
og_image_alt: Screenshot of a GS1 coupon barcode generated with custom supplement
  space using Aspose.BarCode for .NET
og_title: 為 GS1 優惠券補充建立條碼自訂空間 – Aspose.BarCode .NET
schemas:
- author: Aspose
  dateModified: '2026-09-28'
  description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  headline: How to create barcode custom space for GS1 coupon supplement
  type: TechArticle
- description: Learn how to create barcode custom space for GS1 coupons with Aspose.BarCode
    for .NET and increase barcode readability. Follow our step‑by‑step guide.
  name: How to create barcode custom space for GS1 coupon supplement
  steps:
  - name: '**Visual Studio** – The primary IDE for .NET development.'
    text: '**Visual Studio** – The primary IDE for .NET development.'
  - name: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the library from the [Aspose.BarCode
      for .NET documentation](https://reference.aspose.com/barcode/net/).'
  - name: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
    text: '**.NET Framework or .NET 5+** – Familiarity with C# and the .NET runtime
      is required.'
  - name: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
    text: '**Create** a `BarcodeGenerator` instance for the `UpcaGs1DatabarCoupon`
      type.'
  - name: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
    text: '**Set** the X‑dimension to 2 pixels, which determines the narrowest bar
      width.'
  - name: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
    text: '**Adjust** the `SupplementSpace.Pixels` property to 30 px, generate an
      image, then repeat with 50 px.'
  type: HowTo
- questions:
  - answer: It adds a mandatory blank margin around the supplemental data, improving
      scanner reliability and meeting retailer‑specified minimum widths.
    question: What is the purpose of the GS1 Coupon Supplement Space in barcodes?
  - answer: Yes, set `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` to any
      integer value; the library instantly applies the change to the generated image.
    question: Can I customize the width of the GS1 Coupon Supplement Space with Aspose.BarCode
      for .NET?
  - answer: Refer to the [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)
      and visit the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      for community assistance.
    question: Where can I find additional documentation and support for Aspose.BarCode
      for .NET?
  - answer: Absolutely. The API offers straightforward methods for quick tasks and
      advanced options for fine‑tuned barcode generation.
    question: Is Aspose.BarCode for .NET suitable for both beginners and experienced
      developers?
  - answer: Yes, request a trial license from the [Aspose temporary license website](https://purchase.aspose.com/temporary-license/).
    question: Can I obtain a temporary license for Aspose.BarCode for .NET to evaluate
      its features?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- barcode configuration
- GS1 standards
- Aspose.BarCode
- .NET barcode generation
title: 如何為 GS1 優惠券補充建立條碼自訂空間
url: /zh-hant/net/gs1-barcode-encoding/gs1-coupon-supplement-space-configuration/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 優惠券補充空間設定

在本教學中，您將使用 Aspose.BarCode for .NET **建立條碼自訂空間** 於 GS1 優惠券補充空間。調整補充空間在需要於低解析度掃描器上 **提升條碼可讀性** 或遵守零售商規定的邊距時至關重要。完成本指南後，您將了解補充空間的重要性、如何以程式方式設定，以及如何產生不同像素值的影像。

## 快速解答
- **補充空間控制什麼？** 它定義了優惠券資料與條碼其餘部分之間的空白區域（以像素為單位）。  
- **使用哪種條碼類型？** `EncodeTypes.UpcaGs1DatabarCoupon`。  
- **我可以更改空間大小嗎？** 可以 – 將 `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` 設為任意整數值。  
- **此功能需要授權嗎？** 臨時授權可用於評估；正式使用需購買完整授權。  
- **支援哪些輸出格式？** PNG、JPEG、BMP、GIF、TIFF 等，透過 `BarCodeImageFormat` 可取得更多格式。  

## 什麼是 GS1 優惠券補充空間？
GS1 優惠券補充空間是出現在 GS1‑Databar 優惠券條碼中的一個固定空白區域。零售系統利用此空間提升掃描可靠性，並符合業界規範對補充資料周圍最小邊距的要求。

## 為何要設定補充空間？
補充空間直接 **提升條碼可讀性**，並協助您符合嚴格的零售商指引。透過增加額外像素，可降低低解析度掃描器的誤讀機率，確保在不同標籤尺寸下的掃描一致性，並提供在印刷版面中平衡條碼的視覺彈性。

## 前置條件

在使用 Aspose.BarCode for .NET 設定 GS1 優惠券補充空間之前，請確保您具備以下條件：

1. **Visual Studio** – .NET 開發的主要 IDE。  
2. **Aspose.BarCode for .NET** – 從 [Aspose.BarCode for .NET 文件說明](https://reference.aspose.com/barcode/net/) 下載此函式庫。  
3. **.NET Framework 或 .NET 5+** – 需要熟悉 C# 與 .NET 執行環境。  

環境就緒後，讓我們繼續實作。

## 匯入命名空間

`Aspose.BarCode.Generation` 命名空間包含 `BarcodeGenerator` 類別及相關設定。

```csharp
using Aspose.BarCode;
```

## 步驟 1：定義路徑

選擇一個用於儲存產生影像的資料夾。路徑必須以符合您作業系統的目錄分隔符結尾。

```csharp
string path = "Your Directory Path";
```

## 步驟 2：產生 GS1 優惠券補充空間設定

以下程式碼片段會建立條碼、設定 X‑dimension，並調整補充空間。

```csharp
System.Console.WriteLine("Gs1CouponSupplementSpace:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Set coupon supplement space to 30 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 30;
gen.Save($"{path}Gs1CouponSpace30Pixels.png", BarCodeImageFormat.Png);

// Set coupon supplement space to 50 pixels
gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels = 50;
gen.Save($"{path}Gs1CouponSpace50Pixels.png", BarCodeImageFormat.Png);
```

在此範例中，我們會：

1. **建立** `UpcaGs1DatabarCoupon` 類型的 `BarcodeGenerator` 實例。  
2. **設定** X‑dimension 為 2 像素，決定最窄條寬。  
3. **調整** `SupplementSpace.Pixels` 屬性為 30 像素，產生影像，然後以 50 像素重複一次。  

歡迎自行嘗試其他像素值，以符合您的列印工作流程。

## 常見問題與技巧

- **路徑無效** – 確認 `path` 變數以符合您作業系統的反斜線 (`\`) 或斜線 (`/`) 結尾。  
- **權限不足** – 以系統管理員身分執行 Visual Studio，或選擇應用程式具有寫入權限的資料夾。  
- **資料格式不正確** – 資料字串必須符合 GS1 語法（`(8110)` 代表補充識別碼）。  

## 為何這對您的業務重要

Aspose.BarCode 支援 **超過 60 種條碼符號**，且可渲染最高達 **10,000 × 10,000 像素** 的影像而不會耗盡記憶體。對於大規模零售部署而言，這表示您可以在批次模式下產生高解析度的 GS1 優惠券，同時在一般伺服器硬體上每張影像的處理時間維持在一秒以內。

## 常見問答

**Q: 條碼中的 GS1 優惠券補充空間有何用途？**  
A: 它在補充資料周圍添加必須的空白邊距，提升掃描器的可靠性，並符合零售商規定的最小寬度。

**Q: 我可以使用 Aspose.BarCode for .NET 自訂 GS1 優惠券補充空間的寬度嗎？**  
A: 可以，將 `gen.Parameters.Barcode.Coupon.SupplementSpace.Pixels` 設為任意整數值；函式庫會立即將變更套用至產生的影像。

**Q: 我在哪裡可以找到 Aspose.BarCode for .NET 的其他文件與支援？**  
A: 請參考 [Aspose.BarCode for .NET 文件說明](https://reference.aspose.com/barcode/net/) 並前往 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 取得社群協助。

**Q: Aspose.BarCode for .NET 是否適合新手與有經驗的開發者？**  
A: 絕對適合。API 提供簡易的方法以快速完成任務，同時也有進階選項供精細調整條碼產生。

**Q: 我可以取得 Aspose.BarCode for .NET 的臨時授權以評估其功能嗎？**  
A: 可以，請從 [Aspose 臨時授權網站](https://purchase.aspose.com/temporary-license/) 申請試用授權。

## 結論

依照上述步驟，您現在已了解如何 **建立條碼自訂空間** 於 GS1 優惠券補充空間，這是 **提升條碼可讀性** 並符合零售標準的關鍵技巧。將程式碼整合至您現有的掃描解決方案，嘗試不同的像素值，並探索 Aspose.BarCode for .NET 所提供的其他條碼類型。

---

**最後更新：** 2026-09-28  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相關教學

- [使用 .NET API 產生 Aspose.BarCode Databar 條碼 – 行與列設定](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/)
- [使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 – 步驟指南](/barcode/net/datamatrix-barcode-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}