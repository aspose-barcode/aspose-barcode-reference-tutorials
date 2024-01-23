---
title: Tạo và lưu mã vạch trong Java
linktitle: Tạo và lưu mã vạch
second_title: API Java Aspose.BarCode
description: Tạo và lưu mã vạch dễ dàng trong Java với Aspose.BarCode. Tích hợp liền mạch, tùy chỉnh giao diện và tận hưởng hỗ trợ mã vạch mở rộng.
type: docs
weight: 12
url: /vi/java/symbology-and-format/generating-saving-barcode/
---

## Giới thiệu

Bạn đang tìm cách tích hợp liền mạch việc tạo mã vạch vào ứng dụng Java của mình? Đừng tìm đâu xa! Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình sử dụng Aspose.BarCode cho Java để tạo và lưu mã vạch một cách hiệu quả. Aspose.BarCode là một thư viện Java mạnh mẽ giúp đơn giản hóa việc tạo và thao tác mã vạch, cung cấp cho bạn các công cụ cần thiết để nâng cao chức năng mã vạch cho ứng dụng của bạn.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Môi trường phát triển Java: Đảm bảo bạn đã thiết lập môi trường phát triển Java trên máy của mình.

- Thư viện Aspose.BarCode: Tải xuống và cài đặt thư viện Aspose.BarCode. Bạn có thể tìm thấy liên kết tải xuống[đây](https://releases.aspose.com/barcode/java/).

- Cơ sở dữ liệu MySQL: Thiết lập cơ sở dữ liệu MySQL nơi bạn dự định lưu trữ thông tin liên quan đến mã vạch.

- Kết nối cơ sở dữ liệu: Đảm bảo bạn có thông tin xác thực và kết nối cần thiết để tương tác với cơ sở dữ liệu MySQL.

## Gói nhập khẩu

Trong dự án Java của bạn, hãy nhập các gói cần thiết để kết nối Aspose.BarCode và MySQL.

```java
import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.generation.BarcodeGenerator;

import java.io.File;
import java.io.FileInputStream;
import java.sql.Connection;
import java.sql.DriverManager;
import java.sql.PreparedStatement;
```

## Bước 1: Tạo và lưu mã vạch

```java
// Bước 1 - Tạo mã vạch và lưu tạm thời vào một tệp
String strBarCodeImage = "c:\\temp\\code39.jpg";
String strCodeText = "NOK-E71";

BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText(strCodeText);
generator.save(strBarCodeImage);
```

Giải thích: Bước này bao gồm việc tạo mã vạch bằng Aspose.BarCode, đặt văn bản mã và lưu hình ảnh mã vạch vào một vị trí được chỉ định.

## Bước 2: Chèn bản ghi vào cơ sở dữ liệu MySQL

```java
// Bước 2 - Chèn bản ghi mới vào MySQL DB
Connection con = null;

// Mở kết nối
Class.forName("com.mysql.jdbc.Driver").newInstance();
con = DriverManager.getConnection(Common.HOST_URI, Common.USERNAME, Common.PASSWORD);

// Chuẩn bị tuyên bố
PreparedStatement pre = con.prepareCall(
        "Insert INTO Product (ProductNumber, ProductName, BarCodeImage) " + "VALUES (?, ?, ?) ");

// Đặt số sản phẩm và tên sản phẩm
pre.setString(1, "NOK-E71");
pre.setString(2, "Nokia E Series - E71");

// Cột thứ 3 dành cho hình ảnh mã vạch. Loại DB là BLOB
// Để lưu hình ảnh, chúng ta cần tạo luồng từ tệp hình ảnh
File imgFile = new File(strBarCodeImage);
FileInputStream fin = new FileInputStream(imgFile);
pre.setBinaryStream(3, fin, (int) imgFile.length());

// Thực hiện tuyên bố
pre.executeUpdate();
System.out.println("Insertion successful.");

// Đóng kết nối
pre.close();
con.close();
```

Giải thích: Bước này bao gồm việc kết nối với cơ sở dữ liệu MySQL và chèn bản ghi mới có thông tin sản phẩm và hình ảnh mã vạch liên quan.

## Phần kết luận

Chúc mừng! Bạn đã tích hợp thành công Aspose.BarCode for Java vào ứng dụng của mình để tạo và lưu mã vạch. Thư viện mạnh mẽ này đơn giản hóa quy trình, giúp việc triển khai mã vạch trở nên dễ dàng.

## Các câu hỏi thường gặp

### Câu hỏi: Aspose.BarCode có tương thích với các loại mã vạch khác nhau không?
Trả lời: Có, Aspose.BarCode hỗ trợ nhiều loại mã vạch khác nhau, bao gồm CODE_39_STANDARD, CODE_128, QR, v.v.

### Câu hỏi: Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Đ: Chắc chắn rồi! Aspose.BarCode cung cấp các tùy chọn tùy chỉnh mở rộng về giao diện mã vạch, cho phép bạn điều chỉnh nó theo nhu cầu cụ thể của mình.

### Câu hỏi: Aspose.BarCode có bản dùng thử miễn phí không?
 Đ: Có, bạn có thể truy cập bản dùng thử miễn phí[đây](https://releases.aspose.com/).

### Câu hỏi: Tôi có thể tìm tài liệu chi tiết về Aspose.BarCode ở đâu?
 A: Tham khảo tài liệu[đây](https://reference.aspose.com/barcode/java/).

### Câu hỏi: Làm cách nào để tôi nhận được hỗ trợ cho Aspose.BarCode?
 A: Truy cập diễn đàn hỗ trợ[đây](https://forum.aspose.com/c/barcode/13) cho bất kỳ sự trợ giúp hoặc thắc mắc.