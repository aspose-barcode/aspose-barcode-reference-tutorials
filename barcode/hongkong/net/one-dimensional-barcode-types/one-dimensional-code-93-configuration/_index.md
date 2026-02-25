---
date: 2026-02-25
description: 學習如何使用 Aspose.BarCode for .NET 產生條碼圖像並將條碼儲存為 PNG – 完整的 Aspose 條碼範例。
linktitle: One-Dimensional Code 93 Configuration
second_title: Aspose.BarCode .NET API
title: 產生條碼圖像 – Code 93 與 Aspose.BarCode
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-code-93-configuration/
weight: 12
---

 Support](https://forum.aspose.com/c/barcode/13) 獲得支援與討論。"

--- separator unchanged.

**Last Updated:** 2026-02-25 -> keep.

**Tested With:** Aspose.BarCode 24.11 for .NET -> keep.

**Author:** Aspose -> keep.

Then closing shortcodes.

Also need to translate "Generate barcode image – One-Dimensional Code 93 with Aspose.BarCode" heading.

Make sure to keep dash and hyphen.

Now produce final content with same markdown and shortcodes.

Let's assemble.{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生條碼影像 – 一維 Code 93 使用 Aspose.BarCode

## 簡介

在當今的數位時代，條碼已成為我們生活中不可或缺的一部分，簡化了庫存管理、產品標籤及銷售點追蹤等流程。**產生條碼影像** 通常是將這些識別碼整合到應用程式中的第一步。Aspose.BarCode for .NET 提供一個強大且易於使用的 API，讓您只需幾行 C# 程式碼即可建立高品質的 Code 93 條碼。無論您是構建倉儲系統、零售應用程式或自訂報表工具，本教學都會帶您完成完整的 **aspose barcode example**，示範如何產生、客製化以及 **save barcode PNG** 檔案。

## 快速解答
- **本教學涵蓋什麼內容？** 建立並儲存帶有檢查碼處理的 Code 93 條碼影像。  
- **使用哪個函式庫？** Aspose.BarCode for .NET（最新穩定版）。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **可以變更輸出格式嗎？** 可以——只要修改 `BarCodeImageFormat` 即可儲存為 PNG、JPEG、BMP 等格式。  
- **最低需求是什麼？** .NET Framework 4.6+ 或 .NET Core 3.1+，以及 Visual Studio。

## 什麼是 Code 93 條碼？

Code 93 是一種高密度、字母數字混合的符號系統，支援完整的 ASCII 字元集。它常因其緊湊尺寸與內建檢查碼而被選用，能在掃描時確保資料完整性。

## 為什麼使用 Aspose.BarCode 產生條碼影像？

- **完整控制** 編碼類型、檢查碼、尺寸與影像格式。  
- **無外部相依性**——此函式庫可在任何 .NET 平台上執行。  
- **卓越的渲染品質**，適用於螢幕顯示與高解析度列印。  
- **完整的文件說明** 與大量範例，可加速開發。

## 先決條件

在深入程式碼之前，請先確保您已具備以下項目：

1. **Visual Studio**（任何近期版本）。  
2. 已安裝 **Aspose.BarCode for .NET**——可從官方下載頁面取得。  
3. 基本了解 **C#** 與 .NET 專案結構。

現在環境已備妥，讓我們繼續逐步說明。

## 匯入命名空間

首先，匯入所需的命名空間，以便存取條碼產生類別。

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 步驟 1：設定目錄路徑

定義產生的條碼影像要儲存的位置。請將佔位字串替換為您機器上有效的資料夾路徑。

```csharp
string path = "Your Directory Path";
```

## 步驟 2：建立一維 Code 93 條碼

使用 `Code93Extended` 類型與欲編碼的資料，實例化 `BarcodeGenerator`。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code93Extended, "CODE");
```

## 步驟 3：啟用檢查碼（可選）

Code 93 預設已包含檢查碼。您可透過 `IsChecksumEnabled` 屬性切換其開啟與關閉。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
```

## 步驟 4：儲存條碼影像（Save Barcode PNG）

產生影像並依先前指定的資料夾儲存為 PNG 檔案。

```csharp
gen.Save($"{path}OneCSCode93WithChecksum.png", BarCodeImageFormat.Png);
```

## 步驟 5：例外處理 – 產生不含檢查碼的條碼

若需建立 **不含** 檢查碼的條碼，必須處理可能發生的例外情況。

```csharp
try
{
    gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.No;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### 常見問題與解決方案
- **路徑無效**——請確認目錄存在且應用程式具備寫入權限。  
- **不支援的字元**——Code 93 支援完整 ASCII 集合，但控制字元可能導致錯誤。  
- **未設定授權**——若未提供有效授權，函式庫將以評估模式執行，可能會加上浮水印。

## 常見問題 (FAQs)

### 問：在哪裡可以找到 Aspose.BarCode for .NET 的文件說明？
您可以在 [Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/) 找到文件說明。

### 問：如何下載 Aspose.BarCode for .NET？
您可從網站的 [Aspose.BarCode for .NET Download](https://releases.aspose.com/barcode/net/) 下載 Aspose.BarCode for .NET。

### 問：Aspose.BarCode for .NET 是否提供免費試用？
是的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.BarCode for .NET 的免費試用版。

### 問：如何購買 Aspose.BarCode for .NET 的授權？
您可在購買頁面 [Aspose.BarCode for .NET Purchase](https://purchase.aspose.com/buy) 購買授權。

### 問：在哪裡可以取得 Aspose.BarCode for .NET 的支援或提問？
您可於社群論壇 [Aspose.BarCode for .NET Support](https://forum.aspose.com/c/barcode/13) 獲得支援與討論。

---

**Last Updated:** 2026-02-25  
**Tested With:** Aspose.BarCode 24.11 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}