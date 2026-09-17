---
date: 2026-02-28
description: 了解如何在 .NET 中使用 Aspose 建立一維 Databar 2D 條碼產生器。請遵循我們的逐步指南進行設定與自訂。
linktitle: One-Dimensional Databar 2D Component Configuration
second_title: Aspose.BarCode .NET API
title: 建立條碼產生器 Aspose – Databar 2D 設定
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 單維 Databar 2D 元件設定

在本教學中，您將 **create barcode generator Aspose** 用於單維 Databar 2D 元件，使用 Aspose.BarCode .NET 函式庫。無論您是製作零售標籤、庫存標籤，或任何需要緊湊高密度資料的應用程式，本指南將逐步說明從專案設定到儲存最終 PNG 圖像的每一步。

## 快速問答
- **2D 元件旗標的作用是什麼？** 它告訴產生器是否在 Databar 條碼中嵌入複合 2D 符號。  
- **我可以變更 X‑dimension 嗎？** 可以，`XDimension.Pixels` 屬性控制模組寬度。  
- **範例中使用哪種影像格式？** PNG，透過 `BarCodeImageFormat.Png`。  
- **開發時需要授權嗎？** 免費試用可用於測試；正式上線需購買商業授權。  
- **此程式碼相容 .NET Core 嗎？** 當然相容——Aspose.BarCode 支援 .NET Framework 與 .NET Core。

## 什麼是單維 Databar 2D 元件？
Databar 2D 元件將傳統線性條碼與一個小型 2D 複合符號結合，使您能在不增加條碼整體尺寸的情況下儲存額外資訊（例如 URL 或其他資料欄位）。

## 為什麼在此任務中使用 Aspose.BarCode？
- **完整的 .NET 整合** – 可無縫於 C# 專案使用。  
- **豐富的設定 API** – 可調整尺寸、啟用/停用 2D 元件，並從多種輸出格式中選擇。  
- **無外部相依性** – 此函式庫自包含，使部署變得簡單。

## 先決條件
1. **安裝** – 確保已安裝 Aspose.BarCode for .NET。可從網站 [here](https://releases.aspose.com/barcode/net/) 下載。  
2. **基礎知識** – 熟悉 C# 與 .NET 開發將有助於您跟隨步驟。  
3. **開發環境** – Visual Studio、Rider，或任何相容 C# 的編輯器。

掌握上述基礎後，讓我們開始設定 Databar 2D 元件。

## 匯入命名空間
首先需要匯入 Aspose.BarCode 命名空間，以便存取其類別。

```csharp
using Aspose.BarCode;
```

## 定義輸出路徑
指定產生的條碼圖像在檔案系統中的儲存位置。

```csharp
string path = "Your Directory Path";
```

將 `"Your Directory Path"` 替換為您機器上實際的資料夾路徑。

## 建立條碼產生器
使用 Databar Expanded 類型實例化 `BarcodeGenerator`，並提供要編碼的資料。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DatabarExpanded, "(01)12345678901231");
```

您可以自行將範例資料替換為自己的 GS1‑application 識別碼或其他有效負載。

## 如何為單維 Databar 2D 建立 Aspose 條碼產生器
現在設定視覺屬性與 2D 元件旗標，然後儲存圖像。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;

// Disable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = false;
gen.Save($"{path}Databar2DComponentDisabled.png", BarCodeImageFormat.Png);

// Enable 2D component flag
gen.Parameters.Barcode.DataBar.Is2DCompositeComponent = true;
gen.Save($"{path}Databar2DComponentEnabled.png", BarCodeImageFormat.Png);
```

- **XDimension** 控制每個條碼模組的寬度。  
- 將 `Is2DCompositeComponent` 設為 **false** 會產生純線性 Databar。  
- 將其設為 **true** 會加入複合 2D 符號，可用於編碼額外資料。

## 常見問題與技巧
- **Invalid Path** – 確認資料夾已存在且應用程式具有寫入權限。  
- **License Exception** – 若看到授權警告，請在產生條碼前套用您的 Aspose 授權。  
- **Image Not Visible** – 確認 `BarCodeImageFormat` 與您使用的檔案副檔名相符。

## 結論
您現在已學會如何 **create barcode generator Aspose** 用於單維 Databar 2D 元件，切換 2D 複合旗標並調整 X‑dimension。此彈性方法讓您能將條碼套用於各種商業情境。欲進一步自訂，請參考完整的 Aspose.BarCode 文件：[Aspose.BarCode for .NET Documentation](https://reference.aspose.com/barcode/net/)。

如果您需要更多範例或遇到挑戰，Aspose 社群是提問的好去處。

## 常見問答
### Aspose.BarCode for .NET 是否相容各種條碼類型？
**是**，Aspose.BarCode for .NET 支援廣泛的條碼類型，使其在各種應用中具高度彈性。

### 我可以自訂產生的條碼外觀嗎？
**當然可以！** 您可以調整條碼的尺寸、顏色及其他多項視覺屬性，以符合需求。

### Aspose.BarCode for .NET 有哪些授權選項？
**有**，Aspose 提供多種授權方案以滿足不同需求，您可於官網上了解。

### Aspose.BarCode 適合新手與有經驗的開發者嗎？
**Aspose.BarCode 設計友善，適合新手與有經驗的開發者使用。**

### 我可以在哪裡取得 Aspose.BarCode for .NET 的支援與協助？
您可於 [Aspose.BarCode for .NET support forum](https://forum.aspose.com/c/barcode/13) 尋求協助並與社群互動。

## 常見問題
**Q: 我可以產生除 PNG 之外的其他格式條碼嗎？**  
A: 可以，`Save` 方法透過指定相應的 `BarCodeImageFormat` 支援 BMP、JPEG、GIF、TIFF 等格式。

**Q: 如何為條碼套用自訂顏色？**  
A: 使用 `gen.Parameters.Barcode.ForeColor` 與 `gen.Parameters.Barcode.BackColor` 設定前景與背景顏色。

**Q: 能否在條碼圖像中嵌入標誌？**  
A: Aspose.BarCode 提供 `Image` 屬性，允許在條碼產生後覆蓋標誌。

**Q: 支援哪些 .NET 版本？**  
A: 此函式庫相容 .NET Framework 4.5 以上、 .NET Core 3.1 以上、 .NET 5 以上，以及 .NET 6 以上。

**Q: 如何提升低解析度列印的掃描可靠性？**  
A: 提高 `XDimension` 數值，並確保條碼與背景之間有足夠的對比度。

---

**最後更新：** 2026-02-28  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}