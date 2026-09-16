---
date: 2026-05-19
description: 了解如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼、調整長寬比、編碼位元組或文字，以及掌握符號模式。
keywords:
- create aztec barcode
- aztec barcode encoding
- aspose barcode .net
linktitle: Aztec 條碼編碼
schemas:
- author: Aspose
  dateModified: '2026-05-19'
  description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  headline: How to create Aztec barcode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create Aztec barcode using Aspose.BarCode for .NET, customize
    aspect ratios, encode bytes or text, and master symbol modes.
  name: How to create Aztec barcode with Aspose.BarCode for .NET
  steps:
  - name: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
    text: '**Create a `BarcodeGenerator` instance** with `EncodeTypes.Aztec`.'
  - name: '**Assign your data** (text, bytes, or numeric string).'
    text: '**Assign your data** (text, bytes, or numeric string).'
  - name: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
    text: '**Set `AspectRatio`** – for example, `1.5` for a wider bar.'
  - name: '**Generate the image** using `Save` or `GetBarCodeImage`.'
    text: '**Generate the image** using `Save` or `GetBarCodeImage`.'
  - name: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
    text: '**Prepare the byte array** (e.g., `byte[] data = Encoding.UTF8.GetBytes("Hello")`).'
  - name: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
    text: '**Instantiate `BarcodeGenerator`** with `EncodeTypes.Aztec`.'
  - name: '**Call `EncodeBytes(data)`** to load the binary content.'
    text: '**Call `EncodeBytes(data)`** to load the binary content.'
  - name: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
    text: '**Render the barcode** with `Save` or `GetBarCodeImage`.'
  - name: '**Create the generator** with `EncodeTypes.Aztec`.'
    text: '**Create the generator** with `EncodeTypes.Aztec`.'
  - name: '**Set `CodeText`** to the string you want to encode.'
    text: '**Set `CodeText`** to the string you want to encode.'
  type: HowTo
- questions:
  - answer: The library works with .NET Framework 4.5+, .NET Core 3.1+, .NET 5, .NET
      6, and later.
    question: Which .NET versions are supported by Aspose.BarCode for Aztec encoding?
  - answer: Yes—set the `Resolution` property (e.g., 300 dpi) before saving the image
      to obtain print‑ready quality.
    question: Can I create a high‑resolution Aztec barcode for printing?
  - answer: Up to 3,000 numeric or 2,300 alphanumeric characters, or roughly 1,800
      bytes of raw data in Compact mode.
    question: How large a data payload can an Aztec barcode hold?
  - answer: Absolutely—Aspose.BarCode’s decoder automatically detects orientation
      and corrects it during the read operation.
    question: Is it possible to read an Aztec barcode that has been rotated?
  - answer: A free evaluation license is available for testing; a commercial license
      is required for production deployments.
    question: Do I need a license for development and testing?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 建立 Aztec 條碼
url: /zh-hant/net/aztec-barcode-encoding/
weight: 28
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aztec 條碼編碼

您是否已準備好深入 Aztec 條碼編碼的世界，並學習如何使用 Aspose.BarCode for .NET **建立 Aztec 條碼** 圖像？此函式庫讓您完全掌控尺寸、錯誤更正與資料表示，適用於從行動票務到庫存追蹤的各種情境。

## 快速解答
- **哪個函式庫支援 Aztec 條碼？** Aspose.BarCode for .NET  
- **我可以更改長寬比嗎？** 可以，透過 `AspectRatio` 屬性  
- **可以進行位元層級編碼嗎？** 當然可以 – 使用 `EncodeBytes` 方法  
- **有哪些錯誤更正等級可用？** 等級 0 到 4（等級越高，冗餘度越大）  
- **生產環境需要授權嗎？** 需要，商業授權會移除評估限制  

## Aztec 條碼是什麼？
Aztec 條碼是一種二維矩陣碼，可編碼最多 3,000 個數字或 2,300 個字母數字字元。它具備位於中心的定位圖樣，即使在低解析度列印時也能快速掃描。由於圖樣位於中心，條碼可從任何方向讀取，因而在行動與工業應用中具備高度可靠性。

## 如何自訂 Aztec 條碼的長寬比？
`BarcodeGenerator` 是 Aspose.BarCode 中用於建立條碼的主要類別。於 `BarcodeGenerator` 物件上設定 `AspectRatio` 屬性為所需的寬高比例，然後產生圖像。調整長寬比有助於將條碼適配於受限的 UI 空間或標籤版面，同時不犧牲掃描可靠性，亦可符合品牌指引或特定印表機需求。

### 自訂長寬比的步驟
1. **建立 `BarcodeGenerator` 實例**，使用 `EncodeTypes.Aztec`。  
2. **指定您的資料**（文字、位元組或數字字串）。  
3. **設定 `AspectRatio`** – 例如，`1.5` 代表較寬的條紋。  
4. **產生圖像**，使用 `Save` 或 `GetBarCodeImage`。  

## 如何將原始位元組編碼成 Aztec 條碼？
`EncodeBytes` 是接受位元組陣列並將其轉換為 Aztec 矩陣的方法。將位元組陣列傳遞給 `BarcodeGenerator` 的 `EncodeBytes` 方法。API 會自動將二進位資料轉換為緊湊的 Aztec 矩陣，保留每一位元。此功能非常適合將加密負載、二進位識別碼或壓縮檔案直接嵌入條碼中。

### 編碼位元組的步驟
1. **準備位元組陣列**（例如 `byte[] data = Encoding.UTF8.GetBytes("Hello")`）。  
2. **實例化 `BarcodeGenerator`**，使用 `EncodeTypes.Aztec`。  
3. **呼叫 `EncodeBytes(data)`** 以載入二進位內容。  
4. **渲染條碼**，使用 `Save` 或 `GetBarCodeImage`。  

## 如何將文字編碼成 Aztec 條碼？
`CodeText` 是保存要編碼之純文字資料的屬性。使用 `BarcodeGenerator` 的 `CodeText` 屬性提供純文字資料。函式庫會自動選擇最佳的編碼模式（數字、字母數字或位元組），並套用相應的錯誤更正等級。這讓嵌入 URL、產品 ID 或任何可讀字串變得簡單。

### 編碼文字的步驟
1. **建立產生器**，使用 `EncodeTypes.Aztec`。  
2. **設定 `CodeText`** 為您想編碼的字串。  
3. **可選擇調整 `ErrorLevel`** 以提升容錯能力。  
4. **產生圖像**，使用 `Save` 或 `GetBarCodeImage`。  

## 如何產生不同錯誤更正等級的 Aztec 條碼？
`ErrorLevel` 是控制條碼中加入冗餘資料量的屬性。於渲染前調整 `ErrorLevel` 屬性（0‑4）。等級越高，冗餘資料越多，使條碼即使在高達 30 % 符號受損的情況下仍可被讀取。此特性對於工業標籤或戶外指示牌等惡劣環境尤為重要。

### 設定錯誤更正的步驟
1. **實例化 `BarcodeGenerator`** 用於 Aztec。  
2. **指定您的資料**（文字或位元組）。  
3. **設定 `ErrorLevel`** – 例如 `generator.Parameters.Barcode.Aztec.ErrorLevel = 3`。  
4. **渲染條碼**，使用您偏好的輸出格式。  

## 不同的 Aztec 符號模式是什麼？以及如何使用它們？
`SymbolMode` 是決定產生的 Aztec 代碼矩陣大小與資料容量的設定。函式庫提供四種模式：**Auto**、**FullRange**、**Compact** 和 **Rune**。  

- **Auto** – 產生器會選擇最小可能的尺寸。  
- **FullRange** – 允許在極大量資料時使用最大矩陣大小。  
- **Compact** – 產生較小且更緊密的符號，適合空間受限的情況。  
- **Rune** – 用於編碼 Unicode 符文的專門模式。  

透過 `Generator.Parameters.Barcode.Aztec.SymbolMode` 選擇模式。每種模式在尺寸、可讀性與資料容量之間取得平衡，讓您依應用需求調整條碼。

## Aztec 條碼編碼教學
以下是針對上述各主題的逐步教學指南。點擊任一連結即可瀏覽完整程式碼範例、先決條件與最佳實踐技巧。

### [自訂 Aztec 條碼長寬比](./aztec-aspect-ratio-customization/)
了解如何使用 Aspose.BarCode for .NET 自訂 Aztec 條碼的長寬比。為您的 .NET 應用程式建立獨特且彈性的條碼。

### [Aztec 位元組編碼](./aztec-bytes-encoding/)
了解如何使用 Aspose.BarCode for .NET 執行 Aztec 位元組編碼。包括逐步指南、先決條件與程式碼範例。

### [Aztec 文字編碼](./aztec-code-text-encoding/)
探索使用 Aspose.BarCode for .NET 進行 Aztec 文字編碼的強大功能。學習如何在您的 .NET 應用程式中建立與辨識 Aztec 代碼。

### [產生 Aztec 錯誤更正條碼](./aztec-error-level-example/)
了解如何使用 Aspose.BarCode for .NET 以不同錯誤更正等級產生 Aztec 條碼。提供完整的條碼建立指南。

### [精通 Aztec 符號模式](./aztec-symbol-mode-example/)
在 Aspose.BarCode for .NET 中探索 Aztec 符號模式，學習如何輕鬆產生多功能條碼。透過本完整教學實作 Auto、FullRange、Compact 與 Rune 模式。

## 常見問題

**Q: 哪些 .NET 版本支援 Aspose.BarCode 的 Aztec 編碼？**  
A: 此函式庫相容於 .NET Framework 4.5+、.NET Core 3.1+、.NET 5、.NET 6 以及更高版本。

**Q: 我可以建立高解析度的 Aztec 條碼以供列印嗎？**  
A: 可以——在儲存圖像前設定 `Resolution` 屬性（例如 300 dpi），即可取得列印品質。

**Q: Aztec 條碼能容納多大的資料負載？**  
A: 最多可容納 3,000 個數字或 2,300 個字母數字字元，或在 Compact 模式下約 1,800 位元組的原始資料。

**Q: 能讀取已旋轉的 Aztec 條碼嗎？**  
A: 完全可以——Aspose.BarCode 的解碼器會自動偵測方向並在讀取時校正。

**Q: 開發與測試是否需要授權？**  
A: 可取得免費的評估授權供測試使用；商業授權則是生產部署的必要條件。

---

**最後更新：** 2026-05-19  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [如何使用 Aspose.BarCode for .NET 產生自訂長寬比的 Aztec 條碼](/barcode/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [使用 barcode generator .net 進行 Aztec 位元組編碼](/barcode/net/aztec-barcode-encoding/aztec-bytes-encoding/)
- [如何在 .NET 中建立具錯誤更正的 Aztec 條碼](/barcode/net/aztec-barcode-encoding/aztec-error-level-example/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}