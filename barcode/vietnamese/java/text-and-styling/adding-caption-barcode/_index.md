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

## Introduction

Nếu bạn cần **cách thêm caption** vào mã vạch để cải thiện khả năng đọc và thương hiệu, bạn đã đến đúng nơi. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước để thêm caption ở trên và dưới hình ảnh mã vạch bằng Aspose.BarCode cho Java. Khi hoàn thành, bạn sẽ có một mã vạch được định dạng đầy đủ, không chỉ mã hoá dữ liệu mà còn hiển thị văn bản hữu ích — hoàn hảo cho nhãn sản phẩm, hệ thống tồn kho, hoặc bất kỳ trường hợp nào mà người dùng hưởng lợi từ ngữ cảnh bổ sung.

## Quick Answers
- **Thư viện nào được yêu cầu?** Aspose.BarCode cho Java.  
- **Tôi có thể thay đổi phông chữ và màu sắc không?** Có — cả phông chữ và màu văn bản của caption đều có thể tùy chỉnh.  
- **Các loại mã vạch nào hoạt động?** Tất cả các symbology được Aspose.BarCode hỗ trợ (ví dụ: CODE_128, QR, DataMatrix).  
- **Tôi có cần giấy phép để thử nghiệm không?** Có bản dùng thử miễn phí; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Thời gian triển khai mất bao lâu?** Thông thường dưới 10 phút sau khi đã thêm thư viện.

## What is a caption in a barcode?

Caption là văn bản thuần xuất hiện ở trên hoặc dưới đồ họa mã vạch. Nó có thể truyền tải tên sản phẩm, giá cả, hoặc bất kỳ thông tin nào khác bổ trợ cho dữ liệu đã mã hoá.

## Why add captions with Aspose.BarCode?
- **Cải thiện trải nghiệm người dùng:** Người dùng có thể ngay lập tức đọc ý nghĩa của mã vạch mà không cần quét.  
- **Nhất quán thương hiệu:** Bạn có thể áp dụng phông chữ, màu sắc và căn chỉnh riêng để phù hợp với hướng dẫn phong cách công ty.  
- **Kiểm soát toàn diện:** API của Aspose.BarCode cho phép bạn bật/tắt hiển thị, đặt căn chỉnh và định dạng mỗi caption một cách độc lập.

## Prerequisites

- Java Development Kit (JDK) đã được cài đặt.  
- Thư viện Aspose.BarCode cho Java đã tải về và được thêm vào dự án của bạn. Bạn có thể tìm liên kết tải xuống [tại đây](https://releases.aspose.com/barcode/java/).  
- Một IDE như IntelliJ IDEA hoặc Eclipse.

## Import Packages

Trong tệp nguồn Java của bạn, nhập các lớp Aspose.BarCode cần thiết và lớp AWT `Color`:

```java
import com.aspose.barcode.*;
import java.awt.*;
```

## Step 1: Set Up Document and Resource Directories

Xác định nơi bạn muốn lưu hình ảnh mã vạch được tạo. Điều chỉnh các đường dẫn để phù hợp với môi trường của bạn.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

## Step 2: Create Barcode Generator Instance

Tạo một thể hiện của `BarcodeGenerator` với symbology mong muốn (ví dụ: CODE_128) và văn bản mã bạn muốn mã hoá.

```java
BarcodeGenerator bb = new BarcodeGenerator(EncodeTypes.CODE_128, "12345678");
```

## Step 3: Configure Caption Above the Barcode

Đặt caption sẽ xuất hiện ở trên mã vạch. Bạn có thể kiểm soát căn chỉnh, văn bản, hiển thị, phông chữ, kích thước và màu sắc.

```java
bb.getParameters().getCaptionAbove().setAlignment(TextAlignment.LEFT);
bb.getParameters().getCaptionAbove().setText("Aspose.Demo");
bb.getParameters().getCaptionAbove().setVisible(true);
bb.getParameters().getCaptionAbove().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionAbove().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionAbove().setTextColor(Color.RED);
```

## Step 4: Configure Caption Below the Barcode

Tương tự, định nghĩa caption ở dưới mã vạch. Bạn có thể sử dụng căn chỉnh hoặc kiểu dáng khác nếu cần.

```java
bb.getParameters().getCaptionBelow().setAlignment(TextAlignment.RIGHT);
bb.getParameters().getCaptionBelow().setText("Aspose.Demo");
bb.getParameters().getCaptionBelow().setVisible(true);
bb.getParameters().getCaptionBelow().getFont().setFamilyName("Pristina");
bb.getParameters().getCaptionBelow().getFont().getSize().setPoint(14);
bb.getParameters().getCaptionBelow().setTextColor(Color.RED);
```

## Step 5: Save the Barcode Image

Cuối cùng, ghi mã vạch (cùng với caption) vào tệp hình ảnh. Định dạng được suy ra từ phần mở rộng tệp.

```java
bb.save(dataDir + "barcodeCaption.jpg");
```

Bạn có thể lặp lại các bước trên để thử nghiệm các phông chữ, màu sắc hoặc căn chỉnh khác nhau, hoặc để tạo nhiều hình ảnh mã vạch trong một vòng lặp.

## Common Issues & Tips

- **Caption không hiển thị?** Đảm bảo đã gọi `setVisible(true)` cho caption bạn muốn hiển thị.  
- **Màu không đúng?** Sử dụng hằng số `java.awt.Color` hoặc tạo màu tùy chỉnh bằng `new Color(r, g, b)`.  
- **Vấn đề đường dẫn?** Kiểm tra `dataDir` trỏ tới thư mục có thể ghi được; nếu không, `bb.save()` sẽ ném `IOException`.  
- **Mẹo hiệu suất:** Tái sử dụng một thể hiện `BarcodeGenerator` duy nhất khi tạo nhiều mã vạch; chỉ thay đổi `EncodeTypes` hoặc `codetext` khi cần.

## Frequently Asked Questions (FAQs)

### Can I customize the font style of the barcode captions?
Có, bạn có thể tùy chỉnh phông chữ, kích thước và màu sắc của cả caption ở trên và dưới mã vạch.

### Is Aspose.BarCode compatible with different barcode symbologies?
Chắc chắn! Aspose.BarCode hỗ trợ nhiều loại symbology, đảm bảo tính linh hoạt trong việc tạo mã vạch.

### How can I integrate Aspose.BarCode into my Java project?
Bạn có thể tham khảo hướng dẫn tích hợp chi tiết có sẵn [tại đây](https://reference.aspose.com/barcode/java/) để biết các bước thực hiện.

### Is there a free trial available for Aspose.BarCode for Java?
Có, bạn có thể truy cập bản dùng thử miễn phí [tại đây](https://releases.aspose.com/) để khám phá tất cả các tính năng trước khi mua.

### Where can I get help if I run into issues?
Cộng đồng diễn đàn Aspose.BarCode là nơi tuyệt vời để nhận hỗ trợ và thảo luận. Truy cập diễn đàn [tại đây](https://forum.aspose.com/c/barcode/13).

---

**Cập nhật lần cuối:** 2025-12-27  
**Đã kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}