---
date: 2026-05-04
description: Tìm hiểu cách tạo mã vạch Data Matrix bằng thư viện mã vạch Java và đặt
  vị trí văn bản mã vạch phía trên biểu tượng với Aspose.BarCode. Thực hiện theo ví
  dụ tạo mã vạch từng bước của chúng tôi.
keywords:
- java barcode library
- barcode generation example
- barcode text above
- customize barcode text
linktitle: Cài đặt vị trí văn bản mã
second_title: Aspose.BarCode Java API
title: Tạo mã Data Matrix bằng Thư viện Mã vạch Java và Đặt vị trí văn bản mã
url: /vi/java/text-and-styling/setting-code-text-location/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã Vạch Data Matrix với Thư Viện Mã Vạch Java và Đặt Vị Trí Văn Bản Mã

## Giới thiệu

Nếu bạn đang xây dựng một hệ thống quản lý kho, vận chuyển hoặc theo dõi bằng Java, bạn sẽ nhanh chóng nhận ra rằng một **java barcode library** đáng tin cậy là điều cần thiết. Với **Aspose.BarCode for Java** bạn có thể tạo một **Data Matrix barcode** chỉ trong vài dòng mã và kiểm soát hoàn toàn bố cục hình ảnh, bao gồm vị trí của văn bản có thể đọc được bởi con người. Trong hướng dẫn này, chúng tôi sẽ trình bày một **barcode generation example** đầy đủ, chỉ cho bạn cách **customize barcode text** placement, và giải thích tại sao việc đặt văn bản phía trên biểu tượng có thể cải thiện khả năng sử dụng.

## Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.BarCode for Java  
- **Loại mã vạch nào được minh họa?** Data Matrix  
- **Làm thế nào để đặt vị trí văn bản mã?** Sử dụng `CodeLocation.ABOVE` (bạn cũng có thể dùng `BELOW`)  
- **Bạn có cần giấy phép cho môi trường sản xuất không?** Có, cần giấy phép thương mại  
- **Mã có chạy trên Java 8+ không?** Hoàn toàn, nó hỗ trợ Java 8 và các phiên bản sau  

## Thư viện mã vạch Java là gì?
Một **java barcode library** cung cấp cho các nhà phát triển các API đã sẵn sàng để tạo, đọc và định dạng các mã vạch 1‑D và 2‑D trực tiếp từ các ứng dụng Java. Nó trừu tượng hoá các quy tắc mã hoá phức tạp và cho phép bạn tập trung vào logic nghiệp vụ thay vì xử lý ảnh mức thấp.

## Tại sao nên sử dụng thư viện mã vạch Java cho ví dụ tạo mã vạch?
- **Tốc độ:** Tạo mã vạch chất lượng cao trong mili giây.  
- **Độ tin cậy:** Tuân thủ tích hợp các tiêu chuẩn ISO/IEC.  
- **Linh hoạt:** Kiểm soát toàn bộ kích thước, màu sắc, lề và vị trí **barcode text**.  
- **Đa nền tảng:** Hoạt động trên bất kỳ môi trường JVM nào, từ ứng dụng desktop đến dịch vụ đám mây.

## Mã vạch Data Matrix là gì?
Mã vạch Data Matrix là một biểu tượng hai chiều (2‑D) lưu trữ lượng lớn dữ liệu trong một mẫu vuông hoặc chữ nhật gọn gàng. Nó được sử dụng rộng rãi để đánh dấu các vật phẩm nhỏ, thiết bị điện tử và thiết bị y tế vì có thể mã hoá tới 2.335 ký tự chữ và số.

## Tại sao đặt vị trí văn bản mã vạch?
Việc đặt văn bản có thể đọc được **phía trên**, **phía dưới**, hoặc **bên cạnh** mã vạch giúp người dùng nhanh chóng xác minh dữ liệu đã mã hoá mà không cần quét. Điều chỉnh vị trí văn bản cải thiện tính nhất quán giao diện, đáp ứng các hướng dẫn thương hiệu, và có thể giảm lỗi khi nhập dữ liệu thủ công.

## Yêu cầu trước

- Kiến thức cơ bản về lập trình Java.  
- Java Development Kit (JDK) đã được cài đặt.  
- Một IDE như Eclipse hoặc IntelliJ IDEA.  
- Thư viện Aspose.BarCode for Java (tải xuống từ [tại đây](https://releases.aspose.com/barcode/java/)).  

## Nhập các gói

Đầu tiên, nhập các lớp Aspose.BarCode cần thiết vào dự án của bạn:

```java
import com.aspose.barcode.generation.CodeLocation;
import com.aspose.barcode.generation.BarcodeGenerator;
```

Các import này cho phép bạn truy cập vào trình tạo mã vạch và enum điều khiển vị trí văn bản.

## Hướng dẫn từng bước

### Bước 1: Xác định Đường dẫn Thư mục
Xác định nơi bạn muốn đọc/ghi các tệp. Thay thế các placeholder bằng các đường dẫn thực tế trên máy của bạn.

```java
String path = "Your Directory Path";
String dataDir = "Your Document Directory";
```

### Bước 2: Tạo một Instance của BarcodeGenerator
Khởi tạo `BarcodeGenerator` với loại **Data Matrix** và cung cấp văn bản mã mà bạn muốn mã hoá.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DATA_MATRIX,
        "GTIN:898978777776665655 " + "UID: 121212121212121212 " + "Batch:GH768 " + "Exp.Date:150923");
```

### Bước 3: Đặt vị trí văn bản mã vạch (tùy chỉnh văn bản mã vạch)
Sử dụng enum `CodeLocation` để di chuyển văn bản có thể đọc được bởi con người. Trong ví dụ này chúng tôi đặt nó **phía trên** mã vạch.

```java
generator.getParameters().getBarcode().getCodeTextParameters().setLocation(CodeLocation.ABOVE);
```

> **Mẹo chuyên nghiệp:** Để đặt văn bản **phía dưới** biểu tượng, chỉ cần thay đổi `CodeLocation.ABOVE` thành `CodeLocation.BELOW`.

### Bước 4: Lưu Ảnh Mã Vạch Được Tạo
Cuối cùng, ghi ảnh mã vạch ra đĩa. Tệp sẽ chứa biểu tượng Data Matrix với văn bản được đặt phía trên.

```java
generator.save(dataDir + "codetextAbove.png");
```

## Các vấn đề thường gặp và giải pháp
- **Văn bản không hiển thị:** Đảm bảo bạn đang sử dụng phiên bản Aspose.BarCode hỗ trợ `CodeLocation`.  
- **Lỗi đường dẫn tệp:** Kiểm tra `dataDir` kết thúc bằng dấu phân tách tệp (`/` hoặc `\\`) phù hợp với hệ điều hành của bạn.  
- **Ký tự không được hỗ trợ:** Data Matrix chỉ có thể mã hoá một tập ký tự hạn chế; tránh các ký hiệu đặc biệt không có trong tiêu chuẩn ISO/IEC 16022.  

## Câu hỏi thường gặp (FAQs)

### H: Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
A: Có, Aspose.BarCode cung cấp các tùy chọn tùy chỉnh phong phú, cho phép bạn kiểm soát màu sắc, lề và kiểu phông chữ.

### H: Aspose.BarCode có tương thích với Java 8 và các phiên bản sau không?
A: Hoàn toàn, thư viện hoạt động với Java 8 và tất cả các phiên bản tiếp theo.

### H: Làm thế nào tôi có thể tích hợp Aspose.BarCode vào dự án Java hiện có của mình?
A: Thêm các tệp JAR của Aspose.BarCode vào classpath của dự án, nhập các gói cần thiết, và bạn đã sẵn sàng tạo mã vạch.

### H: Có phiên bản dùng thử cho Aspose.BarCode không?
A: Có, bạn có thể khám phá các tính năng của Aspose.BarCode bằng cách nhận bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

### H: Tôi có thể tìm kiếm trợ giúp hoặc hỗ trợ cho Aspose.BarCode ở đâu?
A: Truy cập [Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13) để nhận hỗ trợ cộng đồng và hỗ trợ chính thức.

## Các câu hỏi thường gặp bổ sung

**H: Tôi có thể tạo mã vạch với văn bản nằm dưới biểu tượng không?**  
A: Có, đặt `CodeLocation.BELOW` trong cùng phương thức `setLocation`.

**H: Thư viện có hỗ trợ các mã vạch 2‑D khác như QR Code không?**  
A: Chắc chắn, chỉ cần thay đổi `EncodeTypes.DATA_MATRIX` thành `EncodeTypes.QR`.

**H: Làm thế nào để thay đổi kích thước phông chữ của văn bản mã vạch?**  
A: Sử dụng `generator.getParameters().getBarcode().getCodeTextParameters().setFontSize(double size)`.

## Kết luận

Bạn đã học cách **tạo một Data Matrix barcode** trong Java bằng **java barcode library** và kiểm soát chính xác **cách đặt vị trí văn bản mã vạch** với Aspose.BarCode. Hãy thử nghiệm các giá trị `CodeLocation` khác, cài đặt phông chữ và tùy chọn màu sắc để phù hợp với yêu cầu thiết kế của ứng dụng.

---

**Last Updated:** 2026-05-04  
**Tested With:** Aspose.BarCode for Java 24.11  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}