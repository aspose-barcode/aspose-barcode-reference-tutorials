---
title: 使用 Aspose.BarCode for .NET 設定 DataMatrix 程式碼文字
linktitle: DataMatrix 擴充程式碼文字配置
second_title: Aspose.BarCode .NET API
description: 了解使用 Aspose.BarCode for .NET 配置 DataMatrix 擴充程式碼文字。在 .NET 應用程式中產生、識別和整合條碼。
type: docs
weight: 17
url: /zh-hant/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
---
在軟體開發領域，條碼整合已成為各種應用程式的關鍵必需品。透過 Aspose.BarCode for .NET 等程式庫，您可以在 .NET 應用程式中輕鬆產生和識別條碼。本教學將引導您完成使用 Aspose.BarCode for .NET 設定 DataMatrix 擴充程式碼文字的過程。在深入了解詳細資訊之前，讓我們先看一下本指南的先決條件。

## 先決條件

在開始之前，請確保您已具備以下條件：

1. Aspose.BarCode for .NET 函式庫
您需要安裝 Aspose.BarCode for .NET。如果還沒有，您可以從網站下載[這裡](https://releases.aspose.com/barcode/net/).

2. .NET 開發環境
要學習本教學課程，您應該在系統上設定 .NET 開發環境。您可以使用 Visual Studio 或任何其他首選 IDE。

3. C#基礎知識
對 C# 程式設計的基本了解對於本教程至關重要。

現在您已經具備了必要的工具和知識，讓我們將使用 Aspose.BarCode for .NET 配置 DataMatrix 擴充程式碼文字的過程分解為簡單的逐步說明。

## 導入命名空間

使用 Aspose.BarCode for .NET 的第一步是匯入所需的命名空間。將以下命名空間加入您的程式碼：

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

這些命名空間提供了處理條碼所需的類別和方法。

## 步驟 1：DataMatrix 擴充代碼文字配置

在此步驟中，我們將引導您完成配置 DataMatrix 擴充程式碼文字的過程。

## 步驟 2：定義目錄路徑

您需要指定要儲存產生的 DataMatrix 條碼的目錄路徑。代替`"Your Directory Path"`與系統上的實際路徑。

```csharp
string path = "Your Directory Path";
```

## 第 3 步：建立程式碼文本

若要建立 DataMatrix 條碼的代碼文本，您將使用`DataMatrixExtCodetextBuilder`。此建構器可讓您新增具有不同編碼的各種類型的程式碼文字。

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

此代碼使用不同編碼的混合來配置代碼文字。

## 第 4 步：產生程式碼文本

配置程式碼文字後，產生 DataMatrix 程式碼文字字串。

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

## 步驟 5：產生 DataMatrix 條碼

現在，使用產生的程式碼文字建立 DataMatrix 條碼。您也可以設定條碼的各種參數，例如X尺寸和代碼文字顯示。

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

此程式碼使用指定的設定產生並儲存 DataMatrix 條碼影像。

## 第六步：嘗試識別

為了確保條碼可以被識別，您可以使用`BarCodeReader`讀取條碼的類別。

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

此步驟透過嘗試識別產生的條碼來驗證它。

恭喜！您已使用 Aspose.BarCode for .NET 成功配置了 DataMatrix 擴充程式碼文字。現在您可以將此功能整合到您的 .NET 應用程式中。

## 結論

在本教學中，我們探索了使用 Aspose.BarCode for .NET 設定 DataMatrix 擴充程式碼文字的過程。我們介紹了先決條件、逐步說明，並示範如何產生和識別條碼。有了這些知識，您就可以透過新增條碼產生和識別功能來增強您的 .NET 應用程式。

## 常見問題解答

### Q1：什麼是 Aspose.BarCode for .NET？

A1：Aspose.BarCode for .NET 是一個功能強大的程式庫，可讓開發人員在.NET 應用程式中產生和識別條碼。它支援廣泛的條碼符號體系並提供各種客製化選項。

### Q2：在哪裡可以找到 Aspose.BarCode for .NET 的文件？

A2：您可以存取 Aspose.BarCode for .NET 的文檔[這裡](https://reference.aspose.com/barcode/net/).

### Q3：Aspose.BarCode for .NET 有沒有免費試用版？

 A3：是的，您可以獲得 Aspose.BarCode for .NET 的免費試用版[這裡](https://releases.aspose.com/).

### Q4：如何取得 Aspose.BarCode for .NET 的臨時授權？

 A4：如果您需要臨時許可證用於測試或評估目的，您可以獲得一份[這裡](https://purchase.aspose.com/temporary-license/).

### Q5：我可以在哪裡獲得有關 Aspose.BarCode for .NET 的支援或提出問題？

 A5：有關 Aspose.BarCode for .NET 的任何支援或問題，您可以造訪 Aspose.BarCode 論壇[這裡](https://forum.aspose.com/c/barcode/13).