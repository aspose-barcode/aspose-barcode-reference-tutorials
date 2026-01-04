---
date: 2026-01-04
description: 了解如何在使用 Aspose.BarCode for .NET 產生 Codabar 條碼時加入校驗碼。一步一步的指南，涵蓋 Mod10
  與 Mod16 校驗碼模式。
linktitle: Codabar Checksum Calculation
second_title: Aspose.BarCode .NET API
title: 如何使用 Aspose.BarCode for .NET 為 Codabar 條碼添加校驗碼
url: /zh-hant/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Aspose.BarCode for .NET 中為 Codabar 條碼加入校驗碼

Codabar 是一種廣泛應用的線性條碼符號，特別於物流、圖書館及醫療保健領域。為 Codabar 條碼加入校驗碼可大幅提升資料完整性，透過偵測抄寫錯誤以防止問題發生。在本教學中，您將學習 **如何在產生 Codabar 條碼時加入校驗碼**，並會看到 Mod10 與 Mod16 兩種校驗模式的實際運作。

## 快速答覆
- **在 Codabar 中「加入校驗碼」是什麼意思？** 它會啟用錯誤偵測位元，以驗證編碼資料的正確性。
- **支援哪些校驗碼模式？** Mod10（常用）與 Mod16（用於更高精度的情境）。
- **使用此功能是否需要授權？** 是的，正式環境必須擁有有效的 Aspose.BarCode for .NET 授權。
- **相容的 .NET 版本有哪些？** 此函式庫支援 .NET Framework 4.5 以上、.NET Core 3.1 以上，以及 .NET 5/6/7。
- **產生的影像儲存於何處？** 會儲存至您在 `path` 變數中指定的資料夾。

## 什麼是 Codabar 中的「加入校驗碼」？
加入校驗碼是指設定條碼產生器，根據您提供的資料計算並附加額外的數字（或多位數字）。掃描器會驗證這些額外資訊，以降低讀取錯誤的機率。

## 為何要產生帶校驗碼的 Codabar 條碼？
- **提升可靠性：** 能偵測單一字元錯誤及大多數顛倒錯誤。
- **符合規範：** 某些行業（例如血庫）要求使用帶校驗碼的條碼。
- **彈性：** Aspose.BarCode 只需更改一個屬性即可在 Mod10 與 Mod16 之間切換。

## 先決條件

在開始之前，請確保您已具備以下項目：

1. **Aspose.BarCode for .NET** – 從 [here](https://releases.aspose.com/barcode/net/) 下載最新版本。  
2. **C# 開發環境** – 如 Visual Studio、VS Code，或任何支援 .NET 開發的 IDE。

現在環境已備妥，讓我們一步步完成實作。

## 匯入命名空間

在 C# 檔案的最上方加入必要的命名空間，以便存取條碼產生類別：

```csharp
using Aspose.BarCode.Generation;
```

## 步驟 1：初始化條碼產生器

建立 `BarcodeGenerator` 實例，指定 Codabar 符號，並提供欲編碼的資料。請將 `"Your Directory Path"` 替換為實際欲儲存影像的資料夾路徑。

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

## 步驟 2：產生 **不含** 校驗碼的 Codabar 條碼

若需要純條碼（無校驗碼），將校驗碼選項設為 `Default`。這對不預期校驗碼位元的舊有系統很有用。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

## 步驟 3：產生帶 **Mod10** 校驗碼的 Codabar 條碼

啟用校驗碼並選擇 Mod10 演算法。這是 Codabar 最常用的校驗碼模式。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

## 步驟 4：產生帶 **Mod16** 校驗碼的 Codabar 條碼

對於需要更高錯誤偵測能力的應用，請切換至 Mod16。程式碼變更極少——只需更新 `CodabarChecksumMode`。

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

透過這四個簡單步驟，您已學會 **如何在 Codabar 條碼加入校驗碼**，以及如何使用 Aspose.BarCode for .NET 在 Mod10 與 Mod16 模式之間切換。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 產生的影像為空白 | `path` 指向不存在的資料夾 | 確保資料夾存在，或在儲存前使用 `Directory.CreateDirectory(path)` 建立。 |
| 未套用校驗碼 | `IsChecksumEnabled` 保持為 `Default` | 在儲存前設定 `IsChecksumEnabled = EnableChecksum.Yes`。 |
| 校驗碼模式錯誤 | 使用了錯誤的列舉值 | 根據需求使用 `CodabarChecksumMode.Mod10` 或 `CodabarChecksumMode.Mod16`。 |

## 結論

本指南說明了在使用 Aspose.BarCode for .NET 產生 Codabar 條碼時 **如何加入校驗碼**，展示了 Mod10 與 Mod16 兩種校驗模式，並強調了帶校驗碼條碼對資料完整性的重要性。歡迎嘗試不同的資料字串，並探索 Aspose 提供的豐富條碼客製化選項。

若您遇到任何問題，Aspose.BarCode 社群可於 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 提供協助。

## 常見問答

### Q1：什麼是 Codabar？

A1：Codabar 是一種線性條碼符號，常用於各行各業的標籤與識別用途。

### Q2：為何在 Codabar 條碼中計算校驗碼很重要？

A2：校驗碼計算為資料完整性增添一層保護，確保編碼資訊的準確與無誤。

### Q3：如何取得 Aspose.BarCode for .NET 的暫時授權？

A3：您可從 [here](https://purchase.aspose.com/temporary-license/) 取得暫時授權。

### Q4：Aspose.BarCode for .NET 是否相容於不同的 .NET 框架？

A4：是的，Aspose.BarCode for .NET 相容於多種 .NET 框架，具備彈性且適用於廣泛的應用。

### Q5：在哪裡可以找到 Aspose.BarCode for .NET 的完整文件？

A5：您可於 [here](https://reference.aspose.com/barcode/net/) 取得完整文件。

## 常見問題

**Q：我可以在圖書館書籍條碼使用 Mod16 校驗碼嗎？**  
A：當然可以。Mod16 提供更強的錯誤偵測，對於圖書館等高流量環境非常有益。

**Q：啟用校驗碼會影響掃描速度嗎？**  
A：額外的數字幾乎不增加處理時間，大多數掃描器都能在不明顯延遲的情況下處理。

**Q：如何以程式方式驗證校驗碼？**  
A：產生條碼後，可使用相同的 `CodabarChecksumMode` 重新計算校驗碼，並與編碼字串的最後一個字元比較。

**Q：能否自訂校驗碼位元的外觀？**  
A：可以。使用 `BarcodeGenerator` 的外觀設定（例如 `BarHeight`、`ForeColor`）來樣式化整個條碼，包括校驗碼位元。

**Q：如果需要在迴圈中產生多個條碼該怎麼做？**  
A：建立單一的 `BarcodeGenerator`，在每次迭代時更新 `CodeText` 屬性，並以唯一的檔名呼叫 `Save`。

---

**最後更新：** 2026-01-04  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}