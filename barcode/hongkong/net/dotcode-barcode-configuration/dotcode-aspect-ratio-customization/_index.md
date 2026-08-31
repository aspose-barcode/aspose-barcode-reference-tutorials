---
date: 2026-06-14
description: 了解如何使用 Aspose.BarCode for .NET 建立 DotCode 條碼 .NET 並自訂其長寬比。
keywords:
- create dotcode barcode .net
- dotcode aspect ratio
- aspose barcode .net
- barcode customization
- .net barcode generation
linktitle: DotCode 長寬比自訂
schemas:
- author: Aspose
  dateModified: '2026-06-14'
  description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  headline: Create DotCode Barcode .NET – Customize Aspect Ratio
  type: TechArticle
- description: Learn how to create DotCode barcode .NET and customize its aspect ratio
    using Aspose.BarCode for .NET.
  name: Create DotCode Barcode .NET – Customize Aspect Ratio
  steps:
  - name: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download the library from the official site [here](https://releases.aspose.com/barcode/net/).'
  - name: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
    text: '**IDE** – Visual Studio, Rider, or any .NET‑compatible editor.'
  - name: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
    text: '**Output folder** – replace “Your Directory Path” in the sample with a
      real folder on your machine.'
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode supports DotCode out‑of‑the‑box.
    question: Can I generate DotCode barcodes in .NET?
  - answer: The `AspectRatio` property of `BarcodeGenerator`.
    question: Which property controls the shape?
  - answer: A commercial license is required; a free trial works for development.
    question: Do I need a license for production?
  - answer: .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
    question: Supported .NET versions?
  - answer: Less than a second for a typical 200 × 200 pixel barcode.
    question: How long does the code take to run?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 建立 DotCode 條碼 .NET – 自訂長寬比
url: /zh-hant/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 DotCode 條碼 .NET – 自訂長寬比

如果您需要 **create DotCode barcode .NET** 解決方案以適應狹小空間或特定佈局需求，Aspose.BarCode for .NET 為您提供完整控制。在本教學中，我們將逐步說明產生 DotCode 條碼並調整其長寬比的整個過程，讓它在包裝、標籤或行動螢幕上呈現出您想要的樣子。  

## 快速解答
- **我可以在 .NET 中產生 DotCode 條碼嗎？** 是的，Aspose.BarCode 內建支援 DotCode。  
- **哪個屬性控制形狀？** The `AspectRatio` property of `BarcodeGenerator`.  
- **我需要商業授權才能投入生產嗎？** A commercial license is required; a free trial works for development.  
- **支援的 .NET 版本？** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.  
- **程式執行需要多久？** Less than a second for a typical 200 × 200 pixel barcode.

## 本教學的主要目標是什麼？
本教學旨在示範如何使用 Aspose.BarCode for .NET 產生 DotCode 條碼，並調整其長寬比以符合特定佈局限制。透過本步驟，您將學會設定產生器、修改尺寸參數，並以常見格式匯出影像。

## 如何在 .NET 中建立 DotCode 條碼？
在 .NET 中建立 DotCode 條碼，只需以 `EncodeTypes.DotCode` 和欲編碼的資料實例化 `BarcodeGenerator`。接著設定 X‑Dimension 與 AspectRatio 屬性以控制大小與形狀，最後呼叫 `Save` 方法將影像寫入指定格式的檔案。

## 前置條件

1. **Aspose.BarCode for .NET** – 從官方網站 [here](https://releases.aspose.com/barcode/net/) 下載程式庫。  
2. **IDE** – Visual Studio、Rider，或任何相容 .NET 的編輯器。  
3. **Output folder** – 在範例中將 “Your Directory Path” 替換為您機器上的實際資料夾路徑。

## 匯入命名空間

`Aspose.BarCode.Generation` 提供在 .NET 中產生與設定條碼所需的類別。  
```csharp
using Aspose.BarCode.Generation;
```

## 步驟 1：初始化條碼產生器

`BarcodeGenerator` 是根據指定的條碼類型與資料建立條碼影像的主要類別。  
```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Your code goes here
}
```

## 步驟 2：設定條碼的 X‑Dimension（大小）

`XDimension` 定義單一模組（點）在像素上的寬度，會影響條碼的整體尺寸。  
```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

## 步驟 3：自訂長寬比

`AspectRatio` 設定每個模組的高寬比例，讓您可以垂直拉伸或壓縮條碼。  
```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

## 步驟 4：儲存條碼影像

`Save` 將產生的條碼寫入檔案，支援 PNG、JPEG 等影像格式。  
```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## 為何使用 Aspose.BarCode 進行 DotCode 客製化？
Aspose.BarCode 提供完整的 DotCode 產生功能，包括高解析度輸出、廣泛的格式支援，以及對條碼尺寸（如長寬比）的精細控制。它可在所有主要 .NET 平台上執行，無需外部相依性，且渲染效能快速，適用於桌面與 Web 應用程式。

## 常見使用情境

- **Healthcare**: Compact patient‑ID tags that need to fit on small wristbands.  
- **Postal Services**: Wide‑format shipping labels where a lower height improves scan reliability.  
- **Manufacturing**: Inline labeling of parts where space constraints demand a custom aspect ratio.

## 常見問與答

**Q:** DotCode 條碼的長寬比是什麼？  
**A:** 它是模組高度與寬度的比例；調整此比例會改變條碼的整體形狀。

**Q:** 哪些產業最能受惠於 DotCode 條碼？  
**A:** 醫療、郵政服務與製造業常使用 DotCode 以實現緊湊且高密度的資料編碼。

**Q:** 我可以在 Aspose.BarCode for .NET 中自訂其他 DotCode 參數嗎？  
**A:** 當然可以。您可以修改錯誤更正等級、前景/背景顏色，甚至嵌入商標。

**Q:** Aspose.BarCode 是否適用於 Web 與桌面 .NET 應用程式？  
**A:** 是的，該程式庫可在 ASP.NET、WPF、WinForms 以及主控台應用程式中無縫運作。

**Q:** 我可以在哪裡找到更多文件與範例？  
**A:** 詳細的 API 參考與程式碼範例可於 [here](https://reference.aspose.com/barcode/net/) 取得。

---

**最後更新：** 2026-06-14  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose

## 相關教學

- [DotCode Extended Code Text Configuration with Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/)
- [DotCode Structured Append Mode Configuration with Aspose.BarCode for .NET](/barcode/net/dotcode-barcode-configuration/dotcode-structured-append-mode-configuration/)
- [Create DotCode barcode image – rows & columns (Aspose.BarCode)](/barcode/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}

{{< blocks/products/products-backtop-button >}}

{{< /blocks/products/pf/main-wrap-class >}}