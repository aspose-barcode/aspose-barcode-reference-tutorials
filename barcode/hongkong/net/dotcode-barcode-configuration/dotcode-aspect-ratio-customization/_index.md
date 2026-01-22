---
date: 2026-01-22
description: 了解如何使用 Aspose.BarCode for .NET 產生具有自訂 DotCode 長寬比的條碼圖像 – 快速一步一步的指南。
linktitle: DotCode Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 產生具自訂 DotCode 長寬比的條碼影像
url: /zh-hant/net/dotcode-barcode-configuration/dotcode-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用 Aspose.BarCode for .NET 產生自訂 DotCode 長寬比的條碼影像

## 介紹

如果您是需要 **產生條碼影像** 檔案且必須符合特定版面配置的 .NET 開發者，Aspose.BarCode for .NET 能讓這件事變得輕而易舉。其最強大的功能之一就是自訂 DotCode 的長寬比——非常適合醫療標籤、郵件標籤或任何空間受限的包裝。本教學將一步步說明從專案設定到最終影像儲存的完整流程。

## 快速答覆
- **「長寬比」控制什麼？** 它定義每個 DotCode 模組的高寬比例。  
- **為什麼要調整？** 為了在狹窄空間內放置條碼，或在不犧牲可讀性的前提下符合品牌規範。  
- **需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買商業授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.5 以上、.NET Core 3.1 以上、.NET 5/6/7。  
- **需要多久時間？** 不到五分鐘即可產生自訂的條碼影像。

## 什麼是 DotCode 條碼？

DotCode 是一種高密度的二維條碼，最多可儲存 1,500 個字元。它在需要緊湊且具錯誤容忍度的領域廣受採用——例如醫療設備、郵件分揀與庫存追蹤。

## 為什麼要自訂長寬比？

自訂長寬比可以讓您：

* 將條碼嵌入緊湊的標籤尺寸。  
* 與既有設計格線對齊。  
* 針對特定印表機解析度最佳化掃描效能。  

## 前置作業

在開始之前，請先確保您具備以下項目：

1. **Aspose.BarCode for .NET** – 前往 **[此處](https://releases.aspose.com/barcode/net/)** 下載程式庫。  
2. **IDE** – Visual Studio（任一較新版本）或其他相容 .NET 的編輯器。  
3. **輸出資料夾** – 決定條碼影像要儲存的路徑，並在程式碼中將 `"Your Directory Path"` 替換為實際路徑。

## 匯入命名空間

首先，匯入包含條碼產生類別的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

## 如何產生自訂 DotCode 長寬比的條碼影像

以下為逐步說明。每一步都會先提供簡短說明，接著給出可直接複製的程式碼。

### 步驟 1：初始化 BarcodeGenerator

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, "Aspose"))
{
    // Subsequent configuration goes here
}
```

我們建立 `BarcodeGenerator` 實例，指定 `EncodeTypes.DotCode`，並提供要編碼的資料字串 `"Aspose"`。

### 步驟 2：設定條碼的 X 方向尺寸

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 10;
```

X 方向尺寸決定每個模組的寬度。調整像素值即可讓整個條碼變大或變小。

### 步驟 3：自訂長寬比

```csharp
gen.Parameters.Barcode.DotCode.AspectRatio = 0.5f;
```

此處將長寬比設為 **0.5**（高度為寬度的一半）。您可依版面需求在 **0.2f** 至 **1.0f** 之間自行測試。

### 步驟 4：儲存產生的條碼影像

```csharp
gen.Save($"{path}DotCodeAspectRatio0.5.png", BarCodeImageFormat.Png);
```

將 `{path}` 替換為先前準備好的資料夾路徑。影像會以 PNG 格式儲存，方便嵌入報表、列印標籤或在 UI 中顯示。

## 常見問題與技巧

| 問題 | 解決方案 |
|------|----------|
| **條碼模糊不清** | 提高 `XDimension.Pixels` 數值或改為較高解析度的格式（例如 BMP）。 |
| **掃描器無法讀取** | 確認長寬比未過於極端，建議保持 ≥ 0.2。 |
| **找不到路徑錯誤** | 確認資料夾已存在且程式具有寫入權限。 |
| **授權例外** | 開發階段使用試用授權；部署前請套用正式商業授權。 |

## FAQ

### Q1：DotCode 條碼的長寬比是什麼？

A1：DotCode 條碼的長寬比指的是條碼中單一模組的高度與寬度之比例，可依需求自行調整。

### Q2：哪些產業會受惠於 DotCode 條碼？

A2：DotCode 常見於醫療、郵務與製造業等需要高效編碼資訊的領域。

### Q3：我可以使用 Aspose.BarCode for .NET 自訂 DotCode 的其他參數嗎？

A3：可以，Aspose.BarCode for .NET 提供豐富的自訂選項，讓您針對 DotCode 及其他條碼類型調整多項參數以符合需求。

### Q4：Aspose.BarCode for .NET 是否適用於 Web 與桌面應用程式？

A4：是的，Aspose.BarCode for .NET 可在 Web 與桌面應用程式中產生與操作條碼。

### Q5：在哪裡可以取得更多 Aspose.BarCode for .NET 的資訊與文件？

A5：您可前往 **[此處](https://reference.aspose.com/barcode/net/)** 瀏覽完整文件與範例。

## 常見問答

**Q：我可以產生 PNG 以外格式的條碼影像嗎？**  
A：當然可以。`Save` 方法支援 BMP、JPEG、GIF、TIFF 等多種格式，只要更改 `BarCodeImageFormat` 列舉值即可。

**Q：如何變更條碼的前景色？**  
A：在呼叫 `Save` 前加入 `gen.Parameters.Barcode.BarcodeColor = System.Drawing.Color.Blue;`。

**Q：能否在條碼下方加入可讀文字說明？**  
A：可以。設定 `gen.Parameters.Barcode.CodeLocation = CodeLocation.Below;`，並視需要調整 `gen.Parameters.Barcode.Font`。

**Q：長寬比會影響錯誤更正能力嗎？**  
A：錯誤更正等級不會改變，僅會改變每個模組的視覺形狀。

**Q：能否在迴圈中產生多個不同長寬比的條碼？**  
A：可以。將設定程式碼放入 `foreach` 迴圈，並為每次迭代調整 `AspectRatio`。

---

**最後更新：** 2026-01-22  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}