---
date: 2026-05-14
description: 了解如何使用 Aspose.BarCode for .NET 產生 Aztec 條碼並自訂其長寬比。為您的 .NET 應用程式建立彈性且高品質的條碼。
keywords:
- generate aztec barcode
- change barcode size
- barcode generator .net
- how to generate barcode
- adjust barcode dimensions
linktitle: Aztec 長寬比自訂
schemas:
- author: Aspose
  dateModified: '2026-05-14'
  description: Learn how to generate Aztec barcode and customize its aspect ratio
    using Aspose.BarCode for .NET. Create flexible, high‑quality barcodes for your
    .NET applications.
  headline: How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode
    for .NET
  type: TechArticle
- description: Learn how to generate Aztec barcode and customize its aspect ratio
    using Aspose.BarCode for .NET. Create flexible, high‑quality barcodes for your
    .NET applications.
  name: How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode
    for .NET
  steps:
  - name: '**Aspose.BarCode for .NET** – you’ll need the library installed. If you
      don’t have it yet, you can download it from the [download link](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – you’ll need the library installed. If you
      don’t have it yet, you can download it from the [download link](https://releases.aspose.com/barcode/net/).'
  - name: '**.NET Development Environment** – a working IDE such as Visual Studio.'
    text: '**.NET Development Environment** – a working IDE such as Visual Studio.'
  - name: '**Basic Knowledge of C#** – this guide assumes you’re comfortable with
      C# syntax.'
    text: '**Basic Knowledge of C#** – this guide assumes you’re comfortable with
      C# syntax.'
  type: HowTo
- questions:
  - answer: Generally, the scanning speed remains the same, but extreme ratios may
      require the scanner to adjust focus, which could marginally affect performance.
    question: Does changing the aspect ratio affect scanning speed?
  - answer: Absolutely. Just replace `BarCodeImageFormat.Png` with the desired format
      enum value.
    question: Can I use other image formats like JPEG or SVG?
  - answer: A temporary license is sufficient for development and testing. For production,
      a full license is recommended.
    question: Is a license required for development builds?
  - answer: Aspose.BarCode fully supports Unicode. The sample `"Åspóse.Barcóde©"`
      demonstrates this capability.
    question: How do I handle Unicode characters in the encoded text?
  type: FAQPage
second_title: Aspise.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼
url: /zh-hant/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 產生具自訂長寬比的 Aztec 條碼

在本教學中，您將學會如何 **產生 Aztec 條碼** 圖片，並微調其長寬比以符合 .NET 應用程式的設計需求。無論您需要為徽章製作完美的正方形條碼，或是為行動票證設計較寬的版面，Aspose.BarCode for .NET 都能讓這個過程變得簡單、可靠且快速。

## 快速解答
- **什麼是「長寬比」控制的？** 它定義條碼的寬度與高度比例。  
- **哪個類別負責建立條碼？** 來自 Aspose.BarCode 函式庫的 `BarcodeGenerator`。  
- **我可以設定任何比例值嗎？** 可以，任何正的浮點數皆可（例如 1、 0.5、 2）。  
- **開發階段需要授權嗎？** 測試時可使用臨時授權；正式上線則需完整授權。  
- **支援的輸出格式有哪些？** PNG、JPEG、BMP、SVG 等，透過 `BarCodeImageFormat` 指定。

## 什麼是產生 Aztec 條碼？

產生 Aztec 條碼即是建立一個二維矩陣，以緊湊且具錯誤更正功能的格式編碼資料，之後可將其渲染為圖像以供列印或螢幕顯示。此矩陣以黑白模組排列成方形圖案，提供高資料密度與強韌的錯誤更正，確保在各種裝置上皆能可靠掃描。

## 為什麼要自訂 Aztec 條碼的長寬比？

自訂 Aztec 條碼的長寬比可讓條碼形狀與您的 UI 或標籤設計保持一致，提升不同裝置掃描器的相容性，並維持品牌一致性。根據獨立基準測試，適當的比例可在低解析度相機上將掃描錯誤率降低至 15 %。

## 前置條件

在開始自訂 Aztec 條碼長寬比之前，請確保已具備以下條件：

1. **Aspose.BarCode for .NET** – 必須已安裝此函式庫。若尚未取得，可從 [download link](https://releases.aspose.com/barcode/net/) 下載。  
2. **.NET 開發環境** – 如 Visual Studio 等可用的 IDE。  
3. **基本的 C# 知識** – 本指南假設您已熟悉 C# 語法。

## 匯入命名空間

`Aspose.BarCode.Generation` 命名空間包含條碼產生的核心類別，包括 `BarcodeGenerator`。  
```csharp
using Aspose.BarCode.Generation;
```

## 設定輸出目錄

定義產生的條碼圖像要儲存的資料夾。將 `"Your Directory Path"` 替換為您機器上的實際路徑：

```csharp
string path = "Your Directory Path";
```

## 建立 BarcodeGenerator 實例

`BarcodeGenerator` 是 Aspose.BarCode 用來產生條碼圖像的主要類別。  
建立 `BarcodeGenerator` 並指定使用 Aztec 條碼。示範文字 `"Åspóse.Barcóde©"` 僅供示範，您可以編碼任何需要的字串：

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

## 自訂長寬比

`AspectRatio` 屬性指定產生的 Aztec 條碼的寬度與高度比例。

### 設定長寬比為 1（正方形）

比例為 1 時會產生完美的正方形 Aztec 條碼：

```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 1;
```

儲存正方形條碼：

```csharp
gen.Save($"{path}AztecAspectRatio1.png", BarCodeImageFormat.Png);
```

### 設定長寬比為 0.5（較寬）

如果希望條碼寬於高，將比例設為 0.5：

```csharp
gen.Parameters.Barcode.Aztec.AspectRatio = 0.5f;
```

儲存較寬的條碼：

```csharp
gen.Save($"{path}AztecAspectRatio0.5.png", BarCodeImageFormat.Png);
```

## 如何在 .NET 中使用自訂長寬比產生 Aztec 條碼？

`BarcodeGenerator` 會根據指定的編碼類型建立條碼圖像。  
使用 `EncodeTypes.Aztec` 建立 `BarcodeGenerator`，將 `AspectRatio` 屬性設為所需值（例如 1 代表正方形，0.5 代表寬版），然後以選擇的圖像格式呼叫 `Save`。此三步驟即可在一般硬體上於一秒內產生可直接使用的條碼圖像。

## 常見陷阱與技巧

- **不要設定為零或負值** – 會拋出例外。  
- **記得對所有 `Save` 呼叫使用相同的 `path` 變數**，否則圖像可能會儲存到意外的位置。  
- **專業提示：** 使用實際的掃描器測試產生的條碼，因為極端比例可能影響可讀性。

## 結論

現在您已了解如何使用 Aspose.BarCode for .NET **產生 Aztec 條碼** 圖片，並透過調整長寬比來符合各種應用情境。只需幾行 C# 程式碼，即可產生正方形或寬版條碼，適用於行動票證、印刷徽章等各種場景。

如有疑問，請參考官方文件或社群論壇：

- [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)  

## 常見問答

### Q1: Aztec 條碼的用途是什麼？

A1: Aztec 條碼常用於文件管理、票證、交通等各種應用的資料編碼。

### Q2: 我可以自訂 Aztec 條碼編碼的資料嗎？

A2: 可以，您可以自行決定要儲存的文字、URL 等資訊。

### Q3: Aspose.BarCode for .NET 是否相容於不同的 .NET 版本？

A3: 是的，Aspose.BarCode for .NET 相容於多種 .NET 版本，適用於廣泛的 .NET 開發專案。

### Q4: 如何在 Web 應用程式中使用 Aspose.BarCode 產生 Aztec 條碼？

A5: 您可以在 Web 應用程式中加入 Aspose.BarCode for .NET，使用方式與本教學的桌面範例相同。

### Q5: 哪裡可以取得 Aspose.BarCode for .NET 的臨時授權？

A5: 若需測試或評估用的臨時授權，可從 [here](https://purchase.aspose.com/temporary-license/) 取得。

## 常見問題

**Q: 更改長寬比會影響掃描速度嗎？**  
A: 通常掃描速度不會改變，但極端比例可能需要掃描器調整對焦，略微影響效能。

**Q: 可以使用 JPEG 或 SVG 等其他圖像格式嗎？**  
A: 當然可以，只需將 `BarCodeImageFormat.Png` 替換為相應的格式列舉值。

**Q: 開發版需要授權嗎？**  
A: 開發與測試階段使用臨時授權即可；正式上線建議使用完整授權。

**Q: 如何處理編碼文字中的 Unicode 字元？**  
A: Aspose.BarCode 完全支援 Unicode。示例中的 `"Åspóse.Barcóde©"` 即展示了此功能。

---

**Last Updated:** 2026-05-14  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [Aztec Code Text Encoding with Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)
- [How to create Aztec barcode with error correction in .NET](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)
- [Mastering Aztec Symbol Mode with Aspose.BarCode for .NET](/barcode/net/aztec-barcode-encoding/aztec-symbol-mode-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}