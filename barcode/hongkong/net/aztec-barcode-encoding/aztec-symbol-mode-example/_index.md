---
title: 使用 Aspose.BarCode for .NET 掌握 Aztec 符號模式
linktitle: 阿茲特克符號模式範例
second_title: Aspose.BarCode .NET API
description: 探索 Aspose.BarCode for .NET 中的 Aztec 符號模式，並了解如何輕鬆產生通用條碼。在這個綜合教程中親身體驗自動、全範圍、緊湊和符文模式。
weight: 14
url: /zh-hant/net/aztec-barcode-encoding/aztec-symbol-mode-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 掌握 Aztec 符號模式

如果您希望將強大的條碼產生功能合併到您的 .NET 應用程式中，Aspose.BarCode for .NET 是一個絕佳的解決方案。在本教程中，我們將深入研究 Aztec 符號模式，並使用 Aspose.BarCode for .NET 探索其各種選項。我們將介紹先決條件、匯入命名空間，並將每個範例分解為多個步驟來引導您完成整個過程。

## 先決條件

在我們開始之前，請確保您具備以下先決條件：

- .NET 開發的實用知識。
- Visual Studio 安裝在您的電腦上。
-  .NET 的 Aspose.BarCode 副本。你可以下載它[這裡](https://releases.aspose.com/barcode/net/).

現在您已準備就緒，讓我們深入研究 Aztec 符號模式範例。

## 導入命名空間

首先，您需要匯入必要的命名空間才能使用 Aspose.BarCode for .NET。開啟 Visual Studio 專案並在程式碼檔案頂部新增以下 using 語句：

```csharp
using Aspose.BarCode.Generation;
```

命名空間就位後，現在可以開始使用 Aspose.BarCode for .NET。

## 第 1 步：設定條碼產生器

首先使用 Aztec 編碼類型初始化條碼產生器並提供代碼文字。操作方法如下：

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("AztecSymbolModeExample:");

BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Aztec, "Åspóse.Barcóde©");
```

在這一步驟中，我們設定了生成器並提供了用於編碼的程式碼文字。

## 步驟 2：將符號模式設定為自動

現在，讓我們將 Aztec 符號模式設為「自動」並將條碼影像儲存為 PNG 檔案。您可以這樣做：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Auto;
gen.Save($"{path}AztecSymbolModeAuto.png", BarCodeImageFormat.Png);
```

此步驟可確保自動確定 Aztec 符號模式，並儲存產生的條碼影像。

## 步驟 3：將符號模式設定為 FullRange

如果要將 Aztec 符號模式指定為“FullRange”，可以使用下列程式碼來執行此操作：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.FullRange;
gen.Save($"{path}AztecSymbolModeFullRange.png", BarCodeImageFormat.Png);
```

這將建立具有 FullRange Aztec 符號模式的條碼。

## 步驟 4：將符號模式設定為緊湊

若要建立將 Aztec 符號模式設為「緊湊」的條碼，請使用下列程式碼：

```csharp
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Compact;
gen.Save($"{path}AztecSymbolModeCompact.png", BarCodeImageFormat.Png);
```

此步驟配置要使用緊湊 Aztec 符號模式產生的條碼。

## 步驟5：將符號模式設定為符文

最後，如果您想使用「符文」阿茲特克符號模式，您可以透過以下設定來實現：

```csharp
gen.CodeText = "123"; //如果需要，請更改程式碼文本
gen.Parameters.Barcode.Aztec.AztecSymbolMode = AztecSymbolMode.Rune;
gen.Save($"{path}AztecSymbolModeRune.png", BarCodeImageFormat.Png);
```

此步驟將代碼文字變更為“123”並產生具有 Rune Aztec 符號模式的條碼。

## 結論

在本教程中，我們探索了 Aspose.BarCode for .NET 中的 Aztec 符號模式。我們介紹了設定條碼產生器、將 Aztec 符號模式配置為自動、全範圍、緊湊和符文，以及保存生成的條碼影像。有了這些知識，您現在可以輕鬆地將多功能條碼生成整合到您的 .NET 應用程式中。

如果您有任何疑問或需要進一步協助，請隨時聯繫 Aspose.BarCode 社區[支援論壇](https://forum.aspose.com/c/barcode/13).

## 常見問題解答

### Q1：Aztec Symbol Mode 在條碼產生中的用途是什麼？

A1：Aztec 符號模式可讓您指定 Aztec 條碼的編碼方法，為條碼產生提供彈性。

### Q2：我可以在 Aspose.BarCode for .NET 中更改 Aztec 條碼的程式碼文字嗎？

A2: 是的，您在產生 Aztec 條碼時可以根據您的特定要求輕鬆更改程式碼文字。

### Q3：Aspose.BarCode for .NET 有免費試用版嗎？

A3：是的，您可以下載 Aspose.BarCode for .NET 的免費試用版[這裡](https://releases.aspose.com/).

### Q4：在哪裡可以找到 Aspose.BarCode for .NET 的完整文件？

 A4：您可以參考Aspose.BarCode for .NET的完整文檔[這裡](https://reference.aspose.com/barcode/net/).

### Q5：如何取得 Aspose.BarCode for .NET 的臨時授權？

 A5：您可以透過存取取得 Aspose.BarCode for .NET 的臨時許可證[這個連結](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
