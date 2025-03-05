---
title: 一維碼128配置
linktitle: 一維碼128配置
second_title: Aspose.BarCode .NET API
description: 了解如何使用 Aspose.BarCode 在 .NET 中產生一維 Code 128 條碼。請遵循我們的無縫條碼集成分步指南。
type: docs
weight: 10
url: /zh-hant/net/one-dimensional-barcode-types/one-dimensional-code-128-configuration/
---

如果您是 .NET 開發人員，正在尋找一個強大的工具來在應用程式中產生條碼，那麼 Aspose.BarCode for .NET 是您的首選解決方案。本綜合指南將引導您完成利用 Aspose.BarCode for .NET 的功能建立一維 Code 128 條碼的過程，它是為初學者和經驗豐富的開發人員設計的。 

## 先決條件

在我們深入了解使用 Aspose.BarCode 產生條碼的令人興奮的世界之前，請確保您具備以下先決條件：

1. Visual Studio：確保您的系統上安裝了 Visual Studio。

2.  Aspose.BarCode for .NET：您需要下載並安裝Aspose.BarCode for .NET。你可以從[這裡](https://releases.aspose.com/barcode/net/).

3. 您的 .NET 專案：您應該設定一個 .NET 專案並準備好整合條碼產生。

現在，讓我們開始吧！

## 導入命名空間

第一步是匯入專案所需的命名空間。這些命名空間將使您能夠存取 Aspose.BarCode 的特性和功能。

### 第 1 步：導入命名空間

```csharp
using Aspose.BarCode.Generation;
```

## 一維碼128配置

現在，讓我們使用 Aspose.BarCode for .NET 建立 Code 128 條碼。我們將詳細介紹每個步驟，確保您清楚地了解流程。

### 第2步：設定路徑

首先，設定要儲存產生的條碼影像的目錄的路徑。

```csharp
string path = "Your Directory Path";
```

### 第 3 步：建立 Code 128 條碼產生器

創建一個`BarcodeGenerator`用於產生 Code 128 條碼的實例。您可以指定要產生的條碼類型（在本例中為 Code128）以及要編碼的值。

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.Code128, "CODE");
```

### 步驟4：設定條碼參數

在產生條碼之前，您可以配置各種參數。例如，您可以選擇顯示或隱藏校驗和。

#### 選項 1：不顯示校驗和

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = false;
```

#### 選項 2：顯示校驗和

```csharp
gen.Parameters.Barcode.ChecksumAlwaysShow = true;
```

### 第 5 步：儲存條碼圖像

現在，是時候將生成的條碼圖像儲存到您指定的目錄了。您可以儲存有或沒有校驗和的條碼，具體取決於您在上一個步驟中選擇的配置。

#### 儲存不含校驗和的條碼

```csharp
gen.Save($"{path}OneCSCode128NotShowChecksum.png", BarCodeImageFormat.Png);
```

#### 儲存帶有校驗和的條碼

```csharp
gen.Save($"{path}OneCSCode128ShowChecksum.png", BarCodeImageFormat.Png);
```

就是這樣！您已使用 Aspose.BarCode for .NET 成功產生一維 Code 128 條碼。您可以在各種應用中使用這些條碼，例如庫存管理、產品標籤等。

## 結論

Aspose.BarCode for .NET 為 .NET 應用程式中的條碼產生提供了強大且使用者友好的解決方案。憑藉其直覺的 API 和豐富的文檔，您可以輕鬆地將條碼功能整合到您的專案中。無論您需要建立一維還是二維條碼，Aspose.BarCode 都能滿足您的需求。

立即將 Aspose.BarCode 整合到您的 .NET 應用程式中，輕鬆簡化您的條碼產生過程。

### 常見問題解答

### Aspose.BarCode for .NET 與 .NET Core 相容嗎？
是的，Aspose.BarCode for .NET 與 .NET Framework 和 .NET Core 也相容。

### 我可以自訂產生的條碼的外觀嗎？
絕對地！ Aspose.BarCode 可讓您自訂條碼的各個方面，包括大小、顏色和文字位置。

### Aspose.BarCode適合產生二維碼嗎？
雖然 Aspose.BarCode 主要專注於一維條碼，但您也可以使用 Aspose.BarCode for .NET 產生 QR 碼。

### 有免費試用嗎？
是的，您可以透過下載試用版免費試用 Aspose.BarCode for .NET[這裡](https://releases.aspose.com/).

### 在哪裡可以獲得 Aspose.BarCode for .NET 支援？
您可以在 Aspose.BarCode for .NET 論壇上尋求協助並分享您的經驗[這裡](https://forum.aspose.com/c/barcode/13).
