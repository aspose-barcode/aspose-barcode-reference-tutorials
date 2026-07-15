---
date: 2026-02-22
description: 學習如何在 .NET 中使用 Aspose.BarCode 自訂條碼高度，快速且精確地調整一維條碼的高度。
linktitle: Create Barcode Custom Height – One-Dimensional Barcodes
second_title: Aspose.BarCode .NET API
title: 建立條碼自訂高度 – 一維條碼
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-barcode-height-adjustment/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立條碼自訂高度 – 一維條碼

當您需要在 .NET 應用程式中 **create barcode custom height** 時，Aspose.BarCode for .NET 為您提供對一維條碼外觀的完整控制。無論您是製作庫存標籤、銷售點收據，或是運送標籤，能夠微調條碼高度都能確保最佳掃描效能與精緻外觀。在本步驟指南中，我們將逐步說明使用 Aspose.BarCode for .NET 調整一維條碼高度的所有要點。

## 快速解答
- **什麼是「barcode custom height」？** 它是 1‑D 條碼符號的以像素為單位的垂直尺寸。  
- **哪個屬性控制高度？** `Parameters.Barcode.BarHeight.Pixels`。  
- **我可以在一次執行中產生多個高度嗎？** 可以 – 只需更改屬性並再次呼叫 `Save()`。  
- **支援的影像格式？** PNG, JPEG, TIFF, BMP, GIF, and more.  
- **調整高度需要授權嗎？** 不需要，該功能在免費試用版中可用；正式使用需購買授權。  

## 什麼是「create barcode custom height」？
建立具有自訂高度的條碼即是為條碼條的垂直尺寸指定精確的像素值。當您有嚴格的版面需求、需要匹配現有印刷品，或想提升不同媒介上掃描器的可讀性時，這非常有用。

## 為什麼使用 Aspose.BarCode for .NET？
- **Rich API** – 功能豐富的 API – 透過簡單的屬性設定即可調整尺寸、顏色、文字等。  
- **Cross‑platform** – 跨平台 – 支援 .NET Framework、.NET Core 以及 .NET 5/6+。  
- **No external dependencies** – 無外部相依性 – 可直接產生影像，無需額外函式庫。  
- **High‑quality rendering** – 高品質渲染 – 即使在自訂尺寸下也能保證條碼可被掃描。  

## 前置條件

在開始之前，請確保已具備以下前置條件：

- 具備 .NET Framework 或 .NET Core 的開發環境。  
- 已安裝 Aspose.BarCode for .NET。您可從網站 [here](https://releases.aspose.com/barcode/net/) 下載。  
- 您慣用的程式碼編輯器。  

現在已完成前置條件的設定，讓我們深入探討調整一維條碼高度的流程。

## 匯入命名空間

首先，您需要將必要的命名空間匯入至專案中。這些命名空間對於使用 Aspose.BarCode for .NET 至關重要。以下是操作方式：

```csharp
using Aspose.BarCode.Generation;
```

## 步驟 1：設定目錄路徑

首先定義要儲存產生的條碼影像的目錄路徑。將 `"Your Directory Path"` 替換為系統上實際的路徑。

```csharp
string path = "Your Directory Path";
```

## 步驟 2：建立條碼產生器

現在，建立 `BarcodeGenerator` 類別的實例。您可以指定條碼類型（此處使用 `Code128`）以及條碼值（此例為 `"ASPOSE"`）。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "ASPOSE");
```

## 步驟 3：調整條碼高度

在此步驟中，您將使用 `BarHeight` 屬性設定條碼的高度。舉例來說，我們會將高度分別調整為 40 像素與 80 像素，並相應儲存兩張條碼影像。此示例說明了即時 **create barcode custom height** 多種高度值是多麼簡單。

```csharp
// Set BarHeight to 40 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 40;
gen.Save($"{path}BarHeight40Code128.png", BarCodeImageFormat.Png);

// Set BarHeight to 80 pixels
gen.Parameters.Barcode.BarHeight.Pixels = 80;
gen.Save($"{path}BarHeight80Code128.png", BarCodeImageFormat.Png);
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|-------|--------|-----|
| 高度變更後條碼顯得過細 | 寬度未成比例調整 | 如有需要，使用 `Parameters.Barcode.XDimension` 來調整條寬。 |
| 影像未儲存 | 路徑無效或缺少寫入權限 | 確認 `path` 以反斜線結尾且資料夾已存在。 |
| 產生的條碼無法掃描 | 高度對掃描器而言過低或過高 | 使用一般掃描器測試；對大多數 1‑D 條碼，將高度維持在 30‑100 像素之間。 |

## 常見問與答

**Q: Aspose.BarCode for .NET 支援哪些條碼類型？**  
A: Aspose.BarCode for .NET 支援多種條碼類型，包括 Code128、QR Code、DataMatrix 等等。您可在文件中找到完整清單。

**Q: 我也可以調整一維條碼的寬度嗎？**  
A: 可以，您可使用 Aspose.BarCode for .NET 調整一維條碼的寬度。調整方式與高度類似，您可完整控制條碼的尺寸。

**Q: 是否提供 Aspose.BarCode for .NET 的免費試用？**  
A: 有，您可透過免費試用體驗 Aspose.BarCode for .NET。可從 [here](https://releases.aspose.com/) 下載。

**Q: 我可以產生不同影像格式的條碼嗎？**  
A: 可以，Aspose.BarCode for .NET 支援多種影像格式，包括 PNG、JPEG 與 TIFF。您可依應用需求選擇最適合的格式。

**Q: 我在哪裡可以找到 Aspose.BarCode for .NET 的詳細文件？**  
A: 您可參考文件 [here](https://reference.aspose.com/barcode/net/) 以取得關於在 .NET 專案中使用 Aspose.BarCode 的深入資訊。

## 結論

在本教學中，我們說明了使用 Aspose.BarCode for .NET 為一維條碼 **create barcode custom height** 的流程。透過微調 `BarHeight` 屬性，您可以產生完全符合版面需求的條碼影像，無論是緊湊的標籤或是大型高可見度的條碼皆可。

如果您遇到任何問題或有其他疑問，歡迎透過 Aspose 社群的 [support forum](https://forum.aspose.com/c/barcode/13) 與我們聯繫。

---

**最後更新：** 2026-02-22  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}