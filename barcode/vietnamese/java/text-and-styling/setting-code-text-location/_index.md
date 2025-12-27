---
date: 2025-12-27
description: Tìm hiểu cách tạo mã vạch Data Matrix và cách đặt vị trí văn bản mã vạch
  trong Java bằng Aspose.BarCode. Hãy theo dõi hướng dẫn từng bước của chúng tôi để
  tùy chỉnh đầy đủ.
linktitle: Setting Code Text Location
second_title: Aspose.BarCode Java API
title: Tạo mã Data Matrix và đặt vị trí văn bản mã trong Java
url: /vi/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch Data Matrix và đặt vị trí văn bản mã trong Java

## Giới thiệu

Việc tạo mã vạch là một yêu cầu thường xuyên cho quản lý tồn kho, vận chuyển và nhiều ứng dụng khác dựa trên Java. Với **Aspose.BarCode for Java** bạn có thể **tạo mã vạch Data Matrix** nhanh chóng và kiểm soát mọi khía cạnh hình ảnh, bao gồm vị trí hiển thị văn bản có thể đọc được bởi con người. Trong hướng dẫn này, chúng tôi sẽ hướng dẫn chi tiết các bước để **tạo mã vạch Data Matrix** và minh họa **cách đặt văn bản mã** phía trên ký hiệu để phù hợp với các yêu cầu thiết kế của bạn.

## Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.BarCode for Java  
- **Loại mã vạch nào được minh họa?** Data Matrix  
- **Bạn đặt văn bản mã ở vị trí nào?** Sử dụng `CodeLocation.ABOVE`  
- **Bạn có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại  
- **Mã có thể chạy trên Java 8+ không?** Chắc chắn, nó hỗ trợ Java 8 và các phiên bản sau  

## Data Matrix là gì?
Mã vạch Data Matrix là một ký hiệu hai chiều (2‑D) lưu trữ lượng lớn dữ liệu trong một mẫu vuông hoặc hình chữ nhật gọn gàng. Nó được sử dụng rộng rãi để đánh dấu các vật phẩm nhỏ, thiết bị điện tử và thiết bị y tế vì có thể mã hoá tới 2.335 ký tự chữ và số.

## Tại sao cần đặt vị trí văn bản mã?
Đặt văn bản có thể đọc được bởi con người **phía trên**, **phía dưới**, hoặc **bên cạnh** mã vạch giúp người dùng nhanh chóng xác minh dữ liệu đã mã hoá mà không cần quét. Điều chỉnh vị trí văn bản cải thiện tính nhất quán giao diện người dùng và đáp ứng các hướng dẫn thương hiệu.

## Điều kiện tiên quyết

- Kiến thức cơ bản về lập trình Java.  
- Java Development Kit (JDK) đã được cài đặt.  
- Một IDE như Eclipse hoặc IntelliJ IDEA.  
- Thư viện Aspose.BarCode for Java (tải xuống từ [here](https://releases.aspose.com/barcode/java/)).  

## Nhập các gói

Đầu tiên, nhập các lớp Aspose.BarCode cần thiết vào dự án của bạn:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Các import này cho phép bạn truy cập vào trình tạo mã vạch và enumeration điều khiển vị trí văn bản.

## Hướng dẫn từng bước

### Bước 1: Xác định Đường dẫn Thư mục
Xác định nơi bạn muốn đọc/ghi các tệp. Thay thế các placeholder bằng các đường dẫn thực tế trên máy của bạn.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Bước 2: Tạo một thể hiện BarcodeGenerator
Tạo một thể hiện `BarcodeGenerator` với loại **Data Matrix** và cung cấp văn bản mã mà bạn muốn mã hoá.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Bước 3: Cách đặt vị trí văn bản mã
Sử dụng enumeration `CodeLocation` để di chuyển văn bản có thể đọc được bởi con người. Trong ví dụ này, chúng tôi đặt nó **phía trên** mã vạch.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

### Bước 4: Lưu hình ảnh Mã vạch Đã tạo
Cuối cùng, ghi hình ảnh mã vạch ra đĩa. Tệp sẽ chứa ký hiệu Data Matrix với văn bản được đặt phía trên.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Các vấn đề thường gặp và giải pháp
- **Văn bản không hiển thị:** Đảm bảo bạn đang sử dụng phiên bản Aspose.BarCode hỗ trợ `CodeLocation`.  
- **Lỗi đường dẫn tệp:** Kiểm tra `dataDir` kết thúc bằng dấu phân tách tệp (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Ký tự không được hỗ trợ:** Data Matrix chỉ có thể mã hoá một tập ký tự giới hạn; tránh các ký hiệu đặc biệt không có trong tiêu chuẩn ISO/IEC 16022.  

## Câu hỏi thường gặp (FAQs)

### H: Tôi có thể tùy chỉnh giao diện của mã vạch đã tạo không?
Đ: Có, Aspose.BarCode cung cấp các tùy chọn tùy chỉnh phong phú, cho phép bạn kiểm soát màu sắc, lề và kiểu phông chữ.

### H: Aspose.BarCode có tương thích với Java 8 và các phiên bản sau không?
Đ: Chắc chắn, thư viện hoạt động với Java 8 và tất cả các phiên bản tiếp theo.

### H: Làm thế nào tôi có thể tích hợp Aspose.BarCode vào dự án Java hiện có của mình?
Đ: Thêm các tệp JAR của Aspose.BarCode vào classpath của dự án, nhập các gói cần thiết, và bạn đã sẵn sàng tạo mã vạch.

### H: Có phiên bản dùng thử cho Aspose.BarCode không?
Đ: Có, bạn có thể khám phá các khả năng của Aspose.BarCode bằng cách nhận bản dùng thử miễn phí [here](https://releases.aspose.com/).

### H: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ cho Aspose.BarCode ở đâu?
Đ: Truy cập [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) để nhận hỗ trợ cộng đồng và hỗ trợ chính thức.

## Các câu hỏi thường gặp bổ sung

**H: Tôi có thể tạo mã vạch với văn bản đặt phía dưới ký hiệu không?**  
Đ: Có, đặt `CodeLocation.BELOW` trong cùng phương thức `setLocation`.

**H: Thư viện có hỗ trợ các mã vạch 2‑D khác như QR Code không?**  
Đ: Chắc chắn, chỉ cần thay đổi `EncodeTypes.DATA_MATRIX` thành `EncodeTypes.QR`.

**H: Làm thế nào để thay đổi kích thước phông chữ của văn bản mã vạch?**  
Đ: Sử dụng `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Kết luận

Bạn đã học cách **tạo mã vạch Data Matrix** trong Java và kiểm soát chính xác **cách đặt vị trí văn bản mã vạch** bằng Aspose.BarCode. Hãy thử nghiệm các giá trị `CodeLocation` khác và các tùy chọn kiểu dáng để phù hợp với yêu cầu thiết kế của ứng dụng của bạn.

---

**Cập nhật lần cuối:** 2025-12-27  
**Kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}