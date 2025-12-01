---
date: 2025-11-30
description: 學習如何在 Java 中使用 Aspose.Barcode 評估條碼讀取品質。逐步指南教您取得辨識品質百分比。
language: zh-hant
linktitle: Getting Barcode Recognition Quality in Percent
second_title: Aspose.Barcode Java API
title: Aspose.Barcode Java – 獲取條碼識別品質（百分比）
url: /java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/
weight: 21
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Aspose.Barcode Java – 取得條碼辨識品質百分比

## 介紹

如果您需要在 Java 應用程式中 **評估條碼讀取品質**，**Aspose.Barcode Java** 提供一個簡單的 API，會以百分比形式回傳辨識品質。在本教學中，我們將逐步說明取得該百分比的完整流程，解釋此指標的重要性，並示範如何將呼叫整合到您現有的程式碼中。

## 快速回答
- **「reading quality」是什麼意思？** 這是函式庫為每個解碼條碼指派的信心分數（0‑100 %）。  
- **需要哪個函式庫版本？** 任何近期的 Aspose.Barcode Java 版本（範例使用最新的 24.x 系列）。  
- **需要授權嗎？** 測試時可使用臨時授權；正式環境需購買完整授權。  
- **能讀取所有條碼類型嗎？** 可以 – 使用 `DecodeType.ALL_SUPPORTED_TYPES` 旗標即可啟用 Aspose.Barcode 支援的所有格式。  
- **品質值對 QR Code 可靠嗎？** 絕對可靠 – 相同的信心演算法適用於 1‑D 與 2‑D 符號。

## Aspose.Barcode Java 是什麼以及如何評估條碼讀取品質？

**Aspose.Barcode Java** 是一套完整管理的函式庫，讓開發者在不依賴外部元件的情況下產生、讀取與分析條碼。其中最有用的診斷指標之一是 **reading quality**，它告訴您引擎對於解碼符號的信心程度。當您需要決定是否接受掃描、要求重新捕捉，或觸發錯誤處理邏輯時，這個指標相當關鍵。

## 為什麼使用 Aspose.Barcode Java 來評估條碼讀取品質？

- **在所有支援的符號中提供一致的信心分數**。  
- **無需原生 DLL** – 純 Java，適用於任何相容 JVM 的平台。  
- **細緻的控制**：您可以取得每個條碼的品質，而非僅有全域通過/失敗。  
- **效能優化** 的讀取引擎，能從桌面擴展到雲端服務。

## 前置條件

在開始之前，請確保您已具備：

- **Java 開發環境** – JDK 8 或更新版本，搭配您喜愛的 IDE（IntelliJ、Eclipse、VS Code 等）。  
- **Aspose.Barcode Java 函式庫** – 從官方網站下載最新的 JAR：[Aspose.Barcode for Java](https://releases.aspose.com/barcode/java/)。  
- **範例條碼影像** – 本教學使用位於 `BarcodeReader/advanced_features/` 資料夾的 `code39Extended.jpg`。

現在環境已備妥，讓我們深入程式碼。

## 匯入命名空間

以下的匯入讓您可以存取讀取器與結果類別，以便取得品質資訊。

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
```

### 步驟 1：設定資源目錄路徑

定義包含範例影像的資料夾。`Utils.getDataDir` 是一個協助函式，可為目前專案解析絕對路徑。

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GetBarCodeRecognitionQualityInPercent.class)
        + "BarcodeReader/advanced_features/";
```

### 步驟 2：初始化 BarCodeReader 物件

建立 `BarCodeReader` 實例，指向影像檔案，並告訴它嘗試 **所有支援的條碼類型**。

```java
// Initialize the BarCodeReader object
BarCodeReader reader = new BarCodeReader(dataDir + "code39Extended.jpg",
        com.aspose.barcode.barcoderecognition.DecodeType.ALL_SUPPORTED_TYPES);
```

### 步驟 3：讀取條碼並取得品質百分比

遍歷每個偵測到的條碼，印出其文字、類型，以及 `getReadingQuality()` 回傳的 **reading quality** 百分比。

```java
// Call the read method
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println(result.getCodeText() + " Type: " + result.getCodeType());
    double percent = result.getReadingQuality();
    System.out.println("Percent: " + percent);
}
```

**這裡發生了什麼？**  
- `readBarCodes()` 會回傳一個 `BarCodeResult` 物件集合，對應每個找到的條碼。  
- `getReadingQuality()` 產生介於 `0` 到 `100` 之間的 `double`，代表信心等級。  
- 您可以利用此數值判斷掃描是否可接受，或是否需要提示使用者再次嘗試。

## 常見問題與解決方案

| 問題 | 原因 | 解決方案 |
|------|------|----------|
| **品質始終為 0** | 圖像解析度過低或嚴重模糊。 | 使用較高解析度的來源或進行影像前處理（例如銳化）。 |
| **未偵測到條碼** | `DecodeType` 旗標設定錯誤。 | 確認使用 `DecodeType.ALL_SUPPORTED_TYPES`，或指定您預期的確切類型。 |
| **`Utils.getDataDir` 發生例外** | 專案結構與範例不同。 | 將輔助函式呼叫改為硬編碼的絕對路徑或符合您布局的相對路徑。 |

## 常見問答

### Q1：Aspose.Barcode 是否相容所有條碼類型？

A1：Aspose.Barcode 支援廣泛的條碼符號，包括 1‑D（Code‑39、Code‑128、UPC）與 2‑D（QR、DataMatrix、PDF417）等標準。

### Q2：我可以將 Aspose.Barcode 用於商業用途嗎？

A2：可以，您可以在個人或商業專案中使用 Aspose.Barcode。授權細節請參閱 [此處](https://purchase.aspose.com/buy)。

### Q3：如何取得測試用的臨時授權？

A3：可從 Aspose 入口網站取得臨時授權，網址在 [此處](https://purchase.aspose.com/temporary-license/)。

### Q4：在哪裡可以找到更多支援與社群討論？

A4：請造訪 [Aspose.Barcode 論壇](https://forum.aspose.com/c/barcode/13) 取得同儕支援與官方協助。

### Q5：文件中是否有程式碼範例？

A5：官方文件提供完整的程式碼範例，請參考 [此處](https://reference.aspose.com/barcode/java/)。

## 結論

透過 **Aspose.Barcode Java**，您可以輕鬆取得任何掃描符號的 **條碼讀取品質** 百分比。此指標讓您能建立更智慧的驗證邏輯、提升使用者體驗，並在 Java 應用程式中維持高資料完整性。

---

**最後更新：** 2025-11-30  
**測試環境：** Aspose.Barcode Java 24.11  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}