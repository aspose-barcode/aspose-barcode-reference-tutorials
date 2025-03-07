---
title: GS1 程式碼 128 範例逐步指南
linktitle: GS1 程式碼 128 範例
second_title: Aspose.BarCode .NET API
description: 了解如何使用 Aspose.BarCode for .NET 建立 GS1 Code 128 條碼。使用 C# 產生條碼的逐步指南。現在就開始吧！
weight: 10
url: /zh-hant/net/gs1-barcode-encoding/gs1-code-128-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# GS1 程式碼 128 範例逐步指南


## 介紹

歡迎來到 Aspose.BarCode for .NET 的世界！如果您希望在 .NET 應用程式中產生、自訂和使用條碼，那麼您來對地方了。在這份綜合指南中，我們將引導您了解使用 Aspose.BarCode for .NET 的基本知識，確保您清楚地了解該程式庫、其先決條件及其各種功能。在本教程結束時，您將能夠輕鬆、精確地建立條碼。

## 先決條件
在深入了解 Aspose.BarCode for .NET 的迷人世界之前，必須確保您具備必要的先決條件。這是您需要的：

1. .NET 開發環境：您應該有一個有效的 .NET 開發環境，包括 Visual Studio 或其他首選 IDE。

2.  Aspose.BarCode for .NET：您可以透過以下網址下載 Aspose.BarCode for .NET：[這個連結](https://releases.aspose.com/barcode/net/)。確保正確安裝和設定庫。

3. 熟悉 C#：對 C# 程式語言的基本了解將有助於遵循範例和編寫程式碼。

4. GS1 Code 128 的想法：雖然不是強制性的，但了解 GS1 Code 128 條碼的一些知識可以幫助您更好地理解該範例。

現在，讓我們將 GS1 Code 128 範例分解為多個步驟，以提供逐步指南：

## 導入命名空間
要開始使用 Aspose.BarCode for .NET，您需要匯入必要的命名空間。這些命名空間提供對庫的特性和功能的存取。您可以這樣做：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 第 1 步：設定目錄路徑
在產生 GS1 Code 128 條碼之前，您需要指定要儲存條碼影像的目錄路徑。您可以這樣設定路徑：

```csharp
string path = "Your Directory Path";
```

代替`"Your Directory Path"`與您要儲存條碼影像的實際路徑。

## 第 2 步：建立 GS1 Code 128 條碼
現在，是時候使用 Aspose.BarCode for .NET 建立 GS1 Code 128 條碼了。在此範例中，我們將建立一個包含資料「(01)12345678901231(21)ASPOSE(30)9876」的條碼。您可以這樣做：

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

此程式碼使用指定的類型和資料初始化條碼產生器。

## 步驟3：自訂條碼參數
Aspose.BarCode for .NET可讓您自訂條碼的各種參數，例如XDimension（條碼中窄元素的寬度）。在此範例中，我們將 XDimension 設定為 2 像素：

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

您可以根據您的要求調整這些參數。

## 第 4 步：儲存條碼圖像
最後，您可以將生成的條碼儲存為圖像。在此範例中，我們將其另存為 PNG 檔案：

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

確保更換`GS1Code128Example.png`與您喜歡的檔案名稱。

## 結論：
在本逐步指南中，我們向您介紹了 Aspose.BarCode for .NET 並解釋了入門的先決條件。我們將 GS1 Code 128 條碼產生範例分解為多個步驟，幫助您清楚地理解流程。現在，您可以使用 Aspose.BarCode for .NET 並為您的 .NET 應用程式建立自訂條碼。快樂編碼！


## 常見問題：

### 在哪裡可以找到 Aspose.BarCode for .NET 的文檔？
您可以存取該文件：[https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).

### 如何下載 .NET 版 Aspose.BarCode？
您可以從以下位置下載該程式庫[https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).

### 有免費試用嗎？
是的，您可以從以下位置獲得免費試用[https://releases.aspose.com/](https://releases.aspose.com/).

### 在哪裡可以購買 Aspose.BarCode for .NET 的授權？
您可以在以下位置購買許可證[https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).

### 需要協助或有疑問嗎？我在哪裡可以找到支援？
如需支援和社區討論，請訪問[https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
