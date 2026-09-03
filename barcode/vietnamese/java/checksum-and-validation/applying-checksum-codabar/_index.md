---
date: 2026-04-05
description: Tìm hiểu cách tạo hình ảnh mã vạch Codabar bằng Java có kiểm tra tổng
  và xem ví dụ trình đọc mã vạch Java sử dụng Aspose.BarCode. Hãy làm theo hướng dẫn
  từng bước này để tạo và nhận dạng mã vạch.
keywords:
- create codabar barcode java
- java barcode reader example
- codabar checksum
- aspose barcode java
linktitle: Áp dụng kiểm tra tổng cho CodaBar
second_title: Aspose.BarCode Java API
title: Cách tạo hình ảnh mã vạch Codabar bằng Java có checksum
url: /vi/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch codabar bằng Java với checksum

## Giới thiệu

Trong hướng dẫn này, bạn sẽ **tạo mã vạch codabar java** hình ảnh với checksum Mod 10 bằng cách sử dụng Aspose.BarCode cho Java. Chúng tôi sẽ hướng dẫn cách tạo mã vạch CodaBar, bật checksum và sau đó xác thực nó bằng một **ví dụ đọc mã vạch java**. Khi kết thúc, bạn sẽ có một đoạn mã sẵn sàng để sử dụng mà bạn có thể chèn vào bất kỳ dự án Java nào, dù bạn đang xây dựng hệ thống thư viện, máy in nhãn phòng thí nghiệm y tế, hay giải pháp thanh toán bán lẻ.

## Câu trả lời nhanh
- **Checksum làm gì?** Nó xác thực tính toàn vẹn của dữ liệu mã vạch khi quét.  
- **Thư viện nào cần thiết?** Aspose.BarCode cho Java.  
- **Tôi có cần giấy phép để phát triển không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể tùy chỉnh giao diện mã vạch không?** Có – màu sắc, kích thước và phông chữ có thể thay đổi thông qua các tham số của trình tạo.  
- **Điều này có tương thích với mọi phiên bản Java không?** Thư viện hỗ trợ Java 8 và các phiên bản mới hơn.

## Cách tạo mã vạch codabar bằng Java

Dưới đây bạn sẽ tìm thấy một hướng dẫn ngắn gọn, từng bước giải thích **tại sao mỗi dòng lại quan trọng**, để bạn có thể điều chỉnh mã cho dự án của mình một cách tự tin.

### Mã vạch CodaBar là gì?

CodaBar là một ký hiệu tuyến tính (1‑chiều) được sử dụng rộng rãi trong thư viện, ngân hàng máu và bán lẻ. Nó mã hoá dữ liệu số và một vài ký tự đặc biệt, làm cho nó trở nên lý tưởng cho các nhãn đơn giản, có thể đọc bằng máy. Thêm checksum (Mod 10) cải thiện độ chính xác khi đọc, đặc biệt trên các bản in chất lượng thấp.

### Tại sao nên sử dụng Aspose.BarCode cho Java?

Aspose.BarCode cung cấp một **ví dụ đọc mã vạch java** giúp trừu tượng hoá các chi tiết cấp thấp của việc tạo và nhận dạng mã vạch. Nó cung cấp:

* Kiểm soát đầy đủ các chế độ checksum.  
* Tích hợp liền mạch với các IDE Java.  
* Tài liệu phong phú và hỗ trợ nhanh chóng.  

### Yêu cầu trước

- Java Development Kit (JDK) 8 hoặc mới hơn đã được cài đặt.  
- Thư viện Aspose.BarCode cho Java. Bạn có thể tải xuống từ [here](https://releases.aspose.com/barcode/java/).  
- Kiến thức cơ bản về các khái niệm lập trình Java.  

### Nhập gói

Trong dự án Java của bạn, nhập các lớp cần thiết để làm việc với Aspose.BarCode:

```java
import java.io.IOException;

import com.aspose.barcode.CodabarChecksumMode;
import com.aspose.barcode.EnableChecksum;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.ChecksumValidation;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
```

### Hướng dẫn từng bước

#### Bước 1: Thiết lập môi trường

Tạo một dự án Java mới và thêm tệp JAR Aspose.BarCode vào đường dẫn biên dịch của bạn. Xác định một thư mục để lưu các hình ảnh được tạo.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

#### Bước 2: Tạo hình ảnh mã vạch CodaBar với checksum

Khởi tạo `BarcodeGenerator`, bật checksum, chọn chế độ Mod 10 và lưu hình ảnh.

```java
// Instantiate BarcodeGenerator object
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODABAR, "1234567890");

// Set the EnableChecksum property to yes
generator.getParameters().getBarcode().setChecksumEnabled(EnableChecksum.YES);

// Set the CodabarChecksumMode
generator.getParameters().getBarcode().getCodabar().setCodabarChecksumMode(CodabarChecksumMode.MOD_10);

// Save the image on the system
generator.save(dataDir + "Codabar_Mod10.png");
```

#### Bước 3: Ví dụ đọc mã vạch Java – Nhận dạng mã vạch

Bây giờ đọc lại mã vạch, bật xác thực checksum để đảm bảo dữ liệu đúng.

```java
// Initialize reader object
BarCodeReader reader = new BarCodeReader(dataDir + "Codabar_Mod10.png", DecodeType.CODABAR);

// Set ChecksumValidation property of the reader to On
reader.setChecksumValidation(ChecksumValidation.ON);

for (BarCodeResult result : reader.readBarCodes()) {
    System.out.println("CodeText: " + result.getCodeText());
    System.out.println("Symbology type: " + result.getCodeType());

    // Get checksum value
    System.out.println("Checksum:" + result.getExtended().getOneD().getCheckSum());
}
```

Chạy mã sẽ xuất ra văn bản đã giải mã, loại ký hiệu, và checksum đã tính, xác nhận rằng mã vạch đã được tạo và xác thực đúng.

### Các trường hợp sử dụng phổ biến

- **Quản lý thư viện:** Mã hoá ID sách để quét nhanh khi trả sách.  
- **Nhãn ngân hàng máu:** Đảm bảo xác định bệnh nhân chính xác với bảo vệ checksum.  
- **Nhãn kệ bán lẻ:** In mã vạch chi phí thấp, tốc độ cao để theo dõi tồn kho.  

### Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Kiểm tra checksum thất bại** | Xác minh rằng `EnableChecksum` được đặt thành `YES` và `CodabarChecksumMode` khớp với chế độ được sử dụng khi tạo (Mod 10). |
| **Lỗi không tìm thấy tệp** | Đảm bảo `dataDir` trỏ tới một thư mục tồn tại và hình ảnh đã tạo (`Codabar_Mod10.png`) được lưu ở đó trước khi đọc. |
| **Phiên bản Java không được hỗ trợ** | Sử dụng Java 8 hoặc mới hơn; các phiên bản cũ hơn có thể thiếu các API cần thiết. |

## Câu hỏi thường gặp

**Q: Aspose.BarCode có tương thích với mọi phiên bản Java không?**  
A: Aspose.BarCode được thiết kế để hoạt động với Java 8 và các phiên bản mới hơn. Kiểm tra tài liệu chính thức để biết chi tiết về khả năng tương thích.

**Q: Tôi có thể tùy chỉnh giao diện của mã vạch đã tạo không?**  
A: Có, bạn có thể thay đổi màu sắc, phông chữ và định dạng hình ảnh thông qua API tham số của trình tạo.

**Q: Có giấy phép tạm thời cho mục đích thử nghiệm không?**  
A: Có, bạn có thể lấy giấy phép tạm thời cho Aspose.BarCode từ [here](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm hỗ trợ và tài nguyên bổ sung ở đâu?**  
A: Truy cập [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) để nhận hỗ trợ cộng đồng và thảo luận.

**Q: Có bản dùng thử miễn phí không?**  
A: Có, bạn có thể khám phá các tính năng của Aspose.BarCode bằng cách tải bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

---

**Cập nhật lần cuối:** 2026-04-05  
**Đã kiểm tra với:** Aspose.BarCode for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}