---
date: 2026-02-15
description: 學習如何使用 Aspose.BarCode for .NET 及 GS1 Coupon UPC‑A Databar 設定產生條碼圖像，快速上手。
linktitle: Generate barcode image – GS1 Coupon UPC-A Databar
second_title: Aspose.BarCode .NET API
title: 產生條碼圖像 – GS1 優惠券 UPC-A Databar
url: /zh-hant/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生條碼影像 – GS1 Coupon UPC-A Databar

## 介紹

您是否想在 .NET 應用程式中 **產生條碼影像**，使用 GS1 Coupon UPC-A Databar 設定？您來對地方了。Aspose.BarCode for .NET 是您產生條碼的可靠夥伴。本完整指南將一步步帶您建立 GS1 Coupon UPC-A Databar 條碼，說明整個流程，並確保您能順利將此功能整合至專案中。

## 快速回答
- **需要哪個函式庫？** Aspose.BarCode for .NET  
- **實作需要多久？** 基本條碼約 5‑10 分鐘即可完成  
- **支援哪些 .NET 版本？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6  
- **測試需要授權嗎？** 提供免費試用授權  
- **可以自訂 X‑dimension 嗎？** 可以，透過 `Parameters.Barcode.XDimension`

## 什麼是 GS1 Coupon UPC‑A Databar？
GS1 Coupon UPC‑A Databar 是一種緊湊且高密度的條碼格式，專為優惠券與促銷活動設計。它在編碼標準 UPC‑A 資料的同時，加入額外的 GS1 應用識別碼 (AI)，例如優惠券的折扣金額，十分適合零售掃描使用。

## 為什麼要使用 Aspose.BarCode 產生條碼影像？
- **完整控制** – 可直接在 C# 中調整尺寸、解析度與編碼選項。  
- **跨平台** – 支援 Windows、Linux 與 macOS。  
- **無外部相依** – 純 .NET 函式庫，無需原生 DLL。  
- **支援 ASP.NET** – 非常適合網頁式條碼產生情境。

## 前置條件

在開始使用 Aspose.BarCode for .NET 進行 GS1 Coupon UPC‑A Databar 設定之前，請先確保您具備以下條件：

1. **已安裝 Aspose.BarCode for .NET** – 若尚未安裝，請從 [Aspose.BarCode for .NET page](https://releases.aspose.com/barcode/net/) 下載。  
2. **具備基本的 C# 知識** – 熟悉 .NET 框架與 Visual Studio。  

接下來，我們將逐步說明實作方式。

### 匯入命名空間

要使用條碼產生功能，需要匯入相關的命名空間。

#### 步驟 1：加入 Using 指令
在 Visual Studio 開啟您的專案，於 C# 檔案頂部加入以下 `using` 陳述式：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

這些指令會讓 Aspose.BarCode 類別在程式碼中可用。

### 步驟 2：定義輸出目錄
指定產生的 PNG 檔案要儲存的位置。將 `"Your Directory Path"` 替換為您機器上的實際資料夾路徑：

```csharp
string path = "Your Directory Path";
```

### 步驟 3：產生 GS1 Coupon UPC‑A Databar
建立 `BarcodeGenerator` 實例、設定 X‑dimension，然後儲存影像：

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.UpcaGs1DatabarCoupon, "123456789012(8110)ASPOSE");
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Save($"{path}Gs1CouponUpcaDatabar.png", BarCodeImageFormat.Png);
```

- **EncodeTypes.UpcaGs1DatabarCoupon** 告訴函式庫使用 GS1 Coupon UPC‑A Databar 格式。  
- 資料字串 `"123456789012(8110)ASPOSE"` 包含 UPC‑A 編號，後接 AI `(8110)` 代表優惠券金額。  
- `XDimension.Pixels = 2` 控制條紋寬度，產生清晰且可掃描的影像。  

執行程式後，您會在先前指定的資料夾中看到 `Gs1CouponUpcADatabar.png`。

## 常見問題與技巧

| 問題 | 解決方案 |
|-------|----------|
| **影像未儲存** | 確認 `path` 以反斜線 (`\`) 或斜線 (`/`) 結尾，且程式具有寫入權限。 |
| **條碼模糊不清** | 提高 `XDimension` 數值，或透過設定 `gen.Parameters.ImageResolution` 以更高 DPI 儲存影像。 |
| **資料格式無效** | 確認資料字串符合 GS1 語法：`<UPC>(<AI>)<value>`。缺少括號會拋出 `BarcodeException`。 |
| **在 ASP.NET 中使用** | 將產生的影像存入記憶體串流，並以 `FileResult` 回傳，避免寫入磁碟。 |

## 常見問答

**Q: 什麼是 GS1 Coupon UPC‑A Databar？**  
A: 這是一種用於編碼優惠券資料的條碼標準，結合傳統 UPC‑A 代碼與 GS1 應用識別碼。

**Q: 從哪裡可以下載 Aspose.BarCode for .NET？**  
A: 您可於 [download page](https://releases.aspose.com/barcode/net/) 下載。

**Q: 有免費試用版嗎？**  
A: 有，請從 [here](https://releases.aspose.com/) 取得。

**Q: 如何取得臨時授權？**  
A: 詳情請見 [here](https://purchase.aspose.com/temporary-license/)。

**Q: 哪裡可以取得 Aspose.BarCode for .NET 的支援？**  
A: 前往 [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13)。

## 結論

Aspose.BarCode for .NET 簡化了 **產生條碼影像** 的工作，讓您能輕鬆在桌面或 Web 應用程式中嵌入 GS1 Coupon UPC‑A Databar 產生功能。依照上述步驟，您已具備建立、客製化與除錯條碼影像的能力。

欲了解函式庫的完整功能，請參考 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/)，其中包含顏色客製化、DPI 設定與批次產生等進階選項。

---

**最後更新：** 2026-02-15  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}