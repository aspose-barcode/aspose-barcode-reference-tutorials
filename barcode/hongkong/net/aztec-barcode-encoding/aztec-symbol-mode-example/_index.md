---
date: 2026-01-02
description: 學習如何在 Aspose.BarCode for .NET 中使用 Aztec 條碼產生器——逐步指南，說明如何設定 Aztec 符號模式（自動、全範圍、緊湊、符文）。
linktitle: Aztec Symbol Mode Example
second_title: Aspose.BarCode .NET API
title: 條碼產生器 Aztec – 精通 Aztec 符號模式，使用 Aspose.BarCode for .NET
url: /zh-hant/net/aztec-barcode-encoding/aztec-symbol-mode-example/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# barcode generator aztec – 掌握 Aztec Symbol Mode 與 Aspose.BarCode for .NET

## 快速回答
- **主要類別是什麼？** `BarcodeGenerator` from `Aspose.BarCode.Generation`.
- **可用的 Symbol Modes 有哪些？** Auto, FullRange, Compact, and Rune.
- **我需要授權嗎？** A temporary license works for testing; a full license is required for production.
- **我可以更改代碼文字嗎？** Yes, set `gen.CodeText` before saving.
- **支援哪些影像格式？** PNG, JPEG, BMP, GIF, TIFF, and more.

## 什麼是 barcode generator aztec？
barcode generator aztec 會產生二維 Aztec 碼，這是一種緊湊的矩陣條碼，能在小空間內儲存大量資料。它非常適合用於行動票券、URL 以及空間受限的二進位資料。

## 為什麼使用 Aspose.BarCode for .NET？
- **完整的 .NET 支援** – 可在 .NET Framework、.NET Core 以及 .NET 5/6 上運作。
- **功能豐富** – 多種 Symbol Mode、錯誤更正與廣泛的自訂功能。
- **無外部相依性** – 完全在程式內部產生條碼。
- **跨平台** – 可在 Windows、Linux 與 macOS 上執行。

## 前置條件

- 具備 .NET 開發的基礎知識。  
- 機器上已安裝 Visual Studio。  
- 一份 Aspose.BarCode for .NET。您可以在此處下載 [here](https://releases.aspose.com/barcode/net/)。

現在您已準備就緒，讓我們來探索 Aztec Symbol Mode 的選項。

## 如何使用 barcode generator aztec 設定 Aztec Symbol Mode

### 匯入命名空間

首先，在 C# 檔案的頂部加入所需的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

匯入命名空間後，即可開始建立 Aztec 條碼。

### 步驟 1：設定 Barcode Generator

使用 Aztec 編碼類型初始化產生器，並提供要編碼的文字：

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

> **小技巧：** 請使用相容 UTF‑8 的字串來處理國際字符，如上例所示。

### 步驟 2：將 Symbol Mode 設為 Auto

**Auto** 模式會讓函式庫根據資料長度自動決定最佳尺寸：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

產生的 PNG 會儲存至您指定的資料夾。

### 步驟 3：將 Symbol Mode 設為 FullRange

若您希望函式庫使用 Aztec 符號尺寸的完整範圍，請選擇 **FullRange**：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

### 步驟 4：將 Symbol Mode 設為 Compact

若需更緊湊且仍具良好可讀性的條碼，請使用 **Compact**：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

### 步驟 5：將 Symbol Mode 設為 Rune

**Rune** 模式是為需要不同視覺風格的特殊使用情境而設計的：

```csharp
gen.CodeText = "123"; // Change the code text if needed
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

### 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| 條碼影像為空白 | 確認 `path` 指向一個已存在且可寫入的目錄。 |
| 不支援的字元 | 僅使用 Aztec 標準支援的字元，或改用 UTF‑8 編碼。 |
| 符號尺寸不正確 | 嘗試使用 `AztecSymbolMode.Auto`，讓函式庫自行選擇最佳尺寸。 |

## 常見問答

**Q: Aztec Symbol Mode 在條碼產生中的目的為何？**  
A: 它讓您能控制 Aztec 碼的視覺密度與錯誤更正等級，依據空間與可讀性需求調整條碼。

**Q: 我可以在 Aspose.BarCode for .NET 中更改 Aztec 條碼的代碼文字嗎？**  
A: 可以，只需在呼叫 `Save` 前將新字串指派給 `gen.CodeText`。

**Q: Aspose.BarCode for .NET 有免費試用版嗎？**  
A: 有，您可在此處下載免費試用版 [here](https://releases.aspose.com/)。

**Q: 在哪裡可以找到 Aspose.BarCode for .NET 的完整文件？**  
A: 完整的 API 參考可於此處取得 [here](https://reference.aspose.com/barcode/net/)。

**Q: 如何取得 Aspose.BarCode for .NET 的臨時授權？**  
A: 可透過此連結申請臨時授權 [this link](https://purchase.aspose.com/temporary-license/)。

## 結論

本指南涵蓋了使用 **barcode generator aztec** 搭配 Aspose.BarCode for .NET 所需的全部知識，從設定產生器到精通每種 Symbol Mode（Auto、FullRange、Compact、Rune）。有了這些範例，您現在可以快速且可靠地將多功能的 Aztec 條碼嵌入任何 .NET 應用程式中。

若您有其他問題，歡迎加入 Aspose.BarCode 社群的 [support forum](https://forum.aspose.com/c/barcode/13) 交流。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}

---

**最後更新：** 2026-01-02  
**測試環境：** Aspose.BarCode 24.10 for .NET  
**作者：** Aspose