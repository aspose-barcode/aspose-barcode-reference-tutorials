---
date: 2026-04-05
description: 學習如何使用 Aspose.BarCode 在 Java 中建立帶檢查碼的 Codabar 條碼圖像，並查看 Java 條碼讀取器範例。請依照本步驟指南產生與辨識條碼。
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: 為 CodaBar 應用校驗碼
second_title: Aspose.BarCode Java API
title: 如何在 Java 中建立帶校驗碼的 Codabar 條碼圖像
url: /zh-hant/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何使用校驗碼建立 Codabar 條碼 Java 圖像

## 簡介

在本教學中，您將使用 Aspose.BarCode for Java 以 Mod 10 校驗碼 **create codabar barcode java** 圖像。我們將示範產生 CodaBar 條碼、啟用校驗碼，然後使用 **java barcode reader example** 進行驗證。完成後，您將擁有一段可直接放入任何 Java 專案的即用程式碼，無論是圖書館系統、醫驗室標籤印表機，或是零售結帳解決方案。

## 快速解答
- **What does the checksum do?** 它在掃描時驗證條碼資料的完整性。  
- **Which library is required?** Aspose.BarCode for Java.  
- **Do I need a license for development?** 臨時授權可用於測試；正式授權則需於生產環境使用。  
- **Can I customize the barcode appearance?** 可以 — 顏色、尺寸與字型皆可透過產生器參數調整。  
- **Is this compatible with all Java versions?** 此函式庫支援 Java 8 及更新版本。

## 如何建立 codabar barcode java

以下您將看到簡潔的逐步說明，解釋 **why each line matters**，讓您能有信心將程式碼套用到自己的專案中。

### 什麼是 CodaBar 條碼？

CodaBar 是一種線性（1 維）符號，廣泛應用於圖書館、血庫與零售業。它能編碼數字資料及少量特殊字元，適合用於簡單的機器可讀標籤。加入校驗碼（Mod 10）可提升讀取精度，尤其在低品質列印時更為顯著。

### 為何使用 Aspose.BarCode for Java？

Aspose.BarCode 提供 **java barcode reader example**，抽象化條碼產生與辨識的底層細節。它提供：

* 對校驗碼模式的完整控制。  
* 與 Java IDE 無縫整合。  
* 豐富的文件與即時支援。  

### 前置條件

在深入之前，請確保您已具備：

- 已安裝 Java Development Kit (JDK) 8 或更新版本。  
- Aspose.BarCode for Java 函式庫。您可從 [here](https://releases.aspose.com/barcode/java/) 下載。  
- 具備基本的 Java 程式概念。  

### 匯入套件

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

### 步驟指南

#### 步驟 1：設定環境

建立一個新的 Java 專案，並將 Aspose.BarCode JAR 加入建置路徑。定義一個資料夾以儲存產生的圖像。

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### 步驟 2：產生帶校驗碼的 CodaBar 條碼圖像

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

#### 步驟 3：Java barcode reader example – 讀取條碼

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

執行程式碼將輸出解碼文字、符號類型與計算出的校驗碼，確認條碼已正確產生與驗證。

### 常見使用情境

- **Library Management:** 編碼書籍 ID，以便在結帳時快速掃描。  
- **Blood Bank Labels:** 透過校驗碼保護確保病患身分的準確性。  
- **Retail Shelf Labels:** 列印低成本、高速條碼以追蹤庫存。  

### 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **Checksum validation fails** | 確認 `EnableChecksum` 已設定為 `YES`，且 `CodabarChecksumMode` 與產生時使用的模式（Mod 10）相符。 |
| **File not found error** | 確保 `dataDir` 指向已存在的資料夾，且產生的圖像 (`Codabar_Mod10.png`) 已儲存於該處再進行讀取。 |
| **Unsupported Java version** | 使用 Java 8 或更新版本；較舊版本可能缺少必要的 API。 |

## 常見問與答

**Q: Is Aspose.BarCode compatible with all Java versions?**  
A: Aspose.BarCode 設計可在 Java 8 及更新版本上運作。請參閱官方文件以取得詳細相容性資訊。

**Q: Can I customize the appearance of the generated barcode?**  
A: 可以，您可透過產生器的參數 API 修改顏色、字型與圖像格式。

**Q: Are temporary licenses available for testing purposes?**  
A: 可以，您可從 [here](https://purchase.aspose.com/temporary-license/) 取得 Aspose.BarCode 的臨時授權。

**Q: Where can I find additional support and resources?**  
A: 前往 [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) 取得社群支援與討論。

**Q: Is there a free trial available?**  
A: 可以，您可從 [here](https://releases.aspose.com/) 下載免費試用版以體驗 Aspose.BarCode 功能。

---

**最後更新：** 2026-04-05  
**測試環境：** Aspose.BarCode for Java 24.12  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}