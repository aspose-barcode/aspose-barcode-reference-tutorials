---
date: 2026-01-20
description: 學習如何使用 Aspose.BarCode for .NET 以 ASCII 模式程式化建立條碼圖像。提供逐步說明與程式碼範例。
linktitle: DataMatrix Encoding Mode (ASCII)
second_title: Aspose.BarCode .NET API
title: 如何以程式方式建立條碼圖像 – 使用 Aspose.BarCode for .NET 進行 DataMatrix ASCII 編碼
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 以 ASCII 模式編碼 DataMatrix

## 介紹

如果您需要 **以程式方式建立條碼影像**，ASCII 模式的 DataMatrix 格式是一個快速且可靠的選擇。在本教學中，我們將使用 Aspose.BarCode for .NET，從 PNG示範整個流程。無論您是資深開發者或剛開始接觸條碼產生，都能找到清晰、口語化的說明與即用的程式碼範例。

## 快速回答
- **需要哪個函式庫？** Aspose.BarCode for .NET  
- **可以用一行程式碼產生權  
相是 DataMatrix ASCII 編碼？
DataMatrix 是一種二維條碼，能在極小的空間內儲存大量資料。ASCII 編碼模式直接對應每個字元，特別適合產品編號或短網址等字母數字字串。

## 為什麼使用 Aspose.BarCode for .NET？
Aspose.BarCode 提供高階 API，將條碼產生背後的複雜數學抽象化。只需幾個屬性設定，即可 **以程式方式建立條碼影像**，支援多種條碼格式，且提供豐富的客製化選項（尺寸、顏色、邊距等）。

## 前置條件

1. **開發環境** – Visual Studio、Visual Studio Code 或任何相容 .NET 的 IDE。  
2. **Aspose.BarCode for .NET** – 從 [here](https基本的 C# 知識** – 程式碼相當直接，但熟悉 C# 語法會更順手。

現在一切就緒，讓我們開始實作吧。

## 如何以程式方式使用 DataMatrix ASCII 模式建立條碼影像

### 匯入命名空間

首先，加入必要的命名空間，使產生器類別可用。

```csharp
using Aspose.BarCode.Generation;
```

### 步驟 1：建立目錄

選擇一個資料夾來儲存產生的條碼。將 `"Your Directory Path"` 替換為您機器上的絕對或相對路徑。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：以 ASCII 模式編碼資料

本教學的核心 – 我們實例化 `BarcodeGenerator`、設定 DataMatrix 參數、將編碼模式設為 ASCII，最後儲存影像。以下程式碼片段正好示範了如何 **以程式方式建立條碼影像**。

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

執行程式後，您會在先前指定的資料夾中看到名為 `DataMatrixEncodeModeASCII.png` 的檔案。使用任何影像檢視器開啟，即可看到產生的條碼。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| **檔案未儲存** | `path` 指向不存在的資料夾或缺乏寫入權限。 | 確認資料夾已建立，且應用程式具有寫入權限。 |
| **條碼模糊** | X‑dimension 設定過低，無法容納資料量。 | 提高 `gen.Parameters.Barcode.XDimension.Pixels`（例如設定為 6 或 8）。 |
| **不支援的字元** | ASCII 模式僅支援 0‑127 的字元。 | 若需二進位資料，請改用其他編碼模式（如 Base256）。 |

## 常見問答

**Q: 除了 C#，我可以在其他程式語言中使用 Aspose.BarCode for .NET 嗎？**  
A: Aspose.BarCode 支援多種語言（Java、Python 等），但本教學以 C# 為例。

**Q: DataMatrix 條碼有哪些不同的編碼模式？**  
A: 包括 ASCII、C40、Text 與 Base256，各自針對不同類型的資料進行最佳化。

**Q: 我可以自訂產生條碼的外觀，例如尺寸與顏色嗎？**  
A: 可以，透過 `Parameters.Barcode` 屬性調整尺寸、顏色、邊距等設定。

**Q: 有免費試用版的 Aspose.BarCode for .NET 嗎？**  
A: 有，您可以從 [here](https://releases.aspose.com/) 下載免費試用版。

**Q: 哪裡可以購買 Aspose.BarCode for .NET 的授權？**  
A: 可於 Aspose 官方網站的 [here](https://purchase.aspose.com/buy) 購買授權。

## 結論

本指南示範了如何使用 Aspose.BarCode for .NET 的 DataMatrix ASCII 編碼 **以程式方式建立條碼影像**。只需幾行程式碼，即可產生高品質條碼，適用於庫存系統、運送標籤或任何需要緊湊機器可讀資料的情境。歡迎自行嘗試其他編碼模式、顏色與尺寸，以符合您的特定需求。

如需更詳細資訊，請參考官方文件 [Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/) 或加入 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 社群交流。

---

**最後更新：** 2026-01-20  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}