---
date: 2026-01-12
description: 學習如何產生 DataMatrix 條碼、如何產生 DataMatrix，並探索 Aspose 在 C# 專案中的條碼產生技術。
linktitle: DataMatrix ECC 200 Configuration
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 生成 DataMatrix 條碼 (ECC 200)
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼 (ECC 200)

## 介紹

您準備好深入了解 **如何產生 DataMatrix** 條碼並使用 Aspose.BarCode for .NET 嗎？無論您是在建置庫存系統、銷售點應用程式，或是自動化文件工作流程，本指南都會一步步帶您了解 **使用 Aspose 產生條碼** 的流程，並示範如何在 C# 中建立可靠的 DataMatrix ECC 200 條碼。

## 快速回答
- **哪個函式庫最適合在 .NET 中使用 DataMatrix？** Aspose.BarCode for .NET  
- **ECC 200 提供哪種錯誤更正等級？** 提供高密度錯誤更正，確保掃描穩定。  
- **執行範例是否需要授權？** 評估期間可使用臨時授權；正式上線需購買正式授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6 以上。  
- **可以輸出 PNG、JPEG 或 TIFF 嗎？** 可以 – `Save` 方法支援多種影像格式。

## 前置條件

1. **開發環境** – 已安裝相應 .NET 框架的 Visual Studio。  
2. **Aspose.BarCode for .NET** – 從官方網站下載並安裝，[此處](https://releases.aspose.com/barcode/net/)。  
3. **授權** – 從 [此處](https://purchase.aspose.com/temporary-license/) 取得測試用臨時授權。  
4. **C# 基礎** – 熟悉 C# 語法與專案結構。

現在已完成基礎說明，讓我們繼續設定 DataMatrix ECC 200。

## 匯入命名空間

首先匯入必要的命名空間，以便存取條碼產生類別：

```csharp
using Aspose.BarCode.Generation;
```

## 如何產生 DataMatrix ECC 200 條碼

### 步驟 1：初始化 BarcodeGenerator

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixEcc200:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Your code goes here
}
```

在此程式碼片段中，我們建立 `BarcodeGenerator` 實例，指定 **DataMatrix** 條碼類型，並提供要編碼的資料。請將 `"Your Directory Path"` 替換為您希望儲存影像的資料夾路徑。

### 步驟 2：設定 XDimension 與 ECC 類型

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
gen.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

此處我們定義 **XDimension**（每個模組的大小），並選擇 **ECC 200** 以獲得強大的錯誤更正。若需要更大或更小的模組，可調整像素值。

### 步驟 3：產生並儲存條碼影像

```csharp
gen.Save($"{path}DataMatrixEcc200.png", BarCodeImageFormat.Png);
```

`Save` 方法會將條碼寫入 PNG 檔案。若有需要，可將 `BarCodeImageFormat.Png` 改為 `Jpeg` 或 `Tiff`。這就是使用 Aspose **產生條碼影像 C#** 的核心程式碼。

## 為什麼選擇 Aspose 條碼產生？

- **功能完整的 API** – 支援數十種條碼規格，包含 QR、PDF417 與 DataMatrix。  
- **無外部相依性** – 純 .NET 函式庫，易於整合。  
- **高品質渲染** – 可產生可縮放向量輸出，且對尺寸有精確控制。  
- **跨平台** – 在 Windows、Linux 與 macOS 上皆可於 .NET Core 執行。

## 常見問題與故障排除

| 症狀 | 可能原因 | 解決方式 |
|------|----------|----------|
| 條碼顯示模糊 | XDimension 設定過低 | 將 `XDimension.Pixels` 提升至 6‑8 |
| 手機掃描失敗 | ECC 等級不正確 | 確認 `DataMatrixEcc = DataMatrixEccType.Ecc200` |
| 檔案未建立 | 路徑字串無效 | 使用絕對路徑或確保資料夾已存在 |

## 常見問答

### Q1：什麼是 Aspose.BarCode for .NET？

A1：Aspose.BarCode for .NET 是一套功能強大的函式庫，讓 .NET 開發者能在各種應用程式中產生、客製化與處理條碼。

### Q2：使用 Aspose.BarCode for .NET 是否需要授權？

A2：是的，必須擁有有效授權才能在專案中使用 Aspose.BarCode for .NET。您可以取得臨時授權以進行測試。

### Q3：我可以自訂使用 Aspose.BarCode 產生的條碼外觀嗎？

A3：當然可以！您可以自訂條碼的外觀、尺寸以及其他多項屬性，以符合特定需求。

### Q4：Aspose.BarCode for .NET 支援哪些條碼類型？

A4：支援多種條碼類型，包括 QR Code、DataMatrix、Code 128 等等。

### Q5：在哪裡可以找到 Aspose.BarCode for .NET 的文件說明？

A5：您可以在此取得文件說明 [here](https://reference.aspose.com/barcode/net/)。

## Frequently Asked Questions

**Q: 可以在 .NET Core 主控台應用程式中使用此程式碼嗎？**  
A: 可以，相同的 API 也適用於 .NET Core、.NET 5 與 .NET 6 專案。

**Q: 要如何將輸出格式改成 JPEG？**  
A: 在 `Save` 呼叫中將 `BarCodeImageFormat.Png` 替換為 `BarCodeImageFormat.Jpeg`。

**Q: 能否直接將條碼嵌入 PDF 中？**  
A: 可以 – 先產生影像，然後使用 Aspose.PDF 或其他 PDF 函式庫將其加入 PDF。

**Q: 若要編碼 Unicode 字元該怎麼做？**  
A: DataMatrix 支援 UTF‑8，只需直接傳入字串即可，如範例所示。

**Q: 函式庫是否支援批次產生多筆條碼？**  
A: 完全支援 – 將產生程式碼放入迴圈，並為每次迭代更換資料/值即可。

## 結論

在本步驟教學中，我們說明了 **如何產生 DataMatrix** ECC 200 條碼，探討了 **Aspose 條碼產生** 的優勢，並示範了可直接嵌入任何 .NET 專案的 **產生條碼影像 C#** 程式碼。請自行嘗試 Aspose 提供的各種設定選項，將條碼調整至最符合您需求的狀態。

若在使用過程中遇到任何問題，歡迎前往 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 尋求協助。祝開發順利！

---

**最後更新：** 2026-01-12  
**測試版本：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}