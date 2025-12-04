---
date: 2025-12-04
description: 了解如何設定高效能模式，以及如何使用高效能條碼閱讀器搭配 Aspose.BarCode for Java 快速讀取條碼。
language: zh-hant
linktitle: Faster Image Processing for Barcode Recognition
second_title: Aspose.BarCode Java API
title: 高效能條碼讀取器：在 Java 中使用 Aspose.BarCode 加速條碼辨識的影像處理
url: /java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 高效能條碼讀取器：在 Java 中使用 Aspose.BarCode 加速圖像處理以進行條碼辨識

在現代的 Java 應用程式中，**高效能條碼讀取器** 功能是因應即時掃描需求的關鍵。當您需要 **如何快速且可靠地讀取條碼** 時，Aspose.BarCode for Java 為您提供加速圖像處理而不犧牲準確度的工具。本指南將逐步說明如何啟用高效能模式、微調品質設定，並實現更快的條碼辨識。

## 快速解答
- **「高效能條碼讀取器」是什麼意思？** 這是一種透過最佳化圖像處理演算法來最大化掃描速度的設定。  
- **範例中使用哪種條碼符號？** DataMatrix（2‑D 條碼的一種）。  
- **如何啟用高效能模式？** 呼叫 `reader.setQualitySettings(QualitySettings.getHighPerformance())`。  
- **生產環境需要授權嗎？** 需要，非試用版必須使用商業授權。  
- **支援哪個 Java 版本？** 完全支援 Java 8 及以上版本。

## 什麼是高效能條碼讀取器？
**高效能條碼讀取器** 是 Aspose.BarCode 引擎的特別調校實例，能減少處理開銷、套用積極的圖像前處理，並加速解碼迴圈。此模式特別適用於高吞吐量掃描站、行動應用程式，或大量圖像批次處理等情境。

## 為什麼要使用 Aspose.BarCode 的高效能模式？
- **速度：** 相較於預設設定，可提升 2‑3 倍的解碼速度。  
- **可擴展性：** 在一般硬體上每分鐘可處理數千張圖像。  
- **準確度：** 透過自動套用中值平滑等最佳化，仍能維持高辨識率。  
- **彈性：** 您仍可針對特定使用情境自訂個別品質設定。

## 前置條件
- **Java 開發環境：** JDK 8 或更新版本，您慣用的 IDE（IntelliJ、Eclipse 等）。  
- **Aspose.BarCode for Java：** 從 [Aspose.BarCode 下載頁面](https://releases.aspose.com/barcode/java/) 取得最新 JAR。

## 匯入命名空間

開始之前，先匯入所需的類別：

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.QualitySettings;
```

## 步驟 1：設定資源目錄

定義存放範例圖像的資料夾。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(FasterImageProcessingForBarcodeRecognition.class) + "BarcodeReader/advanced_features/";
```

## 步驟 2：選取包含條碼的圖像

將讀取器指向您要解碼的圖像。本範例使用 DataMatrix 圖像。

```java
// Read code39 barcode from image
String imageFilePath = dataDir + "datamatrix.bmp";
```

## 步驟 3：建立 BarCodeReader 實例

以圖像路徑與預期的條碼符號建立 `BarCodeReader`。

```java
// Create an instance of BarCodeReader and set image and symbology type to recognize
BarCodeReader reader = new BarCodeReader(imageFilePath, DecodeType.DATA_MATRIX);
```

## 步驟 4：啟用高效能模式

開啟內建的高效能設定，這就是 **高效能條碼讀取器** 的核心。

```java
// Set high performance mode
reader.setQualitySettings(QualitySettings.getHighPerformance());
```

## 步驟 5：微調個別選項（可選）

您仍可調整個別品質設定以符合圖像特性。啟用中值平滑通常能改善雜訊圖像的辨識結果。

```java
// Set separate options
reader.getQualitySettings().setAllowMedianSmoothing(true);
reader.getQualitySettings().setMedianSmoothingWindowSize(4);
```

## 步驟 6：從圖像辨識條碼

執行讀取器並輸出解碼資訊，這就是 **如何讀取條碼** 的最後一步。

```java
// Try to recognize the barcode from the image
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("BarCode CodeText: " + result.getCodeText());
    System.out.println("BarCode CodeType: " + result.getCodeTypeName());
}
```

依照上述步驟，您現在已擁有一個 **高效能條碼讀取器**，能快速且可靠地處理圖像。

## 常見問題與解決方案
- **未偵測到條碼：** 請確認圖像路徑正確，且條碼未旋轉超過 45°。可考慮增大 `MedianSmoothingWindowSize`。  
- **即使啟用高效能模式仍效能緩慢：** 請確保使用最新的 Aspose.BarCode JAR；舊版可能缺乏效能改進。  
- **不支援的條碼符號：** 請檢查傳入的 `DecodeType` 是否與圖像中的條碼相符。

## 常見問答

**Q: Aspose.BarCode 是否支援多種條碼符號？**  
A: 是的，支援廣泛的 1‑D 與 2‑D 符號，包括 Code128、QR Code、DataMatrix 等。

**Q: 我可以同時使用 Aspose.BarCode 產生與辨識條碼嗎？**  
A: 當然可以。此函式庫提供完整的 API，讓您在 Java 應用程式中建立與讀取條碼。

**Q: Aspose.BarCode 有哪些授權方案？**  
A: 您可於 [Aspose.BarCode 購買頁面](https://purchase.aspose.com/buy) 了解各種授權計畫。

**Q: 有提供 Aspose.BarCode 的免費試用版嗎？**  
A: 有，您可從 [Aspose 下載頁面](https://releases.aspose.com/) 取得功能完整的試用版。

**Q: 如何取得支援或加入社群？**  
A: 請造訪官方 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 取得協助、範例與社群討論。

---

**最後更新：** 2025-12-04  
**測試環境：** Aspose.BarCode 24.12 for Java  
**作者：** Aspose

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
