---
date: 2026-06-29
description: 了解如何使用 Aspose.BarCode for .NET 調整 Codablock F 條碼尺寸，並控制條碼的寬高比例。適用於庫存追蹤與產品標籤生成。
keywords:
- adjust barcode size
- barcode width height ratio
- barcode for inventory tracking
- barcode generation .net core
- save barcode image
linktitle: Codablock F 長寬比自訂
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to adjust barcode size and control the barcode width height
    ratio for Codablock F using Aspose.BarCode for .NET. Ideal for inventory tracking
    and product label generation.
  headline: How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode
    for .NET
  type: TechArticle
- description: Learn how to adjust barcode size and control the barcode width height
    ratio for Codablock F using Aspose.BarCode for .NET. Ideal for inventory tracking
    and product label generation.
  name: How to Adjust Barcode Size – Codablock F Aspect Ratio with Aspose.BarCode
    for .NET
  steps:
  - name: '**.NET Development Environment** – a working .NET setup on your machine.'
    text: '**.NET Development Environment** – a working .NET setup on your machine.'
  - name: '**Aspose.BarCode for .NET** – download and install it from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – download and install it from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# Knowledge** – you should be comfortable with C# syntax and Visual
      Studio (or any other IDE).'
    text: '**Basic C# Knowledge** – you should be comfortable with C# syntax and Visual
      Studio (or any other IDE).'
  - name: '**Development IDE** – Visual Studio, Rider, or VS Code will work just fine.'
    text: '**Development IDE** – Visual Studio, Rider, or VS Code will work just fine.'
  type: HowTo
- questions:
  - answer: Absolutely. Aspose.BarCode supports .NET Core, .NET 5, and .NET 6+.
    question: Can I use this code in a .NET Core project?
  - answer: No. The data remains identical; only the visual dimensions of the barcode
      change.
    question: Does changing the aspect ratio affect the encoded data?
  - answer: Start with the default, test with your scanner, then adjust up or down
      until you achieve optimal readability and fit.
    question: How do I choose the right aspect ratio?
  - answer: A temporary license is sufficient for testing; a full license is needed
      for production deployments.
    question: Is a license required for development builds?
  - answer: The official Aspose.BarCode documentation provides extensive code samples
      for size, color, text, and more.
    question: Where can I find more examples of barcode customization?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何調整條碼尺寸 – 使用 Aspose.BarCode for .NET 的 Codablock F 長寬比
url: /zh-hant/net/codablock-f-encoding/codablock-f-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 自訂 Codablock F 長寬比

## 介紹

在本完整教學中，您將學習**如何調整條碼尺寸**，以使用 Aspose.BarCode for .NET 產生 Codablock F 符號。無論您是開發庫存追蹤軟件、產生產品標籤，或是微調掃描器效能，控制條碼的寬高比例都能在不影響資料完整性的前提下，取得像素級的完美結果。

## 快速回答
- **長寬比會影響什麼？** 它決定產生條碼的寬度與高度比例。  
- **哪個屬性控制它？** `BarcodeGenerator.Parameters.Barcode.Codablock.AspectRatio`。  
- **支援的值？** 任意整數；常見選擇有 15、30 等。  
- **需要授權嗎？** 生產環境必須使用臨時或正式授權。  
- **可以在 .NET Core 使用嗎？** 可以 — Aspose.BarCode 支援 .NET Framework、.NET Core 以及 .NET 5/6+。

## 前置條件

在深入 Codablock F 長寬比自訂之前，請確保您已具備以下前置條件：

1. **.NET 開發環境** – 您機器上已安裝可運作的 .NET 環境。  
2. **Aspose.BarCode for .NET** – 從 [here](https://releases.aspose.com/barcode/net/) 下載並安裝。  
3. **基本 C# 知識** – 您應熟悉 C# 語法及 Visual Studio（或其他 IDE）。  
4. **開發 IDE** – Visual Studio、Rider 或 VS Code 都可使用。

現在，讓我們一步一步開始自訂 Codablock F 長寬比。

## 如何調整 Codablock F 條碼尺寸？

載入 `BarcodeGenerator`，將 `Codablock.AspectRatio` 屬性設定為所需的整數，然後呼叫 `Save` —— 這就是改變條碼寬高比例所需的全部。API 會自動更新內部模組尺寸，因此產生的影像會直接反映新尺寸，無需額外的縮放步驟。

## 匯入命名空間

`BarcodeGenerator` 類別是 Aspose.BarCode 的核心物件，用於在記憶體中建立與呈現條碼。請在實例化之前匯入所需的命名空間。

```csharp
using Aspose.BarCode.Generation;
```

## 步驟 1：初始化條碼產生器

`BarcodeGenerator` 是所有條碼操作的入口。建立實例、指定 `CodablockF` 符號，並提供要編碼的資料。

```csharp
string path = "Your Directory Path";

System.Console.WriteLine("CodablockF Aspect Ratio:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.CodablockF, "Aspose");
```

在此程式碼片段中，我們已設定產生器使用 Codablock F 編碼，並以樣本資料 **“Aspose.”** 為例。

## 步驟 2：如何自訂條碼長寬比

`Codablock` 設定中的 `AspectRatio` 屬性定義產生條碼時每個模組的寬高比例。將其設定為整數，即告訴產生器多少個水平單位對應一個垂直單位，直接改變條碼的整體形狀而不影響編碼資料。以下示範兩個實用範例。

```csharp
gen.Parameters.Barcode.Codablock.AspectRatio = 15;
gen.Save($"{path}CodablockFAspectRatio15.png", BarCodeImageFormat.Png);
```

我們將比例設定為 15，並將影像儲存為 **CodablockFAspectRatio15.png**。

### 範例 2 – 長寬比 30

```csharp
gen.Parameters.Barcode.Codablock.AspectRatio = 30;
gen.Save($"{path}CodablockFAspectRatio30.png", BarCodeImageFormat.Png);
```

此處將比例提升至 30，產生較寬的條碼影像。

透過調整 `AspectRatio` 屬性，您可以微調條碼以符合任何標籤尺寸、掃描器需求或設計指引。

## 為什麼要調整長寬比？

變更長寬比會直接影響掃描器的可讀性與標籤排版。較寬的比例（例如 30）有助於偏好水平模組的掃描器偵測，而較低的比例（例如 15）則可在緊湊標籤上節省垂直空間。請選擇在可讀性與包裝實體限制之間取得平衡的值。

## 常見陷阱與技巧

- **技巧：** 更改比例後，務必使用目標掃描器硬體測試產生的條碼。  
- **陷阱：** 設定極端比例（例如 1 或 100）可能導致條碼無法辨識。除非有特定需求，否則請使用適中的值。  
- **技巧：** 使用 `gen.Save` 輸出 PNG 以獲得無損品質；JPEG 可能產生壓縮雜訊，影響掃描。

## 結論

恭喜！您現在已了解如何使用 Aspose.BarCode for .NET **調整 Codablock F 條碼尺寸**。只需幾行程式碼，即可產生完美符合應用視覺與功能需求的條碼——無論是庫存管理、產品標籤或其他情境。

如有任何問題、遇到困難，或想探索更多條碼功能，歡迎造訪 [Aspose.BarCode 文件](https://reference.aspose.com/barcode/net/) 或加入 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 取得支援。

## 常見問題

**問：我可以在 .NET Core 專案中使用此程式碼嗎？**  
**答：** 當然可以。Aspose.BarCode 支援 .NET Core、.NET 5 以及 .NET 6+。

**問：變更長寬比會影響編碼資料嗎？**  
**答：** 不會。資料保持不變，僅條碼的視覺尺寸會改變。

**問：如何選擇合適的長寬比？**  
**答：** 先使用預設值，使用您的掃描器測試，然後上下調整，直至達到最佳可讀性與適配度。

**問：開發版是否需要授權？**  
**答：** 測試時臨時授權即可，正式部署則需完整授權。

**問：在哪裡可以找到更多條碼自訂範例？**  
**答：** 官方 Aspose.BarCode 文件提供大量關於尺寸、顏色、文字等的程式碼範例。

---

**最後更新：** 2026-06-29  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose

## 相關教學

- [如何自訂條碼 - 使用 Aspose.BarCode 進行 Codablock F 編碼](/barcode/net/codablock-f-encoding/)
- [如何使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [使用 Aspose.BarCode for .NET 自訂 DotCode 長寬比](/barcode/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}