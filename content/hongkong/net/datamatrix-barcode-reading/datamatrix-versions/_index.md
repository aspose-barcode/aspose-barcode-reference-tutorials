---
title: 使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼
linktitle: 資料矩陣版本
second_title: Aspose.BarCode .NET API
description: 了解如何使用 Aspose.BarCode for .NET 在 .NET 中產生 DataMatrix 條碼。自訂尺寸、ECC 支援等等。
type: docs
weight: 12
url: /zh-hant/net/datamatrix-barcode-reading/datamatrix-versions/
---
如果您正在尋找可靠的解決方案來在 .NET 應用程式中產生 DataMatrix 條碼，Aspose.BarCode for .NET 就是您的最佳選擇。在本逐步指南中，我們將引導您完成使用 Aspose.BarCode for .NET 建立 DataMatrix 條碼的過程。我們將把每個範例分解為多個步驟，確保您可以輕鬆遵循。

## 先決條件

在我們深入研究程式碼之前，請確保您具備以下先決條件：
- 具有 .NET 支援的開發環境。
-  Aspose.BarCode for .NET 的副本，您可以從下列位置下載[這個連結](https://releases.aspose.com/barcode/net/).
- C# 和 .NET 架構的基礎知識。

現在，讓我們來探索 DataMatrix 版本以及如何使用 Aspose.BarCode for .NET 產生它們。

## 導入命名空間

在任何 C# 專案中，導入必要的命名空間至關重要。對於 Aspose.BarCode，您需要包含以下內容：

```csharp
using Aspose.BarCode.Generation;
```

此命名空間提供對`BarcodeGenerator`類，這對於產生條碼至關重要。

現在，讓我們將該範例分解為多個步驟。

## 第 1 步：設定目錄路徑

首先定義要儲存產生的 DataMatrix 條碼的目錄路徑。

```csharp
string path = "Your Directory Path";
```

代替`"Your Directory Path"`與您要儲存條碼影像的實際路徑。

## 第 2 步：初始化條碼產生器

建立一個實例`BarcodeGenerator`類別並將條碼類型指定為`DataMatrix`。您也可以提供要在條碼中編碼的資料。

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    //產生條碼的程式碼位於此處
}
```

## 步驟 3：配置條碼屬性

您可以自訂 DataMatrix 條碼的各種屬性，例如尺寸和 ECC（糾錯碼）類型。以下是將 X 尺寸設為 4 像素並選擇 ECC200 的範例：

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## 步驟4：設定DataMatrix版本並儲存

您可以透過設定行數和列數來指定 DataMatrix 版本。配置版本後，儲存條碼影像。

例如，若要使用 ECC200 建立 22 行 22 列的 DataMatrix 條碼：

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

同樣，您可以根據需要變更版本和ECC類型來產生具有不同參數的條碼。

## 步驟 5：對其他版本重複此操作

對於其他 DataMatrix 版本，您可以重複步驟 4。例如，要使用 ECC200 建立 12 行 64 列的條碼：

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## 步驟 6：切換 ECC 類型

如果要將 ECC 類型變更為 Ecc140，可以透過更新 ECC 屬性來實現：

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## 步驟 7：產生不同版本和 ECC 的條碼

對其他 DataMatrix 版本和 ECC 類型重複步驟 4，用唯一的檔案名稱儲存每個條碼。

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

現在您已經了解如何使用 Aspose.BarCode for .NET 產生 DataMatrix 條碼，您可以輕鬆地將此功能整合到您的 .NET 應用程式中。

## 結論

Aspose.BarCode for .NET 簡化了在 .NET 應用程式中產生 DataMatrix 條碼的過程。透過此逐步指南，您可以建立具有不同版本和 ECC 類型的條碼，從而提供靈活性和自訂來滿足您的特定需求。

如果您有任何疑問或需要協助，請隨時訪問[Aspose.BarCode for .NET 文檔](https://reference.aspose.com/barcode/net/)或查看[Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)為了支持。

## 常見問題解答

### Q1：DataMatrix 條碼中的 ECC 是什麼？

A1：ECC（糾錯碼）是 DataMatrix 條碼的重要組成部分，有助於確保資料完整性。不同的 ECC 等級提供不同程度的糾錯。

### 問題 2：我可以使用 Aspose.BarCode for .NET 產生具有自訂尺寸的 DataMatrix 條碼嗎？

A2：是的，您可以透過設定行數和列數來自訂 DataMatrix 條碼的尺寸，如教學課程所示。

### Q3：哪裡可以下載 Aspose.BarCode for .NET？

 A3：您可以從下列位置下載 Aspose.BarCode for .NET[這個連結](https://releases.aspose.com/barcode/net/).

### Q4：Aspose.BarCode for .NET 有免費試用版嗎？

 A4：是的，您可以免費試用 Aspose.BarCode for .NET[這裡](https://releases.aspose.com/).

### Q5：如何取得 Aspose.BarCode for .NET 的臨時授權？

 A5：要取得 Aspose.BarCode for .NET 的臨時許可證，請訪問[這個連結](https://purchase.aspose.com/temporary-license/).