---
date: 2026-10-19
description: Tìm hiểu cách tạo QR code java và tạo nhiều barcode trên một hình ảnh
  duy nhất bằng Aspose.BarCode for Java. Bao gồm setup, code và troubleshooting.
keywords:
- create qr code java
- how to create qr
- java barcode library
- generate multiple barcodes
- aspose trial license
lastmod: 2026-10-19
linktitle: Tạo nhiều barcode trên một hình ảnh duy nhất
og_description: Tạo QR code java và kết hợp nhiều loại barcode vào một hình ảnh duy
  nhất với Aspose.BarCode for Java. Thực hiện hướng dẫn step‑by‑step, xem code snippets
  và học các troubleshooting tips.
og_image_alt: Screenshot of a Java application generating a QR code and other barcodes
  on one combined image
og_title: Tạo QR code java – tạo nhiều barcode trên một hình ảnh
schemas:
- author: Aspose
  dateModified: '2026-10-19'
  description: Learn how to create QR code java and generate multiple barcodes on
    a single image using Aspose.BarCode for Java. Includes setup, code, and troubleshooting.
  headline: Create QR code java – generate multiple barcodes on one image
  type: TechArticle
- questions:
  - answer: Yes. Use the `BarcodeGenerator` properties such as `setBarColor`, `setBackgroundColor`,
      and `setXDimension` to style each barcode independently before adding it to
      the canvas.
    question: Can I customize the appearance of individual barcodes in the generated
      image?
  - answer: Absolutely. The library supports 50+ symbologies, including CODE_39, DATA_MATRIX,
      QR, CODE_128, EAN_13, and AZTEC, as demonstrated in this tutorial.
    question: Is Aspose.BarCode compatible with different barcode symbologies?
  - answer: Download the JAR from the Aspose.BarCode for Java library download page,
      add it to your project’s classpath, and import the required namespaces as shown
      in the “Import namespaces” section.
    question: How do I integrate Aspose.BarCode into my Java project?
  - answer: Yes. Purchase a license from the Aspose.BarCode license purchase page
      to remove trial limitations and obtain full production support.
    question: Can I use Aspose.BarCode for commercial applications?
  - answer: Certainly. A free trial license is available from the Aspose.BarCode free
      trial download page, giving you full API access for evaluation.
    question: Are there trial options available for Aspose.BarCode?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- create qr code
- aspose barcode
- java barcode generation
- multiple barcodes image
title: Tạo QR code java – tạo nhiều barcode trên một hình ảnh
url: /vi/java/advanced-settings-and-optimization/generating-multiple-barcodes-single-image/
weight: 19
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã QR java – tạo nhiều mã vạch trên một hình ảnh

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **how to create QR code java** và hợp nhất nhiều loại mã vạch khác nhau lên một canvas duy nhất bằng **Aspose.BarCode for Java**. Cho dù bạn cần một nhãn QR gọn nhẹ, một mã vạch sản phẩm, hoặc một sự kết hợp của các ký hiệu 2‑D và tuyến tính, hướng dẫn này sẽ dẫn bạn qua mọi bước — từ thiết lập dự án đến lưu hình ảnh kết hợp cuối cùng — để bạn có thể bắt đầu tích hợp việc tạo mã vạch vào các ứng dụng Java của mình ngay lập tức.

## Câu trả lời nhanh
- **Thư viện nào tôi nên sử dụng?** Aspose.BarCode for Java provides the most complete set of symbologies.  
- **Tôi có thể tạo các loại mã vạch khác nhau cùng lúc không?** Yes, you can mix CODE_39, QR, AZTEC, and more on a single canvas.  
- **Tôi có cần giấy phép cho việc phát triển không?** A free trial works for testing; a commercial license is required for production.  
- **Phiên bản Java nào được hỗ trợ?** Java 8 and newer are fully compatible.  
- **Định dạng đầu ra có thể cấu hình không?** You can export the combined image as PNG, JPEG, BMP, or TIFF.

## create QR code java là gì?

`create QR code java` đề cập đến quá trình chuyển một chuỗi văn bản thành ma trận hai chiều có thể được quét bằng điện thoại thông minh hoặc máy đọc mã vạch. Aspose.BarCode for Java thực hiện việc mã hoá và render, vì vậy bạn có thể tập trung vào logic nghiệp vụ thay vì xử lý hình ảnh ở mức độ pixel.

## Tại sao nên sử dụng Aspose.BarCode Java để generate barcodes java?

Aspose.BarCode hỗ trợ **over 50 barcode symbologies** — bao gồm QR, Data Matrix, Code 128, AZTEC và các mã tuyến tính truyền thống — khiến nó trở thành thư viện mã vạch Java đa năng nhất. Nó render **anti‑aliased images at up to 1200 dpi**, đảm bảo quét rõ nét trên màn hình và bản in. API chỉ yêu cầu JVM và cung cấp mô hình cấu hình linh hoạt để tùy chỉnh kích thước, màu sắc, lề và sửa lỗi chỉ trong vài dòng code.

## Yêu cầu trước

- Kiến thức vững chắc về các nguyên tắc cơ bản của Java.  
- JDK 8 hoặc mới hơn đã được cài đặt và cấu hình trong PATH của bạn.  
- Tệp JAR Aspose.BarCode for Java (tải xuống từ trang tải về chính thức của Aspose.BarCode for Java).  
- Một IDE như IntelliJ IDEA hoặc Eclipse để chỉnh sửa và chạy mẫu.  

## Nhập không gian tên

Các câu lệnh import đưa các lớp của Aspose.BarCode như `BarcodeGenerator`, `EncodeTypes` và `BarCodeImageFormat` vào phạm vi, cho phép bạn tham chiếu chúng mà không cần tên đầy đủ.  
`BarcodeGenerator` là lớp chính được sử dụng để cấu hình và tạo hình ảnh mã vạch.  
`EncodeTypes` là một enum trong Aspose.BarCode xác định ký hiệu mã vạch cần tạo.  
`BarCodeImageFormat` định nghĩa định dạng hình ảnh đầu ra cho mã vạch được tạo.

## Bước 1: đặt thư mục tài nguyên

Thư mục **resource directory** là thư mục trên hệ thống tập tin của bạn nơi tất cả các hình ảnh mã vạch được tạo sẽ được ghi. Định nghĩa một lần giúp dự án của bạn được tổ chức và dễ dàng dọn dẹp các tệp cũ.

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

## Bước 2: tạo bộ sưu tập các mã vạch

`HashMap<String, EncodeTypes>` lưu trữ chuỗi dữ liệu của mỗi mã vạch cùng với ký hiệu bạn muốn sử dụng. `HashMap` là một collection của Java ánh xạ khóa tới giá trị. Bộ sưu tập này điều khiển vòng lặp tạo mã vạch tiếp theo. `EncodeTypes` là một enum chỉ định loại mã vạch cần tạo.

```java
// The path to the resource directory.
String dataDir = Utils.getDataDir(GenerateMultipleBarcodesOnASingleImage.class)
        + "BarcodeReader/advanced_features/";
```

## Bước 3: tạo hình ảnh mã vạch

Vòng lặp tạo mã lặp qua `HashMap`, tạo một `BarcodeGenerator` cho mỗi mục và gọi `generateBarCodeImage()` để nhận được một `BufferedImage`. `generateBarCodeImage()` tạo một `BufferedImage` chứa mã vạch đã render. `BufferedImage` là một lớp Java đại diện cho hình ảnh trong bộ nhớ. Tất cả các hình ảnh được thêm vào một `ArrayList<BufferedImage>` để ghép sau này. `ArrayList` là một triển khai danh sách có thể thay đổi kích thước trong Java.

```java
HashMap<String, EncodeTypes> collection = new HashMap<>();
collection.put("ONE123", EncodeTypes.CODE_39_STANDARD);
collection.put("Process Collection", EncodeTypes.DATA_MATRIX);
collection.put("Dictionary Collection", EncodeTypes.QR);
collection.put("X06712AT", EncodeTypes.CODE_128);
collection.put("979026000043", EncodeTypes.EAN_13);
collection.put("Aztec BarCode", EncodeTypes.AZTEC);
```

## Bước 4: tạo hình ảnh kết hợp

Đầu tiên, thuật toán tính **maximum width** trong số tất cả các hình ảnh mã vạch và **total height** cần thiết để xếp chúng theo chiều dọc với khoảng cách tùy chọn. Sau đó nó tạo một `BufferedImage` có kích thước đó và vẽ mỗi mã vạch lên canvas bằng một đối tượng `Graphics2D`. `Graphics2D` là một lớp Java cung cấp khả năng render 2D để vẽ hình dạng và hình ảnh.

```java
ArrayList<BufferedImage> images = new ArrayList<>();
for (Object key : collection.keySet()) {
    BarcodeGenerator bb = new BarcodeGenerator((BaseEncodeType) collection.get(key));
    bb.setCodeText((String) key);
    images.add(bb.generateBarCodeImage());
}
```

## Bước 5: lưu kết quả

Cuối cùng, hình ảnh ghép được ghi ra đĩa bằng `ImageIO.write`, sử dụng định dạng bạn đã chỉ định (PNG, JPEG, BMP hoặc TIFF). `ImageIO.write` ghi một `BufferedImage` vào tệp với định dạng đã chọn. Đường dẫn tệp là tương đối so với thư mục tài nguyên đã định nghĩa ở trên.

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

## Các trường hợp sử dụng phổ biến cho việc tạo nhiều mã vạch

- **Packaging labels** – kết hợp mã sản phẩm, lô và vận chuyển trên một nhãn duy nhất để giảm chi phí in.  
- **Event tickets** – nhúng các định danh QR, Data Matrix và Code 128 cho các trạm quét khác nhau tại địa điểm.  
- **Inventory management** – hiển thị SKU, dữ liệu thẻ RFID và số sê-ri cùng nhau để kiểm kê nhanh và truy xuất nguồn gốc.

## Khắc phục sự cố & mẹo

- **Image size issues** – điều chỉnh biến `offset` để tăng hoặc giảm khoảng cách giữa các mã vạch.  
- **Unsupported symbology** – xác minh rằng phiên bản Aspose.BarCode của bạn hỗ trợ loại mã vạch mong muốn; các bản phát hành mới hơn thêm các mã 2‑D bổ sung.  
- **Performance** – tái sử dụng một đối tượng `Graphics2D` duy nhất khi tạo nhiều hình ảnh trong vòng lặp để giảm thiểu chi phí cấp phát đối tượng.

## Câu hỏi thường gặp

**Q: Tôi có thể tùy chỉnh giao diện của từng mã vạch trong hình ảnh đã tạo không?**  
A: Có. Sử dụng các thuộc tính của `BarcodeGenerator` như `setBarColor`, `setBackgroundColor`, và `setXDimension` để tạo kiểu cho mỗi mã vạch một cách độc lập trước khi thêm vào canvas.

**Q: Aspose.BarCode có tương thích với các ký hiệu mã vạch khác nhau không?**  
A: Hoàn toàn. Thư viện hỗ trợ hơn 50 ký hiệu, bao gồm CODE_39, DATA_MATRIX, QR, CODE_128, EAN_13 và AZTEC, như đã minh họa trong hướng dẫn này.

**Q: Làm thế nào để tích hợp Aspose.BarCode vào dự án Java của tôi?**  
A: Tải JAR từ trang tải về thư viện Aspose.BarCode for Java, thêm nó vào classpath của dự án, và nhập các không gian tên cần thiết như được mô tả trong phần “Import namespaces”.

**Q: Tôi có thể sử dụng Aspose.BarCode cho các ứng dụng thương mại không?**  
A: Có. Mua giấy phép từ trang mua giấy phép Aspose.BarCode để loại bỏ các hạn chế của bản dùng thử và nhận hỗ trợ đầy đủ cho sản phẩm.

**Q: Có các tùy chọn dùng thử cho Aspose.BarCode không?**  
A: Chắc chắn. Giấy phép dùng thử miễn phí có sẵn trên trang tải về dùng thử Aspose.BarCode, cung cấp quyền truy cập đầy đủ API để đánh giá.

**Q: Làm thế nào để tạo mã QR độ phân giải cao cho việc in?**  
A: Đặt thuộc tính `setResolutionDpi` trên `BarcodeGenerator` trước khi gọi `generateBarCodeImage()`, sau đó lưu kết quả ở định dạng không mất dữ liệu như PNG.

**Q: Tôi nên làm gì nếu hình ảnh kết hợp bị cắt ngắn?**  
A: Kiểm tra rằng các phép tính `offset` và kích thước canvas đã tính đúng tất cả chiều cao của mã vạch; tăng chiều cao canvas hoặc giảm kích thước từng mã vạch sẽ giải quyết hầu hết các vấn đề cắt ngắn.

---

**Cập nhật lần cuối:** 2026-10-19  
**Kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose  

```java
File outputfile = new File(dataDir + "output.png");
ImageIO.write(resultBitmap, "png", outputfile);
```

## Các hướng dẫn liên quan

- [Cách tạo hình ảnh mã vạch Java – Thêm viền với Aspose](/barcode/java/image-manipulation/adding-borders-barcode-image/)
- [Cách tạo mã vạch Java: Lưu vào Streams với Aspose.BarCode](/barcode/java/advanced-settings-and-optimization/saving-barcode-image-streams/)
- [Cách tạo mã vạch Java và In mã vạch với Aspose](/barcode/java/barcode-rendering-techniques/rendering-barcode-printer/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}