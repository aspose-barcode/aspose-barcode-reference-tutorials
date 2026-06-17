---
date: 2026-04-03
description: Tìm hiểu cách tạo mã QR bằng Java và tạo nhiều mã vạch trên một hình
  ảnh duy nhất bằng Aspose.BarCode cho Java. Bao gồm cài đặt, mã nguồn và khắc phục
  sự cố.
keywords:
- create qr code java
- aspose barcode java
- generate barcodes java
linktitle: Tạo nhiều mã vạch trên một hình ảnh
second_title: Aspose.BarCode Java API
title: Tạo mã QR bằng Java – Tạo nhiều mã vạch trên một hình ảnh
url: /vi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã QR Java – Tạo Nhiều Mã Vạch Trên Một Hình Ảnh

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **cách tạo QR code java** và kết hợp nhiều loại mã vạch khác nhau vào một hình ảnh duy nhất bằng **Aspose.BarCode for Java**. Dù bạn cần một nhãn QR gọn gàng, một mã vạch sản phẩm, hay sự kết hợp giữa các ký hiệu 2‑D và tuyến tính, hướng dẫn này sẽ dẫn bạn qua từng bước — từ thiết lập dự án đến lưu hình ảnh kết hợp cuối cùng — để bạn có thể bắt đầu tích hợp việc tạo mã vạch vào các ứng dụng Java của mình ngay lập tức.

## Câu trả lời nhanh
- **Thư viện nào nên sử dụng?** Aspose.BarCode for Java cung cấp bộ ký hiệu đầy đủ nhất.  
- **Tôi có thể tạo các loại mã vạch khác nhau cùng lúc không?** Có, bạn có thể trộn CODE_39, QR, AZTEC và nhiều loại khác trên một canvas duy nhất.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 và các phiên bản mới hơn đều tương thích hoàn toàn.  
- **Định dạng đầu ra có thể cấu hình không?** Bạn có thể xuất hình ảnh kết hợp dưới dạng PNG, JPEG, BMP, v.v.  

## Tạo mã QR java là gì?

Tạo mã QR trong Java có nghĩa là chuyển một chuỗi văn bản thành một ma trận hai chiều có thể được quét bằng điện thoại thông minh hoặc máy đọc mã vạch. **Aspose.BarCode for Java** xử lý việc mã hoá và render, cho phép bạn tập trung vào logic nghiệp vụ thay vì xử lý ảnh ở mức thấp.

## Tại sao nên sử dụng Aspose.BarCode Java để tạo mã vạch java?

- **Hỗ trợ đa dạng các loại mã** – từ các mã tuyến tính cổ điển đến các ma trận 2‑D hiện đại.  
- **Kết xuất chất lượng cao** – đầu ra chống răng cưa hoạt động trên mọi thiết bị.  
- **API đơn giản** – tạo, tùy chỉnh và kết hợp mã vạch chỉ với vài lệnh gọi phương thức.  
- **Không phụ thuộc bên ngoài** – mọi thứ chạy trên JVM mà không cần thư viện gốc.  

## Yêu cầu trước

Trước khi bắt đầu hướng dẫn, hãy đảm bảo bạn đã có các yêu cầu sau:

- Hiểu biết cơ bản về lập trình Java.  
- Java Development Kit (JDK) đã được cài đặt trên hệ thống của bạn.  
- Thư viện Aspose.BarCode for Java đã được tải xuống và thiết lập. Bạn có thể tải về [tại đây](https://releases.aspose.com/barcode/java/).  
- Môi trường phát triển tích hợp (IDE) như Eclipse hoặc IntelliJ IDEA.  

## Nhập các gói

Trong dự án Java của bạn, nhập các gói cần thiết để truy cập chức năng của Aspose.BarCode. Thêm các câu lệnh import sau vào đầu lớp Java của bạn:

```java
import java.awt.Color;
import java.awt.Graphics;
import java.awt.image.BufferedImage;
import java.io.File;
import java.util.ArrayList;
import java.util.HashMap;

import javax.imageio.ImageIO;

import com.aspose.barcode.BaseEncodeType;
import com.aspose.barcode.EncodeTypes;


import com.aspose.barcode.generation.BarcodeGenerator;
```

## Bước 1: Đặt thư mục tài nguyên

Xác định đường dẫn tới thư mục tài nguyên nơi các mã vạch được tạo sẽ được lưu. Thư mục này rất quan trọng để tổ chức và quản lý các hình ảnh mã vạch của bạn.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Bước 2: Tạo bộ sưu tập các mã vạch

Khởi tạo một `HashMap` để lưu trữ dữ liệu mã vạch. Mỗi mục trong bộ sưu tập đại diện cho một mã vạch với loại mã hoá tương ứng.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Bước 3: Tạo hình ảnh mã vạch

Duyệt qua bộ sưu tập và tạo hình ảnh mã vạch bằng thư viện Aspose.BarCode. Lưu các hình ảnh vào một `ArrayList` để xử lý tiếp theo.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Bước 4: Tạo hình ảnh kết hợp

Xác định chiều rộng tối đa và tổng chiều cao của các hình ảnh mã vạch. Tạo một `BufferedImage` để kết hợp các hình ảnh mã vạch riêng lẻ thành một hình ảnh đầu ra duy nhất.

```java
int maxWidth = 0;
int sumHeight = 0;
for (BufferedImage bmp : images) {
    sumHeight += bmp.getHeight();
    if (maxWidth < bmp.getWidth())
        maxWidth = bmp.getWidth();
}

int offset = 10;
BufferedImage resultBitmap = new BufferedImage(maxWidth + offset * 2, sumHeight + offset * images.size(),
        BufferedImage.TYPE_INT_ARGB);
Graphics g = resultBitmap.getGraphics();
g.setColor(Color.white);
g.fillRect(0, 0, resultBitmap.getWidth(), resultBitmap.getHeight());

int yPosition = offset;
for (int i = 0; i < images.size(); ++i) {
    BufferedImage currentBitmap = images.get(i);
    g.drawImage(currentBitmap, offset, yPosition, null);
    yPosition += currentBitmap.getHeight() + offset;
}
```

## Bước 5: Lưu kết quả

Lưu hình ảnh kết hợp cuối cùng vào vị trí tệp tin được chỉ định.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Các trường hợp sử dụng phổ biến cho việc tạo nhiều mã vạch

- **Nhãn bao bì** – kết hợp mã sản phẩm, lô và vận chuyển trên một nhãn duy nhất.  
- **Vé sự kiện** – nhúng QR, Data Matrix và mã Code 128 cho các trạm quét khác nhau.  
- **Quản lý tồn kho** – hiển thị SKU, dữ liệu thẻ RFID và số sê-ri cùng nhau để kiểm kê nhanh.  

## Khắc phục sự cố & Mẹo

- **Vấn đề kích thước hình ảnh** – điều chỉnh biến `offset` để tăng hoặc giảm khoảng cách giữa các mã vạch.  
- **Mã vạch không được hỗ trợ** – xác minh phiên bản Aspose.BarCode của bạn hỗ trợ loại mã vạch mong muốn.  
- **Hiệu năng** – tái sử dụng một đối tượng `Graphics` duy nhất nếu bạn tạo nhiều hình ảnh trong vòng lặp.  

## Câu hỏi thường gặp

**Q1: Tôi có thể tùy chỉnh giao diện của từng mã vạch trong hình ảnh được tạo không?**  
A1: Có, Aspose.BarCode cung cấp các tùy chọn tùy chỉnh rộng rãi cho giao diện mã vạch, cho phép bạn điều chỉnh phong cách của mỗi mã vạch theo sở thích.

**Q2: Aspose.BarCode có tương thích với các loại mã vạch khác nhau không?**  
A2: Chắc chắn! Aspose.BarCode hỗ trợ một loạt các ký hiệu, bao gồm CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 và AZTEC, như đã minh họa trong hướng dẫn này.

**Q3: Làm thế nào để tích hợp Aspose.BarCode vào dự án Java của tôi?**  
A3: Chỉ cần tải xuống thư viện Aspose.BarCode for Java từ [đây](https://releases.aspose.com/barcode/java/) và làm theo hướng dẫn cài đặt trong tài liệu.

**Q4: Tôi có thể sử dụng Aspose.BarCode cho các ứng dụng thương mại không?**  
A4: Có, bạn có thể mua giấy phép từ [đây](https://purchase.aspose.com/buy) để sử dụng Aspose.BarCode cho mục đích thương mại.

**Q5: Có tùy chọn dùng thử nào cho Aspose.BarCode không?**  
A5: Chắc chắn! Bạn có thể khám phá các tính năng của Aspose.BarCode bằng cách nhận giấy phép dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q6: Làm thế nào để tạo mã QR độ phân giải cao cho việc in ấn?**  
A6: Đặt DPI mong muốn trên `BarcodeGenerator` trước khi gọi `generateBarCodeImage()`, sau đó lưu hình ảnh ở định dạng không mất dữ liệu như PNG.

**Q7: Tôi nên làm gì nếu hình ảnh kết hợp bị cắt ngắn?**  
A7: Xác minh rằng các phép tính `offset` và kích thước canvas đã tính đúng tất cả chiều cao của mã vạch; tăng chiều cao canvas hoặc giảm kích thước từng mã vạch thường giải quyết được vấn đề cắt ngắn.

---

**Last Updated:** 2026-04-03  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}