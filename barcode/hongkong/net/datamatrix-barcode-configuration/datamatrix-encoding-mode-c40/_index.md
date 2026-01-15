---
date: 2026-01-15
description: 學習如何在使用 Aspose.BarCode for .NET 的 DataMatrix 編碼模式（C40）時儲存 PNG 檔案——一步一步的條碼教學。
linktitle: DataMatrix Encoding Mode (C40)
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode 以 DataMatrix C40 保存 PNG
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 的 DataMatrix 主編碼模式 (C40)

## 簡介

如果您正在尋找一個清晰、實用的指南，說明 **how to save PNG** 檔案的同時產生 DataMatrix 條碼，您來對地方了。無論您是構建庫存系統、運輸標籤產生器，或任何需要緊湊、高密度條碼的解決方案，掌握 C40 編碼模式都能為您提供尺寸效率與可靠的資料表示。在本教學中，我們將從前置條件走到最終 PNG 輸出，逐步說明 **step by step barcode** 的建立過程，使用 Aspose.BarCode for .NET。

## 快速答案
- **「how to save png」指的是什麼？** 將產生的條碼儲存為 PNG 圖像檔案。  
- **涵蓋哪種編碼模式？** DataMatrix C40 編碼。  
- **需要授權嗎？** 免費試用可用於測試；正式環境需購買授權。  
- **可以在 .NET Core 上執行嗎？** 可以，Aspose.BarCode 同時支援 .NET Framework 與 .NET Core。  
- **產生的檔案格式是什麼？** PNG（Portable Network Graphics）圖像。

## 如何使用 DataMatrix C40 編碼儲存 PNG
將條碼儲存為 PNG 是在完成生成器設定後的最後一步。`Save` 方法接受檔案路徑、檔名以及圖像格式 (`BarCodeImageFormat.Png`)；這確保條碼以無失真的格式儲存，能在瀏覽器、印表機與行動裝置上正常顯示。

## 什麼是 DataMatrix 編碼模式 (C40)？
C40 是一種針對字母與數字資料的高效字元集，能在較小的 DataMatrix 符號中容納更多資訊。當需要編碼包含字母、數字以及有限特殊字元的文字時，特別適用。

## 為什麼使用 Aspose.BarCode for .NET？
- **完整控制** 條碼尺寸、錯誤更正與編碼模式。  
- **零相依** 產生——不需外部服務。  
- **跨平台** 支援 .NET Framework、.NET Core 以及 .NET 5/6 以上版本。  

## 先決條件

在開始撰寫程式碼前，請確保您已具備以下條件：

1. **.NET 開發環境** – Visual Studio、Rider 或任何支援 C# 的 IDE。  
2. **Aspose.BarCode for .NET** – 透過 NuGet 或官方安裝程式安裝。詳情請參閱[文件說明](https://reference.aspose.com/barcode/net/)。  
3. **基本的 C# 知識** – 需要熟悉命名空間、類別與 using 陳述式。  
4. **可寫入的資料夾** – 您機器上用來存放 PNG 的目錄。

## 匯入必要的命名空間

在 C# 原始檔的最上方加入所需的命名空間，以便存取條碼產生類別：

```csharp
using Aspose.BarCode.Generation;
```

## 逐步條碼產生

以下是一個 **step by step barcode** 的完整示範。每一步都以簡單語言說明，且原始程式碼保持不變，方便直接複製貼上。

### 步驟 1：定義目錄路徑
設定 PNG 圖像要儲存的資料夾。請將佔位符替換為您機器上的實際路徑。

```csharp
string path = "Your Directory Path";
```

### 步驟 2：設定條碼產生
建立 `BarcodeGenerator` 實例，指定 `EncodeTypes.DataMatrix`，並提供要編碼的資料。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### 步驟 3：自訂條碼
設定 X‑dimension（模組的像素寬度），並將編碼模式切換為 C40。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### 步驟 4：儲存條碼影像
最後，將產生的條碼儲存為 PNG 檔案。這就是 **how to save png** 與 Aspose.BarCode 結合的具體解答。

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

執行程式後，您會在先前指定的資料夾中看到 `DataMatrixEncodeModeC40.png`，即可用於報表、標籤或網頁。

## 常見問題與技巧

- **Invalid Path** – 確認目錄已存在且您具有寫入權限，否則 `gen.Save` 會拋出例外。  
- **Incorrect Encoding Mode** – 若需編碼超出 C40 集合的字元，請切換至 `DataMatrixEncodeMode.Auto` 或其他適當模式。  
- **Image Size** – 調整 `XDimension.Pixels` 可在不影響可讀性的前提下增減條碼整體大小。

## 常見問答

**Q: 什麼是 DataMatrix 編碼模式 (C40)？**  
A: C40 是一種緊湊的字母數字編碼方案，適用於包含字母、數字及有限特殊字元的 DataMatrix 符號。

**Q: 在哪裡可以找到 Aspose.BarCode for .NET 的文件說明？**  
A: 您可在[此處](https://reference.aspose.com/barcode/net/)取得文件說明，裡面提供了所有條碼類型與編碼選項的詳細指引。

**Q: Aspose.BarCode for .NET 是否相容所有 .NET 版本？**  
A: 是的，該函式庫支援廣泛的 .NET 版本，從 .NET Framework 4.5 以上到 .NET 6 及更高版本皆可使用。

**Q: 購買前可以先試用 Aspose.BarCode for .NET 嗎？**  
A: 可以，您可透過[此連結](https://releases.aspose.com/)下載免費試用版，測試函式庫的功能與效能。

**Q: 在哪裡可以取得 Aspose.BarCode for .NET 的支援？**  
A: 您可在[Aspose 論壇](https://forum.aspose.com/c/barcode/13)找到社群與技術支援。

## 結論

透過本 **step by step barcode** 教學，您現在已清楚了解如何使用 Aspose.BarCode for .NET 以 DataMatrix C40 編碼 **how to save PNG** 檔案。此方法讓您完整掌控條碼的外觀、尺寸與資料表示，輕鬆將高品質條碼整合至任何 .NET 應用程式中。

---

**最後更新：** 2026-01-15  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}