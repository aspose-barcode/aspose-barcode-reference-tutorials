---
date: 2026-01-09
description: 學習如何使用 Aspose.BarCode for .NET 建立可自訂錯誤更正等級的 Aztec 條碼。提供逐步指南與程式碼範例。
linktitle: Aztec Error Level Example
second_title: Aspose.BarCode .NET API
title: 如何在 .NET 中建立具錯誤更正功能的 Aztec 條碼
url: /zh-hant/net/aztec-barcode-encoding/aztec-error-level-example/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 .NET 中建立具錯誤更正的 Aztec 條碼

在本分步教學中，您將學習如何使用 Aspose.BarCode for .NET 函式庫**建立 Aztec 條碼**圖像，並包含不同的錯誤更正等級。無論您需要用於包裝、票務或行動掃描的可靠條碼，控制錯誤等級都能協助您在資料容量與抗損毀性之間取得平衡。我們將逐一說明每個設定選項，展示您所需的完整程式碼，並解釋每個設定的意義。

## 快速回答
- **使用哪個函式庫？** Aspose.BarCode for .NET  
- **可以設定自訂錯誤等級嗎？** 可以 – 任意介於 0 % 到 100 % 的整數  
- **建議使用哪個 IDE？** Visual Studio（任何版本）或具 .NET 支援的 VS Code  
- **需要授權嗎？** 臨時授權可用於評估；正式使用需購買完整授權  
- **支援的輸出格式？** PNG、JPEG、BMP、GIF 等  

## 什麼是具錯誤更正的 Aztec 條碼？

Aztec 條碼是一種二維矩陣碼，可在緊湊的方形中儲存大量資料。錯誤更正會加入冗餘資料，使條碼即使部分受損或被遮蔽仍能被讀取。調整錯誤更正等級可讓您在較高資料容量（較低錯誤等級）與較高抗損毀性（較高錯誤等級）之間做選擇。

## 為什麼使用 Aspose.BarCode for .NET？

Aspose.BarCode 提供流暢的 API，抽象化低階編碼細節，讓您專注於業務邏輯。它支援多種條碼標準，提供廣泛的自訂功能（尺寸、顏色、邊距），且可在 .NET Framework、.NET Core 以及 .NET 5/6+ 上運作。這使其成為對可靠性與彈性要求極高的企業級應用的理想選擇。

## 前置條件

- 具備 C# 及 .NET 生態系統的基本知識。  
- Visual Studio、Visual Studio Code，或任何相容 C# 的 IDE。  
- Aspose.BarCode for .NET 函式庫 – 從 [此連結](https://releases.aspose.com/barcode/net/) 下載。  
- （可選）臨時授權以便無障礙試用 – 請於 [此處](https://purchase.aspose.com/temporary-license/) 取得。

## 匯入命名空間

首先，將所需的 Aspose.BarCode 命名空間加入您的專案：

```csharp
using Aspose.BarCode.Generation;
```

## 步驟 1：設定條碼產生器

建立 `BarcodeGenerator` 實例，指定 **Aztec** 類型，並提供您想要編碼的資料。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecErrorLevelExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde© is a powerful library to generate & recognize 1D & 2D barcodes");
```

> **小技巧：** 將 `"Your Directory Path"` 替換為您具有寫入權限的絕對或相對路徑。

## 步驟 2：定義 X‑Dimension

X‑Dimension 控制條碼中最小模組（像素）的寬度。將其設定為 4 像素即可產生清晰、可掃描的圖像。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 4;
```

## 步驟 3：選擇 Aztec Symbol Mode

Aztec 支援多種符號模式。使用 `FullRange` 可讓函式庫根據您的資料與錯誤更正設定自動選擇最佳尺寸。

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
```

## 步驟 4：設定錯誤更正容量

現在我們調整錯誤更正等級。在此範例中，我們建立兩個條碼——一個為 5 % 的適度錯誤等級，另一個為 50 % 的高容錯等級，以說明視覺差異。

```csharp
// Set error correction capacity to 5%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 5;
gen.Save($"{path}AztecErrorLevel5.png", BarCodeImageFormat.Png);

// Set error correction capacity to 50%
gen.Parameters.Barcode.Aztec.AztecErrorLevel = 50;
gen.Save($"{path}AztecErrorLevel50.png", BarCodeImageFormat.Png);
```

執行程式碼後會在指定資料夾產生兩個 PNG 檔案。50 % 版本包含更多冗餘資料，使其對損壞的容忍度更高，但會使符號略為變大。

## 常見問題與解決方案

| 症狀 | 可能原因 | 解決方式 |
|---------|--------------|-----|
| 條碼圖像模糊 | X‑Dimension 對於所選輸出尺寸過低 | 增加 `XDimension.Pixels`（例如調整為 6 或 8）。 |
| 儲存操作拋出 *AccessDenied* | 路徑無效或不可寫入 | 確認 `path` 變數指向可寫入的資料夾。 |
| 掃描器無法讀取條碼 | 錯誤等級對資料量而言過高 | 降低 `AztecErrorLevel` 或縮短編碼文字。 |

## 常見問答

**Q: 為什麼 Aztec 條碼需要錯誤更正？**  
A: 錯誤更正可確保即使條碼部分受損、劃痕或被遮蔽，仍能被讀取。較高的等級會加入更多冗餘，提高可靠性。

**Q: 我可以自訂產生的 Aztec 條碼外觀嗎？**  
A: 可以。除了 X‑Dimension 與錯誤等級外，您還能修改顏色、邊距，甚至使用其他 Aspose.BarCode 參數嵌入標誌。

**Q: Aspose.BarCode for .NET 是否支援其他條碼格式？**  
A: 當然支援。相同的 `BarcodeGenerator` 類別支援 QR Code、DataMatrix、PDF417、Code128 等多種條碼。

**Q: 使用 Aspose.BarCode for .NET 是否需要授權？**  
A: 評估期間可使用臨時授權。正式上線時，請從 [此連結](https://purchase.aspose.com/buy) 購買完整授權。

**Q: 我可以在哪裡找到官方文件？**  
A: 完整的 API 參考文件可在 [此處](https://reference.aspose.com/barcode/net/) 取得。

## 結論

現在您已了解如何使用 Aspose.BarCode for .NET **建立 Aztec 條碼** 圖像，並自訂錯誤更正等級。透過調整 X‑Dimension、符號模式與錯誤等級，您可以產生符合應用程式精確可靠性與尺寸需求的條碼。歡迎嘗試不同的資料字串與錯誤百分比，觀察條碼的變化。

如果您遇到任何問題，社群活躍於 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)，官方文件亦提供更深入的進階自訂說明。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-09  
**測試環境：** Aspose.BarCode 24.12 for .NET  
**作者：** Aspose