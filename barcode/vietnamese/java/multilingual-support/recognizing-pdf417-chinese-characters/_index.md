---
date: 2025-12-25
description: Học cách trích xuất văn bản từ hình ảnh mã vạch, cụ thể là PDF417 có
  ký tự Trung Quốc, bằng Aspose.BarCode cho Java. Hãy theo dõi hướng dẫn từng bước
  của chúng tôi để đọc dữ liệu mã vạch một cách hiệu quả.
linktitle: 'Extract Text from Barcode: PDF417 Chinese Characters'
second_title: Aspose.BarCode Java API
title: 'Trích xuất văn bản từ mã vạch: Ký tự Trung Quốc PDF417 trong Java'
url: /vi/java/multilingual-support/recognizing-pdf417-chinese-characters/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Trích xuất Văn bản từ Mã vạch: PDF417 Ký tự Trung Quốc trong Java

## Giới thiệu

Việc tích hợp nhận dạng mã vạch vào các ứng dụng Java là một kỹ năng quý giá, đặc biệt khi bạn cần **trích xuất văn bản từ mã vạch** trong các hình ảnh chứa dữ liệu đa ngôn ngữ. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách sử dụng Aspose.BarCode cho Java để nhận dạng mã vạch PDF417 có ký tự Trung Quốc. Khi hoàn thành, bạn sẽ biết chính xác cách đọc dữ liệu mã vạch và giải mã chúng thành văn bản có thể đọc được.

## Câu trả lời nhanh
- **Thư viện nào hỗ trợ PDF417 với ký tự Trung Quốc?** Aspose.BarCode cho Java.  
- **Bộ ký tự nào cần thiết cho việc giải mã tiếng Trung?** MS936 (GBK).  
- **Tôi có cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Có, cần giấy phép thương mại.  
- **Tôi có thể chạy trên bất kỳ phiên bản Java nào không?** Nó hoạt động với Java 8 và các phiên bản mới hơn.  
- **Có bản dùng thử miễn phí không?** Chắc chắn – tải xuống từ trang web của Aspose.

## “Trích xuất văn bản từ mã vạch” là gì?

Trích xuất văn bản từ mã vạch có nghĩa là chuyển đổi dữ liệu đã mã hoá trở lại dạng đọc được bởi con người. Đối với mã vạch PDF417 lưu trữ ký tự Trung Quốc, việc này còn đòi hỏi chọn đúng bộ mã ký tự để các byte được ánh xạ tới các glyph chính xác.

## Tại sao nên sử dụng Aspose.BarCode cho Java?

Aspose.BarCode cung cấp hỗ trợ mạnh mẽ cho nhiều loại symbology mã vạch, bao gồm PDF417, và xử lý các bộ ký tự phức tạp ngay từ đầu. Nó trừu tượng hoá việc xử lý ảnh mức thấp, cho phép bạn tập trung vào logic nghiệp vụ thay vì các chi tiết giải mã.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

1. **Java Development Kit (JDK)** – nên sử dụng phiên bản mới nhất.  
2. **Aspose.BarCode cho Java** – tải xuống từ [đây](https://releases.aspose.com/barcode/java/).  
3. **Một ảnh mã vạch PDF417** chứa ký tự Trung Quốc (ví dụ: `barcode.png`).

## Nhập khẩu Gói

Trong dự án Java của bạn, nhập các lớp cần thiết để làm việc với Aspose.BarCode:

```java
import java.nio.ByteBuffer;
import java.nio.charset.Charset;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Bước 1: Đặt Thư mục Tài liệu

Xác định thư mục chứa ảnh mã vạch của bạn:

```java
String dataDir = "Your Document Directory";
```

Thay thế `"Your Document Directory"` bằng đường dẫn thực tế trên máy của bạn.

## Bước 2: Tải Ảnh Mã vạch

Tạo một thể hiện `BarCodeReader` trỏ tới tệp PNG và chỉ định cho bộ đọc tìm kiếm symbology PDF417:

```java
BarCodeReader reader = new BarCodeReader(dataDir + "barcode.png", DecodeType.PDF_417);
```

## Bước 3: Đọc Mã vạch

Lặp qua các kết quả phát hiện, lấy mảng byte thô và giải mã chúng bằng bộ ký tự GBK (MS936):

```java
for (BarCodeResult result : reader.readBarCodes()) {
    byte[] bytes = result.getCodeBytes();
    ByteBuffer bytebuf = ByteBuffer.wrap(bytes);
    System.out.println(Charset.forName("MS936").decode(bytebuf).toString());
}
```

Vòng lặp này **trích xuất văn bản từ mã vạch** và in các ký tự Trung Quốc đã giải mã ra console.

## Cách đọc mã vạch với PDF417?

Mã trên minh họa **cách đọc mã vạch** dữ liệu từng bước:

1. **Khởi tạo** bộ đọc với `DecodeType` đúng.  
2. **Lặp lại** qua mỗi `BarCodeResult` trả về.  
3. **Chuyển đổi** các byte thô bằng charset thích hợp (`MS936` cho tiếng Trung).  

Nếu mã vạch của bạn chứa các ngôn ngữ khác, chỉ cần đổi charset sang bộ phù hợp với dữ liệu của bạn.

## Các vấn đề thường gặp & Giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| Ký tự bị rối sau khi giải mã | Xác nhận bạn đang sử dụng charset đúng (`MS936` cho GBK). |
| Không phát hiện mã vạch | Đảm bảo chất lượng ảnh cao và mã vạch không bị quay; bạn có thể tiền xử lý ảnh nếu cần. |
| Nhiều kết quả được trả về | PDF417 có thể lưu nhiều đoạn; lặp qua tất cả kết quả như đã minh họa. |

## Câu hỏi thường gặp (FAQs)

### Tôi có thể sử dụng Aspose.BarCode cho Java trong các dự án thương mại không?
Có, bạn có thể sử dụng Aspose.BarCode cho Java trong các dự án thương mại. Để biết chi tiết về giấy phép, truy cập [đây](https://purchase.aspose.com/buy).

### Có bản dùng thử miễn phí không?
Có, bạn có thể truy cập bản dùng thử miễn phí của Aspose.BarCode cho Java [đây](https://releases.aspose.com/).

### Làm thế nào để tôi nhận được hỗ trợ cho Aspose.BarCode?
Truy cập diễn đàn Aspose.BarCode [đây](https://forum.aspose.com/c/barcode/13) để được hỗ trợ hoặc đặt câu hỏi.

### Tôi có thể lấy giấy phép tạm thời để thử nghiệm không?
Có, bạn có thể nhận giấy phép tạm thời [đây](https://purchase.aspose.com/temporary-license/).

### Tôi có thể tìm tài liệu ở đâu?
Tài liệu có sẵn [đây](https://reference.aspose.com/barcode/java/).

**Câu hỏi bổ sung**

**Q: Nếu ảnh mã vạch của tôi ở định dạng JPEG thì sao?**  
A: `BarCodeReader` hoạt động với JPEG, PNG, BMP và các định dạng ảnh phổ biến khác—chỉ cần thay đổi phần mở rộng tệp cho phù hợp.

**Q: Tôi có thể giải mã mã vạch từ một luồng thay vì tệp không?**  
A: Có, bạn có thể truyền một `InputStream` vào hàm khởi tạo `BarCodeReader` để giải mã ngay trong luồng.

**Q: Aspose.BarCode có hỗ trợ các bộ ký tự khác không?**  
A: Chắc chắn. Sử dụng `Charset.forName("<your‑charset>")` để giải mã byte cho UTF‑8, ISO‑8859‑1, v.v.

## Kết luận

Bạn đã học cách **trích xuất văn bản từ mã vạch** trong các ảnh, cụ thể là mã vạch PDF417 chứa ký tự Trung Quốc, bằng cách sử dụng Aspose.BarCode cho Java. Khả năng này mở ra nhiều cơ hội cho các hệ thống quản lý tồn kho đa ngôn ngữ, tự động hoá tài liệu và hơn thế nữa. Hãy thử nghiệm với các symbology và bộ ký tự khác để mở rộng phạm vi ứng dụng của bạn.

---

**Last Updated:** 2025-12-25  
**Tested With:** Aspose.BarCode cho Java 24.12  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}