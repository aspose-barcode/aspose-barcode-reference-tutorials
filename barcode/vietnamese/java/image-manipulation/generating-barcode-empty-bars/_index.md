---
date: 2026-04-12
description: Tìm hiểu cách tạo mã vạch Code128 với các thanh trống trong Java bằng
  Aspose.BarCode. Hướng dẫn này cho bạn thấy cách tạo nhanh các hình ảnh mã vạch Java.
keywords:
- create code128 barcode
- generate barcode java
- barcode generator java example
- java generate barcode image
linktitle: Tạo mã vạch với các thanh trống
second_title: Aspose.BarCode Java API
title: Cách tạo mã vạch Code128 với các thanh trống trong Java
url: /vi/java/image-manipulation/generating-barcode-empty-bars/
weight: 14
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Mã vạch Code128 với Các Thanh Trống trong Java

## Giới thiệu

Việc tích hợp tạo mã vạch vào các ứng dụng Java là một yêu cầu thường gặp, cho dù bạn đang xây dựng hệ thống quản lý tồn kho, nền tảng bán vé, hoặc giải pháp điểm bán hàng. Với **Aspose.BarCode for Java**, bạn có thể **tạo hình ảnh mã vạch Code128** chỉ trong vài dòng mã. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn các bước để **tạo hình ảnh mã vạch Java** có các thanh trống (không được tô đầy), giúp bạn kiểm soát hoàn toàn phong cách hiển thị của mã vạch.

## Câu trả lời nhanh
- **Thư viện nào?** Aspose.BarCode for Java  
- **Trường hợp sử dụng chính?** Tạo mã vạch Code128 với các thanh trống cho thiết kế UI tùy chỉnh  
- **Yêu cầu tiên quyết?** Java JDK 8+, Aspose.BarCode JAR, quyền ghi vào thư mục để lưu ảnh đầu ra  
- **Thời gian triển khai điển hình?** 5‑10 phút cho một ví dụ cơ bản  
- **Có thể tùy chỉnh màu sắc không?** Có – API cung cấp các tùy chọn định dạng phong phú  

## Code128 là gì?

Code128 là một ký hiệu mã vạch tuyến tính mật độ cao, mã hoá toàn bộ bộ ký tự ASCII. Nó được sử dụng rộng rãi trong logistics, vận chuyển và bán lẻ vì có thể biểu diễn dữ liệu alphanumeric một cách gọn gàng. Mặc định, Aspose.BarCode hiển thị các thanh Code128 dưới dạng hình chữ nhật đặc; việc đặt thuộc tính **FilledBars** thành `false` sẽ biến chúng thành các thanh trống (đường viền), hữu ích cho việc tạo thương hiệu theo phong cách.

## Tại sao nên sử dụng Aspose.BarCode cho Java?

- **Bộ tính năng phong phú** – hỗ trợ hơn 50 loại mã vạch, bao gồm QR, DataMatrix và PDF417.  
- **Không phụ thuộc bên ngoài** – một JAR duy nhất hoạt động trên bất kỳ môi trường Java nào.  
- **Kiểm soát chi tiết** – bạn có thể điều chỉnh độ rộng thanh, màu sắc, phông chữ và thuộc tính `FilledBars`.  
- **Đa nền tảng** – hoạt động trên Windows, Linux và macOS mà không cần thư viện gốc.  

## Yêu cầu tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Môi trường phát triển Java** – JDK 8 hoặc mới hơn đã được cài đặt và cấu hình `JAVA_HOME`.  
2. **Aspose.BarCode cho Java** – tải JAR mới nhất từ [trang tải xuống](https://releases.aspose.com/barcode/java/).  
3. **Thư mục tài liệu** – một thư mục trên máy tính của bạn để lưu ảnh mã vạch được tạo.  

## Nhập các gói

Trong dự án Java của bạn, nhập các lớp cần thiết để làm việc với Aspose.BarCode:

```java
import java.io.IOException;
import com.aspose.barcode.BarCodeImageFormat;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Các import này cung cấp cho bạn quyền truy cập vào trình tạo mã vạch, liệt kê định dạng ảnh và xử lý ngoại lệ.

## Bước 1: Thiết lập Thư mục tài nguyên

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Thay thế `"Your Document Directory"` bằng đường dẫn tuyệt đối tới thư mục bạn đã tạo trong phần yêu cầu tiên quyết. Đây là nơi tệp PNG sẽ được ghi.

## Bước 2: Tạo Instance Trình tạo Mã vạch Code128

```java
// Create an instance of BarcodeGenerator and initialize it with CodeText and Symbology
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "TEXT");
```

Ở đây chúng ta khởi tạo `BarcodeGenerator` với ký hiệu **CODE_128** và văn bản mẫu `"TEXT"`. Đây là một **ví dụ Java về trình tạo mã vạch** mà bạn có thể điều chỉnh cho bất kỳ chuỗi nào cần mã hoá.

## Bước 3: Đặt Thuộc tính FilledBars thành False

```java
// Set the FilledBars property to false
generator.getParameters().getBarcode().setFilledBars(false);
```

Bằng cách đặt `FilledBars` thành `false`, mã vạch được tạo sẽ hiển thị các thanh trống thay vì các thanh đặc, đạt được hiệu ứng hình ảnh mà chúng ta mong muốn.

## Bước 4: Lưu Ảnh Mã vạch

```java
// Save the resultant barcode image on disk
generator.save(dataDir + "barcodeWithEmptyBars.png", BarCodeImageFormat.PNG);
```

Phương thức `save` ghi mã vạch vào thư mục đã chỉ định ở định dạng PNG. Bạn có thể thay đổi `BarCodeImageFormat.PNG` thành `JPG`, `BMP`, hoặc `TIFF` nếu cần loại ảnh khác.

## Các trường hợp sử dụng phổ biến

- **Thương hiệu tùy chỉnh** – các thanh trống có thể được phủ lên các mẫu nền hoặc màu sắc.  
- **Tài sản sẵn sàng in** – tạo PNG độ phân giải cao để đưa vào hoá đơn hoặc nhãn vận chuyển.  
- **Tạo động** – tạo mã vạch ngay lập tức trong các dịch vụ web hoặc ứng dụng desktop.  

## Mẹo khắc phục sự cố

- **Đường dẫn không hợp lệ** – đảm bảo `dataDir` kết thúc bằng ký tự phân tách tệp (`/` hoặc `\\`) hoặc nối bằng `File.separator`.  
- **Cần giấy phép** – bản dùng thử hoạt động cho việc đánh giá, nhưng cần giấy phép đầy đủ cho môi trường sản xuất.  
- **Ký tự không được hỗ trợ** – Code128 hỗ trợ toàn bộ bộ ASCII; tránh các ký tự Unicode trừ khi bạn chuyển sang ký hiệu khác.  

## Kết luận

Bây giờ bạn đã biết cách **tạo hình ảnh mã vạch Code128** với các thanh trống bằng Aspose.BarCode cho Java. Cách tiếp cận đơn giản này cho phép bạn nhanh chóng tạo đồ họa mã vạch có thể tùy chỉnh, dù bạn đang xây dựng công cụ quản lý tồn kho trên desktop hay API dựa trên đám mây.

## Câu hỏi thường gặp

### Aspose.BarCode có tương thích với mọi môi trường phát triển Java không?
Có, Aspose.BarCode được thiết kế để tích hợp liền mạch với bất kỳ IDE Java nào hoặc hệ thống xây dựng nào, bao gồm Maven, Gradle và các dự án JAR thuần.

### Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Chắc chắn! Ngoài `FilledBars`, bạn có thể thay đổi màu sắc, độ rộng thanh, lề, và thậm chí thêm văn bản có thể đọc được bằng con người bằng API phong phú.

### Có phiên bản dùng thử cho Aspose.BarCode không?
Có, bạn có thể khám phá các khả năng của Aspose.BarCode bằng cách nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### Làm thế nào tôi có thể nhận hỗ trợ cho Aspose.BarCode?
Đối với bất kỳ câu hỏi hoặc hỗ trợ nào, hãy truy cập [diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

### Tôi có thể tìm tài liệu chi tiết cho Aspose.BarCode ở đâu?
Tài liệu chi tiết có sẵn [tại đây](https://reference.aspose.com/barcode/java/).

**Câu hỏi bổ sung**

**Q: Làm sao để tôi tạo ảnh mã vạch ở định dạng khác, như JPEG?**  
A: Thay đổi đối số thứ hai của `save` thành `BarCodeImageFormat.JPEG`.

**Q: Tôi có thể tạo nhiều mã vạch trong một vòng lặp không?**  
A: Có – khởi tạo một `BarcodeGenerator` mới trong vòng lặp của bạn hoặc tái sử dụng cùng một instance với `CodeText` mới.

---

**Cập nhật lần cuối:** 2026-04-12  
**Đã kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}