---
date: 2025-12-18
description: 學習如何使用 Aspose.BarCode 建立 Codabar 條碼圖像，並查看 Java 條碼讀取範例。透過本步驟指南，輕鬆產生與辨識條碼。
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: 如何在 Java 中建立帶校驗碼的 Codabar 條碼圖像
url: /zh-hant/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中使用校驗碼建立 Codabar 條碼圖像

## 介紹

在本教學中，您將學習如何使用 Aspose.BarCode 在 Java 中 **建立帶校驗碼的 Codabar 條碼圖像**。我們將示範產生 Codabar 條碼、啟用校驗碼，然後使用 **java 條碼讀取範例** 讀回。完成後，您將擁有一段可直接放入任何 Java 專的即用程式碼片段。

## 快速解答
- **校驗碼的作用是什麼？** 它在掃描時驗證條碼資料的完整性。  
- **需要哪個函式庫？** Aspose.BarCode for Java。  
- **開發時需要授權嗎？** 測試時可使用臨時授權；正式環境需購買完整授權。  
- **我可以自訂條碼外觀嗎？** 可以——顏色、尺寸與字型皆可透過產生器參數調整。  
- **這與所有 Java 版本相容嗎？** 此函式庫支援 Java 8 及更新版本。

## 什麼是 CodaBar 條碼？

CodaBar 是一種線性（1 維）符號，廣泛應用於圖書館、血庫與零售業。它能編碼數字資料及少量特殊字元，適合用於簡易、機器可讀的標籤。加入校驗碼（Mod 10）可提升讀取精確度，尤其在低品質列印時更為顯著。

## 為什麼要使用 Aspose.BarCode for Java？

Aspose.BarCode 提供 **java 條碼讀取範例**，將條碼產生與辨識的底層細節抽象化。它具備以下優勢：

* 完全掌控校驗碼模式。  
* 與 Java IDE 無縫整合。  
* 完備的文件與支援。  

## 前置條件

在開始之前，請確保您已具備以下條件：

- 已在電腦上安裝 Java Development Kit（JDK）。  
- Aspose.BarCode for Java 函式庫。您可從 [here](https://releases.aspose.com/barcode/java/) 下載。  
- 具備基本的 Java 程式設計概念。  

## 匯入套件

在您的 Java 專案中，匯入使用 Aspose.BarCode 所需的類別：

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

## 步驟說明

### 步驟 1：設定環境

建立一個新的 Java 專案，並將 Aspose.BarCode JAR 加入建置路徑。定義一個資料夾，用於儲存產生的圖像。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### 步驟 2：產生帶校驗碼的 CodaBar 條碼圖像

實例化 `BarcodeGenerator`，啟用校驗碼，選擇 Mod 10 模式，並儲存圖像。

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

### 步驟 3：Java 條碼讀取範例 – 辨識條碼

現在讀取條碼，開啟校驗碼驗證以確保資料正確。

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

執行程式後會輸出解碼文字、符號類型與計算出的校驗碼，證實條碼已正確產生且驗證無誤。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **校驗碼驗證失敗** | 確認 `EnableChecksum` 已設定為 `YES`，且 `CodabarChecksumMode` 與產生時使用的模式（Mod 10）相符。 |
| **找不到檔案錯誤** | 確保 `dataDir` 指向已存在的資料夾，且產生的圖像（`Codabar_Mod10.png`）已儲存於該處再進行讀取。 |
| **不支援的 Java 版本** | 使用 Java 8 或更新版本；較舊版本可能缺少必要的 API。 |

## 常見問答

**Q: Aspose.BarCode 是否相容所有 Java 版本？**  
A: Aspose.BarCode 設計可在 Java 8 及更新版本上運作。請參閱官方文件以取得詳細相容性資訊。

**Q: 我可以自訂產生的條碼外觀嗎？**  
A: 可以，您可透過產生器的參數 API 調整顏色、字型與圖像格式。

**Q: 是否提供測試用的臨時授權？**  
A: 可以，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得 Aspose.BarCode 的臨時授權。

**Q: 我可以在哪裡取得其他支援與資源？**  
A: 請前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得社群支援與討論。

**Q: 是否提供免費試用？**  
A: 可以，您可從 [here](https://releases.aspose.com/) 下載免費試用版，體驗 Aspose.BarCode 功能。

---

**最後更新：** 2025-12-18  
**測試環境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}