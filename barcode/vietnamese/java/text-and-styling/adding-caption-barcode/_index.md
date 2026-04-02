---
date: 2025-12-27
description: Học cách thêm chú thích vào hình ảnh mã vạch trong Java bằng Aspose.BarCode.
  Ví dụ tạo mã vạch Java này cho thấy cách tạo hình ảnh mã vạch Java một cách dễ dàng.
linktitle: Adding Caption to Barcode
second_title: Aspose.BarCode Java API
title: Cách Thêm Chú Thì cho Mã Vạch trong Java bằng Aspose.BarCode
url: /vi/java/text-and-styling/adding-caption-barcode/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Thêm Caption vào Mã Vạch trong Java Sử Dụng Aspose.BarCode

## Giới thiệu

Nếu bạn cần **cách thêm chú thích** vào mã vạch để cải thiện khả năng đọc và tín hiệu thương hiệu, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước để thêm chú thích ở trên và dưới hình ảnh mã vạch bằng Aspose.BarCode cho Java. Khi hoàn thành, bạn sẽ có một mã vạch được định dạng đầy đủ, không mã hóa dữ liệu mà vẫn hiển thị văn bản hữu ích — hoàn hảo cho nhãn sản phẩm, hệ thống tồn tại hoặc bất kỳ trường hợp nào mà người dùng được hưởng lợi từ ngữ cảnh bổ sung.

## Trả lời nhanh
- **Thư viện nào được yêu cầu?** Aspose.BarCode cho Java.
- **Tôi có thể thay đổi phông chữ và màu sắc không?** Có — cả phông chữ và văn bản màu của chú thích đều có thể tùy chỉnh.
- **Các loại mã vạch nào hoạt động?** Tất cả các loại ký hiệu đều được Aspose.BarCode hỗ trợ (ví dụ: CODE_128, QR, DataMatrix).
- **Tôi có cần giấy phép để thử nghiệm không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho môi trường sản xuất.
- **Thời gian phát triển khai mất bao lâu?** Thông thường dưới 10 phút sau khi thêm thư viện.

## Chú thích trên mã vạch là gì?

Caption là văn bản tĩnh xuất hiện ở trên hoặc dưới đồ họa mã vạch. Nó có thể truyền tải sản phẩm tên, giá cả hoặc bất kỳ thông tin nào khác hỗ trợ cho mã hóa dữ liệu.

## Tại sao thêm chú thích bằng Aspose.BarCode?
- **Người dùng trải nghiệm trải nghiệm:** Người dùng có thể ngay lập tức đọc ý nghĩa của mã vạch mà không cần quét.
- **Nhất quán thương hiệu:** Bạn có thể áp dụng phông chữ, màu sắc và căn chỉnh riêng để phù hợp với phong cách công ty hướng dẫn.
- **Kiểm soát toàn diện:** API của Aspose.BarCode cho phép bạn bật/tắt hiển thị, đặt căn chỉnh và định dạng mỗi chú thích một cách độc lập.

## Điều kiện tiên quyết

- Bộ công cụ phát triển Java (JDK) đã được cài đặt.
- Thư viện Aspose.BarCode cho Java đã được tải xuống và bổ sung vào dự án của bạn. Bạn có thể tìm liên kết tải xuống [tại đây](https://releases.aspose.com/barcode/java/).
- Một IDE như IntelliJ IDEA hoặc Eclipse.

## Nhập gói

Trong tệp nguồn Java của bạn, nhập các lớp Aspose.BarCode cần thiết và lớp AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Bước 1: Thiết lập thư mục tài liệu và tài nguyên

Xác định nơi bạn muốn lưu hình ảnh mã vạch được tạo. Điều chỉnh các đường dẫn để phù hợp với môi trường của bạn.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Bước 2: Tạo phiên bản trình tạo mã vạch

Tạo một thể hiện của `BarcodeGenerator` với symbology mong muốn (ví dụ: CODE_128) và văn bản mã bạn muốn mã hoá.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Bước 3: Cấu hình chú thích phía trên mã vạch

Đặt caption sẽ xuất hiện ở trên mã vạch. Bạn có thể kiểm soát căn chỉnh, văn bản, hiển thị, phông chữ, kích thước và màu sắc.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Bước 4: Cấu hình chú thích phía dưới mã vạch

Tương tự, định nghĩa caption ở dưới mã vạch. Bạn có thể sử dụng căn chỉnh hoặc kiểu dáng khác nếu cần.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Bước 5: Lưu hình ảnh mã vạch

Cuối cùng, ghi mã vạch (cùng với caption) vào tệp hình ảnh. Định dạng được suy ra từ phần mở rộng tệp.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

Bạn có thể lặp lại các bước trên để thử nghiệm các phông chữ, màu sắc hoặc căn chỉnh khác nhau, hoặc để tạo nhiều hình ảnh mã vạch trong một vòng lặp.

## Các vấn đề thường gặp & Mẹo

- **Chú thích không hiển thị?** Đảm bảo đã gọi `setVisible(true)` cho chú thích bạn muốn hiển thị.
- **Màu sai?** Sử dụng hằng số `java.awt.Color` hoặc tạo tùy chọn màu bằng `new Color(r, g, b)`.
- **Đường dẫn chủ đề?** Kiểm tra con trỏ `dataDir` tới thư mục có thể ghi được; nếu không, `bb.save()` sẽ xử lý `IOException`.
- **Mã hiệu suất:** Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất khi tạo nhiều mã vạch; chỉ thay đổi `EncodeTypes` hoặc `codetext` khi cần.

## Câu hỏi thường gặp (FAQ)

### Tôi có thể tùy chỉnh kiểu phông chữ của chú thích mã vạch không?
Có, bạn có thể tùy chỉnh phông chữ, kích thước và màu sắc của cả chú thích ở trên và dưới mã vạch.

### Aspose.BarCode có tương thích với các hệ thống ký hiệu mã vạch khác nhau không?
Chắc chắn! Aspose.BarCode hỗ trợ nhiều loại ký hiệu, đảm bảo tính linh hoạt trong việc tạo mã vạch.

### Làm cách nào tôi có thể tích hợp Aspose.BarCode vào dự án Java của mình?
Bạn có thể tham khảo sẵn các hướng dẫn tích hợp chi tiết [tại đây](https://reference.aspose.com/barcode/java/) để biết các bước thực hiện.

### Có bản dùng thử miễn phí cho Aspose.BarCode cho Java không?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/) để khám phá tất cả các tính năng trước khi mua.

### Tôi có thể nhận trợ giúp ở đâu nếu gặp vấn đề?
Cộng đồng diễn đàn Aspose.BarCode là nơi tuyệt vời để nhận được hỗ trợ và thảo luận. Truy cập diễn đàn [tại đây](https://forum.aspose.com/c/barcode/13).

---

**Cập nhật lần cuối:** 2025-12-27
**Đã kiểm tra với:** Aspose.BarCode for Java 24.11
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}