---
title: 用 Java 產生和保存條碼
linktitle: 產生並儲存條碼
second_title: Aspose.BarCode Java API
description: 使用 Aspose.BarCode 在 Java 中輕鬆產生並保存條碼。無縫整合、自訂外觀並享受廣泛的條碼支援。
type: docs
weight: 12
url: /zh-hant/java/symbology-and-format/generating-saving-barcode/
---

## 介紹

您是否希望將條碼生成無縫整合到您的 Java 應用程式中？別再猶豫了！在本逐步指南中，我們將引導您完成使用 Aspose.BarCode for Java 高效產生和儲存條碼的過程。 Aspose.BarCode 是一個功能強大的 Java 程式庫，可簡化條碼的建立和操作，為您提供透過條碼功能增強應用程式所需的工具。

## 先決條件

在深入學習本教程之前，請確保您具備以下先決條件：

- Java 開發環境：確保您的電腦上設定了 Java 開發環境。

- Aspose.BarCode 函式庫：下載並安裝 Aspose.BarCode 函式庫。你可以找到下載鏈接[這裡](https://releases.aspose.com/barcode/java/).

- MySQL 資料庫：設定一個 MySQL 資料庫，用於儲存條碼相關資訊。

- 資料庫連線：確保您擁有與 MySQL 資料庫互動所需的憑證和連線。

## 導入包

在您的 Java 專案中，匯入 Aspose.BarCode 和 MySQL 連線所需的套件。

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## 第 1 步：產生並儲存條碼

```java
//步驟 1 - 產生條碼並暫時儲存在檔案中
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

說明：此步驟涉及使用Aspose.BarCode建立條碼、設定代碼文字以及將條碼圖像儲存到指定位置。

## 步驟2：在MySQL資料庫中插入記錄

```java
//步驟 2 - 在 MySQL DB 中插入一筆新記錄
Connection con = null;

//開啟連接
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

//準備聲明
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

//設定產品編號和產品名稱
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

//第三列用於條碼影像。資料庫類型是BLOB
//為了保存圖像，我們需要從圖像檔案建立一個串流
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

//執行語句
pre.executeUpdate();
System.out.println("Insertion successful.");

//緊密連接
pre.close();
con.close();
```

說明：此步驟涉及連接到 MySQL 資料庫並插入包含產品資訊和關聯條碼映像的新記錄。

## 結論

恭喜！您已成功將 Aspose.BarCode for Java 整合到您的應用程式中以產生和儲存條碼。這個強大的函式庫簡化了流程，讓條碼的實作變得輕而易舉。

## 經常問的問題

### Q：Aspose.BarCode 是否相容於不同的條碼類型？
答：是的，Aspose.BarCode 支援各種條碼類型，包括 CODE_39_STANDARD、CODE_128、QR 等。

### Q：我可以自訂產生的條碼的外觀嗎？
答：當然！ Aspose.BarCode 為條碼外觀提供了廣泛的自訂選項，可讓您根據您的特定需求進行自訂。

### Q：Aspose.BarCode 是否有免費試用版？
答：是的，您可以免費試用[這裡](https://releases.aspose.com/).

### Q：哪裡可以找到 Aspose.BarCode 的詳細文件？
答：參考文檔[這裡](https://reference.aspose.com/barcode/java/).

### Q：如何獲得對 Aspose.BarCode 的支援？
答：造訪支援論壇[這裡](https://forum.aspose.com/c/barcode/13)如有任何幫助或疑問。