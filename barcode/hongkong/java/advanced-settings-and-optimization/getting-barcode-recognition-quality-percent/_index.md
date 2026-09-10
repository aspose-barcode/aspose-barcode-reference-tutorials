---
date: 2026-07-23
description: 了解如何在 Java 中使用 Aspose.Barcode 評估條碼讀取品質。逐步說明如何使用 aspose barcode java 取得辨識品質百分比。
keywords:
- aspose barcode java
- barcode reading quality
- barcode confidence score
lastmod: 2026-07-23
linktitle: 取得條碼辨識品質（百分比）
og_description: aspose barcode java 可讓您以信心百分比的方式取得條碼讀取品質。於本簡明指南中了解完整步驟、前置條件與最佳實踐。
og_image_alt: Guide to retrieve barcode reading quality percentage using Aspose.Barcode
  Java
og_title: Aspose.Barcode Java – 取得條碼辨識品質（百分比）
schemas:
- author: Aspose
  dateModified: '2026-07-23'
  description: Learn how to assess barcode reading quality in Java with Aspose.Barcode.
    Step‑by‑step guide to retrieve recognition quality percentage using aspose barcode
    java.
  headline: Aspose.Barcode Java – Getting Barcode Recognition Quality in Percent
  type: TechArticle
- questions:
  - answer: It’s the confidence score (0‑100 %) that the library assigns to each decoded
      barcode.
    question: What does “reading quality” mean?
  - answer: Any recent Aspose.Barcode Java release (the sample uses the latest 24.x
      series).
    question: Which library version is required?
  - answer: A temporary license works for testing; a full license is required for
      production.
    question: Do I need a license?
  - answer: Yes – the `DecodeType.ALL_SUPPORTED_TYPES` flag enables every format supported
      by Aspose.Barcode.
    question: Can I read all barcode types?
  - answer: Absolutely – the same confidence algorithm is applied across 1‑D and 2‑D
      symbologies.
    question: Is the quality value reliable for QR codes?
  type: FAQPage
second_title: Aspose.Barcode Java API
tags:
- barcode recognition
- aspose barcode
- java barcode processing
title: Aspose.Barcode Java – 取得條碼辨識品質（百分比）
url: /zh-hant/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – 取得條碼辨識品質（百分比）

## 簡介

如果您需要在 Java 應用程式中**評估條碼讀取品質**，**Aspose.Barcode Java** 提供簡單的 API，可返回辨識品質的百分比。在本教學中，我們將逐步說明取得該百分比的具體步驟，解釋此指標的重要性，並示範如何將呼叫整合到現有程式碼中。使用 **aspose barcode java**，您可以即時決定掃描是否足夠可靠以供後續處理。

## 快速回答
- **閱讀品質是什麼意思？** 這是程式庫對每個解碼條碼所指派的信心分數（0‑100 %）。  
- **需要哪個程式庫版本？** 任何近期的 Aspose.Barcode Java 版本（範例使用最新的 24.x 系列）。  
- **我需要授權嗎？** 測試可使用臨時授權；正式環境需購買完整授權。  
- **我可以讀取所有條碼類型嗎？** 是的 – `DecodeType.ALL_SUPPORTED_TYPES` 旗標會啟用 Aspose.Barcode 支援的所有格式。  
- **品質值對 QR 碼可靠嗎？** 絕對可靠 – 相同的信心演算法適用於 1‑D 與 2‑D 符號。

## Aspose.Barcode Java 是什麼以及如何評估條碼閱讀品質？

Aspose.Barcode Java 是一個純 Java 程式庫，可產生、讀取與分析超過 **30 種條碼類型**的條碼。其中最有用的診斷功能之一是 **reading quality** 指標，可告訴您引擎解碼符號的信心程度。當您需要決定是否接受掃描、要求重新捕獲或觸發錯誤處理邏輯時，此指標相當重要。

## 為何使用 Aspose.Barcode Java 來取得條碼閱讀品質？

使用 Aspose.Barcode Java 可為開發人員提供跨所有支援條碼類型的可靠信心指標，實現精確的掃描驗證。此程式庫的純 Java 實作消除本機相依性，且優化的引擎提供快速處理與詳細的品質分數，協助應用程式在接受或拒絕條碼資料時作出明智決策。

- **一致的信心分數** across all supported symbologies.  
- **無本機 DLL** – pure Java, so it works on any JVM‑compatible platform.  
- **細緻的控制**: you can retrieve the quality per barcode, not just a global pass/fail.  
- **效能最佳化** reading engine that processes images up to 10 MB in under 200 ms on a typical server.  
- **支援 30+ 種條碼類型**, from classic Code‑39 to modern QR and DataMatrix.

## 先決條件

在開始之前，請確保您已具備以下條件：

- **Java 開發環境** – JDK 8 或更新版本，搭配您喜愛的 IDE（IntelliJ、Eclipse、VS Code 等）。  
- **Aspose.Barcode Java 程式庫** – 從官方網站下載最新的 JAR： [Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/)。  
- **範例條碼影像** – 本教學使用位於 `BarcodeReader/advanced_features/` 資料夾中的 `code39Extended.jpg`。

設定完成後，讓我們深入程式碼。

## 匯入命名空間

`BarCodeReader`、`BarCodeResult` 以及工具類別位於 `com.aspose.barcode` 套件中。BarCodeReader 是用來讀取影像並偵測條碼的核心類別。BarCodeResult 代表單一解碼條碼及其相關屬性。匯入它們即可取得讀取器與結果物件，以便提取品質資訊。

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

## 步驟 1：設定資源目錄路徑

定義包含範例影像的資料夾。`Utils.getDataDir` 是協助取得目前專案絕對路徑的工具函式。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

## 步驟 2：初始化 BarCodeReader 物件

BarCodeReader 為指定的影像與解碼設定建立掃描會話。`BarCodeReader` 是掃描影像並返回偵測到的條碼集合的核心類別。傳入 `DecodeType.ALL_SUPPORTED_TYPES` 可指示引擎搜尋所有已知格式。

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

## 步驟 3：讀取條碼並取得品質百分比

BarCodeResult 包含單一條碼的解碼文字與品質指標。`getReadingQuality()` 方法以百分比返回信心分數。使用 `new BarCodeReader(imagePath, DecodeType.ALL_SUPPORTED_TYPES)` 載入影像，呼叫 `readBarCodes()`，然後遍歷每個 `BarCodeResult` 並呼叫 `getReadingQuality()`。此方法回傳 0 到 100 之間的 double 值，代表信心程度。透過評估此數值，您可以設定接受門檻、記錄指標，或在品質低落時提示使用者重新掃描，以確保資料處理的可靠性。

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**發生了什麼？**  
- `readBarCodes()` 會回傳 `BarCodeResult` 物件的集合，每個找到的條碼對應一個物件。  
- `getReadingQuality()` 產生介於 `0` 與 `100` 之間的 `double`，代表信心等級。  
- 您可以利用此數值決定掃描是否可接受，或是否需要提示使用者再次嘗試。

## 閱讀品質指標是什麼？

閱讀品質指標是由 Aspose.Barcode 引擎根據影像清晰度、條碼對比度與解碼成功率計算出的信心百分比（0‑100 %）。數值越高，表示引擎對解碼資料與實際符號的匹配程度越有把握。

## 如何取得條碼閱讀品質百分比？

使用 `new BarCodeReader(imagePath, DecodeType.ALL_SUPPORTED_TYPES)` 載入影像，呼叫 `readBarCodes()`，然後遍歷每個 `BarCodeResult` 並呼叫 `getReadingQuality()`。此方法回傳 0 到 100 之間的 double 值，代表信心程度。透過評估此數值，您可以設定接受門檻、記錄指標，或在品質低落時提示使用者重新掃描，以確保資料處理的可靠性。

## 常見問題與解決方案

| Issue | Cause | Fix |
|-------|-------|-----|
| **品質始終為 0** | 圖像解析度低或嚴重模糊。 | 使用較高解析度的來源或套用影像前處理（例如銳化）。 |
| **未偵測到條碼** | `DecodeType` 旗標設定錯誤。 | 確認使用 `DecodeType.ALL_SUPPORTED_TYPES`，或指定您預期的確切類型。 |
| **`Utils.getDataDir` 發生例外** | 專案結構與範例不同。 | 將輔助函式呼叫改為硬編碼的絕對路徑，或使用符合您目錄結構的相對路徑。 |

## 常見問答

### Q1：Aspose.Barcode 是否相容所有條碼類型？

A1: Aspose.Barcode 支援廣泛的條碼符號，包括 1‑D（Code‑39、Code‑128、UPC）與 2‑D（QR、DataMatrix、PDF417）標準。

### Q2：我可以將 Aspose.Barcode 用於商業用途嗎？

A2: 可以，您可在個人或商業專案中使用 Aspose.Barcode。授權細節請參閱[此處](https://purchase.aspose.com/buy)。

### Q3：如何取得測試用的臨時授權？

A3: 可從 Aspose 入口網站取得臨時授權，請點選[此處](https://purchase.aspose.com/temporary-license/)。

### Q4：在哪裡可以找到其他支援與社群討論？

A4: 前往 [Aspose.Barcode 論壇](https://forum.aspose.com/c/barcode/13) 取得同儕支援與官方協助。

### Q5：文件中是否提供程式碼範例？

A5: 有，官方文件中提供完整的程式碼範例，請參閱[此處](https://reference.aspose.com/barcode/java/)。

## 結論

透過 **Aspose.Barcode Java**，您可以輕鬆取得任何掃描符號的 **條碼閱讀品質** 百分比。此指標讓您能構建更智慧的驗證邏輯、提升使用者體驗，並在 Java 應用程式中維持高資料完整性。

---

**最後更新：** 2026-07-23  
**測試環境：** Aspose.Barcode Java 24.11  
**作者：** Aspose  

{{< blocks/products/products-backtop-button >}}

## 相關教學

- [從影像讀取條碼 – 精通 Java 中的條碼區域提取 (Aspose.BarCode)](/barcode/java/advanced-settings-and-optimization/extracting-barcode-region-information/)
- [偵測 Java 中的條碼方向 (Aspose.BarCode)](/barcode/java/advanced-settings-and-optimization/configuring-barcode-orientation/)
- [如何在 Java 中使用 Aspose.BarCode 讀取 1D 條碼](/barcode/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}