---
date: 2026-03-07
description: 學習如何在 .NET 使用 Aspose.BarCode 建立一維 DataBar GS1 編碼條碼。本指南說明如何設定 GS1、配置條碼產生器，並快速產生條碼。
linktitle: One-Dimensional Databar GS1 Encoding
second_title: Aspose.BarCode .NET API
title: 使用 Aspose.BarCode 創建一維 DataBar GS1 編碼
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-databar-gs1-encoding/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 建立一維 Databar GS1 編碼

在本教學中，您將 **create one-dimensional databar** 條碼，符合 GS1 標準，使用 .NET 的 Aspose.BarCode 函式庫。無論您需要嚴格的 GS1 驗證或較彈性的條碼，我們都會逐步說明——從安裝函式庫到處理編碼例外——讓您能在自己的應用程式中產生可靠的條碼。

## 快速解答
- **“create one-dimensional databar” 是什麼意思？** 它表示產生屬於 Databar 系列的線性 (1‑D) 條碼，常用於零售與物流。  
- **如何設定 GS1 驗證？** 在 `DataBar` 參數上將 `IsAllowOnlyGS1Encoding` 設為 `true`。  
- **我需要授權嗎？** 免費試用版可用於開發；正式環境需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **在哪裡下載函式庫？** 從官方 Aspose 發佈頁面（請參閱前置條件）。

## 什麼是 “create one-dimensional databar”？
一維 Databar（亦稱為 RSS）是一種緊湊的線性條碼，可編碼數字資料、日期或 AI（應用識別碼）字串。結合 GS1 編碼時，條碼遵循全球認可的資料結構，適用於零售、醫療保健及供應鏈等情境。

## 為什麼在 .NET 中使用 Aspose.BarCode？
Aspose.BarCode 提供流暢的 API、完整的 GS1 支援，並能微調條碼的每個視覺細節。它消除低階編碼的猜測工作，讓您專注於業務邏輯。

## 前置條件

1. **Aspose.BarCode for .NET** – 從 [here](https://releases.aspose.com/barcode/net/) 下載並安裝。  
2. **Your Directory Path** – 在範例中將 `"Your Directory Path"` 替換為您具有寫入權限的資料夾路徑。

## 匯入命名空間

在 C# 檔案的頂部加入所需的 `using` 陳述式：

```csharp
using Aspose.BarCode;
using System;
```

## 步驟 1：初始化條碼產生器

建立 `BarcodeGenerator` 實例，並指定 Databar Expanded 符號集：

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("OneDDatabarGS1Encoding:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "");
```

## 步驟 2：設定 GS1 – 產生具嚴格 GS1 驗證的條碼

啟用僅限 GS1 的編碼，指定符合 GS1 的 codetext，並儲存影像：

```csharp
gen.CodeText = "(01)12345678901231";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
gen.Save($"{path}DatabarGS1RightEncoding.png", BarCodeImageFormat.Png);
```

## 步驟 3：使用 Aspose 產生條碼 – 可變編碼（不檢查 GS1）

如果您需要的條碼 **不** 強制執行 GS1 規則，請關閉檢查：

```csharp
gen.CodeText = "ASPOSE";
gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = false;
gen.Save($"{path}DatabarGS1VariableEncoding.png", BarCodeImageFormat.Png);
```

## 步驟 4：條碼產生器 GS1 檢查 – 處理例外

當 `IsAllowOnlyGS1Encoding` 為 `true` 但 codetext 不符合 GS1 時，Aspose 會拋出例外。以下範例示範如何捕捉並記錄此例外：

```csharp
try
{
    gen.CodeText = "ASPOSE";
    gen.Parameters.Barcode.DataBar.IsAllowOnlyGS1Encoding = true;
    gen.GenerateBarCodeImage();
}
catch (Exception e)
{
    Console.WriteLine(e.Message);
}
```

### 常見陷阱與技巧
- **陷阱：** 在啟用 GS1 檢查時提供非 GS1 字串，會導致條碼產生失敗。  
- **專業提示：** 在將 AI 字串指派給 `CodeText` 前先進行驗證，以避免執行時錯誤。  
- **技巧：** 使用絕對路徑或 `Path.Combine` 來安全地在不同平台上組合檔案名稱。

## 結論

現在您已了解如何 **create one-dimensional databar** 條碼搭配 GS1 編碼、如何切換 GS1 檢查，以及如何處理相關例外——全部使用 Aspose.BarCode for .NET。歡迎透過 `Parameters.Barcode` 物件探索其他樣式選項，例如條碼尺寸、顏色與邊距。

如果您遇到任何問題，官方文件與社群論壇都是極佳的資源：

- [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/)  
- [Aspose.BarCode support forum](https://forum.aspose.com/c/barcode/13)

## 常見問題

### 1. 什麼是條碼中的 GS1 編碼？
GS1 編碼是一種標準化的方式，用於在條碼內結構化資料（例如產品識別碼），確保零售商、製造商與物流供應商之間的互通性。

### 2. 我可以自訂產生的條碼外觀嗎？
可以。Aspose.BarCode 允許您透過 `Parameters.Barcode` 設定調整尺寸、顏色、邊距，甚至加入可讀文字。

### 3. 我可以在哪裡找到 Aspose.BarCode 的其他資源與文件？
您可在 [Aspose.BarCode documentation](https://reference.aspose.com/barcode/net/) 找到完整的文件與範例。這是學習與排除問題的寶貴資源。

### 4. 是否提供 Aspose.BarCode 的試用版？
是的，您可從 [here](https://releases.aspose.com/) 取得 Aspose.BarCode for .NET 的免費試用版。

### 5. 我要如何購買 Aspose.BarCode for .NET 的授權？
若要購買 Aspose.BarCode for .NET 的授權，請前往 Aspose 官方網站的 [purchase page](https://purchase.aspose.com/buy)。

---

**最後更新：** 2026-03-07  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}