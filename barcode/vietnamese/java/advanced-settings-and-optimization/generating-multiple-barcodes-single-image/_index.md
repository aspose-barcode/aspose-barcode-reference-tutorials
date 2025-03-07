---
title: Tạo nhiều mã vạch trên một hình ảnh trong Java bằng Aspose.BarCode
linktitle: Tạo nhiều mã vạch trên một hình ảnh
second_title: API Java Aspose.BarCode
description: Tạo nhiều mã vạch trên một hình ảnh một cách dễ dàng bằng Aspose.BarCode cho Java. Hãy làm theo hướng dẫn từng bước của chúng tôi để tích hợp liền mạch.
weight: 19
url: /vi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo nhiều mã vạch trên một hình ảnh trong Java bằng Aspose.BarCode

## Giới thiệu

Trong thế giới năng động của lập trình Java, việc tạo và quản lý mã vạch một cách hiệu quả là rất quan trọng đối với các ứng dụng khác nhau. Aspose.BarCode for Java đơn giản hóa quy trình này, cho phép các nhà phát triển tạo nhiều mã vạch trên một hình ảnh một cách liền mạch. Hướng dẫn này sẽ hướng dẫn bạn các bước để đạt được điều này bằng cách sử dụng Aspose.BarCode trong môi trường Java.

## Điều kiện tiên quyết

Trước khi đi sâu vào hướng dẫn, hãy đảm bảo bạn có các điều kiện tiên quyết sau:

- Hiểu biết cơ bản về lập trình Java.
- Bộ công cụ phát triển Java (JDK) được cài đặt trên hệ thống của bạn.
- Thư viện Aspose.BarCode cho Java được tải xuống và thiết lập. Bạn có thể tải nó xuống[đây](https://releases.aspose.com/barcode/java/).
- Một môi trường phát triển tích hợp (IDE) như Eclipse hoặc IntelliJ IDEA.

## Nhập không gian tên

Trong dự án Java của bạn, hãy nhập các vùng tên cần thiết để truy cập chức năng Aspose.BarCode. Thêm các câu lệnh nhập sau vào đầu lớp Java của bạn:

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

Xác định đường dẫn đến thư mục tài nguyên nơi lưu mã vạch được tạo. Thư mục này rất quan trọng để tổ chức và quản lý hình ảnh mã vạch của bạn.

```java
// Đường dẫn đến thư mục tài nguyên.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Bước 2: Tạo bộ sưu tập mã vạch

Khởi tạo HashMap để lưu trữ dữ liệu mã vạch. Mỗi mục trong bộ sưu tập đại diện cho một mã vạch có loại mã hóa tương ứng.

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

Lặp lại bộ sưu tập và tạo hình ảnh mã vạch bằng thư viện Aspose.BarCode. Lưu trữ hình ảnh trong ArrayList để xử lý thêm.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Bước 4: Tạo một hình ảnh kết hợp

Xác định chiều rộng tối đa và tổng chiều cao của hình ảnh mã vạch. Tạo BufferedImage để kết hợp các hình ảnh mã vạch riêng lẻ thành một hình ảnh đầu ra duy nhất.

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

Lưu hình ảnh kết hợp cuối cùng vào một vị trí tệp được chỉ định.

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Phần kết luận

Chúc mừng! Bạn đã tạo thành công nhiều mã vạch trên một hình ảnh bằng Aspose.BarCode cho Java. Thư viện mạnh mẽ này giúp đơn giản hóa việc xử lý mã vạch, khiến nó trở thành một công cụ vô giá cho các nhà phát triển Java.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể tùy chỉnh giao diện của từng mã vạch trong hình ảnh được tạo không?

Câu trả lời 1: Có, Aspose.BarCode cung cấp các tùy chọn tùy chỉnh mở rộng về giao diện mã vạch, cho phép bạn điều chỉnh kiểu dáng của từng mã vạch theo sở thích của mình.

### Câu hỏi 2: Aspose.BarCode có tương thích với các hệ thống ký hiệu mã vạch khác nhau không?

A2: Chắc chắn rồi! Aspose.BarCode hỗ trợ nhiều loại ký hiệu, bao gồm CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 và AZTEC, như được minh họa trong hướng dẫn này.

### Câu hỏi 3: Làm cách nào tôi có thể tích hợp Aspose.BarCode vào dự án Java của mình?

 Câu trả lời 3: Chỉ cần tải xuống thư viện Aspose.BarCode cho Java từ[đây](https://releases.aspose.com/barcode/java/) và làm theo hướng dẫn cài đặt được cung cấp trong tài liệu.

### Câu hỏi 4: Tôi có thể sử dụng Aspose.BarCode cho các ứng dụng thương mại không?

 A4: Có, bạn có thể lấy giấy phép từ[đây](https://purchase.aspose.com/buy) sử dụng Aspose.BarCode cho mục đích thương mại.

### Câu hỏi 5: Có bất kỳ tùy chọn dùng thử nào cho Aspose.BarCode không?

 A5: Chắc chắn rồi! Bạn có thể khám phá các tính năng của Aspose.BarCode bằng cách lấy giấy phép dùng thử miễn phí[đây](https://releases.aspose.com/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
