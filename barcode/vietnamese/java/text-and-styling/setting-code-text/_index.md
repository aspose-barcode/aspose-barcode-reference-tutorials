---
date: 2025-12-30
description: Tìm hiểu cách tạo mã vạch Java bằng Aspose.BarCode. Hướng dẫn từng bước
  này chỉ cho bạn cách đặt văn bản mã vạch tùy chỉnh, điều chỉnh độ rộng và lưu hình
  ảnh.
linktitle: Setting Code Text
second_title: Aspose.BarCode Java API
title: 'Tạo mã vạch Java - Đặt văn bản mã bằng Aspose.BarCode'
url: /vi/java/text-and-styling/setting-code-text/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã Vạch Java: Đặt Văn Bản Mã Sử Dụng Aspose.BarCode

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học cách **tạo mã vạch Java** với thư viện Aspose.BarCode cho Java. Dù bạn đang xây dựng hệ thống quản lý tồn kho, giải pháp theo dõi tài liệu, hay bất kỳ ứng dụng nào cần mã vạch, hướng dẫn này sẽ dẫn bạn qua từng bước — từ việc tạo mã vạch **Code128** đến tùy chỉnh văn bản mã và điều chỉnh độ rộng thanh. Khi hoàn thành, bạn sẽ có một hình ảnh sẵn sàng để sử dụng và có thể nhúng ở bất kỳ nơi nào bạn cần.

## Câu trả lời nhanh
- **Thư viện nào tôi nên sử dụng?** Aspose.BarCode for Java.  
- **Loại mã vạch nào được trình bày?** CODE_128.  
- **Làm thế nào để đặt văn bản mã vạch tùy chỉnh?** Sử dụng hàm khởi tạo `BarcodeGenerator` hoặc phương thức `setCodeText`.  
- **Tôi có thể thay đổi độ rộng thanh không?** Có, thông qua `XDimension` tính bằng milimet.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại.

## Yêu cầu trước

Trước khi bắt đầu hướng dẫn, hãy chắc chắn rằng bạn đã chuẩn bị các mục sau:

- Kiến thức cơ bản về lập trình Java.  
- Môi trường phát triển Java hoạt động đã được cài đặt.  
- Thư viện Aspose.BarCode cho Java. Bạn có thể tải xuống **[here](https://releases.aspose.com/barcode/java/)**.  
- Trình soạn thảo mã, chẳng hạn IntelliJ IDEA hoặc Eclipse.  

## Nhập Gói

Bắt đầu bằng việc nhập các gói cần thiết vào dự án Java của bạn. Các gói này là thiết yếu để làm việc với Aspose.BarCode.

```java
import com.aspose.barcode.generation.BarcodeGenerator;
```

Bây giờ, chúng ta sẽ khám phá quy trình đặt văn bản mã sử dụng Aspose.BarCode trong Java. Hãy làm theo các bước sau:

## Hướng Dẫn Barcode Generator: Tạo Mã Vạch Code128

### Bước 1: Tạo một Instance của `BarcodeGenerator`

```java
// The path to the documents directory.
String path = "Your Directory Path";
// The path to the resource directory.
String dataDir = "Your Document Directory";
BarcodeGenerator generator = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_128, "12345678");
```

Ở đây, chúng ta tạo một instance `BarcodeGenerator`, chỉ định kiểu mã vạch (**CODE_128**) và **văn bản mã vạch tùy chỉnh** `"12345678"`.

### Bước 2: Điều chỉnh Độ Rộng Mã Vạch cho Văn Bản Mã Vạch Tùy Chỉnh

```java
generator.getParameters().getBarcode().getXDimension().setMillimeters(0.5f);
```

Điều chỉnh độ rộng của các thanh theo sở thích của bạn. Trong ví dụ này, chúng tôi **điều chỉnh độ rộng mã vạch** thành `0.5` mm, phù hợp với hầu hết các kích thước nhãn.

### Bước 3: Lưu Hình Ảnh Mã Vạch

```java
generator.save(dataDir + "setCodeText.jpg");
```

Lưu hình ảnh mã vạch đã tạo vào thư mục được chỉ định. Trong trường hợp này, tệp được lưu dưới tên **`setCodeText.jpg`** trong thư mục tài liệu của bạn.

## Tại sao nên sử dụng Aspose.BarCode cho Java?

- **API toàn diện** – Hỗ trợ hơn 60 kiểu mã vạch, bao gồm Code128, QR, DataMatrix, và nhiều hơn nữa.  
- **Kết xuất chất lượng cao** – Tạo ra hình ảnh sắc nét ở các định dạng PNG, JPEG, SVG và PDF.  
- **Dễ dàng tùy chỉnh** – Thay đổi văn bản, kích thước, màu sắc, và thậm chí thêm chú thích có thể đọc được bằng con người chỉ với vài dòng mã.  
- **Đa nền tảng** – Hoạt động trên Windows, Linux và macOS với bất kỳ môi trường chạy Java 8+ nào.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Mã vạch bị mờ** | Tăng độ phân giải hình ảnh hoặc xuất ra các định dạng vector (SVG, PDF). |
| **Văn bản bị cắt ngắn** | Đảm bảo `XDimension` (độ rộng thanh) và `BarHeight` đủ lớn cho kiểu mã vạch đã chọn. |
| **Giấy phép không được áp dụng** | Đặt tệp giấy phép của bạn (`Aspose.BarCode.lic`) vào thư mục gốc của dự án và tải nó bằng `License license = new License(); license.setLicense("Aspose.BarCode.lic");`. |

## Các câu hỏi thường gặp bổ sung

**Q:** *Sự khác biệt giữa `CODE_128` và các biến thể Code128 khác là gì?*  
**A:** `CODE_128` là kiểu chuẩn tự động chọn mã hóa hiệu quả nhất (A, B hoặc C) dựa trên văn bản đầu vào.

**Q:** *Tôi có thể đổi định dạng xuất ra PNG thay vì JPEG không?*  
**A:** Chắc chắn. Sử dụng `generator.save(dataDir + "setCodeText.png", com.aspose.barcode.BarcodeImageFormat.PNG);`.

**Q:** *Có thể thêm chú thích có thể đọc được bằng người dưới mã vạch không?*  
**A:** Có. Đặt `generator.getParameters().getBarcode().getCaption().setTopMargin(5);` và chỉ định văn bản chú thích.

**Q:** *Aspose.BarCode có hỗ trợ ký tự Unicode không?*  
**A:** Có. Cung cấp văn bản ở định dạng UTF‑8 và đảm bảo kiểu mã vạch đã chọn hỗ trợ bộ ký tự đó.

**Q:** *Làm thế nào để tôi tạo nhiều mã vạch trong một vòng lặp?*  
**A:** Tạo một `BarcodeGenerator` mới trong vòng lặp, đặt văn bản cho mỗi lần lặp, và gọi `save` với tên tệp duy nhất.

---

**Cập nhật lần cuối:** 2025-12-30  
**Đã kiểm tra với:** Aspose.BarCode 24.12 cho Java  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}