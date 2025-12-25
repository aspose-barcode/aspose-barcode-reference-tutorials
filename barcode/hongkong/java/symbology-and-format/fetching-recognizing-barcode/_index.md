---
date: 2025-12-25
description: 輕鬆整合 Aspose.BarCode for Java——從資料庫提取並辨識條碼。了解如何使用完整範例讀取 Java 條碼。
linktitle: Fetching and Recognizing Barcode
second_title: Aspose.BarCode Java API
title: 讀取條碼 Java – 獲取與辨識條碼
url: /zh-hant/java/symbology-and-format/fetching-recognizing-barcode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取條碼 Java – 取得與辨識條碼

## 簡介

您是否想在應用程式中 **read barcode java** 而不必與低階影像處理糾纏？Aspose.BarCode for Java 提供功能強大且易於使用的 API，讓您能從資料庫取得條碼影像並在幾行程式碼內完成辨識。在本步驟指南中，我們將逐步說明所有必要的操作——從環境設定到解碼 CODE‑39 條碼——讓您能快速且有信心地整合條碼辨識功能。

## 快速答覆
- **應該使用哪個函式庫？** Aspose.BarCode for Java 提供最完整的條碼讀取功能。
- **示範使用哪種條碼類型？** 此範例聚焦於 CODE‑39 Standard，但 API 支援數十種條碼符號。
- **開發時需要授權嗎？** 可取得臨時評估授權；正式上線則需購買完整授權。
- **主要前置條件是什麼？** Java JDK、Aspose.BarCode for Java，以及以 BLOB 形式儲存條碼影像的資料庫。
- **實作需要多久？** 大約 15‑20 分鐘即可完成可運作的原型。

## 前置條件

在深入本教學之前，請先確保以下前置條件已備妥：

- 具備 Java 程式設計的基本概念。
- 已安裝 Aspose.BarCode for Java 函式庫。您可於 [here](https://releases.aspose.com/barcode/java/) 下載。
- 能存取以 BLOB 格式儲存條碼影像的資料庫。
- 在您的機器上已安裝 Java Development Kit (JDK)。

## 匯入套件

開始之前，請為您的 Java 專案匯入必要的套件。確保已在專案相依性中加入 Aspose.BarCode 函式庫。

```java
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.*;
import java.sql.*;
```

## 步驟 1：建立資料庫連線

```java
String strBarCodeImage = "c:\\temp\\code39.jpg";

// Open a connection to the database
Connection con = null;
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);
```

## 步驟 2：執行 SQL 查詢

```java
// Create a statement to execute the SELECT SQL
PreparedStatement st = con.prepareStatement("SELECT * FROM Product ");
st.executeQuery();
ResultSet rs = st.getResultSet();
```

## 步驟 3：取得並建立影像

```java
while (rs.next()) {
    // Read BLOB field and create an image from it
    String len1 = rs.getString("BarCodeImage");
    int len = len1.length();
    byte[] b = new byte[len];
    InputStream in = rs.getBinaryStream("BarCodeImage");

    int index = in.read(b, 0, len);
    OutputStream outImgBarCode = new FileOutputStream(strBarCodeImage);

    while (index != -1) {
        // Write bytes to file
        outImgBarCode.write(b, 0, index);
        // Read next bytes
        index = in.read(b, 0, len);
    }
    outImgBarCode.close();
```

## 步驟 4：從影像讀取條碼

```java
// Read the barcode from the image
BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_STANDARD);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());
}

nCount++;
}

System.out.println(nCount + " records found.");
con.close();
} catch (Exception ex) {
System.out.println(ex.getMessage());
}
```

依照上述步驟，您即可將 Aspose.BarCode 無縫整合至 Java 應用程式，實現從資料庫高效執行 **read barcode java** 的功能。

## 結論

總結來說，Aspose.BarCode for Java 簡化了取得與辨識條碼的流程，是開發人員尋求可靠且高效解決方案的理想選擇。依照本指南，您可輕鬆在 Java 應用程式中實作條碼辨識功能。

## 常見問題

### Aspose.BarCode 是否相容所有條碼類型？

是，Aspose.BarCode 支援多種條碼類型，包括 CODE_39_STANDARD、QR Code 等。請參閱文件取得完整清單。

### 我可以將 Aspose.BarCode 與不同的資料庫一起使用嗎？

當然可以，Aspose.BarCode 設計上支援多種資料庫。請依需求調整資料庫連線資訊。

### 在條碼辨識過程中，我該如何處理錯誤？

例外處理相當重要。請確保實作健全的錯誤處理機制，以因應條碼辨識時可能發生的任何問題。

### Aspose.BarCode 適用於大型應用程式嗎？

是，Aspose.BarCode 為大型應用程式設計，提供高效能與可靠性。

### 是否提供測試用的臨時授權？

是，您可於 [here](https://purchase.aspose.com/temporary-license/) 取得臨時授權，以供測試與評估使用。

## 其他常見問題

**Q: 還能使用相同程式碼解碼哪些其他符號？**  
A: 只要將 `DecodeType` 列舉改為其他值（例如 `DecodeType.QR`、`DecodeType.CODE_128`），即可讀取其他支援的條碼類型。

**Q: 能否直接從 `ResultSet` 讀取條碼而不寫入檔案？**  
A: 可以，您可以將 `InputStream` 或 `byte[]` 傳入 `BarCodeReader` 建構子，以避免產生中間檔案。

**Q: 如何提升數千筆記錄的辨識速度？**  
A: 重複使用同一個 `BarCodeReader` 實例、批次處理影像，並考慮停用不必要的符號檢查。

**Q: 有沒有方法從同一張影像讀取多個條碼？**  
A: `readBarCodes()` 方法會回傳提供之影像中偵測到的所有條碼，您即可如範例般遍歷結果。

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}