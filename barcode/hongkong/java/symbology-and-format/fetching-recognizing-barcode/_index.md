---
date: 2026-04-29
description: 學習如何使用 Aspose.BarCode 在 Java 中讀取條碼。本教學示範條碼讀取器範例，從資料庫擷取並辨識條碼圖像。
keywords:
- read barcode java
- barcode reader example
- java barcode library
- read barcode image
- recognize barcode image
linktitle: 取得與辨識條碼
second_title: Aspose.BarCode Java API
title: 使用 Aspose 讀取條碼 Java – 獲取並辨識條碼
url: /zh-hant/java/symbology-and-format/fetching-recognizing-barcode/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# 讀取條碼 Java – 取得與辨識條碼

## 介紹

如果您需要快速 **read barcode java** 應用程式，Aspose.BarCode for Java 提供一種簡單且高效的方式，從資料庫取得條碼影像並在幾行程式碼內完成辨識。在本教學中，我們將逐步示範一個完整的實務範例，說明如何連接資料庫、擷取條碼影像，並使用 Aspose 條碼讀取器進行解碼。完成後，您將擁有一段可重複使用的程式碼片段，可直接嵌入任何 Java 專案。

## 快速解答
- **What does the library do?** 它可直接從檔案或串流讀取條碼影像（例如 Code 39）。  
- **Which primary keyword is targeted?** read barcode java  
- **Do I need a license for testing?** 可取得臨時授權供評估使用。  
- **What database type is shown?** 範例使用 MySQL，但程式碼可適用於任何相容 JDBC 的資料庫。  
- **How long does implementation take?** 基本整合大約需要 10‑15 分鐘。

## 什麼是「read barcode java」？
在 Java 中讀取條碼指的是載入包含條碼圖樣的影像，並使用解碼引擎將該圖樣轉換為原始資料字串。Aspose.BarCode 提供功能強大的解碼器，支援數十種條碼符號，包括 Code 39、QR 以及 DataMatrix。

## 為何使用 Aspose 的 Java 條碼函式庫？
- **Broad symbology support** – 開箱即支援超過 150 種條碼類型。  
- **No external dependencies** – 純 Java，於任何支援 JDK 8+ 的平台皆可執行。  
- **High accuracy** – 經過最佳化的演算法降低誤讀，即使在低品質影像上亦能保持高準確度。  
- **Simple API** – 只需幾行程式碼即可將原始影像轉換為可讀文字。

## 前置條件
- 具備 Java 程式設計的基礎知識。  
- Aspose.BarCode for Java 函式庫（在此 **[here](https://releases.aspose.com/barcode/java/)** 下載）。  
- 可存取以 BLOB 形式儲存條碼影像的資料庫。  
- 開發機上已安裝 JDK 8 或更新版本。

## 匯入套件

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

## 步驟 3：擷取並建立影像

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

## 常見問題與解決方案
- **NullPointerException when reading BLOBs** – 確認欄位名稱完全相符，且 BLOB 確實包含資料。  
- **Unsupported barcode type** – 檢查 `DecodeType` 是否與影像中儲存的符號相符；若為 QR Code 請使用 `DecodeType.QR`。  
- **File path permission errors** – `strBarCodeImage` 路徑必須允許 Java 程序寫入；如有需要可改用暫存目錄。  

## 常見問答

**Q: Aspose.BarCode 是否相容所有條碼類型？**  
A: 是的，它支援廣泛的條碼符號，包括 CODE_39_STANDARD、QR Code、DataMatrix 等等。完整列表請參考產品文件。

**Q: 我可以將 Aspose.BarCode 與不同的資料庫一起使用嗎？**  
A: 當然可以。範例使用 MySQL，但您可以透過更新驅動程式類別與連線字串，改用 PostgreSQL、SQL Server 或任何相容 JDBC 的資料庫。

**Q: 在條碼辨識過程中應如何處理錯誤？**  
A: 將讀取邏輯包在 try‑catch 區塊中（如範例所示），並記錄例外訊息。對於暫時性的 I/O 錯誤可考慮重試，且在解碼前先驗證影像檔案是否存在。

**Q: 此函式庫適用於大規模應用嗎？**  
A: 是的。Aspose.BarCode 為高吞吐量情境而設計；在需要時可在多執行緒間重複使用單一 `BarCodeReader` 實例。

**Q: 我可以從哪裡取得測試用的臨時授權？**  
A: 您可於 **[here](https://purchase.aspose.com/temporary-license/)** 取得臨時授權以供評估使用。

---

**最後更新:** 2026-04-29  
**測試環境:** Aspose.BarCode for Java 24.11  
**作者:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}