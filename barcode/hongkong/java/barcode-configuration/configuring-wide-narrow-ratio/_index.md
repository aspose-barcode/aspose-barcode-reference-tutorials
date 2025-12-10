---
date: 2025-12-10
description: 學習如何在 Java 中使用 Aspose.BarCode 以自訂寬窄比例產生條碼，並高效生成條碼圖像。請跟隨我們的逐步指南。
linktitle: Configuring Wide-Narrow Ratio
second_title: Aspose.BarCode Java API
title: 如何在 Java 中生成寬窄比例條碼
url: /zh-hant/java/barcode-configuration/configuring-wide-narrow-ratio/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中產生寬窄比例條碼

## 介紹

如果您需要 **如何產生條碼** 並且要求視覺比例精確，調整寬窄比例是關鍵。  
在本教學中，我們將使用 Aspose.BarCode for Java 逐步說明 **step by step barcode** 的建立流程，示範如何設定比例、產生條碼影像，並 **save barcode png** 至磁碟。  
無論您是製作庫存標籤、運送標籤，或任何需要自訂樣式 CODE_128 條碼的應用程式，您都能在此找到所需的一切。

## 快速解答
- **寬窄比例是什麼？** 它控制條碼中寬條與窄條的相對寬度。  
- **哪種條碼支援比例調整？** 大多數 1‑D 條碼，包括 CODE_128，都允許設定自訂比例。  
- **我需要授權嗎？** 有免費試用版，但正式使用需購買商業授權。  
- **我可以產生 PNG 格式的條碼影像嗎？** 可以——使用 `generator.save(...)` 產生 PNG 條碼影像。  
- **此程式碼是否相容於 Java 8 以上？** 當然；Aspose.BarCode 支援所有現代 Java 版本。

## 前置條件

在深入程式碼之前，請確保您已具備以下項目：

- 已在機器上安裝 Java Development Kit (JDK)。  
- Aspose.BarCode for Java 函式庫。請從 [download link](https://releases.aspose.com/barcode/java/) 下載。

## 匯入套件

首先，將必要的 Aspose.BarCode 類別匯入您的專案。

```java
// Import Aspose.BarCode library
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 寬窄比例是什麼，為何要調整？

寬窄比例決定「寬」條相對於「窄」條的粗細。調整此比例可提升掃描器的可讀性、符合特定印刷標準，或僅僅是配合品牌的視覺風格。

## 如何在 Java 中產生寬窄比例條碼

以下是一個 **step by step barcode** 指南，逐步說明整個流程的每個步驟。

### 步驟 1：設定文件目錄

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

確保目錄已存在且您具有寫入權限；此處將放置 **save barcode png** 檔案。

### 步驟 2：實例化條碼物件

```java
// Instantiate barcode object
// Create an instance of BarcodeGenerator, specify codetext and symbology in the constructor
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

此處我們透過將 `EncodeTypes.CODE_128` 傳入建構子來 **create code_128 barcode**。

### 步驟 3：設定寬窄比例

```java
// Set the wide to narrow ratio for the barcode
generator.getParameters().getBarcode().setWideNarrowRatio(3.0f);
```

`setWideNarrowRatio` 方法讓您微調視覺間距。`3.0f` 表示寬條的寬度是窄條的三倍。

### 步驟 4：將影像儲存至磁碟

```java
// Save the image to disk in PNG format
generator.save(dataDir + "wideNarrowRatio.png");
```

呼叫 `save` 會 **generate barcode image** 並以 PNG 檔案儲存，完成 **save barcode png** 步驟。

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 條碼顯示失真 | 比例對印表機而言過高或過低 | 調整傳入 `setWideNarrowRatio` 的數值（例如 2.0‑2.5）。 |
| 檔案未建立 | `dataDir` 路徑無效或權限不足 | 確認目錄路徑並確保應用程式具有寫入權限。 |
| 掃描器無法讀取條碼 | 比例超出該條碼類型的建議範圍 | 使用標準比例（2.0‑3.0）或以目標掃描器測試。 |

## 常見問答

**Q: 我可以在其他 Java 框架中使用 Aspose.BarCode 嗎？**  
A: 可以，Aspose.BarCode 設計上能與 Spring、Java EE、Android 以及其他 Java 環境無縫整合。

**Q: 我如何產生不同條碼類型的條碼？**  
A: 只要在 `BarcodeGenerator` 建構子中更改條碼類型，例如使用 `EncodeTypes.QR` 產生 QR Code。

**Q: Aspose.BarCode 有提供試用版嗎？**  
A: 有，您可於此取得免費試用版 [here](https://releases.aspose.com/)。

**Q: 我在哪裡可以找到 Aspose.BarCode 的詳細文件？**  
A: 請參考文件 [here](https://reference.aspose.com/barcode/java/)。

**Q: 如何取得 Aspose.BarCode 的支援？**  
A: 前往 Aspose.BarCode 論壇 [here](https://forum.aspose.com/c/barcode/13) 獲得支援與社群討論。

---

**最後更新：** 2025-12-10  
**測試環境：** Aspose.BarCode for Java 24.11（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}