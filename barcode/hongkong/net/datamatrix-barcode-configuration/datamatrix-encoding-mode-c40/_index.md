---
date: 2026-06-09
description: 了解如何使用 Aspose.BarCode 透過 C40 編碼產生 DataMatrix 條碼並儲存為 PNG – .NET Core 條碼產生完整指南
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: DataMatrix 編碼模式 (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode 以 C40 產生 DataMatrix PNG 的方法
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 的主 DataMatrix 編碼模式 (C40)

## 介紹

在本教學中，您將學習 **如何產生 datamatrix** 條碼並使用 C40 編碼模式將其儲存為 PNG 檔案，搭配 Aspose.BarCode for .NET。無論您是建立庫存系統、運送標籤產生器，或任何需要緊湊高密度符號的解決方案，掌握 C40 可讓您在不犧牲可讀性的前提下得到更小的符號。我們將一步步說明，從環境設定到產出最終 PNG，讓您能立即將程式碼整合到專案中。

## 快速解答
- **「如何產生 datamatrix」指的是什麼？** 以程式方式建立 DataMatrix 條碼影像。  
- **涵蓋哪種編碼模式？** DataMatrix C40，一種高效的字母數字編碼方案。  
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買商業授權。  
- **可以在 .NET Core 上執行嗎？** 可以，Aspose.BarCode 完全支援 .NET Core、.NET 5、.NET 6 及更高版本。  
- **產生的檔案格式是什麼？** PNG – 無損、適合網路使用的影像格式。

## 如何使用 C40 編碼產生 DataMatrix

載入資料、設定產生器，然後呼叫 `Save` —— 這就是完整的三步工作流程。`BarcodeGenerator` 類別負責符號建立，而 `BarCodeImageFormat.Png` 列舉告訴 Aspose.BarCode 以 PNG 格式寫入結果。`Save` 會將產生的條碼影像寫入指定的檔案路徑與選定的格式。此段直接回答提供了端對端的解決方案，接下來我們再逐行說明程式碼。

## 什麼是 DataMatrix 編碼模式 (C40)？

`DataMatrixEncodeMode` 是一個列舉，用來指定 Aspose.BarCode 應使用哪種編碼方案產生 DataMatrix 符號。`DataMatrixEncodeMode.C40` 選項會選用 C40 字母數字編碼，將字母、數字與有限的標點符號緊密打包至較少的模組中，減少整體符號大小，同時保持典型庫存文字的可讀性。此高效方案特別適合需要以緊湊形式編碼字母數字資料的情境。

## 為什麼使用 Aspose.BarCode for .NET？

Aspose.BarCode 提供 **30+ 可設定參數** 以控制尺寸、錯誤更正層級與編碼模式，並支援 **50+ 影像與條碼格式**。此函式庫可在 **.NET Framework 4.5+、.NET Core 2.0+、.NET 5/6+** 上執行，提供零相依的產生方式，適用於伺服器、桌面與行動裝置。

## 前置條件

在進入程式碼之前，請確保您具備以下條件：

1. **.NET 開發環境** – Visual Studio、Rider 或任何支援 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 透過 NuGet 或官方安裝程式安裝。詳情請參閱[文件說明](https://reference.aspose.com/barcode/net/)。  
3. **基本 C# 知識** – 需要熟悉命名空間、類別與 using 陳述式。  
4. **可寫入的資料夾** – 您機器上用於儲存 PNG 的目錄。

## 匯入必要的命名空間

`BarcodeGenerator` 類別是建立任何條碼的入口點。請在 C# 原始檔的最上方加入所需的命名空間，以便存取產生 API：

```csharp
using Aspose.BarCode.Generation;
```

## 步驟式條碼產生

以下是一個 **步驟式條碼** 教學。每一步都以簡單語言說明，且保留原始佔位符以方便直接複製貼上。

### 步驟 1：定義目錄路徑
設定 PNG 影像要存放的資料夾。將佔位符替換為您機器上的實際路徑。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：設定條碼產生
建立 `BarcodeGenerator` 實例，指定 `EncodeTypes.DataMatrix`，並提供要編碼的資料。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 步驟 3：自訂條碼
設定 X‑dimension（模組的像素寬度）並切換編碼模式為 C40。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 步驟 4：儲存條碼影像
最後，將產生的條碼儲存為 PNG 檔案。這就是 **如何使用 Aspose.BarCode 儲存 png** 的具體答案。

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

執行程式後，您會在先前指定的資料夾中找到 `DataMatrixEncodeModeC40.png`，即可在報表、標籤或網頁中使用。

## 常見問題與提示

- **路徑無效** – 確認目錄存在且具有寫入權限；否則 `gen.Save` 會拋出例外。  
- **編碼模式不正確** – 若需編碼 C40 集合外的字元，請切換至 `DataMatrixEncodeMode.Auto` 或其他適當模式。  
- **影像大小** – 調整 `XDimension.Pixels` 以增減條碼整體尺寸，且不影響可讀性。

## 常見問答

**Q: 什麼是 DataMatrix 編碼模式 (C40)？**  
A: C40 是一種緊湊的字母數字編碼方案，適用於包含字母、數字與有限特殊字元的文字。

**Q: 在哪裡可以找到 Aspose.BarCode for .NET 的文件說明？**  
A: 您可以在[此處](https://reference.aspose.com/barcode/net/)找到文件說明，裡面提供了所有條碼類型與編碼選項的詳細指引。

**Q: Aspose.BarCode for .NET 是否相容所有 .NET 版本？**  
A: 是的，函式庫支援廣泛的 .NET 版本，從 .NET Framework 4.5+ 到 .NET 6 及更高版本皆可使用。

**Q: 我可以在購買前試用 Aspose.BarCode for .NET 嗎？**  
A: 可以，您可透過[此連結](https://releases.aspose.com/)探索 Aspose.BarCode for .NET 的免費試用版，測試其功能與效能。

**Q: 在哪裡可以取得 Aspose.BarCode for .NET 的支援？**  
A: 您可在[Aspose 論壇](https://forum.aspose.com/c/barcode/13)找到社群與技術支援。

## 結論

透過本 **步驟式條碼** 教學，您現在已掌握 **如何產生 datamatrix** 條碼並使用 C40 編碼模式將其儲存為 PNG 檔案，搭配 Aspose.BarCode for .NET。此方法讓您能完整控制條碼的外觀、尺寸與資料表示，輕鬆將高品質條碼嵌入任何 .NET 應用程式。

---

**最後更新：** 2026-06-09  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [使用 Aspose.BarCode for .NET 的 DataMatrix 位元組編碼](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [使用 Aspose.BarCode for .NET 的主 DataMatrix ASCII 編碼](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}