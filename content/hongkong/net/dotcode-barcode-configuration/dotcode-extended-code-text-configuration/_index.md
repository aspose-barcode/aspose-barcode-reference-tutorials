---
title: 使用 Aspose.BarCode for .NET 進行 DotCode 擴充程式碼文字配置
linktitle: DotCode 擴充程式碼文字配置
second_title: Aspose.BarCode .NET API
description: 使用 Aspose.BarCode for .NET 輕鬆產生 DotCode 擴充程式碼文字配置。請按照我們的逐步指南進行高效率的條碼建立。
type: docs
weight: 13
url: /zh-hant/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
---
## 介紹

在條碼產生和管理領域，Aspose.BarCode for .NET 是一種多功能且高效的解決方案。無論您需要為產品、庫存或任何其他應用程式產生條碼，Aspose.BarCode for .NET 都能滿足您的需求。在這個綜合教程中，我們將專注於使用 Aspose.BarCode for .NET 產生 DotCode 擴充程式碼文字配置。 DotCode 是一種二維矩陣條碼，可以對文字和二進位資料進行編碼，使其成為各個行業的寶貴工具。

## 先決條件

在我們深入研究逐步指南之前，您需要滿足一些先決條件才能有效地遵循：

1.  Aspose.BarCode for .NET：確保您已安裝並準備好 Aspose.BarCode for .NET 程式庫。如果沒有，您可以從以下位置下載[Aspose.BarCode for .NET 文檔](https://reference.aspose.com/barcode/net/).

2. 開發環境：您的系統上應該安裝一個可用的 .NET 開發環境，最好是 Visual Studio。

在按順序滿足這些先決條件後，我們現在可以繼續產生 DotCode 擴展代碼文字配置。

## 導入命名空間

首先，您需要將必要的命名空間匯入到 .NET 專案中，以從 Aspose.BarCode 程式庫存取所需的功能。您可以按照以下方法執行此操作：


```csharp
using Aspose.BarCode.Generation;
```

現在我們已經滿足了先決條件，讓我們將產生 DotCode 擴展代碼文字配置的過程分解為逐步指南。



## 第 1 步：定義目錄路徑

在此步驟中，您需要指定要儲存產生的DotCode擴充程式碼文字影像的目錄路徑。

```csharp
string path = "Your Directory Path";
```

代替`"Your Directory Path"`與系統上的實際路徑。

## 步驟2：建立DotCode擴展代碼文本

若要建立 DotCode 擴充程式碼文本，請執行下列子步驟：

### 2.1 新增FNC1格式標識符

FNC1 格式標識符用於指示新資料欄位的開始。它是 DotCode 擴展代碼文字的重要組成部分。

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 新增ECI代碼文本

ECICodetext 是您可以對特殊字元和國際文字進行編碼的地方。在此範例中，我們使用 UTF-8 編碼對「犬右狗」進行編碼。

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 新增純代碼文字

您也可以將純文字新增至 DotCode 擴充代碼文字。在這裡，我們添加了“純文字”。

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 新增FNC3符號分隔符

FNC3 符號分隔符號用於分隔代碼的不同部分。

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 新增FNC3讀卡機初始化

此步驟新增 FNC3 Reader 初始化資訊。

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 生成程式碼文本

現在，透過呼叫產生 DotCode 擴展代碼文本`GetExtendedCodetext`方法上的`textBuilder`目的。

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## 步驟3：產生DotCode影像

若要將 DotCode 擴充程式碼文字產生為圖像，請執行下列子步驟：

#### 4.1 初始化條碼產生器

初始化`BarcodeGenerator`具有適當的參數。在這種情況下，我們使用`EncodeTypes.DotCode`和生成的程式碼文字。

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    //設定條碼的 X 尺寸（根據需要調整）。
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    //將 DotCode 編碼模式設定為 ExtendedCodetext。
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    //儲存生成的條碼圖像。
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

就是這樣！您已使用 Aspose.BarCode for .NET 成功產生了 DotCode 擴充程式碼文字。

## 結論

Aspose.BarCode for .NET 是一個功能強大的工具，可以簡化條碼產生。在本教程中，我們專注於生成 DotCode 擴展代碼文本，這在各個行業中都至關重要，特別是在需要多語言和專門字元編碼的情況下。透過執行上述步驟，您可以輕鬆建立滿足您特定需求的 DotCode 擴充程式碼文字。

如果您需要進一步指導或有疑問，請隨時訪問[Aspose.BarCode for .NET 文檔](https://reference.aspose.com/barcode/net/)或與社區互動[Aspose.BarCode 支援論壇](https://forum.aspose.com/c/barcode/13).

## 常見問題解答

### Q1：DotCode有什麼用？

A1：DotCode 用於編碼文字和二進位數據，通常應用於醫療保健和物流等行業，用於追蹤和數據編碼目的。

### Q2：我可以自訂DotCode條碼的外觀嗎？

A2：是的，Aspose.BarCode for .NET 提供了自訂 DotCode 條碼外觀的選項，包括大小和編碼模式。

### Q3：Aspose.BarCode for .NET 與各種.NET 框架相容嗎？

A3：是的，Aspose.BarCode for .NET 與廣泛的 .NET 框架相容，確保靈活性和易於整合。

### Q4：如何取得 Aspose.BarCode for .NET 的臨時授權？

 A4：您可以從以下地點獲得臨時許可證：[阿斯普斯的網站](https://purchase.aspose.com/temporary-license/)用於評估和測試目的。

### Q5：Aspose.BarCode for .NET適合企業級條碼產生嗎？

A5：當然，Aspose.BarCode for .NET 旨在滿足小規模和企業級條碼產生的需求，提供可擴展性和可靠性。