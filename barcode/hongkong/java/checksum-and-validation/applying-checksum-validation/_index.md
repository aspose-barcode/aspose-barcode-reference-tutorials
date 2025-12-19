---
date: 2025-12-19
description: 學習如何在 Java 中使用 Aspose.BarCode 停用校驗碼驗證。本分步指南將向您展示如何讀取條碼、關閉校驗碼，以及確保資料處理的可靠性。
linktitle: How to Disable Checksum Validation
second_title: Aspose.BarCode Java API
title: 如何在 Java 中停用校驗和驗證
url: /zh-hant/java/checksum-and-validation/applying-checksum-validation/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 如何在 Java 中停用校驗和驗證

在現代的庫存與物流應用程式中，**如何停用校驗和**可能是讀取不含校驗位的舊版條碼的關鍵。Aspose.BarCode for Java 讓您輕鬆關閉校驗和驗證，同時仍能提取編碼資料。本教學將帶您完成整個流程——從設定專案到在不驗證校驗和的情況下讀取 ONE‑CODE 條碼。

## 快速解答
- **停用校驗和會有什麼作用？** 它會指示讀取器忽略校驗和欄位，允許未包含有效校驗和的條碼被處理。  
- **什麼時候應該停用校驗和？** 在使用舊版系統或省略或損壞校驗和的非標準條碼時。  
- **哪個類別控制校驗和驗證？** `BarCodeReader.setChecksumValidation(ChecksumValidation)`  
- **停用校驗和安全嗎？** 僅當您信任條碼來源時才安全；否則，驗證有助於捕捉錯誤。  
- **這會影響其他條碼類型嗎？** 此設定僅套用於目前的 `BarCodeReader` 實例。

## 什麼是校驗和驗證？
校驗和驗證是一種資料完整性檢查，會根據條碼內容計算出一個小值，並與內嵌的校驗和進行比較。若兩者不相符，條碼即被視為無法讀取。停用此檢查即告訴 Aspose.BarCode 跳過此比較。

## 為何在 Aspose.BarCode 中停用校驗和？
- **舊版支援：** 較舊的掃描器常會產生未包含校驗和的條碼。  
- **效能：** 跳過計算可加快大量讀取的速度。  
- **彈性：** 您可依每個讀取器實例決定是否強制驗證。

## 前置條件
- **Java Development Kit (JDK)：** 請確保已安裝最新的 JDK。  
- **Aspose.BarCode 函式庫：** 從官方網站[此處](https://releases.aspose.com/barcode/java/)下載函式庫。  

## 匯入套件
在您的 Java 專案中，匯入必要的 Aspose.BarCode 類別以使用條碼辨識功能。

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## 步驟說明

### 步驟 1：設定專案
建立一個新的 Java 專案（使用您偏好的 IDE），並將 Aspose.BarCode JAR 加入專案的 classpath。

### 步驟 2：初始化 `BarCodeReader`
載入包含您欲讀取之 ONE‑CODE 條碼的影像。

```java
String dataDir = "Your Document Directory";
BarCodeReader reader = new BarCodeReader(dataDir + "onecode.png", DecodeType.ONE_CODE);
```

### 步驟 3：如何停用校驗和
將屬性設定為 `OFF`，告訴讀取器忽略校驗和驗證。

```java
reader.setChecksumValidation(ChecksumValidation.OFF);
```

### 步驟 4：讀取條碼
遍歷結果，並輸出解碼後的文字與條碼類型。

```java
for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}
```

**結果：** 即使原始影像未包含有效校驗和，仍會顯示條碼文字。

## 常見問題與技巧
- **檔案路徑不正確：** 確認 `dataDir` 指向正確的資料夾；測試時請使用絕對路徑。  
- **不支援的條碼類型：** 確保 `DecodeType` 與您正在讀取的條碼相符。  
- **效能：** 在大量批次中停用校驗和可提升吞吐量，但對於關鍵資料請務必重新啟用。

## 常見問答

### Aspose.BarCode 是否相容於不同的條碼類型？
是的，Aspose.BarCode 支援廣泛的條碼符號集，從 QR 與 DataMatrix 到傳統的一維條碼皆可。

### 我可以將 Aspose.BarCode 用於商業用途嗎？
當然可以。針對需要投入生產環境功能的企業，我們提供商業授權。

### 我該如何取得 Aspose.BarCode 的支援？
前往 [Aspose.BarCode 論壇](https://forum.aspose.com/c/barcode/13) 與社群互動，並獲得產品團隊的協助。

### 是否提供免費試用？
是的，您可下載 [免費試用版](https://releases.aspose.com/) 以體驗完整功能。

### 我可以在哪裡找到詳細文件？
請參考完整的 [文件](https://reference.aspose.com/barcode/java/) 以取得 API 細節、程式碼範例與最佳實踐。

---

**最後更新：** 2025-12-19  
**測試環境：** Aspose.BarCode for Java (latest release)  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}