---
date: 2026-02-28
description: 學習如何使用 Aspose.BarCode 在 .NET 中產生 DataBar 條碼 – 這是一個用於庫存管理與自訂行/列設定的 C#
  條碼產生器範例。
linktitle: Generate Databar barcode .NET – Row & Column Configuration
second_title: Aspose.BarCode .NET API
title: 產生 Databar 條碼 .NET – 列與行設定
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-databar-row-column-configuration/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生 Databar 條碼 .NET – 列與欄配置

## 快速答案
- **使用哪個函式庫？** Aspose.BarCode for .NET  
- **主要使用情境？** 產生具自訂列/欄的 DataBar 條碼以供庫存管理使用  
- **支援語言？** C#（任何 .NET 版本）  
- **是否需要授權？** 是，於正式部署時必須取得授權  
- **程式碼行數？** 基本設定少於 20 行  

## 先決條件

在開始建立動態條碼之前，請先確保具備以下條件：

### 1. .NET 開發環境

您需要在機器上設定好 .NET 開發環境，包含 Visual Studio 或其他適用的 .NET IDE。

### 2. Aspose.BarCode for .NET

確保已安裝 Aspose.BarCode for .NET 函式庫，可從 [此處](https://releases.aspose.com/barcode/net/) 下載。

### 3. 授權

使用 Aspose.BarCode for .NET 於應用程式中必須擁有有效授權。您可於 [此處](https://purchase.aspose.com/buy) 或 [此處](https://purchase.aspose.com/temporary-license/) 取得正式或暫時授權。

## 匯入命名空間

要開始使用 Aspose.BarCode for .NET，必須將必要的命名空間匯入專案中。以下步驟說明如何匯入所需的命名空間：

### 步驟 1：匯入 Aspose.BarCode 命名空間

在 .NET 專案的開頭加入以下程式碼以匯入 Aspose.BarCode 命名空間：

```csharp
using Aspose.BarCode;
```

現在，我們將示範一個 **barcode generator C# example**，說明如何為 DataBar 條碼設定欄數與列數。這在需要將條碼放入有限標籤空間或符合特定掃描設備規格時非常常見。

## 什麼是 DataBar 條碼？

DataBar（舊稱 Reduced Space Symbology）是一種緊湊且高密度的線性條碼，能在小面積內編碼大量資訊。*Expanded Stacked* 變體允許堆疊多列，非常適合需要一眼即可辨識的庫存標籤。

## 為什麼要配置列與欄？

配置列與欄可在不犧牲資料容量的前提下，調整條碼尺寸。此彈性在 **barcode generation inventory management** 場景中特別有價值，因為不同產品線的標籤尺寸會有所差異。

## 步驟 2：設定欄數

若要建立具有特定欄數的 DataBar 條碼，請依照以下步驟操作：

```csharp
// The path to the documents directory.
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarRowCol:");

// Set 4 columns
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
gen.Parameters.Barcode.DataBar.Columns = 4;
gen.Save($"{path}DatabarCols4.png", BarCodeImageFormat.Png);
```

在此程式碼片段中，我們：

1. 初始化 `BarcodeGenerator`，使用 **DatabarExpandedStacked** 類型。  
2. 將 `DataBar.Columns` 設為 **4**，以強制產生四欄。  
3. 將影像儲存為 **DatabarCols4.png**。

## 步驟 3：設定列數

若需要較高的條碼，可改為調整列數：

```csharp
// Set 3 rows
gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
gen.Parameters.Barcode.DataBar.Rows = 3;
gen.Save($"{path}DatabarRows3.png", BarCodeImageFormat.Png);
```

此處重新初始化產生器，將 `DataBar.Rows` 設為 **3**，並儲存結果。

## 步驟 4：同時配置欄與列

通常會同時控制兩個維度。以下範例示範如何同時設定：

```csharp
// Set 6 columns and 10 rows
gen = new BarcodeGenerator(EncodeTypes.DatabarExpandedStacked, "Databar Expanded Stacked long");
gen.Parameters.Barcode.DataBar.Columns = 6;
gen.Parameters.Barcode.DataBar.Rows = 10;
gen.Save($"{path}DatabarCols6Rows10.png", BarCodeImageFormat.Png);
```

透過調整兩個屬性，即可產生完全符合自訂標籤範本的條碼。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方法 |
|------|----------|----------|
| 條碼被截斷 | 欄/列超出影像畫布 | 增加影像尺寸或減少欄/列數量 |
| 掃描器無法讀取條碼 | 對比度低或條碼類型錯誤 | 使用高解析度 PNG 並確認 `EncodeTypes` |
| 執行時授權例外 | 缺少或無效的授權檔案 | 將有效的 `Aspose.BarCode.lic` 放置於執行檔資料夾 |

## 常見問答

### 什麼是 Aspose.BarCode for .NET？
Aspose.BarCode for .NET 是一套功能強大的函式庫，讓 .NET 開發者能夠建立、客製化與操作各種條碼，以應用於不同情境。

### 如何取得 Aspose.BarCode for .NET 的授權？
您可前往 [此連結](https://purchase.aspose.com/buy) 或 [此連結](https://purchase.aspose.com/temporary-license/) 取得正式或暫時授權。

### 我可以使用 Aspose.BarCode for .NET 產生不同樣式與格式的條碼嗎？
可以，Aspose.BarCode for .NET 提供廣泛的客製化選項，包含樣式、格式與資料編碼方式。

### Aspose.BarCode for .NET 適用於 Web 應用程式嗎？
絕對適用！Aspose.BarCode for .NET 可在各種 .NET 應用程式中使用，亦包括 Web 應用程式。

### 有沒有可供參考的範例專案或程式碼示例？
有，文件 [此處](https://reference.aspose.com/barcode/net/) 提供詳細的程式碼範例與範本專案，協助您快速上手。

## 其他常見問答（無新連結）

**問：我可以將此方法套用於其他 DataBar 類型嗎？**  
答：可以，您可以將 `EncodeTypes` 列舉切換至其他 DataBar 變體，如 `DatabarLimited` 或 `DatabarExpanded`。

**問：列/欄配置會影響編碼資料長度嗎？**  
答：不會，資料內容保持不變，僅視覺布局會改變。

**問：列或欄的數量有上限嗎？**  
答：實務上，限制取決於掃描器的讀取能力以及您提供的影像解析度。

## 結論

Aspose.BarCode for .NET 讓開發者能夠為各種應用建立動態且可客製化的條碼。本教學聚焦於 **generate databar barcode .net** 的列與欄配置，示範如何設定開發環境、匯入必要命名空間，並撰寫符合庫存管理需求的 **barcode generator C# example**。

探索更深入的文件 [此處](https://reference.aspose.com/barcode/net/)，取得更多條碼產生選項。若有任何問題或需要進一步協助，請前往 Aspose.BarCode for .NET 支援論壇 [此處](https://forum.aspose.com/c/barcode/13) 尋求專家與社群的協助。

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}