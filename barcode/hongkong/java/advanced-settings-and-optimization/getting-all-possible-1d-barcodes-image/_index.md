---
date: 2026-07-18
description: 了解如何在 Java 中使用 Aspose.BarCode 讀取 1D 條碼 – 這是一個快速的 Java 條碼解碼庫，可從圖像中提取條碼。
keywords:
- read 1d barcodes java
- java barcode decoding library
- java barcode reader example
lastmod: 2026-07-18
linktitle: 在 Java 中讀取 1D 條碼
og_description: 使用 Aspose.BarCode 在 Java 中讀取 1D 條碼，這是一個高效能的 Java 條碼解碼庫，能快速從圖像中讀取多個條碼。
og_image_alt: 'Developer guide: read 1d barcodes in Java with Aspose.BarCode'
og_title: 在 Java 中讀取 1D 條碼 – 使用 Aspose.BarCode 解碼條碼
schemas:
- author: Aspose
  dateModified: '2026-07-18'
  description: Learn how to read 1D barcodes in Java with Aspose.BarCode – a fast
    Java barcode decoding library that extracts barcodes from images.
  headline: read 1d barcodes java – Decode barcodes with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: Yes. A commercial license removes all evaluation limitations and grants
      you full redistribution rights.
    question: Is Aspose.BarCode for Java suitable for commercial projects?
  - answer: Absolutely. Obtain a temporary license from the [Aspose temporary‑license
      page](https://purchase.aspose.com/temporary-license/) for development and testing.
    question: Can I test the library without purchasing a license?
  - answer: The comprehensive documentation is available [here](https://reference.aspose.com/barcode/java/).
    question: Where can I find the full API reference?
  - answer: Post your question on the [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)
      where the community and Aspose engineers can assist you.
    question: How do I get help if I run into a problem?
  - answer: Yes – you can download a trial version from the [Aspose releases page](https://releases.aspose.com/).
    question: Is there a free trial download?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- read 1d barcodes java
- Aspose.BarCode
- Java barcode processing
title: 在 Java 中讀取 1D 條碼 – 使用 Aspose.BarCode 解碼條碼
url: /zh-hant/java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 使用 Aspose.BarCode 讀取 Java 1D 條碼

## 簡介

在本實作指南中，您將學習如何使用功能強大的 **Aspose.BarCode** 函式庫 **在 Java 中讀取 1D 條碼**。無論您需要掃描產品標籤、庫存標籤，或是圖像中嵌入的任何線性條碼，本教程將逐步說明從環境設定到提取圖像中所有可能條碼的每個步驟。完成後，您只需幾行 Java 程式碼即可 **從圖像檔案解碼條碼**。

## 快速解答
- **Aspose.BarCode 的功能是什麼？** 它提供一個功能完整的 Java 條碼函式庫，能產生與解碼 1D/2D 條碼。  
- **我可以從單一圖像讀取多個條碼嗎？** 可以 — `BarCodeReader.readBarCodes()` 方法會返回所有偵測到的符號。  
- **開發時需要授權嗎？** 臨時授權可用於測試；正式環境需購買商業授權。  
- **支援哪些 Java 版本？** Java 8 以上（建議使用 JDK 11）。  
- **此函式庫足夠快以支援即時掃描嗎？** 絕對可以 — 它已針對高效能批次處理進行最佳化。  

`BarCodeReader.readBarCodes()` 方法會掃描提供的圖像，並返回一個 `BarCodeResult` 物件集合，代表每個偵測到的條碼。

## 什麼是「read 1d barcodes java」？

在 Java 中讀取 1D 條碼是使用 Java 函式庫從圖像中提取線性條碼資料的過程。它會分析圖像、定位條碼圖樣，並返回編碼文字以及符號類型、方向等中繼資料。Aspose.BarCode for Java 會自動執行此分析，處理旋轉、低對比度以及各種符號類型，讓您專注於將結果整合至應用程式中。

## 為何選擇 Aspose.BarCode 來從圖像解碼條碼？

Aspose.BarCode 提供業界領先的準確度與速度：一次即可解碼超過 50 種 1D 與 2D 符號，且在標準伺服器上能在 0.2 秒內處理一般 300 dpi 圖像。API 僅需少量方法呼叫，免除外部相依，支援 Java 8 以上，並能每分鐘批次處理數千張圖像。這些具體效益使其成為企業級條碼掃描的首選。

## 先決條件

在開始編寫程式碼之前，請確保您已具備以下項目：

- **Java Development Kit (JDK)** – 版本 8 或更新。從官方的 [Oracle JDK page](https://www.oracle.com/java/technologies/javase-downloads.html) 下載。  
- **Aspose.BarCode for Java** – 從 [Aspose release page](https://releases.aspose.com/barcode/java/) 取得最新的 JAR 檔案。  

環境設定完成後，讓我們開始編寫程式碼。

## 匯入命名空間

加入必要的 `import` 陳述式，讓編譯器能找到 Aspose 的類別。

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 步驟 1：初始化 BarCodeReader 物件

`BarCodeReader` 類別是 Aspose.BarCode 用於掃描圖像與提取條碼資訊的核心元件。建立指向圖像檔案的 `BarCodeReader` 實例。`DecodeType` 參數告訴引擎要偵測哪些符號；以 `CODE_128` 為例可支援多種常見的 1D 碼。

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **小技巧：** 若想掃描所有支援的 1D 類型，請傳入 `DecodeType.ALL_1D`，而非單一符號類型。

## 步驟 2：讀取所有可能的條碼

`BarCodeResult` 物件代表單一偵測到的條碼，提供解碼文字、符號名稱、旋轉角度以及條碼區域四個角座標等屬性。遍歷 `readBarCodes()` 回傳的集合。對於每個結果，我們會列印解碼文字、符號名稱、偵測角度以及條碼區域的四個角座標。

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

此迴圈會自動處理所有偵測到的條碼，無需重複呼叫讀取器。迴圈結束後，`iCount` 會保存偵測到的條碼總數。

## 常見問題與解決方法

| 症狀 | 可能原因 | 解決方案 |
|---------|--------------|----------|
| 未返回條碼 | 圖像過於模糊或對比度低 | 在送入讀取器前先對圖像進行前處理（提升對比度、二值化）。 |
| 報告的符號類型錯誤 | 使用了不正確的 `DecodeType` | 使用 `DecodeType.ALL_1D` 讓引擎自動偵測任何 1D 類型。 |
| 角度值不正確 | 圖像已旋轉 | API 已返回旋轉角度，必要時可將圖像旋轉回原始方向。 |

## 常見問與答

**Q: Aspose.BarCode for Java 是否適用於商業專案？**  
A: 是的。商業授權會移除所有評估限制，並賦予完整的再分發權利。

**Q: 我可以在未購買授權的情況下測試此函式庫嗎？**  
A: 當然可以。可從 [Aspose temporary‑license page](https://purchase.aspose.com/temporary-license/) 取得臨時授權，用於開發與測試。

**Q: 我在哪裡可以找到完整的 API 參考文件？**  
A: 完整文件可在 [here](https://reference.aspose.com/barcode/java/) 取得。

**Q: 若遇到問題，該如何取得協助？**  
A: 可在 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 發問，社群與 Aspose 工程師會提供協助。

**Q: 有免費試用版可下載嗎？**  
A: 有 — 您可從 [Aspose releases page](https://releases.aspose.com/) 下載試用版。

## 結論

您現在已學會使用 Aspose.BarCode **在 Java 中讀取 1D 條碼**，這是一個強大的 **Java 條碼函式庫**，能讓從圖像檔案解碼條碼變得簡單且可靠。將此程式碼片段整合至您的應用程式，可自動化庫存掃描、票券驗證，或任何圖像中出現線性條碼的情境。

---

**最後更新：** 2026-07-18  
**測試環境：** Aspose.BarCode 24.11 for Java  
**作者：** Aspose

## 相關教學

- [Java 讀取條碼：高效能條碼讀取器以加速圖像處理](/barcode/java/advanced-settings-and-optimization/faster-image-processing-barcode-recognition/)
- [從圖像讀取條碼 – 精通使用 Aspose.BarCode 在 Java 中提取條碼區域](/barcode/java/advanced-settings-and-optimization/extracting-barcode-region-information/)
- [Aspose.Barcode Java – 取得條碼辨識品質百分比](/barcode/java/advanced-settings-and-optimization/getting-barcode-recognition-quality-percent/)


{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}
{{< /blocks/products/pf/main-wrap-class >}}