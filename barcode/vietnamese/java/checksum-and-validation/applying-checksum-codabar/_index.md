---
date: 2025-12-18
description: Tìm hiểu cách tạo hình ảnh mã vạch Codabar và xem ví dụ trình đọc mã
  vạch Java bằng Aspose.BarCode. Tạo và nhận dạng mã vạch một cách dễ dàng với hướng
  dẫn từng bước này.
linktitle: Applying Checksum for CodaBar
second_title: Aspose.BarCode Java API
title: Cách tạo hình ảnh mã vạch Codabar có checksum trong Java
url: /vi/java/checksum-and-validation/applying-checksum-codabar/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< /blocks/products/pf/tutorial-page-section >}}

# Cách tạo hình ảnh mã vạch codabar có checksum trong Java

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học cách **tạo hình ảnh mã vạch codabar** có checksum trong Java bằng Aspose.BarCode. Chúng tôi sẽ hướng dẫn cách tạo mã vạch CodaBar, bật checksum, và sau đó đọc lại bằng **java barcode reader example**. Khi hoàn thành, bạn sẽ có một đoạn mã sẵn sàng sử dụng mà có thể chèn vào bất kỳ dự án Java nào.

## Câu trả lời nhanh
- **Checksum làm gì?** Nó xác thực tính toàn vẹn của dữ liệu mã vạch khi quét.  
- **Thư viện nào cần thiết?** Aspose.BarCode for Java.  
- **Tôi có cần giấy phép cho việc phát triển không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Tôi có thể tùy chỉnh giao diện mã vạch không?** Có – sắc, kích thước và phông chữ có thể thay đổi thông qua các tham số của trình tạo.  
- **Liệu nó có tương thích với mọi phiên bản Java không?** Thư viện hỗ trợ Java 8 và các phiên bản mới hơn.

## CodaBar là gì?

CodaBar là một ký hiệu tuyến tính (1‑chiều) được sử dụng rộng rãi trong thư viện, ngân hàng máu và bán lẻ. Nó mã hoá dữ liệu số và một vài ký tự đặc biệt, làm cho nó lý tưởng cho các thẻ đơn giản, có thể đọc bằng máy. Thêm checksum (Mod 10) cải thiện độ chính xác khi đọc, đặc biệt trên các bản in chất lượng thấp.

## Tại sao nên sử dụng Aspose.BarCode cho Java?

Aspose.BarCode cung cấp một **java barcode reader example** trừu tượng hoá các chi tiết mức thấp của việc tạo và nhận dạng mã vạch. Nó cung cấp:

* Kiểm soát đầy đủ chế độ checksum.  
* Tích hợp liền mạch với các IDE Java.  
* Tài liệu và hỗ trợ phong phú.  

## Yêu cầu trước

Trước khi bắt đầu, hãy đảm bảo bạn có:

- Java Development Kit (JDK) đã được cài đặt trên máy của bạn.  
- Thư viện Aspose.BarCode cho Java. Bạn có thể tải xuống từ [here](https://releases.aspose.com/barcode/java/).  
- Kiến thức cơ bản về lập trình Java.  

## Nhập gói

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

## Hướng dẫn từng bước

### Bước 1: Thiết lập môi trường

Tạo một dự án Java mới và thêm file JAR Aspose.BarCode vào đường dẫn biên dịch. Xác định một thư mục để lưu các hình ảnh được tạo.

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

### Bước 2: Tạo hình ảnh mã vạch CodaBar có checksum

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

### Bước 3: Java barcode reader example – Nhận dạng mã vạch

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

Chạy mã sẽ xuất ra văn bản đã giải mã, loại ký hiệu và checksum đã tính, xác nhận rằng mã vạch đã được tạo và xác thực đúng.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Kiểm tra checksum thất bại** | Xác minh rằng `EnableChecksum` được đặt thành `YES` và `CodabarChecksumMode` khớp với chế độ đã dùng khi tạo (Mod 10). |
| **Lỗi không tìm thấy tệp** | Đảm bảo `dataDir` trỏ tới một thư mục tồn tại và hình ảnh đã tạo (`Codabar_Mod10.png`) được lưu ở đó trước khi đọc. |
| **Phiên bản Java không được hỗ trợ** | Sử dụng Java 8 hoặc mới hơn; các phiên bản cũ hơn có thể thiếu các API cần thiết. |

## Câu hỏi thường gặp

**Q: Aspose.BarCode có tương thích với mọi phiên bản Java không?**  
A: Aspose.BarCode được thiết kế để hoạt động với Java 8 và các phiên bản mới hơn. Kiểm tra tài liệu chính thức để biết chi tiết tương thích.

**Q: Tôi có thể tùy chỉnh giao diện của mã vạch đã tạo không?**  
A: Có, bạn có thể thay đổi màu sắc, phông chữ và định dạng ảnh thông qua API tham số của trình tạo.

**Q: Có giấy phép tạm thời cho mục đích thử nghiệm không?**  
A: Có, bạn có thể lấy giấy phép tạm thời cho Aspose.BarCode từ [here](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm hỗ trợ và tài nguyên bổ sung ở đâu?**  
A: Truy cập [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) để nhận hỗ trợ cộng đồng và thảo luận.

**Q: Có bản dùng thử miễn phí không?**  
A: Có, bạn có thể khám phá các tính năng của Aspose.BarCode bằng cách tải bản dùng thử miễn phí từ [here](https://releases.aspose.com/).

---

**Cập nhật lần cuối:** 2025-12-18  
**Được kiểm tra với:** Aspose.BarCode for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/main-wrap-class >}}

{{< /blocks/products/pf/main-container >}}
{{< blocks/products/products-backtop-button >}}

{{< blocks/products/pf/tutorial-page-section >}}