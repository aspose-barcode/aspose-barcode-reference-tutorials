---
date: 2026-05-30
description: 了解如何使用 Aspose.BarCode for .NET 以自訂 DataMatrix 長寬比建立條碼 PNG。提供條碼產生與尺寸自訂的逐步指南。
keywords:
- create barcode png
- generate datamatrix barcode
- asp.net barcode generation
- barcode generation visual studio
linktitle: DataMatrix 長寬比自訂
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  headline: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  type: TechArticle
- description: Learn how to create barcode PNG with a custom DataMatrix aspect ratio
    using Aspose.BarCode for .NET. Step-by-step guide for barcode generation and size
    customization.
  name: Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode
  steps:
  - name: Set Up Your Project
    text: Create a new console or Windows Forms project in Visual Studio and add a
      reference to the Aspose.BarCode DLL.
  - name: Initialize a Barcode Generator
    text: 'Instantiate it with the DataMatrix symbology and the data you want to encode:
      `BarcodeGenerator` creates a barcode image from the specified symbology and
      data. > This line creates a generator ready to produce a DataMatrix barcode
      that contains the sample text.'
  - name: Customize Aspect Ratio and Save PNG Files
    text: 'Now you can change the **aspect ratio** and save each version as a PNG
      image: `AspectRatio` sets the width‑to‑height proportion of the DataMatrix modules.
      `Save` writes the generated barcode image to a file in the chosen format. -
      The first call creates a square‑proportioned barcode (`AspectRatio = '
  type: HowTo
- questions:
  - answer: Yes, many 2‑D barcodes (e.g., QR, PDF417) support aspect‑ratio adjustments
      through their specific parameter objects.
    question: Can I customize the aspect ratio of other barcode types using Aspose.BarCode
      for .NET?
  - answer: Yes, you can access a free trial of Aspose.BarCode for .NET [here](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: You can purchase a license on the Aspose website [here](https://purchase.aspose.com/buy).
    question: Where can I purchase a license for Aspose.BarCode for .NET?
  - answer: Yes, it works with .NET Framework 4.x, .NET Core 3.1+, and the latest
      .NET releases.
    question: Is Aspose.BarCode for .NET compatible with different .NET Framework
      versions?
  - answer: Absolutely – PNG, JPEG, BMP, GIF, TIFF, SVG, and PDF are all supported
      out of the box.
    question: Can I generate barcodes in different formats with Aspose.BarCode for
      .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode

產生具有自訂 DataMatrix 長寬比的 **barcode PNG** 是在需要 **建立 barcode PNG** 檔案以符合特定版面配置限制時的常見需求。在本教學中，我們將逐步說明如何使用 Aspose.BarCode for .NET **建立 barcode PNG** 檔案，解釋為何您可能想調整長寬比，並示範如何為您的應用程式微調輸出。

## 快速解答
- **「長寬比」控制什麼？** 它定義 DataMatrix 模組的寬高比例。  
- **我可以輸出 PNG、JPEG 或 SVG 嗎？** 可以 — `Save` 方法支援 PNG、JPEG、BMP、GIF、TIFF、SVG 以及 PDF。  
- **我需要此功能的授權嗎？** 免費試用可用於開發；正式環境需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.x、.NET Core 3.1+、.NET 5/6/7。  
- **有效的長寬比值有多少種？** 任意正浮點數；常見值為 0.5 – 2.0。

## 什麼是 DataMatrix 條碼，為何要調整其長寬比？
DataMatrix 條碼是一種二維矩陣碼，能在緊湊的方形內儲存大量資料。調整 **aspect ratio** 可讓您水平拉伸或壓縮模組，當需要將條碼放入狹窄欄位或寬闊標籤且不影響掃描可靠性時，這非常有用。

## 為何使用 Aspose.BarCode 來建立條碼 PNG？
Aspose.BarCode 支援 **7 種影像格式** — PNG、JPEG、BMP、GIF、TIFF、SVG 與 PDF —，且能在記憶體中處理 **超過 50 種輸入與輸出格式**，可在不載入整個檔案的情況下處理數百頁文件。此函式庫提供流暢的 API，讓您只需一行程式碼即可產生 DataMatrix 條碼，確保像素完美渲染且完整相容 .NET。

## 前置條件

在開始自訂 DataMatrix 長寬比之前，請確保已具備以下前置條件：

1. **Visual Studio** – 任意近期版本皆可。  
2. **Aspose.BarCode for .NET** – 在此下載 [here](https://releases.aspose.com/barcode/net/)。  
3. 您也可以在此探索其他 Aspose 產品發佈版本 [here](https://releases.aspose.com/)。  
4. **.NET Framework / .NET Core** – 您的專案必須針對受支援的版本。

## 匯入命名空間

首先，您需要在 C# 專案中匯入必要的命名空間：

`using Aspose.BarCode.Generation;` 匯入包含條碼產生類別的命名空間。  

```csharp
using Aspose.BarCode.Generation;
```

> **Pro tip:** 保持此 `using` 陳述式位於檔案頂部，以確保隨時可使用 `BarcodeGenerator` 類別。

## 如何使用自訂長寬比建立條碼 PNG？

載入 `BarcodeGenerator`、設定 DataMatrix 類型、調整 `AspectRatio` 屬性，然後呼叫 `Save`。此單行模式會產生符合您指定比例的條碼 PNG，且函式庫會自動處理模組縮放與安靜區。

`BarcodeGenerator` 會根據指定的符號系統與資料產生條碼影像。  

### 步驟 1：設定您的專案
在 Visual Studio 中建立新的 Console 或 Windows Forms 專案，並加入對 Aspose.BarCode DLL 的參考。

### 步驟 2：初始化條碼產生器
以 DataMatrix 符號系統與您想編碼的資料實例化它：

`BarcodeGenerator` 會根據指定的符號系統與資料產生條碼影像。  

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> 此行會建立一個可產生包含範例文字之 DataMatrix 條碼的產生器。

### 步驟 3：自訂長寬比並儲存 PNG 檔案
現在您可以變更 **aspect ratio**，並將每個版本儲存為 PNG 影像：

`AspectRatio` 設定 DataMatrix 模組的寬高比例。  
`Save` 將產生的條碼影像寫入指定格式的檔案。  

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- 第一個呼叫會產生方形比例的條碼（`AspectRatio = 1`）。  
- 第二個呼叫會水平壓縮條碼（`AspectRatio = 0.5`），產生較寬的外觀。

您現在擁有兩個具有不同長寬比的 **barcode PNG** 檔案，可用於報表、標籤或 UI 元素。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **Generated image is blurry** | 在儲存前提升 `Resolution` 參數（`gen.Parameters.ImageResolution = 300`）。 |
| **Barcode does not scan** | 確保長寬比維持在 0.5 – 2.0 之間，且保留足夠的安靜區（`gen.Parameters.Barcode.CodeTextParameters.Margin`）。 |
| **File path errors** | 使用 `Path.Combine` 建立輸出路徑，並確認資料夾已存在。 |

## 常見問答

**Q: 我可以使用 Aspose.BarCode for .NET 自訂其他條碼類型的長寬比嗎？**  
A: 可以，許多 2‑D 條碼（例如 QR、PDF417）皆支援透過其特定參數物件調整長寬比。

**Q: 是否提供 Aspose.BarCode for .NET 的免費試用？**  
A: 有，您可在此取得 Aspose.BarCode for .NET 的免費試用 [here](https://releases.aspose.com/)。

**Q: 我可以在哪裡購買 Aspose.BarCode for .NET 的授權？**  
A: 您可於 Aspose 官方網站購買授權 [here](https://purchase.aspose.com/buy)。

**Q: Aspose.BarCode for .NET 是否相容於不同的 .NET Framework 版本？**  
A: 可以，它支援 .NET Framework 4.x、.NET Core 3.1+ 以及最新的 .NET 版本。

**Q: 我可以使用 Aspose.BarCode for .NET 產生不同格式的條碼嗎？**  
A: 當然可以 — PNG、JPEG、BMP、GIF、TIFF、SVG 與 PDF 均原生支援。

## 結論

使用 Aspose.BarCode for .NET 自訂 DataMatrix 條碼的 **aspect ratio** 以及 **建立條碼 PNG** 檔案相當簡單。依照上述步驟，您即可產生符合專案精確版面需求的完美尺寸條碼。可進一步探索 `Resolution`、`Margin`、`Color` 等參數，以微調輸出，並在 Visual Studio 中開發適合掃描的應用程式時，考慮 `generate datamatrix barcode` 功能。

欲深入了解，請參閱官方 [documentation](https://reference.aspose.com/barcode/net/) 或加入 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 社群。

---

**最後更新：** 2026-05-30  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [產生 DataMatrix 條碼 – Aspose.BarCode 專業指南](/barcode/net/datamatrix-barcode-configuration/)
- [如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [精通使用 Aspose.BarCode for .NET 以 ASCII 編碼 DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}