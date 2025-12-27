---
date: 2025-12-27
description: 學習如何在 Java 中使用 Aspose.BarCode 為條碼圖像添加說明文字。此 Java 條碼產生器範例展示如何輕鬆建立條碼圖像。
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: 如何在 Java 中使用 Aspose.BarCode 為條碼添加說明文字
url: /zh-hant/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用 Aspose.BarCode 為條碼添加說明文字

## 介紹

如果您需要 **如何添加說明文字** 到條碼，以提升可讀性與品牌形象，您來對地方了。在本教學中，我們將逐步說明如何使用 Aspose.BarCode for Java 在條碼影像的上方與下方加入說明文字。完成後，您將擁有一個完整樣式的條碼，不僅能編碼資料，還能顯示有用的文字——非常適合產品標籤、庫存系統，或任何需要額外說明的情境。

## 快速回答
- **需要的函式庫是什麼？** Aspose.BarCode for Java.  
- **我可以更改字型與顏色嗎？** 可以——說明文字的字型系列與文字顏色皆可自訂。  
- **哪些條碼類型可使用？** 所有 Aspose.BarCode 支援的符號集（例如 CODE_128、QR、DataMatrix）。  
- **測試需要授權嗎？** 有免費試用版；正式上線需購買商業授權。  
- **實作需要多長時間？** 一旦加入函式庫，通常在 10 分鐘內完成。

## 什麼是條碼說明文字？

說明文字是顯示在條碼圖形上方或下方的純文字。它可用於傳達產品名稱、價格或任何補充編碼資料的資訊。

## 為什麼要使用 Aspose.BarCode 添加說明文字？

- **提升使用者體驗：** 使用者無需掃描即可立即了解條碼的含義。  
- **品牌一致性：** 您可以套用自訂字型、顏色與對齊方式，以符合企業風格指南。  
- **完整控制：** Aspose.BarCode 的 API 允許您切換可見性、設定對齊方式，並獨立設計每個說明文字的樣式。

## 先決條件

在開始之前，請確保您已具備以下條件：

- 已安裝 Java Development Kit（JDK）。  
- 已下載 Aspose.BarCode for Java 函式庫並加入專案。您可在此取得下載連結 [here](https://releases.aspose.com/barcode/java/)。  
- 使用 IntelliJ IDEA 或 Eclipse 等 IDE。

## 匯入套件

在 Java 原始碼檔案中，匯入所需的 Aspose.BarCode 類別與 AWT `Color` 類別：

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## 步驟 1：設定文件與資源目錄

指定要儲存產生的條碼影像的路徑。請依您的環境調整路徑。

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## 步驟 2：建立 BarcodeGenerator 實例

使用欲使用的符號集（例如 CODE_128）與欲編碼的文字，實例化 `BarcodeGenerator`。

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## 步驟 3：設定條碼上方的說明文字

設定條碼上方顯示的說明文字。您可以控制對齊方式、文字內容、可見性、字型系列、大小與顏色。

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## 步驟 4：設定條碼下方的說明文字

同樣地，定義條碼下方的說明文字。如有需要，可使用不同的對齊方式或樣式。

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## 步驟 5：儲存條碼影像

最後，將條碼（含說明文字）寫入影像檔案。格式會根據檔案副檔名自動判斷。

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

您可以重複上述步驟，以測試不同的字型、顏色或對齊方式，或在迴圈中產生多張條碼影像。

## 常見問題與技巧

- **說明文字未顯示？** 確認已對欲顯示的說明文字呼叫 `setVisible(true)`。  
- **顏色不正確？** 使用 `java.awt.Color` 常數或以 `new Color(r, g, b)` 建立自訂顏色。  
- **路徑問題？** 確認 `dataDir` 指向已存在且可寫入的資料夾；否則 `bb.save()` 會拋出 `IOException`。  
- **效能提示：** 產生大量條碼時，重複使用同一個 `BarcodeGenerator` 實例，只在需要時變更 `EncodeTypes` 或 `codetext`。

## 常見問題 (FAQs)

### 我可以自訂條碼說明文字的字型樣式嗎？

是的，您可以自訂上方與下方說明文字的字型系列、大小與顏色。

### Aspose.BarCode 是否相容於不同的條碼符號集？

當然！Aspose.BarCode 支援廣泛的符號集，確保條碼產生的彈性。

### 我該如何將 Aspose.BarCode 整合到我的 Java 專案中？

您可以參考此處的詳細整合指南 [here](https://reference.aspose.com/barcode/java/) 逐步說明。

### 是否有 Aspose.BarCode for Java 的免費試用版？

有，您可在此取得免費試用版 [here](https://releases.aspose.com/) 以探索所有功能。

### 如果遇到問題，我該向哪裡尋求協助？

Aspose.BarCode 社群論壇是獲得支援與討論的絕佳場所。請前往論壇 [here](https://forum.aspose.com/c/barcode/13)。

---

**最後更新：** 2025-12-27  
**測試環境：** Aspose.BarCode for Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}