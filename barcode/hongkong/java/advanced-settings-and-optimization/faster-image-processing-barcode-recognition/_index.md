---
date: 2026-02-04
description: 學習如何在 Java 中使用 Aspose.BarCode 的高效能模式快速讀取條碼。
linktitle: Faster Image Processing for Barcode Recognition
second_title: Aspose.BarCode Java API
title: Read Barcode Java：高效能條碼讀取器，提升影像處理速度
url: /zh-hant/java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取條碼 Java：高效能條碼閱讀器，加速影像處理

在現代 Java 應用程式中，**read barcode java** 能快速且可靠地執行是必備功能，尤其是當您面對高吞吐量的掃描站或大量影像批次處理時。Aspose.BarCode for Java 提供 **high performance barcode reader**，讓您開啟高效能模式、微調品質設定，並保持最高的辨識準確度。本指南將逐步說明如何設定閱讀器、解釋效能提升的原因，以及如何排除常見的偵測問題。

## 快速解答
- **「high performance barcode reader」是什麼意思？** 這是一種透過最佳化影像處理演算法來最大化掃描速度的設定。  
- **範例中使用哪種條碼符號？** DataMatrix（2‑D 條碼的一種）。  
- **如何開啟高效能模式？** 呼叫 `reader.setQualitySettings(QualitySettings.getHighPerformance())`。  
- **正式環境需要授權嗎？** 需要，非試用版必須使用商業授權。  
- **支援哪個 Java 版本？** 完全支援 Java 8 及以上版本。

## 什麼是高效能條碼閱讀器？
**high performance barcode reader** 是 Aspose.BarCode 引擎的特別調校版本，能減少處理開銷、套用積極的影像前處理，並加速解碼迴圈。此模式非常適合高吞吐量掃描站、行動應用程式或大量影像批次處理等情境。

## 為什麼要使用 Aspose.BarCode 的高效能模式？
- **速度：** 相較於預設設定，解碼速度提升 2‑3 倍。  
- **可擴展性：** 在一般硬體上每分鐘可處理上千張影像。  
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

## 高效能讀取條碼 Java 的逐步指南

### 步驟 1：設定資源目錄
定義存放範例影像的資料夾。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(FasterImageProcessingForBarcodeRecognition.class) + "BarcodeReader/advanced_features/";
```

### 步驟 2：選取包含條碼的影像
將閱讀器指向您要解碼的影像。本範例使用 DataMatrix 影像。

```java
// Read code39 barcode from image
String imageFilePath = dataDir + "datamatrix.bmp";
```

### 步驟 3：建立 BarCodeReader 實例
以影像路徑與預期的符號類型建立 `BarCodeReader`。

```java
// Create an instance of BarCodeReader and set image and symbology type to recognize
BarCodeReader reader = new BarCodeReader(imageFilePath, DecodeType.DATA_MATRIX);
```

### 步驟 4：啟用高效能模式
只需一次呼叫，即可將引擎切換至最佳化設定。

```java
// Set high performance mode
reader.setQualitySettings(QualitySettings.getHighPerformance());
```

### 步驟 5：微調個別選項（可選）
您仍可調整個別品質設定以符合影像特性。啟用中值平滑通常能改善噪點影像的結果。

```java
// Set separate options
reader.getQualitySettings().setAllowMedianSmoothing(true);
reader.getQualitySettings().setMedianSmoothingWindowSize(4);
```

### 步驟 6：從影像辨識條碼
執行閱讀器並輸出解碼資訊。此步驟完成 **read barcode java** 流程。

```java
// Try to recognize the barcode from the image
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("BarCode CodeText: " + result.getCodeText());
    System.out.println("BarCode CodeType: " + result.getCodeTypeName());
}
```

依照上述步驟，您現在已擁有一個 **high performance barcode reader**，能快速且可靠地處理影像。

## 常見使用情境
- **零售結帳系統**：每小時掃描上千件商品。  
- **倉儲庫存應用**：在 Android 裝置上即時回饋。  
- **批次處理管線**：從掃描文件或 PDF 中解碼條碼。

## 常見問題與解決方案
- **未偵測到條碼：** 確認影像路徑正確，且條碼未旋轉超過 45°。可考慮增大 `MedianSmoothingWindowSize`。  
- **即使開啟高效能模式仍很慢：** 請確保使用最新的 Aspose.BarCode JAR，舊版可能缺少效能改進。  
- **不支援的符號類型：** 檢查傳入的 `DecodeType` 是否與影像中的條碼相符。  
- **授權相關錯誤：** 若出現授權例外，請確認已套用有效的商業授權——這是 **barcode reader licensing** 的最佳實踐之一。

## 常見問答

**Q: Aspose.BarCode 是否支援多種條碼符號？**  
A: 是的，支援廣泛的 1‑D 與 2‑D 符號，包括 Code128、QR Code、DataMatrix 等。

**Q: 我可以同時使用 Aspose.BarCode 產生與辨識條碼嗎？**  
A: 當然可以。此函式庫提供完整的 API，讓您在 Java 應用程式中建立與讀取條碼。

**Q: Aspose.BarCode 有哪些授權方案？**  
A: 您可於 [Aspose.BarCode 購買頁面](https://purchase.aspose.com/buy) 了解各種授權計畫。

**Q: 有免費試用版嗎？**  
A: 有，完整功能的試用版可從 [Aspose 下載頁面](https://releases.aspose.com/) 取得。

**Q: 如何取得支援或加入社群？**  
A: 請前往官方 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 獲取協助、範例與社群討論。

---

**最後更新：** 2026-02-04  
**測試環境：** Aspose.BarCode 24.12 for Java  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}