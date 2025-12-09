---
date: 2025-11-30
description: 學習如何使用 Aspose.BarCode 在 Java 中偵測條碼方向。本指南將教您如何在 Java 中讀取條碼，並高效地從圖像中辨識條碼。
linktitle: Detect Barcode Orientation Java
second_title: Aspose.BarCode Java API
title: 使用 Aspose.BarCode 在 Java 中偵測條碼方向
url: /zh-hant/java/advanced-settings-and-optimization/configuring-barcode-orientation/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 在 Java 中使用 Aspose.BarCode 偵測條碼方向

## 簡介

條碼無處不在——從零售貨架到倉庫庫存——因此能夠可靠地 **detect barcode orientation java** 成為任何現代 Java 應用程式的必備功能。Aspose.BarCode for Java 透過自動辨識條碼在影像中出現的角度，讓這項工作變得輕而易舉。在本教學中，你將學會如何在 Java 中讀取條碼、從影像檔案辨識條碼，並讓程式庫為你處理方向偵測。

## 快速解答
- **「detect barcode orientation java」是什麼意思？**  
  它指的是自動判斷影像中條碼的旋轉角度，以便正確解碼。
- **我需要手動指定旋轉角度嗎？**  
  不需要 — Aspose.BarCode 會自動偵測方向。
- **支援哪些條碼類型？**  
  所有主要的 1‑D 與 2‑D 格式，包括 Code39、QR、DataMatrix 等。
- **主要前置條件是什麼？**  
  已安裝 JDK 以及 Aspose.BarCode for Java 程式庫。
- **我可以在正式環境中使用嗎？**  
  可以，只要使用有效的商業授權。

## 為什麼要偵測條碼方向？

* **提升可靠性：** 掃描圖像常常傾斜；自動偵測可消除讀取失敗。  
* **節省開發時間：** 無需自行撰寫影像處理程式碼。  
* **支援多種條碼標準：** 同時適用於 1‑D（例如 Code39）和 2‑D（例如 QR）符號。

## 前置條件

在開始之前，請確保你已具備：

- 已安裝 Java Development Kit (JDK) 8 或以上版本。  
- Aspose.BarCode for Java 程式庫 ─ 從[官方網站](https://releases.aspose.com/barcode/java/)下載最新版本。  
- 一個包含條碼的影像檔（我們將使用 Code39 範例）。

## 匯入命名空間

首先，匯入所需的類別。這樣即可存取讀取器、結果物件與解碼選項。

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 步驟 1：設定文件目錄

定義測試影像所在的資料夾。將佔位符替換為你機器上的實際路徑。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

## 步驟 2：從影像讀取 Code39 條碼

建立 `BarCodeReader` 實例，指向包含 Code39 條碼的影像檔。`DecodeType.CODE_39_STANDARD` 告訴程式庫預期的類型，但若省略此參數，讀取器也能自動偵測。

```java
// Read code39 barcode from image
String image = dataDir + "code39Extended.jpg";
BarCodeReader reader = new BarCodeReader(image, DecodeType.CODE_39_STANDARD);
```

## 步驟 3：自動條碼方向偵測

Aspose.BarCode for Java **自動偵測條碼方向**，因此你不需要自行旋轉影像。

```java
// Barcode orientation is detected automatically
```

## 步驟 4：在影像中辨識條碼

現在讓讀取器掃描影像。迴圈會遍找到的每個條碼，並同時印出解碼文字與條碼類型。這示範了如何 **在 Java 中讀取條碼** 以及 **從影像檔案辨識條碼**，只需一次呼叫即可完成。

```java
// Try to recognize all possible barcodes in the image
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("BarCode CodeText: " + result.getCodeText());
    System.out.println("BarCode CodeType: " + result.getCodeTypeName());
}
```

## 常見問題與解決方案

| 問題 | 原因 | 解決方式 |
|------|------|----------|
| 沒有輸出結果 | 檔案路徑錯誤或影像格式不支援 | 核對 `dataDir`，並確保影像為支援的類型（PNG、JPEG、BMP）。 |
| 偵測到的方向不正確 | 影像嚴重傾斜（>45°） | 先對影像進行校正，或使用 `reader.setRotateAngle()` 提供提示。 |
| 不支援的條碼類型 | 嘗試讀取 `DecodeType` 未涵蓋的條碼 | 省略 `DecodeType` 參數；程式庫會嘗試對所有支援類型進行自動偵測。 |

## 常見問與答

### Q1：Aspose.BarCode 是否相容所有條碼類型？
**A：** 是的。Aspose.BarCode 支援廣泛的 1‑D 與 2‑D 符號，包括 Code39、QR Code、DataMatrix、PDF417 等等。完整清單請參閱[文件說明](https://reference.aspose.com/barcode/java/)。

### Q2：我可以在商業專案中使用 Aspose.BarCode for Java 嗎？
**A：** 當然可以。正式環境使用需購買商業授權。購買方式請見[Aspose 購買頁面](https://purchase.aspose.com/buy)。

### Q3：有免費試用嗎？
**A：** 有，你可以在[此處](https://releases.aspose.com/)下載功能完整的試用版。

### Q4：如何取得評估用的臨時授權？
**A：** 臨時授權提供短期測試使用。請從[臨時授權頁面](https://purchase.aspose.com/temporary-license/)申請。

### Q5：如果遇到問題，該向哪裡尋求協助？
**A：** Aspose.BarCode 社群論壇是提問與分享解決方案的好地方：[Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13)。

---

**最後更新：** 2025-11-30  
**測試環境：** Aspose.BarCode for Java 24.12（撰寫時的最新版本）  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}