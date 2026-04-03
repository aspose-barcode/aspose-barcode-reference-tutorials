---
date: 2026-02-22
description: 學習如何使用 Aspose.BarCode for .NET 在 C# 中建立條碼圖像，快速且高效地產生 GS1 DataMatrix 條碼。
linktitle: GS1 DataMatrix Example
second_title: Aspose.BarCode .NET API
title: 建立條碼圖像 C# – GS1 DataMatrix 範例
url: /zh-hant/net/gs1-barcode-encoding/gs1-datamatrix-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 DataMatrix 範例

如果您正在尋找在 .NET 應用程式中**建立條碼影像 C#**的可靠方法，Aspose.BarCode for .NET 讓此過程變得簡單。這個功能強大的函式庫支援廣泛的條碼類型，包括 GS1 DataMatrix，並提供簡潔的 API，讓您專注於業務邏輯，而不必處理低階條碼細節。在接下來的幾分鐘內，我們將逐步示範完整的實作範例，說明如何產生 GS1 DataMatrix 條碼、客製化外觀，並將其儲存為影像檔案。

## 快速解答
- **此範例產生什麼？** 一個包含範例產品資料的 GS1 DataMatrix 條碼。  
- **使用哪個函式庫？** Aspose.BarCode for .NET。  
- **我可以變更輸出格式嗎？** 可以，您可以儲存為 PNG、JPEG、BMP 等格式。  
- **開發時需要授權嗎？** 免費試用版可用於測試；正式上線需購買商業授權。  
- **此程式碼相容 .NET Core 嗎？** 絕對相容——相同的 API 可在 .NET Framework 與 .NET Core/5/6 上運作。

## 什麼是 GS1 DataMatrix 條碼？

GS1 DataMatrix 是一種二維條碼，可編碼產品層級資訊（例如 GTIN、序號以及其他應用識別碼）。它廣泛應用於零售、醫療保健與物流領域，以緊湊且高密度的方式儲存資料。

## 為何使用 Aspose.BarCode 來建立條碼影像 C#？

- **Full‑featured API** – 支援 GS1 標準、錯誤更正與尺寸控制。  
- **No external dependencies** – 純 .NET 函式庫，易於整合。  
- **Cross‑platform** – 可在 Windows、Linux 與 macOS 上執行。  
- **Extensive documentation** – 包含本範例等教學，讓您快速上手。

## 前置條件

在開始本教學之前，請先確認已具備以下前置條件：

1. **Aspose.BarCode for .NET** – 您需要安裝 Aspose.BarCode for .NET。若尚未安裝，可在此[下載](https://releases.aspose.com/barcode/net/)。  
2. **Development Environment** – 您應在系統上配置 .NET 開發環境（Visual Studio、VS Code 或任何您偏好的 IDE）。

現在前置條件已備妥，讓我們開始產生 GS1 DataMatrix 條碼吧。

## 匯入命名空間

首先，匯入使用 Aspose.BarCode for .NET 所需的命名空間。這些命名空間提供條碼產生功能。

```csharp
using Aspose.BarCode;
using System;
```

## 如何建立條碼影像 C# – 步驟說明

### 步驟 1：設定條碼產生器

首先，建立 `BarcodeGenerator` 實例，並指定 **GS1 DataMatrix** 符號及欲編碼的資料。本範例編碼字串 **"(01)12345678901231(21)ASPOSE(30)9876"**，符合 GS1 應用識別碼格式。

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("Gs1DataMatrixExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1DataMatrix, "(01)12345678901231(21)ASPOSE(30)9876");
```

*小技巧:* 將範例資料替換為您自己的 GS1 識別碼，以符合產品目錄。

### 步驟 2：自訂條碼屬性

您可以使用 `Parameters` 物件調整條碼外觀。此處將 X‑dimension（最小模組的尺寸）設定為 8 像素，並定義矩陣大小為 36 列 x 12 行。依需求調整這些數值以符合掃描需求。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 8;
gen.Parameters.Barcode.DataMatrix.Columns = 36;
gen.Parameters.Barcode.DataMatrix.Rows = 12;
```

*為何調整 X‑dimension？* 較大的 X‑dimension 可提升低解析度裝置的掃描成功率，而較小的值則可減少影像檔案大小。

### 步驟 3：儲存條碼影像

最後，將產生的條碼儲存至磁碟。範例使用 PNG 格式，您亦可選擇 Aspose.BarCode 支援的 JPEG、GIF、BMP 等格式。

```csharp
gen.Save($"{path}Gs1DataMatrixExample.png", BarCodeImageFormat.Png);
```

執行程式後，您會在指定資料夾中看到 **Gs1DataMatrixExample.png**，即可用於標籤、包裝或數位應用。

## 常見使用情境

- **Retail product labeling** – 編碼 GTIN、批號與有效日期。  
- **Pharmaceutical tracking** – 以符合 GS1 標準的資料滿足法規要求。  
- **Warehouse logistics** – 緊湊儲存位置與庫存資訊。  

## 疑難排解與技巧

- **Incorrect data format** – 請確認字串符合 GS1 應用識別碼語法，否則條碼可能無法掃描。  
- **Image size issues** – 若產生的影像模糊，請提升 `XDimension.Pixels` 的數值。  
- **License errors** – 試用授權可用於評估，正式上線需購買完整授權。  

## 常見問題

### 什麼是 GS1 DataMatrix？

GS1 DataMatrix 是一種二維條碼符號，用於編碼與產品及其識別相關的資料，尤其在零售與醫療保健產業中廣泛使用。

### Aspose.BarCode for .NET 是否適用於其他條碼類型？

是的，Aspose.BarCode for .NET 支援多種條碼類型，具備高度彈性，可應用於各種情境。

### 除 PNG 外，我可以產生其他影像格式的條碼嗎？

可以，Aspose.BarCode for .NET 允許將產生的條碼儲存為多種影像格式，如 JPEG、GIF、BMP 等，除 PNG 之外。

### 使用 Aspose.BarCode for .NET 是否需要授權？

是的，商業使用 Aspose.BarCode for .NET 必須擁有有效授權。您可於 [Aspose 官方網站](https://purchase.aspose.com/buy) 取得授權。

### 我可以從哪裡取得 Aspose.BarCode for .NET 的支援？

您可在 [Aspose.BarCode for .NET 論壇](https://forum.aspose.com/c/barcode/13) 中尋找答案與取得支援。

## 其他常見問題 (AI 優化)

**Q: 如何在 C# 中產生不含 GS1 格式的 DataMatrix 條碼？**  
A: 使用 `EncodeTypes.DataMatrix` 取代 `EncodeTypes.GS1DataMatrix`，並將純資料字串傳入 `BarcodeGenerator`。

**Q: 我可以程式化變更條碼顏色嗎？**  
A: 可以，設定 `gen.Parameters.Barcode.ForeColor` 與 `gen.Parameters.Barcode.BackColor` 以自訂前景與背景顏色。

**Q: 能否直接將產生的條碼嵌入 PDF 中？**  
A: 完全可以——先將條碼取得為 `System.Drawing.Image`，再使用 Aspose.PDF 或其他 PDF 函式庫加入 PDF。

**Q: 支援哪些 .NET 版本？**  
A: Aspose.BarCode for .NET 支援 .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5、.NET 6 以及更高版本。

**Q: 如何提升小標籤的掃描可靠度？**  
A: 提升 X‑dimension、加入靜區 (`gen.Parameters.Barcode.Margin`)，並確保條碼與背景之間有足夠的對比度。

## 結論

在本教學中，我們示範了如何使用 Aspose.BarCode for .NET **建立條碼影像 C#** 以產生 GS1 DataMatrix 條碼。只需幾行程式碼，即可將高品質條碼嵌入您的應用程式，無論是零售解決方案、醫療系統或物流平台。建議進一步探索函式庫，以發掘更多條碼類型、進階渲染選項與整合情境。

欲取得更多資訊與詳細文件，請參閱 [Aspose.BarCode for .NET 文件](https://reference.aspose.com/barcode/net/)。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-02-22  
**測試環境：** Aspose.BarCode for .NET（最新版本）  
**作者：** Aspose