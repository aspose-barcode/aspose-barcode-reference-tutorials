---
date: 2026-05-04
description: 學習如何在 Java 中使用 Aspose.BarCode for Java 產生條碼影像並儲存。一步一步的指南，包含 MySQL 儲存、客製化技巧與完整程式碼。
keywords:
- java generate barcode image
- how to generate barcode java
- how to save barcode image
linktitle: 產生與儲存條碼
second_title: Aspose.BarCode Java API
title: Java 產生條碼圖片並儲存至資料庫
url: /zh-hant/java/symbology-and-format/generating-saving-barcode/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Java 產生條碼圖像

## 介紹

如果您需要快速 **Java 產生條碼圖像** 並將其與產品資料一起儲存，本教學正適合您。我們將示範如何使用 Aspose.BarCode for Java 產生 CODE‑39 條碼、將圖像儲存至磁碟，然後以 BLOB 方式插入 MySQL 資料庫。完成後，您將擁有一套可重複使用的模式，能夠套用於任何條碼類型或儲存需求。

## 快速解答
- **哪個函式庫可以在 Java 中產生條碼？** Aspose.BarCode for Java。  
- **我可以將條碼儲存為檔案嗎？** 可以 – 使用 `generator.save("path")`。  
- **我如何在 MySQL 中儲存圖像？** 將檔案讀入 `FileInputStream`，並在 `PreparedStatement` 中設定為二進位串流。  
- **支援哪些條碼類型？** CODE_39、CODE_128、QR、DataMatrix 等多種。  
- **生產環境需要授權嗎？** 需要商業授權；亦提供免費試用版。

## 什麼是 Java 產生條碼圖像？
在 Java 中產生條碼圖像是指將純文字（例如產品編號）轉換為掃描器可讀取的視覺圖形。Aspose.BarCode 抽象化了低階編碼細節，讓您專注於應用程式邏輯。

## 為什麼在此任務中使用 Aspose.BarCode？
- **功能完整**：支援超過 50 種條碼符號。  
- **簡易 API**：一行程式碼即可建立並儲存圖像。  
- **高品質**：產生 PNG、JPEG、BMP 與 PDF 輸出。  
- **企業就緒**：相容所有主流 Java 版本，且可輕鬆整合資料庫。

## 前置條件

- **Java Development Environment** – 已安裝 JDK 8 以上，並使用您慣用的 IDE。  
- **Aspose.BarCode Library** – 下載並安裝 Aspose.BarCode 函式庫。下載連結請見 [here](https://releases.aspose.com/barcode/java/)。  
- **MySQL Database** – 已啟動的 MySQL 例項，用於儲存產品資訊。  
- **Database Connectivity** – JDBC 驅動程式以及有效的認證資訊（`HOST_URI`、`USERNAME`、`PASSWORD`）。

## 匯入套件

在您的 Java 專案中，匯入 Aspose.BarCode 與 MySQL 連線所需的套件。

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## 如何在 Java 中產生條碼

### 步驟 1：產生並儲存條碼

```java
// Step 1 - Generate barcode and save temporarily in a file
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

*說明*：我們為 CODE‑39 標準建立 `BarcodeGenerator`，指定產品代碼（`NOK-E71`），並將圖像儲存至 `c:\temp\code39.jpg`。此檔案稍後會被串流至資料庫。

## 如何儲存條碼圖像

### 步驟 2：在 MySQL 資料庫中插入記錄

```java
// Step 2 - Insert a new record in MySQL DB
Connection con = null;

// Open connection
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Prepare statement
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Set product number and product name
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// 3rd column is for barcode image. DB type is BLOB
// For saving the image, we need to create a stream from the image file
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Execute the statement
pre.executeUpdate();
System.out.println("Insertion successful.");

// Close connection
pre.close();
con.close();
```

*說明*：在建立 JDBC 連線後，我們準備一個包含 BLOB 欄位的 `INSERT` 陳述式，用於儲存條碼圖像。圖像檔案會被讀入 `FileInputStream`，以二進位資料方式存入。

## 常見問題與解決方案

| 問題 | 原因 | 解決方法 |
|-------|-------|-----|
| **FileNotFoundException** 於儲存條碼時 | 目的資料夾不存在或缺乏寫入權限 | 建立資料夾（`c:\temp`）或選擇可寫入的路徑 |
| **SQLIntegrityConstraintViolationException** 插入時 | `ProductNumber` 主鍵重複 | 確保產品編號唯一，或使用 `ON DUPLICATE KEY UPDATE` |
| **ClassNotFoundException: com.mysql.jdbc.Driver** | MySQL JDBC 驅動程式未在 classpath 中 | 將 MySQL Connector/J JAR 加入專案相依性 |

## 常見問答

**Q：Aspose.BarCode 是否相容於不同的條碼類型？**  
A：是的，Aspose.BarCode 支援多種條碼類型，包括 CODE_39_STANDARD、CODE_128、QR 等。

**Q：我可以自訂產生條碼的外觀嗎？**  
A：當然可以！Aspose.BarCode 提供豐富的外觀自訂選項，讓您依需求調整條碼樣式。

**Q：Aspose.BarCode 有提供免費試用嗎？**  
A：有，您可於此取得免費試用版 [here](https://releases.aspose.com/)。  

**Q：在哪裡可以找到 Aspose.BarCode 的詳細文件？**  
A：請參考文件說明 [here](https://reference.aspose.com/barcode/java/)。  

**Q：如何取得 Aspose.BarCode 的支援？**  
A：請前往支援論壇 [here](https://forum.aspose.com/c/barcode/13) 取得協助或提問。

## 結論

恭喜！您已成功學會 **如何在 Java 中產生條碼** 以及 **如何儲存條碼圖像**，並使用 Aspose.BarCode 將圖像持久化於 MySQL 資料庫。此方法亦可延伸至其他條碼符號、儲存機制（例如 Azure Blob、AWS S3），或整合至更大型的企業系統。

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.10  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}