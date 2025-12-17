---
date: 2025-12-17
description: Học cách tạo mã vạch trong Java bằng Aspose.BarCode, bao gồm việc tạo
  mã vạch động, tạo mã vạch EAN‑13 và lưu hình ảnh mã vạch kèm dữ liệu bổ sung.
linktitle: Supplementing Data
second_title: Aspose.BarCode Java API
title: Cách tạo mã vạch với dữ liệu bổ sung trong Java
url: /vi/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Tạo Mã Vạch với Dữ Liệu Bổ Sung trong Java

## Giới thiệu

Trong môi trường kỹ thuật số ngày càng nhanh chóng hiện nay, **cách tạo mã vạch** một cách hiệu quả là câu hỏi mà nhiều nhà phát triển Java gặp phải. Aspose.BarCode for Java cung cấp một API mạnh mẽ, dễ sử dụng, hỗ trợ **tạo mã vạch động**, bao gồm việc tạo **mã vạch EAN‑13** với dữ liệu bổ sung. Dù bạn đang xây dựng hệ thống quản lý tồn kho, ứng dụng POS bán lẻ, hay phần mềm theo dõi logistics, hướng dẫn này sẽ dẫn bạn qua một **ví dụ tạo mã vạch java** lưu hình ảnh mã vạch vào đĩa và cho phép tùy chỉnh phần bổ sung.

## Trả lời nhanh
- **Thư viện nào là tốt nhất để tạo mã vạch trong Java?** Aspose.BarCode for Java.  
- **Biểu tượng nào tạo mã vạch số 13 chữ số?** EAN‑13.  
- **Tôi có thể thêm dữ liệu bổ sung vào mã vạch EAN‑13 không?** Có, sử dụng API `Supplement`.  
- **Làm sao lưu mã vạch đã tạo thành hình ảnh?** Gọi `generator.save("path/filename.jpg")`.  
- **Cần giấy phép để sử dụng trong môi trường sản xuất không?** Có, cần giấy phép thương mại; có phiên bản dùng thử miễn phí.

## Tạo mã vạch trong Java là gì?

Tạo mã vạch có nghĩa là chuyển đổi dữ liệu—số, chữ hoặc hỗn hợp—thành một mẫu hình ảnh mà máy quét có thể đọc được. Với Aspose.BarCode, bạn có thể tạo **hình ảnh mã vạch độ phân giải cao** ngay lập tức, rất phù hợp cho các trường hợp **tạo mã vạch động** như bán vé thời gian thực hoặc thực hiện đơn hàng.

## Tại sao nên dùng Aspose.BarCode để tạo mã vạch động?

- **Kiểm soát đầy đủ** các loại mã, kích thước, màu sắc và dữ liệu bổ sung.  
- **Không phụ thuộc bên ngoài** – thuần Java, chạy trên mọi nền tảng.  
- **Hỗ trợ tích hợp** cho hàng chục loại mã vạch, bao gồm **tạo mã ean13**.  
- **API đơn giản** cho phép **lưu hình ảnh mã vạch** chỉ bằng một dòng lệnh.

## Yêu cầu trước

Trước khi bắt đầu, hãy đảm bảo bạn có:

- **Java Development Kit (JDK)** – bất kỳ phiên bản mới nào (8 trở lên).  
- **IDE** – IntelliJ IDEA, Eclipse, hoặc trình soạn thảo yêu thích.  
- **Aspose.BarCode for Java** – tải thư viện từ trang chính **[ở đây](https://releases.aspose.com/barcode/java/)** và thêm file JAR vào classpath của dự án.

## Nhập khẩu các gói

Khi đã tham chiếu thư viện, nhập lớp cốt lõi điều khiển việc tạo mã vạch.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hướng dẫn từng bước

### Bước 1: Xác định thư mục tài liệu của bạn

Đặt thư mục nơi hình ảnh được tạo sẽ được lưu.

```java
String dataDir = "Your Document Directory";
```

### Bước 2: Tạo đối tượng Barcode Generator

Khởi tạo `BarcodeGenerator` với **codetext** và **symbology** mong muốn. Ở đây chúng ta **tạo mã ean13** bằng chuỗi số `"123456789123"`.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Bước 3: Đặt dữ liệu bổ sung

Thêm một chuỗi bổ sung 5 chữ số. Điều này hữu ích cho tạp chí, báo cáo, hoặc bất kỳ trường hợp nào có thông tin phụ đi kèm sau mã vạch chính.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Bước 4: Đặt khoảng cách bổ sung

Điều chỉnh khoảng cách giữa mã vạch chính và phần bổ sung. Giá trị được biểu thị bằng điểm.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Bước 5: Lưu hình ảnh mã vạch

Cuối cùng, ghi hình ảnh ra đĩa. Định dạng được suy ra từ phần mở rộng file (JPEG trong ví dụ này).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Mẹo chuyên nghiệp:** Bạn có thể thay đổi phần mở rộng file thành `.png` hoặc `.bmp` để nhận được định dạng ảnh khác mà không cần thêm mã.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|-----------|
| **Không lưu được hình ảnh** | `dataDir` trỏ tới thư mục không tồn tại | Đảm bảo thư mục tồn tại hoặc tạo nó bằng mã (`new File(dataDir).mkdirs();`). |
| **Độ dài bổ sung không hợp lệ** | Bổ sung EAN‑13 phải có 2 hoặc 5 chữ số | Cung cấp đúng 2 hoặc 5 ký tự; nếu không sẽ ném ngoại lệ. |
| **Ký tự không được hỗ trợ** | Có ký tự không phải số trong codetext EAN‑13 | Chỉ dùng các chữ số 0‑9 cho EAN‑13; chuyển sang biểu tượng khác nếu cần ký tự alphanumerics. |

## Câu hỏi thường gặp

### Aspose.BarCode có tương thích với mọi phiên bản Java không?
Aspose.BarCode for Java được thiết kế để tương thích với nhiều phiên bản Java. Tham khảo **[tài liệu](https://reference.aspose.com/barcode/java/)** để biết chi tiết.

### Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Có, Aspose.BarCode cung cấp nhiều tham số và cài đặt để tùy chỉnh giao diện mã vạch. Khám phá tài liệu để biết thông tin chi tiết.

### Có phiên bản dùng thử không?
Có, bạn có thể tải phiên bản dùng thử miễn phí **[ở đây](https://releases.aspose.com/)**.

### Làm sao tôi có thể nhận hỗ trợ cho Aspose.BarCode?
Truy cập **[diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13)** để nhận trợ giúp từ cộng đồng và các chuyên gia.

### Tôi có thể mua Aspose.BarCode for Java ở đâu?
Bạn có thể mua Aspose.BarCode for Java **[ở đây](https://purchase.aspose.com/buy)**.

---

**Cập nhật lần cuối:** 2025-12-17  
**Đã kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}