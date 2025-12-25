---
date: 2025-12-25
description: 學習如何使用 Aspose.BarCode 於 Java 產生條碼、儲存條碼影像，並將其存入 MySQL 資料庫。支援多種 Aspose
  條碼類型。
linktitle: Generating and Saving Barcode
second_title: Aspose.BarCode Java API
title: Java 產生條碼 – 使用 Aspose 生成與儲存條碼
url: /zh-hant/java/symbology-and-format/generating-saving-barcode/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# java generate barcode – 在 Java 中產生與儲存條碼

## 介紹

如果您需要快速 **java generate barcode** 並儲存產生的圖像，您來對地方了。在本教學中，我們將示範如何使用 **Aspose.BarCode for Java** 來建立條碼、將其儲存為圖像檔案，並將圖像持久化到 MySQL 資料庫。完成後，您將看到在任何 Java 應用程式中加入條碼功能是多麼簡單。

## 快速解答
- **我應該使用哪個函式庫？** Aspose.BarCode for Java  
- **我可以將條碼儲存為圖像檔案嗎？** Yes – use the `save` method to write a JPG/PNG/… file  
- **MySQL 是否支援儲存條碼？** Absolutely, store the image as a BLOB column  
- **有哪些條碼類型可用？** CODE_39_STANDARD, CODE_128, QR, DataMatrix, and many more  
- **生產環境需要授權嗎？** A commercial license is required for production use; a free trial is available

## 什麼是 java generate barcode？

在 Java 中產生條碼是指以程式方式建立可供掃描器讀取的資料視覺表示。Aspose.BarCode 提供流暢的 API 來定義條碼類型、設定資料字串，並以常見圖像格式匯出圖形。

## 為什麼使用 Aspose.BarCode 產生器？

- **廣泛的符號支援** – over 50 barcode types (aspose barcode types)  
- **高品質渲染** – lossless vector graphics when needed  
- **簡易 API** – only a few lines of code to produce a professional barcode  
- **易於整合** – works with any Java project, no external native dependencies  

## 前置條件

在深入本教學之前，請確保已具備以下前置條件：

- **Java 開發環境**：確保您的機器已設定好 Java 開發環境。  
- **Aspose.BarCode 函式庫**：下載並安裝 Aspose.BarCode 函式庫。您可在此取得下載連結 [here](https://releases.aspose.com/barcode/java/)。  
- **MySQL 資料庫**：建立您打算儲存條碼相關資訊的 MySQL 資料庫。  
- **資料庫連線**：確保您擁有必要的憑證與連線能力以與 MySQL 資料庫互動。  

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

## 步驟 1：產生並儲存條碼

```java
// Step 1 - Generate barcode and save temporarily in a file
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

**說明：** 此程式碼片段建立一個 `BarcodeGenerator`，選擇 `CODE_39_STANDARD` 符號，設定文字 `"NOK-E71"`，並將產生的圖像儲存至 `c:\temp\code39.jpg`。這就是 **java generate barcode** 的核心——一段簡潔易讀的程式碼。

## 步驟 2：在 MySQL 資料庫中插入記錄

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

**說明：** 這裡我們開啟 JDBC 連線，準備 `INSERT` 陳述式，並將條碼圖像以 BLOB 方式儲存。此程式碼示範如何將 **java generate barcode** 與資料庫儲存結合，完成端對端的工作流程。

## 常見問題與解決方案

| 問題 | 解決方案 |
|-------|----------|
| **找不到檔案路徑** | 確保目錄 (`c:\temp`) 存在，或使用 Java 程序可寫入的絕對路徑。 |
| **找不到 JDBC 驅動程式類別** | 將 MySQL Connector/J JAR 加入專案的 classpath。 |
| **BLOB 大小超過欄位限制** | 使用 `MEDIUMBLOB` 或 `LONGBLOB` 欄位類型以儲存較大的圖像。 |
| **儲存時權限被拒絕** | 以足夠的檔案系統權限執行應用程式，或選擇可寫入的資料夾。 |

## 常見問答

### Q: Aspose.BarCode 是否相容於不同的條碼類型？
A: 是的，Aspose.BarCode 支援多種條碼類型，包括 CODE_39_STANDARD、CODE_128、QR 等等。

### Q: 我可以自訂產生的條碼外觀嗎？
A: 當然可以！Aspose.BarCode 提供豐富的外觀自訂選項，讓您依需求調整條碼樣式。

### Q: 是否提供 Aspose.BarCode 的免費試用？
A: 有的，您可在此取得免費試用 [here](https://releases.aspose.com/).

### Q: 我在哪裡可以找到 Aspose.BarCode 的詳細文件？
A: 請參考文件 [here](https://reference.aspose.com/barcode/java/).

### Q: 我要如何取得 Aspose.BarCode 的支援？
A: 請前往支援論壇 [here](https://forum.aspose.com/c/barcode/13) 取得協助或提問。

## 結論

恭喜！您已成功使用 **Aspose.BarCode for Java** 來 **java generate barcode**，並將條碼圖像儲存至 MySQL 資料庫。此方法簡化了條碼整合，為您構建庫存、追蹤或銷售點系統奠定了堅實基礎。

---

**最後更新：** 2025-12-25  
**測試環境：** Aspose.BarCode for Java 24.10  
**作者：** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}