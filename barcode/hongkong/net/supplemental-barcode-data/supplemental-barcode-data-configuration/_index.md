---
date: 2026-03-07
description: 學習如何在 C# 中使用 Aspose.BarCode for .NET 建立帶有補充資料的 EAN-13 條碼 – 快速產生條碼 PNG。
linktitle: Supplemental Barcode Data Configuration
second_title: Aspose.BarCode .NET API
title: 建立含補充資料的 EAN-13 條碼 – Aspose.BarCode
url: /zh-hant/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立含補充資料的 EAN-13 條碼 – Aspose.BarCode for .NET

在本實作教學中，您將 **建立 EAN-13 條碼**，其中包含補充的 EAN‑2 或 EAN‑5 資料，並且您將看到如何僅用幾行 C# 代碼 **產生條碼 PNG** 檔案。無論您是構建零售結帳系統、物流應用程式，或是簡單的庫存工具，加入補充資訊的能力都能讓條碼更具實用性。

## 快速解答
- **「補充資料」是什麼意思？** 主條碼旁邊印刷的額外數字（EAN‑2/EAN‑5），通常用於價格或期號。  
- **使用哪種條碼類型？** 以 EAN‑13 為主要符號，並可選擇加入 EAN‑2 或 EAN‑5 補充。  
- **可以輸出 PNG 圖片嗎？** 可以 – `Save` 方法可直接匯出為 PNG。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **是否相容於 .NET Core / .NET 6？** 完全相容 – Aspose.BarCode 支援所有現代 .NET 執行環境。

## 先決條件

在開始編寫程式碼之前，請確保您已具備：

- Visual Studio（或任何相容 .NET 的 IDE）。  
- Aspose.BarCode for .NET 的副本 – 於 **[此處](https://releases.aspose.com/barcode/net/)** 下載。  
- 基本的 C# 知識。  
- 一個可寫入的資料夾，用於儲存產生的 PNG 檔案。

## 匯入命名空間

首先，加入 Aspose.BarCode 命名空間，以便存取產生器類別：

```csharp
using Aspose.BarCode.Generation;
```

> **專業提示：** 如果您使用 .NET Core，請將 NuGet 套件 `Aspose.BarCode` 加入您的專案，而不是手動參考 DLL。

## 什麼是補充條碼？

補充條碼是印在主條碼旁邊的輔助數字字串。  
- **EAN‑2** – 兩位數補充，常用於雜誌的期號。  
- **EAN‑5** – 五位數補充，常用於零售商品的價格延伸。

加入這些補充不會改變主 EAN‑13 資料，只是提供掃描器可讀取的額外資訊。

## 為何使用 Aspose.BarCode 處理補充資料？

- **一行 API** – 在同一個物件中同時設定主條碼與補充條碼。  
- **完整尺寸控制** – 調整 X‑dimension、補充間距與圖像格式。  
- **跨平台** – 可在 .NET Framework、.NET Core 以及 .NET 5/6+ 上執行。

## 逐步指南

### 步驟 1：設定輸出目錄

定義 PNG 檔案的儲存位置。請將佔位符替換為您機器上的實際路徑。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：初始化條碼產生器（Barcode Generator C#）

建立 `BarcodeGenerator` 實例，指定 **EAN‑13** 為主要類型，並提供 13 位數的資料。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

### 步驟 3：調整條碼尺寸

微調條碼的視覺大小以及為補充保留的空間。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

### 步驟 4：加入 EAN‑2 補充資料

將補充資料設定為兩位數值（例如「12」），此資訊會顯示在主條碼的右側。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

### 步驟 5：將 EAN‑2 條碼儲存為 PNG

匯出圖像。`BarCodeImageFormat.Png` 參數可確保產出高品質的 PNG 檔案。

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

### 步驟 6：切換為 EAN‑5 補充資料

將 `SupplementData` 改為五位數字串，以用於價格延伸。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

### 步驟 7：將 EAN‑5 條碼儲存為 PNG

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

> **為何這樣可行：** 同一個 `BarcodeGenerator` 實例會被重複使用，只需在每次 `Save` 前修改 `SupplementData` 屬性，即可保持程式碼簡潔，避免不必要的物件建立。

## 常見問題與技巧

- **目錄路徑無效** – 確認資料夾已存在且應用程式具備寫入權限。  
- **補充長度不正確** – EAN‑2 必須恰好 2 位，EAN‑5 必須 5 位，否則會拋出例外。  
- **圖像無法顯示** – 請確認使用 `BarCodeImageFormat.Png`；其他格式（如 JPEG）可能產生壓縮雜訊，影響掃描器可讀性。

## 常見問答

### 可以在 .NET Core 專案中使用 Aspose.BarCode for .NET 嗎？
可以，Aspose.BarCode for .NET 完全相容於 .NET Core、.NET 5 與 .NET 6。

### 有提供免費試用版嗎？
有，您可前往 **[此連結](https://releases.aspose.com/)** 免費試用。

### 從哪裡取得 Aspose.BarCode for .NET 的臨時授權？
您可以從 **[此連結](https://purchase.aspose.com/temporary-license/)** 取得臨時授權。

### Aspose.BarCode 支援多種條碼類型嗎？
當然支援 – 包括 EAN‑13、QR Code、Code 128、DataMatrix、PDF‑417 等多種條碼。

### 可以自訂產生條碼的外觀嗎？
可以，您可透過完整的 `Parameters` API 調整顏色、字型、邊距，甚至加入背景圖像。

## 結論

您現在已掌握如何使用 Aspose.BarCode for .NET **建立含補充 EAN‑2 或 EAN‑5 資料的 EAN-13 條碼**，以及 **產生條碼 PNG** 檔案。此方法讓您能完整控制條碼尺寸、補充間距與輸出格式，十分適合零售、物流以及任何需要額外數字資訊的情境。

欲深入了解，請參考完整參考手冊：**[Aspose.BarCode for .NET 文件](https://reference.aspose.com/barcode/net/)**。

---

**最後更新：** 2026-03-07  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}