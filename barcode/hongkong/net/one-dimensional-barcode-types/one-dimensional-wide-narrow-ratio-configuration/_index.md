---
title: 一維寬窄比配置
linktitle: 一維寬窄比配置
second_title: Aspose.BarCode .NET API
description: 使用 Aspose.BarCode for .NET 輕鬆產生自訂條碼。一維寬窄比配置的分步指南。
weight: 22
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-wide-narrow-ratio-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 一維寬窄比配置


您是否希望在 .NET 應用程式中輕鬆產生和自訂條碼？別再猶豫了！ Aspose.BarCode for .NET 是一個強大的函式庫，讓條碼產生和自訂變得輕而易舉。在本逐步指南中，我們將深入研究如何利用 Aspose.BarCode for .NET 的強大功能來建立具有寬窄比配置的條碼。

## 先決條件

在我們使用 Aspose.BarCode for .NET 進入條碼世界之前，您需要滿足以下先決條件：

### 1. Visual Studio環境
   - 確保您的系統上安裝了 Visual Studio 以使用 .NET 應用程式。
   
### 2. Aspose.BarCode for .NET 函式庫
   - 您必須安裝 Aspose.BarCode for .NET 程式庫。您可以從[網站](https://releases.aspose.com/barcode/net/).

### 3. 許可證密鑰（可選）
   - 如果您有許可證密鑰，則可以使用它來解鎖該庫的其他功能。您可以從以下地址取得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/).

現在您已經具備了先決條件，讓我們開始使用 Aspose.BarCode for .NET 建立具有寬窄比配置的一維條碼。

## 導入命名空間

首先，您需要在專案中包含必要的命名空間，以存取 Aspose.BarCode for .NET 的功能。您可以透過在程式碼頂部新增以下 using 語句來完成此操作：

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

## 第 1 步：定義您的目錄路徑

首先定義要儲存產生的條碼影像的路徑。您可以使用以下程式碼來執行此操作：

```csharp
string path = "Your Directory Path";
```

代替`"Your Directory Path"`與您要儲存條碼影像的實際目錄路徑。

## 步驟 2：建立一維寬窄比條碼

現在，讓我們使用 Aspose.BarCode for .NET 建立一個具有寬窄比配置的一維條碼。在此範例中，我們將使用 Code39Extended 編碼類型並將資料設定為「ASPOSE」。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code39Extended, "ASPOSE");
```

這行程式碼使用指定的編碼類型和資料初始化條碼產生器。

## 步驟 3：設定寬/窄比例

寬窄比決定了條碼中寬窄元素之間的比例。在此步驟中，我們將寬窄比設為 2：

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 2;
```

然後，我們將生成的條碼圖像儲存到指定路徑：

```csharp
gen.Save($"{path}WideNarrow2Code39.png", BarCodeImageFormat.Png);
```

## 第四步：調整寬窄比

您可以嘗試不同的寬窄比以獲得所需的條碼外觀。例如，如果您想要更寬的條碼，請將寬窄比設為 5：

```csharp
gen.Parameters.Barcode.WideNarrowRatio = 5;
```

並儲存條碼圖像：

```csharp
gen.Save($"{path}WideNarrow5Code39.png", BarCodeImageFormat.Png);
```

現在您已經使用 Aspose.BarCode for .NET 成功建立了具有不同寬窄比的一維條碼。該庫使您可以靈活地產生適合您的特定要求的條碼。

## 結論

Aspose.BarCode for .NET 是一個多功能函式庫，可簡化 .NET 應用程式中的條碼產生和自訂。在本教程中，我們介紹了創建具有寬窄比配置的一維條碼的基礎知識。透過微調各種參數的能力，您可以創建完全適合您需求的條碼。

## 經常問的問題

### 1. 如何取得 Aspose.BarCode for .NET 的授權？
您可以從以下位置購買許可證[阿斯普斯網站](https://purchase.aspose.com/buy).

### 2. 我可以在沒有許可證的情況下使用Aspose.BarCode for .NET嗎？
是的，您可以透過臨時許可證使用它，該許可證提供有限的功能。

### 3. Aspose.BarCode for .NET 與.NET Core 相容嗎？
是的，Aspose.BarCode for .NET 與 .NET Core 和 .NET Framework 相容。

### 4. 我可以產生的條碼類型有限制嗎？
Aspose.BarCode for .NET 支援多種條碼符號，包括 QR 碼、Code 39 等等。

### 5. 如何獲得 Aspose.BarCode for .NET 的支援或提出問題？
您可以訪問[Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)以尋求支持和討論。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
