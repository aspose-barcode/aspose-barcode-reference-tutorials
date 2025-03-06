---
title: 使用 Aspose.BarCode for .NET 建立補充條碼數據
linktitle: 補充條碼資料配置
second_title: Aspose.BarCode .NET API
description: 使用 Aspose.BarCode for .NET 產生補充條碼資料。輕鬆自訂 EAN-2 和 EAN-5 條碼。 .NET 開發人員的分步指南。
weight: 10
url: /zh-hant/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode for .NET 建立補充條碼數據


在條碼產生和自訂領域，Aspose.BarCode for .NET 是一款功能強大且多功能的工具。無論您是經驗豐富的開發人員還是剛起步，本逐步指南都會引導您完成使用 Aspose.BarCode for .NET 設定補充條碼資料的過程。 

## 先決條件

在我們深入了解補充條碼資料的世界之前，請確保您具備以下先決條件：

- 使用 Visual Studio 或任何其他 .NET 開發工具設定的開發環境。
-  .NET 的 Aspose.BarCode 副本。如果您還沒有，您可以下載[這裡](https://releases.aspose.com/barcode/net/).
- C# 程式設計基礎知識。
- 可以儲存產生的條碼影像的目錄。

## 導入命名空間

首先，請確保您的 C# 程式碼中包含必要的命名空間，以便與 Aspose.BarCode for .NET 一起使用。在 C# 檔案的開頭導入所需的命名空間：

```csharp
using Aspose.BarCode.Generation;
```

現在，讓我們將配置補充條碼資料的過程分解為多個步驟。

## 第1步：設定目錄路徑

在 C# 程式碼中，定義要儲存產生的條碼影像的目錄路徑。代替`"Your Directory Path"`與您的實際目錄路徑。

```csharp
string path = "Your Directory Path";
```

## 第 2 步：建立條碼產生器

建立一個實例`BarcodeGenerator`透過指定條碼類型和要編碼的資料。在此範例中，我們使用資料為「1234567890128」的 EAN-13 條碼。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## 第 3 步：自訂條碼尺寸

設定條碼的尺寸，例如X尺寸（條碼中最小元素的寬度）和補充空間。在此範例中，我們將 X 尺寸設為 2 像素，將補充空間設為 20 像素。

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## 步驟 4：配置 EAN-2 補充

若要設定 EAN-2 補充條碼，請將補充資料設定為所需的值。在本例中，我們將其設為“12”。 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## 第 5 步：儲存條碼圖像

使用有意義的名稱將產生的條碼圖像儲存到指定目錄。在此範例中，我們將 EAN-2 補充條碼儲存為「SupplementEAN2.png」。

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## 步驟 6：配置 EAN-5 補充

要配置 EAN-5 補充條碼，只需更改`SupplementData`到您想要的值。在這裡，我們將其設定為“12345”。

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## 步驟 7：儲存條碼影像 (EAN-5)

最後，將 EAN-5 補充條碼影像儲存在您指定的目錄中。在本例中，我們將其儲存為「SupplementEAN5.png」。

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

現在，您已經使用 Aspose.BarCode for .NET 成功配置並產生了補充條碼資料。您可以使用此方法建立具有不同補充資料的各種條碼類型。

## 結論

Aspose.BarCode for .NET 是一個強大的條碼產生和自訂工具。在本指南中，我們逐步完成了配置和產生補充條碼資料的過程。透過正確的先決條件和一些編碼，您可以有效地處理條碼資料並滿足您的特定需求。

如需更多資訊和進階用法，請參閱[Aspose.BarCode for .NET 文檔](https://reference.aspose.com/barcode/net/).

## 經常問的問題

### 我可以在 .NET Core 專案中使用 Aspose.BarCode for .NET 嗎？
是的，Aspose.BarCode for .NET 與 .NET Core 也相容。

### Aspose.BarCode for .NET 有沒有免費試用版？
是的，您可以訪問免費試用[這個連結](https://releases.aspose.com/).

### 在哪裡可以獲得 Aspose.BarCode for .NET 的臨時授權？
您可以從以下地址取得臨時許可證[這個連結](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode 是否支援多種條碼類型？
是的，它支援各種條碼類型，包括 EAN-13、QR 碼、Code 128 等。

### 我可以自訂產生的條碼的外觀嗎？
當然，您可以自訂條碼的尺寸、顏色和其他方面來滿足您的要求。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
