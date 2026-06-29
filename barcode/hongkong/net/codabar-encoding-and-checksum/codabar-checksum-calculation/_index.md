---
date: 2026-06-29
description: 了解如何使用 Aspose.BarCode for .NET 產生帶校驗碼的 Codabar 條碼。逐步說明，涵蓋 Mod10 與 Mod16
  校驗碼模式。
keywords:
- generate codabar barcode
- aspose barcode .net
- codabar checksum
- mod10 checksum
- mod16 checksum
linktitle: Codabar 校驗碼計算
schemas:
- author: Aspose
  dateModified: '2026-06-29'
  description: Learn how to generate Codabar barcode with checksum using Aspose.BarCode
    for .NET. Step‑by‑step guide covering Mod10 and Mod16 checksum modes.
  headline: Generate Codabar barcode with checksum (Aspose.BarCode .NET)
  type: TechArticle
- questions:
  - answer: Absolutely. Mod16 provides stronger error detection, which is beneficial
      for high‑throughput environments like libraries.
    question: Can I use the Mod16 checksum for library book barcodes?
  - answer: The additional digit adds negligible processing time; most scanners handle
      it without noticeable delay.
    question: Does enabling checksum affect scanning speed?
  - answer: After generating the barcode, recompute the checksum using the same `CodabarChecksumMode`
      and compare it to the last character of the encoded string.
    question: How do I verify the checksum programmatically?
  - answer: Yes. Use the `BarcodeGenerator` appearance settings (e.g., `BarHeight`,
      `ForeColor`) to style the entire barcode, including the checksum digit.
    question: Is it possible to customize the appearance of the checksum digit?
  - answer: Instantiate a single `BarcodeGenerator`, update the `CodeText` property
      for each iteration, and call `Save` with a unique filename each time.
    question: What if I need to generate multiple barcodes in a loop?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: 產生帶校驗碼的 Codabar 條碼 (Aspose.BarCode .NET)
url: /zh-hant/net/codabar-encoding-and-checksum/codabar-checksum-calculation/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 產生帶校驗碼的 Codabar 條碼 (Aspose.BarCode .NET)

## 快速解答
- **「add checksum」對 Codabar 有何意義？** 它會加入一個錯誤偵測位元，以驗證編碼資料。  
- **支援哪些校驗模式？** Mod10（標準）和 Mod16（更高精度）。  
- **使用此功能是否需要授權？** 是 – 需要有效的 Aspose.BarCode for .NET 授權才能在正式環境使用。  
- **相容的 .NET 版本有哪些？** .NET Framework 4.5+、.NET Core 3.1+、.NET 5/6/7。  
- **產生的影像會儲存在哪裡？** 儲存於您在 `path` 變數中指定的資料夾。

## 如何產生帶校驗碼的 Codabar 條碼？

載入資料、啟用校驗碼、選擇 `CodabarChecksumMode.Mod10` 或 `CodabarChecksumMode.Mod16`，然後呼叫 `Save`。Aspose.BarCode 會自動計算並附加校驗位元，讓您一次呼叫即可取得可直接掃描的影像。儲存時亦可指定輸出資料夾、檔名與影像格式（例如 PNG）。

## 為何要為 Codabar 條碼加入校驗碼？

加入校驗碼可將單字元錯誤降低 **最高 99.9%**，並捕捉大多數顛倒錯誤，這對血庫等行業尤為重要，因為單一數字錯誤可能造成嚴重後果。它同時符合多項物流標準的法規要求。

## 前置條件

1. **Aspose.BarCode for .NET** – 從 [here](https://releases.aspose.com/barcode/net/) 下載最新版本。  
2. **C# 開發環境** – Visual Studio、VS Code，或任何支援 .NET 的 IDE。

現在一切就緒，讓我們一步步走過實作流程。

## 匯入命名空間

`BarcodeGenerator` 類別位於 `Aspose.BarCode.Generation` 命名空間。請在檔案頂部匯入它：

`using Aspose.BarCode.Generation;`

## 什麼是 BarcodeGenerator 類別？

`BarcodeGenerator` 類別是 Aspose.BarCode 的核心物件，用於建立、設定與繪製條碼影像。它封裝了所有條碼相關設定，如條碼類型、文字、尺寸與校驗碼選項，讓您只需一次 `Save` 呼叫即可產生影像。透過修改其 `Parameters` 屬性，您可以自訂外觀、編碼模式與錯誤偵測功能，適用於任何支援的條碼類型。

## 步驟 1：初始化 Barcode Generator

建立 `BarcodeGenerator` 實例，指定 Codabar 條碼類型，並提供您要編碼的資料。將 `"Your Directory Path"` 替換為實際想要儲存影像的資料夾路徑。

`var generator = new BarcodeGenerator(EncodeTypes.Codabar, "A123456A");`  
`string path = @"Your Directory Path";`

## 步驟 2：產生 **不含** 校驗碼的 Codabar 條碼

如果舊有系統只接受純條碼，請將校驗碼選項設為 `Default`。這會停用額外的校驗位元。

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;`  
`generator.Save($"{path}\\Codabar_NoChecksum.png", BarCodeImageFormat.Png);`

## 步驟 3：產生帶 **Mod10** 校驗碼的 Codabar 條碼

啟用校驗碼並選擇 Mod10 演算法，這是 Codabar 最常用的模式。

`generator.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;`  
`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod10;`  
`generator.Save($"{path}\\Codabar_Mod10.png", BarCodeImageFormat.Png);`

## 步驟 4：產生帶 **Mod16** 校驗碼的 Codabar 條碼

在需要更高錯誤偵測的情況下，切換至 Mod16。此變更僅需設定單一屬性。

`generator.Parameters.Barcode.CodabarChecksumMode = CodabarChecksumMode.Mod16;`  
`generator.Save($"{path}\\Codabar_Mod16.png", BarCodeImageFormat.Png);`

透過這四個簡單步驟，您已學會 **如何產生帶校驗碼的 Codabar 條碼**，以及如何使用 Aspose.BarCode for .NET 在 Mod10 與 Mod16 模式之間切換。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|-------|--------|-----|
| 產生的影像為空白 | `path` 指向不存在的資料夾 | 確保資料夾存在，或在儲存前呼叫 `Directory.CreateDirectory(path)` |
| 未套用校驗碼 | `IsChecksumEnabled` 保持為 `Default` | 在儲存前設定 `IsChecksumEnabled = EnableChecksum.Yes` |
| 校驗碼模式錯誤 | 使用了錯誤的列舉值 | 根據需求使用 `CodabarChecksumMode.Mod10` 或 `CodabarChecksumMode.Mod16` |

## 常見問與答

**Q: 我可以在圖書館書籍條碼使用 Mod16 校驗碼嗎？**  
A: 當然可以。Mod16 提供更強的錯誤偵測，對於圖書館等高吞吐量環境非常有益。

**Q: 啟用校驗碼會影響掃描速度嗎？**  
A: 額外的位元幾乎不增加處理時間；大多數掃描器都能在不明顯延遲的情況下處理。

**Q: 如何以程式方式驗證校驗碼？**  
A: 產生條碼後，使用相同的 `CodabarChecksumMode` 重新計算校驗碼，並與編碼字串的最後一個字元比較。

**Q: 可以自訂校驗碼位元的外觀嗎？**  
A: 可以。使用 `BarcodeGenerator` 的外觀設定（例如 `BarHeight`、`ForeColor`）來樣式化整個條碼，包括校驗碼位元。

**Q: 如果需要在迴圈中產生多個條碼該怎麼辦？**  
A: 建立單一個 `BarcodeGenerator`，在每次迭代時更新 `CodeText` 屬性，並以唯一的檔名呼叫 `Save`。

如果遇到任何問題，Aspose.BarCode 社群會在 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 提供協助。

---

**最後更新：** 2026-06-29  
**測試環境：** Aspose.BarCode 24.11 for .NET  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("CodabarChecksum:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Codabar, "-12345-");
```

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Default;
gen.Save($"{path}CodabarChecksumNone.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod10;
gen.Save($"{path}CodabarChecksumMod10.png", BarCodeImageFormat.Png);
```

```csharp
gen.Parameters.Barcode.IsChecksumEnabled = EnableChecksum.Yes;
gen.Parameters.Barcode.Codabar.CodabarChecksumMode = CodabarChecksumMode.Mod16;
gen.Save($"{path}CodabarChecksumMod16.png", BarCodeImageFormat.Png);
```

## 相關教學

- [在 Aspose.BarCode for .NET 中產生帶起止字元的 Codabar 條碼](/barcode/net/codabar-encoding-and-checksum/codabar-start-stop-characters/)
- [Aspose.BarCode for .NET 的完整教學與範例](/barcode/net/)
- [產生 DataMatrix 條碼 – Aspose.BarCode 專業指南](/barcode/net/datamatrix-barcode-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}