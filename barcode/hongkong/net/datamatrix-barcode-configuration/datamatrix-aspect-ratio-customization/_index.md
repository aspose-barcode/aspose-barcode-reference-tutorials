---
date: 2026-01-12
description: 學習如何使用 Aspose.BarCode for .NET 以自訂 DataMatrix 長寬比建立條碼 PNG。逐步指南，說明條碼生成與尺寸自訂。
linktitle: DataMatrix Aspect Ratio Customization
second_title: Aspose.BarCode .NET API
title: 產生條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 建立條碼 PNG – DataMatrix 長寬比 – Aspose.BarCode

產生 **barcode PNG** 並使用自訂的 DataMatrix 長寬比是常見需求，尤其當條碼必須符合特定版面限制時。本教學將逐步說明如何使用 Aspose.BarCode for .NET **建立條碼 PNG** 檔案，解釋為何需要調整長寬比，並示範如何為您的應用程式微調輸出結果。

## 快速解答
- **「長寬比」控制什麼？** 它定義 DataMatrix 模組的寬度與高度比例。  
- **可以輸出 PNG、JPEG 或 SVG 嗎？** 可以 – `Save` 方法支援 PNG、JPEG、BMP、GIF 等多種格式。  
- **使用此功能需要授權嗎？** 開發階段可使用免費試用版；正式上線需購買完整授權。  
- **支援哪些 .NET 版本？** .NET Framework 4.x、.NET Core 3.1+、.NET 5/6/7。  
- **有效的長寬比值有多少種？** 任意正浮點數；常見範圍為 0.5 – 2.0。

## 什麼是 DataMatrix 條碼，為何要調整長寬比？
DataMatrix 是一種二維矩陣條碼，能在小空間內儲存大量資料。調整 **長寬比** 可讓您水平拉伸或壓縮模組，方便將條碼放入窄欄或寬標籤中，同時不影響可讀性。

## 前置作業

在開始自訂 DataMatrix 長寬比之前，請先確保具備以下條件：

1. **Visual Studio** – 任一較新版皆可。  
2. **Aspose.BarCode for .NET** – 前往[此處](https://releases.aspose.com/barcode/net/)下載。  
3. **.NET Framework / .NET Core** – 專案必須目標支援的版本。

## 匯入命名空間

首先，在 C# 專案中匯入必要的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

> **小技巧：** 請將此 `using` 陳述式放在檔案最上方，確保 `BarcodeGenerator` 類別隨時可用。

## 步驟說明

### 步驟 1：設定專案
在 Visual Studio 中建立新的 Console 或 Windows Forms 專案，並加入 Aspose.BarCode DLL 的參考。

### 步驟 2：初始化條碼產生器
建立 `BarcodeGenerator`，指定 DataMatrix 類型與要編碼的資料：

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
```

> 這行程式碼會建立一個可產生 DataMatrix 條碼的產生器，條碼內容為範例文字。

### 步驟 3：自訂長寬比並儲存 PNG 檔案
現在可以變更 **長寬比**，並將每個版本儲存為 PNG 圖片：

```csharp
gen.Parameters.Barcode.DataMatrix.AspectRatio = 1;
gen.Save($"{path}DataMatrixAspectRatio1.png", BarCodeImageFormat.Png);

gen.Parameters.Barcode.DataMatrix.AspectRatio = 0.5f;
gen.Save($"{path}DataMatrixAspectRatio0.5.png", BarCodeImageFormat.Png);
```

- 第一次呼叫產生正方形比例的條碼（`AspectRatio = 1`）。  
- 第二次呼叫水平壓縮條碼（`AspectRatio = 0.5`），呈現較寬的外觀。

如此即可得到兩個 **barcode PNG** 檔案，分別使用不同長寬比，供報表、標籤或 UI 元件使用。

## 常見問題與解決方案
| 問題 | 解決方案 |
|------|----------|
| **產生的影像模糊** | 在儲存前提高 `Resolution` 參數（`gen.Parameters.ImageResolution = 300`）。 |
| **條碼無法掃描** | 確認長寬比維持在 0.5 – 2.0 之間，並保留足夠的靜區（`gen.Parameters.Barcode.CodeTextParameters.Margin`）。 |
| **檔案路徑錯誤** | 使用 `Path.Combine` 組合輸出路徑，並確認資料夾已存在。 |

## 常見問答

**Q: 可以使用 Aspose.BarCode for .NET 調整其他條碼類型的長寬比嗎？**  
A: 可以，許多 2‑D 條碼（例如 QR、PDF417）皆支援透過各自的參數物件調整長寬比。

**Q: Aspose.BarCode for .NET 有提供免費試用嗎？**  
A: 有，您可在[此處](https://releases.aspose.com/)取得免費試用版。

**Q: 哪裡可以購買 Aspose.BarCode for .NET 的授權？**  
A: 可於 Aspose 官方網站[此處](https://purchase.aspose.com/buy)購買。

**Q: Aspose.BarCode for .NET 是否相容不同的 .NET Framework 版本？**  
A: 相容，支援 .NET Framework 4.x、.NET Core 3.1+ 以及最新的 .NET 版本。

**Q: 能否使用 Aspose.BarCode for .NET 產生其他格式的條碼？**  
A: 完全支援 – PNG、JPEG、BMP、GIF、TIFF、SVG 以及 PDF 均可直接輸出。

## 結論

使用 Aspose.BarCode for .NET 調整 DataMatrix 條碼的 **長寬比** 並 **建立條碼 PNG** 檔案相當簡單。依照上述步驟操作，即可產生符合專案版面需求的條碼。您亦可進一步探索 `Resolution`、`Margin`、`Color` 等參數，以客製化輸出效果。

如需更深入的資訊，請參閱官方[文件](https://reference.aspose.com/barcode/net/)或加入[Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)交流。

---

**最後更新：** 2026-01-12  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}