---
date: 2025-12-10
description: Tìm hiểu cách tạo mã vạch trên một hình ảnh duy nhất trong Java bằng
  Aspose.BarCode. Hướng dẫn này bao gồm tích hợp Aspose Barcode Java và việc tạo nhiều
  mã vạch.
linktitle: Generating Multiple Barcodes on a Single Image
second_title: Aspose.BarCode Java API
title: Cách tạo mã vạch trên một hình ảnh duy nhất trong Java
url: /vi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Nhiều Mã Vạch Trên Một Hình Ảnh Đơn Trong Java với Aspose.BarCode

## Introduction

Nếu bạn đang tìm kiếm một cách đáng tin cậy **how to generate barcodes** trong một ứng dụng Java, bạn đã đến đúng nơi. Với Aspose.BarCode for Java, bạn có thể đặt nhiều loại mã vạch khác nhau lên một hình ảnh chỉ trong vài dòng code. Hướng dẫn này sẽ dẫn bạn qua toàn bộ quá trình—từ thiết lập dự án đến lưu hình ảnh kết hợp—để bạn có thể bắt đầu sử dụng việc tạo mã vạch trong các giải pháp của mình ngay lập tức.

## Quick Answers
- **What library should I use?** Aspose.BarCode for Java cung cấp bộ mã symbology đầy đủ nhất.  
- **Can I generate different barcode types together?** Có, bạn có thể kết hợp CODE_39, QR, AZTEC và các loại khác trên một canvas duy nhất.  
- **Do I need a license for development?** Bản dùng thử miễn phí đủ cho việc thử nghiệm; cần giấy phép thương mại cho môi trường sản xuất.  
- **Which Java version is supported?** Java 8 và các phiên bản mới hơn đều tương thích hoàn toàn.  
- **Is the output format configurable?** Bạn có thể xuất hình ảnh kết hợp dưới dạng PNG, JPEG, BMP, v.v.

## What is “how to generate barcodes” in Java?

Tạo mã vạch có nghĩa là chuyển đổi một chuỗi dữ liệu thành một mẫu hình ảnh mà máy quét có thể đọc. Aspose.BarCode tự động xử lý các bước mã hoá, render và tạo ảnh, cho phép bạn tập trung vào logic nghiệp vụ thay vì xử lý ảnh mức thấp.

## Why use Aspose.BarCode for Java barcode generation?
- **Broad symbology support** – từ các mã tuyến tính cổ điển đến các ma trận 2‑D hiện đại.  
- **High‑quality rendering** – đầu ra anti‑aliased hoạt động trên mọi thiết bị.  
- **Simple API** – tạo, tùy chỉnh và kết hợp mã vạch chỉ với vài lời gọi phương thức.  
- **No external dependencies** – mọi thứ chạy trên JVM mà không cần thư viện gốc.

## Prerequisites

- Hiểu biết cơ bản về lập trình Java.  
- Java Development Kit (JDK) đã được cài đặt trên hệ thống của bạn.  
- Thư viện Aspose.BarCode for Java đã được tải xuống và thiết lập. Bạn có thể tải nó [đây](https://releases.aspose.com/barcode/java/).  
- Một môi trường phát triển tích hợp (IDE) như Eclipse hoặc IntelliJ IDEA.

## Import Namespaces

Trong dự án Java của bạn, nhập các namespace cần thiết để truy cập chức năng của Aspose.BarCode. Thêm các câu lệnh import sau vào đầu lớp Java của bạn:

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

## Step 1: Set the Resource Directory

Xác định đường dẫn tới thư mục tài nguyên nơi các mã vạch được tạo sẽ được lưu. Thư mục này rất quan trọng để tổ chức và quản lý các hình ảnh mã vạch của bạn.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Step 2: Create a Collection of Barcodes

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

## Step 3: Generate Barcode Images

Duyệt qua bộ sưu tập và tạo hình ảnh mã vạch bằng thư viện Aspose.BarCode. Lưu các hình ảnh vào một `ArrayList` để xử lý tiếp theo.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Step 4: Create a Combined Image

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

## Step 5: Save the Result

Lưu hình ảnh kết hợp cuối cùng vào vị trí tệp tin được chỉ định.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Common Use Cases for Generating Multiple Barcodes

- **Packaging labels** – kết hợp mã sản phẩm, lô và vận chuyển trên một nhãn duy nhất.  
- **Event tickets** – nhúng QR, Data Matrix và mã Code 128 cho các trạm quét khác nhau.  
- **Inventory management** – hiển thị SKU, dữ liệu thẻ RFID và số sê‑ri cùng nhau để kiểm kê nhanh.

## Troubleshooting & Tips

- **Image size issues** – điều chỉnh biến `offset` để tăng hoặc giảm khoảng cách giữa các mã vạch.  
- **Unsupported symbology** – xác minh rằng phiên bản Aspose.BarCode của bạn hỗ trợ loại mã vạch mong muốn.  
- **Performance** – tái sử dụng một đối tượng `Graphics` duy nhất nếu bạn tạo nhiều hình ảnh trong vòng lặp.

## FAQ's

### Q1: Tôi có thể tùy chỉnh giao diện của từng mã vạch trong hình ảnh được tạo không?

A1: Có, Aspose.BarCode cung cấp các tùy chọn tùy chỉnh rộng rãi cho giao diện mã vạch, cho phép bạn điều chỉnh phong cách của từng mã vạch theo sở thích.

### Q2: Aspose.BarCode có tương thích với các loại symbology mã vạch khác nhau không?

A2: Chắc chắn! Aspose.BarCode hỗ trợ một loạt các symbology, bao gồm CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 và AZTEC, như đã trình bày trong hướng dẫn này.

### Q3: Làm thế nào tôi có thể tích hợp Aspose.BarCode vào dự án Java của mình?

A3: Chỉ cần tải thư viện Aspose.BarCode for Java từ [đây](https://releases.aspose.com/barcode/java/) và làm theo hướng dẫn cài đặt trong tài liệu.

### Q4: Tôi có thể sử dụng Aspose.BarCode cho các ứng dụng thương mại không?

A4: Có, bạn có thể mua giấy phép từ [đây](https://purchase.aspose.com/buy) để sử dụng Aspose.BarCode cho mục đích thương mại.

### Q5: Có tùy chọn dùng thử nào cho Aspose.BarCode không?

A5: Chắc chắn! Bạn có thể khám phá các tính năng của Aspose.BarCode bằng cách nhận giấy phép dùng thử miễn phí [đây](https://releases.aspose.com/).

**Additional Questions**

**Q: Làm thế nào tôi tạo mã QR cụ thể trong Java?**  
A: Sử dụng `EncodeTypes.QR` khi tạo thể hiện `BarcodeGenerator`, như đã minh họa trong ví dụ bộ sưu tập.

**Q: Aspose.BarCode có hỗ trợ đầu ra độ phân giải cao cho việc in không?**  
A: Có, bạn có thể chỉ định DPI khi lưu hình ảnh để đáp ứng yêu cầu chất lượng in.

---

**Cập nhật lần cuối:** 2025-12-10  
**Đã kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}