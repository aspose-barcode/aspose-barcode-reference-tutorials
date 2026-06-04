---
date: 2026-02-04
description: 學習如何使用 Aspose.BarCode for .NET 透過設定行與列來建立 DotCode 條碼影像。
linktitle: DotCode Rows and Columns Configuration
second_title: Aspose.BarCode .NET API
title: 產生 DotCode 條碼圖像 – 行與列 (Aspose.BarCode)
url: /zh-hant/net/dotcode-barcode-configuration/dotcode-rows-columns-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立 DotCode 條碼圖像 – 行與列 (Aspose.BarCode)

## 簡介

歡迎來到使用 Aspose.BarCode for .NET 產生條碼的世界！在本指南中，您將**建立 DotCode 條碼圖像**檔案，並學習如何微調行與列以符合您的精確需求。無論您是建立醫療保健標籤系統、物流追蹤應用程式，或僅僅在實驗 2D 符號，掌握此配置即可讓您精確控制條碼的尺寸與資料容量。

## 快速解答
- **「建立 DotCode 條碼圖像」是什麼意思？** 這表示產生一個視覺的 PNG/JPEG 等檔案，使用 DotCode 2‑D 符號將您的資料編碼。  
- **哪個函式庫負責產生？** Aspose.BarCode for .NET 提供簡易的 API 以產生高品質的 DotCode 圖像。  
- **我需要授權嗎？** 免費試用可用於開發；商業授權則是正式上線所必需。  
- **我可以獨立自訂行與列嗎？** 可以——您可以設定行、列，或讓函式庫自動調整大小。  
- **支援哪些輸出格式？** PNG、JPEG、BMP、GIF、TIFF 等，透過 `BarCodeImageFormat`。

## 什麼是 DotCode 條碼圖像？

DotCode 是一種緊湊的二維條碼，可在小方形或矩形區域內儲存大量資料。它廣泛應用於 **醫療保健** 與 **製藥** 行業，用於追蹤產品、編碼患者資訊等。透過設定行與列，您可控制條碼的密度與實體尺寸。

## 為何要設定行與列？

* 將條碼適配於有限的標籤空間。  
* 優化特定印表機或掃描器的掃描可靠性。  
* 在圖像大小與資料容量之間取得平衡——更多行/列意味著更多資料，但圖像也會變大。  

既然您了解了原因，接下來讓我們一步步說明如何**建立 DotCode 條碼圖像**，並自行設定行與列。

## 先決條件

在深入程式碼之前，請確保您已具備以下條件：

1. **.NET 開發環境** – 已安裝 .NET SDK 的 Visual Studio、Rider 或 VS Code。  
2. **Aspose.BarCode for .NET** – 從官方網站 **[此處](https://releases.aspose.com/barcode/net/)** 下載。  
3. **有效授權**（或臨時試用授權）以進行正式產生。  
4. **基本的 C# 知識** – 您將撰寫少量程式碼片段，概念相當直接。

## 匯入命名空間

範例僅需匯入以下一個命名空間：

```csharp
using Aspose.BarCode.Generation;
```

## 逐步指南：建立 DotCode 條碼圖像

### 步驟 1：設定目錄路徑

首先，決定產生的圖像要儲存的位置。將佔位符替換為您機器上的實際資料夾路徑。

```csharp
string path = "Your Directory Path";
```

> **專業提示：** 使用 `Path.Combine(Environment.CurrentDirectory, "Barcodes")` 以建立跨平台相容的路徑。

### 步驟 2：初始化 DotCode 產生器

建立 `BarcodeGenerator` 實例，指定 `EncodeTypes.DotCode` 符號，並提供欲編碼的資料（例如「Aspose」）。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // All configuration and saving will happen inside this block.
}
```

### 步驟 3：設定 DotCode Columns

若需固定欄位數，設定 `Columns` 屬性。此處我們選擇 **18 欄**，並將結果儲存為 PNG 檔案。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
gen.Parameters.Barcode.DotCode.Columns = 18;
gen.Save($"{path}DotCodeColumns18.png", BarCodeImageFormat.Png);
```

> **為何使用 XDimension？** 調整像素大小會改變每個點的視覺密度，但不會影響編碼資料。

### 步驟 4：設定 DotCode Rows

您也可以固定列數，同時讓函式庫自行決定欄位數（將 `Columns = -1`）。以下範例建立一個具有 **12 列** 的條碼。

```csharp
gen.Parameters.Barcode.DotCode.Columns = -1;
gen.Parameters.Barcode.DotCode.Rows = 12;
gen.Save($"{path}DotCodeRows12.png", BarCodeImageFormat.Png);
```

### 步驟 5：同時設定 Rows 與 Columns

當您需要完整控制時，可同時設定兩個屬性。以下程式碼產生一個 **29 欄**、**26 列** 的條碼。

```csharp
gen.Parameters.Barcode.DotCode.Columns = 29;
gen.Parameters.Barcode.DotCode.Rows = 26;
gen.Save($"{path}DotCodeRows26Columns29.png", BarCodeImageFormat.Png);
```

> **常見陷阱：** 同時將 rows 與 columns 設為過高的值，可能產生超出一般標籤尺寸的圖像。列印前請先預覽測試。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| 條碼顯示模糊 | XDimension 太低 | 增加 `XDimension.Pixels`（例如 12‑15）。 |
| 掃描器無法讀取條碼 | Rows/Columns 對印表機過於密集 | 減少 rows/columns，或使用更高解析度的印表機。 |
| 圖像未儲存 | `path` 字串無效 | 確保目錄存在，或呼叫 `Directory.CreateDirectory(path)`。 |

## 常見問與答

**Q: DotCode 條碼能儲存的最大資料量是多少？**  
A: 這取決於您設定的行與列數。格子越多可儲存的資料越多，但圖像也會變大。

**Q: 我可以變更條碼的顏色嗎？**  
A: 可以。於儲存前使用 `gen.Parameters.Barcode.ForeColor` 與 `BackColor` 設定自訂顏色。

**Q: DotCode 符號在所有平台上都有支援嗎？**  
A: Aspose.BarCode for .NET 可於 .NET Framework、.NET Core 以及 .NET 5/6+ 上執行，因而可在 Windows、Linux 或 macOS 產生圖像。

**Q: 我在哪裡可以找到所有 DotCode 參數的完整清單？**  
A: 官方 API 參考文件提供詳細說明——請參閱 [Aspose.BarCode 文件](https://reference.aspose.com/barcode/net/)。

**Q: 如何在 Web API 中產生條碼而不寫入磁碟？**  
A: 呼叫 `gen.Save(Stream, BarCodeImageFormat.Png)`，並將該串流作為檔案結果回傳。

## 結論

您現在已了解如何使用 Aspose.BarCode for .NET **建立 DotCode 條碼圖像**檔案，並精確控制其行與列。透過調整 `Rows` 與 `Columns` 屬性，您可以為任何標籤或包裝情境量身打造條碼尺寸。嘗試不同的尺寸、顏色與輸出格式以符合專案需求，並探索更廣泛的 Aspose.BarCode 功能以獲得更多自訂可能。

如果您遇到任何挑戰或想深入了解，請參考官方資源：

* [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
* [Aspose.BarCode community support](https://forum.aspose.com/c/barcode/13)

---

**Last Updated:** 2026-02-04  
**Tested With:** Aspose.BarCode for .NET 24.11 (latest at time of writing)  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}