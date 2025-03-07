---
title: Java 取得並識別條碼
linktitle: 取得並識別條碼
second_title: Aspose.BarCode Java API
description: 輕鬆整合 Aspose.BarCode for Java - 從資料庫取得並識別條碼。立即下載以獲得無縫條碼整合體驗。
weight: 11
url: /zh-hant/java/symbology-and-format/fetching-recognizing-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 取得並識別條碼


## 介紹

您是否希望輕鬆地將條碼識別整合到您的 Java 應用程式中？ Aspose.BarCode for Java 提供了一個強大且使用者友好的解決方案，可輕鬆取得和識別條碼。在本逐步指南中，我們將引導您完成使用 Aspose.BarCode 取得和識別條碼的過程，確保無縫整合到您的 Java 專案中。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- 對 Java 程式設計有基本的了解。
-  Aspose.BarCode for Java 程式庫已安裝。你可以下載它[這裡](https://releases.aspose.com/barcode/java/).
- 存取包含以 BLOB 格式儲存的條碼影像的資料庫。
- 您的電腦上安裝了 Java 開發工具包 (JDK)。

## 導入包

首先，導入 Java 專案所需的套件。確保 Aspose.BarCode 庫包含在您的專案依賴項中。

```java

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.io.*;
import java.sql.*;
```

## 步驟1：建立資料庫連接

```java
String strBarCodeImage = "c:\\temp\\code39.jpg";

//開啟與資料庫的連接
Connection con = null;
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);
```

## 第2步：執行SQL查詢

```java
//建立一條語句來執行 SELECT SQL
PreparedStatement st = con.prepareStatement("SELECT * FROM Product ");
st.executeQuery();
ResultSet rs = st.getResultSet();
```

## 第 3 步：取得並建立影像

```java
while (rs.next()) {
    //讀取 BLOB 欄位並從中建立映像
    String len1 = rs.getString("BarCodeImage");
    int len = len1.length();
    byte[] b = new byte[len];
    InputStream in = rs.getBinaryStream("BarCodeImage");

    int index = in.read(b, 0, len);
    OutputStream outImgBarCode = new FileOutputStream(strBarCodeImage);

    while (index != -1) {
        //將位元組寫入文件
        outImgBarCode.write(b, 0, index);
        //讀取下一個位元組
        index = in.read(b, 0, len);
    }
    outImgBarCode.close();
```

## 第 4 步：從影像中讀取條碼

```java
//從影像中讀取條碼
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

透過執行這些步驟，您可以將 Aspose.BarCode 無縫整合到您的 Java 應用程式中，從而能夠從資料庫中有效地取得和識別條碼。

## 結論

總之，Aspose.BarCode for Java 簡化了獲取和識別條碼的過程，使其成為尋求可靠且高效解決方案的開發人員的理想選擇。透過遵循本指南，您可以輕鬆地在 Java 應用程式中實現條碼識別。

## 經常問的問題

### Aspose.BarCode 是否與所有條碼類型相容？
是的，Aspose.BarCode 支援多種條碼類型，包括 CODE_39_STANDARD、QR 碼等。檢查文件以取得完整清單。

### 我可以將 Aspose.BarCode 與不同的資料庫一起使用嗎？
當然，Aspose.BarCode 旨在與各種資料庫配合使用。確保相應地調整資料庫連接詳細資訊。

### 條碼辨識過程中出現錯誤如何處理？
異常處理至關重要。確保實施強大的錯誤處理，以解決條碼識別過程中任何不可預見的問題。

### Aspose.BarCode適合大規模應用嗎？
是的，Aspose.BarCode 旨在處理大型應用程序，提供高效能和可靠性。

### 臨時許可證是否可用於測試目的？
是的，您可以獲得臨時許可證[這裡](https://purchase.aspose.com/temporary-license/)用於測試和評估目的。

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
