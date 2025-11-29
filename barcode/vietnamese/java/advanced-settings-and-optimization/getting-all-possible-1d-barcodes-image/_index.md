---
date: 2025-11-29
description: Tìm hiểu cách đọc mã vạch 1D trong Java với Aspose.BarCode – giải mã
  mã vạch từ hình ảnh nhanh chóng bằng thư viện mã vạch mạnh mẽ cho Java.
language: vi
linktitle: read 1d barcodes java
second_title: Aspose.BarCode Java API
title: Cách đọc mã vạch 1D trong Java bằng Aspose.BarCode
url: /java/advanced-settings-and-optimization/getting-all-possible-1d-barcodes-image/
weight: 20
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# đọc mã vạch 1d java với Aspose.BarCode

## Giới thiệu

Trong hướng dẫn thực hành này, bạn sẽ khám phá cách **đọc mã vạch 1D trong Java** bằng thư viện mạnh mẽ **Aspose.BarCode**. Cho dù bạn cần quét nhãn sản phẩm, thẻ tồn kho, hoặc bất kỳ mã vạch tuyến tính nào được nhúng trong hình ảnh, tutorial này sẽ hướng dẫn bạn từng bước — từ việc thiết lập môi trường đến việc trích xuất mọi mã vạch có thể có trong hình ảnh. Khi hoàn thành, bạn sẽ có thể **giải mã mã vạch từ các tệp hình ảnh** chỉ với vài dòng mã Java.

## Trả lời nhanh
- **Aspose.BarCode làm gì?** Nó cung cấp một thư viện mã vạch đầy đủ tính năng cho Java có thể tạo và giải mã mã vạch 1D/2D.  
- **Tôi có thể đọc nhiều mã vạch từ một hình ảnh không?** Có – phương thức `BarCodeReader.readBarCodes()` trả về tất cả các ký hiệu được phát hiện.  
- **Tôi có cần giấy phép cho việc phát triển không?** Giấy phép tạm thời hoạt động cho việc thử nghiệm; giấy phép thương mại là bắt buộc cho môi trường sản xuất.  
- **Các phiên bản Java nào được hỗ trợ?** Java 8 + (khuyến nghị JDK 11).  
- **Thư viện này có đủ nhanh cho việc quét thời gian thực không?** Hoàn toàn – nó được tối ưu cho xử lý hàng loạt hiệu suất cao.

## “đọc mã vạch 1d java” là gì?

Đọc mã vạch 1D trong Java có nghĩa là sử dụng **thư viện mã vạch cho Java** để phân tích một hình ảnh, xác định các mẫu mã vạch tuyến tính, và trả về văn bản đã mã hoá cùng với siêu dữ liệu như loại symbology và hướng. Aspose.BarCode trừu tượng hoá công việc xử lý ảnh nặng, cho phép bạn tập trung vào logic nghiệp vụ.

## Tại sao chọn Aspose.BarCode để giải mã mã vạch từ hình ảnh?

- **Hỗ trợ symbology rộng** – hơn 50 loại 1D và 2D.  
- **Phát hiện chính xác** – hoạt động ngay cả với mã vạch có độ tương phản thấp hoặc bị quay.  
- **API đơn giản** – một vài lời gọi phương thức sẽ cho bạn tất cả kết quả.  
- **Không phụ thuộc bên ngoài** – thuần Java, dễ nhúng vào bất kỳ dự án nào.  

## Yêu cầu trước

Trước khi chúng ta bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

- **Java Development Kit (JDK)** – phiên bản 8 trở lên. Tải về từ trang [Oracle JDK chính thức](https://www.oracle.com/java/technologies/javase-downloads.html).  
- **Aspose.BarCode for Java** – tải JAR mới nhất từ [trang phát hành Aspose](https://releases.aspose.com/barcode/java/).  

Khi môi trường đã sẵn sàng, chúng ta bắt đầu viết code.

## Nhập khẩu các namespace

Thêm các câu lệnh `import` cần thiết để trình biên dịch có thể tìm thấy các lớp của Aspose.

```java
import java.awt.Point;

import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
```

## Bước 1: Khởi tạo đối tượng BarCodeReader

Tạo một thể hiện `BarCodeReader` trỏ tới tệp hình ảnh của bạn. Tham số `DecodeType` cho engine biết nên tìm kiếm symbology nào; sử dụng `CODE_128` làm ví dụ sẽ hoạt động cho nhiều mã 1D phổ biến.

```java
BarCodeReader reader = new BarCodeReader("path/to/your/image.png", DecodeType.CODE_128);
```

> **Mẹo chuyên nghiệp:** Nếu bạn muốn quét *tất cả* các loại 1D được hỗ trợ, hãy truyền `DecodeType.ALL_1D` thay vì một symbology duy nhất.

## Bước 2: Đọc tất cả các mã vạch có thể

Duyệt qua bộ sưu tập trả về bởi `readBarCodes()`. Đối với mỗi `BarCodeResult` chúng ta in ra văn bản đã giải mã, tên symbology, góc phát hiện, và bốn tọa độ góc của vùng mã vạch.

```java
int iCount = 0;
for (BarCodeResult result : reader.readBarCodes()) {
    // Display code text, symbology, detected angle, recognition percentage of the barcode
    System.out.println("Code Text: " + result.getCodeText() + " Symbology: " + result.getCodeTypeName()
            + " Recognition percentage: " + result.getRegion().getAngle());

    // Display x and y coordinates of barcode detected
    Point[] point = result.getRegion().getPoints();

    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());

    iCount = iCount + 1;
}
```

Vòng lặp tự động xử lý mọi mã vạch được tìm thấy, vì vậy bạn không cần gọi lại reader nhiều lần. Khi vòng lặp kết thúc, `iCount` sẽ chứa tổng số mã vạch đã phát hiện.

## Các vấn đề thường gặp & Cách khắc phục

| Triệu chứng | Nguyên nhân khả dĩ | Giải pháp |
|------------|--------------------|-----------|
| Không có mã vạch nào được trả về | Hình ảnh quá mờ hoặc độ tương phản thấp | Tiền xử lý hình ảnh (tăng độ tương phản, nhị phân hoá) trước khi đưa vào reader. |
| Symbology báo sai | Đã dùng `DecodeType` không phù hợp | Dùng `DecodeType.ALL_1D` để cho engine tự động phát hiện bất kỳ loại 1D nào. |
| Giá trị góc sai | Hình ảnh bị quay | API đã trả về góc quay; bạn có thể quay lại hình ảnh nếu cần. |

## Câu hỏi thường gặp

**H: Aspose.BarCode for Java có phù hợp cho dự án thương mại không?**  
Đ: Có. Giấy phép thương mại loại bỏ mọi hạn chế đánh giá và cho phép bạn phân phối lại hoàn toàn.

**H: Tôi có thể thử thư viện mà không mua giấy phép không?**  
Đ: Chắc chắn. Lấy giấy phép tạm thời từ [trang giấy phép tạm thời của Aspose](https://purchase.aspose.com/temporary-license/) để phát triển và thử nghiệm.

**H: Tôi có thể tìm tài liệu API đầy đủ ở đâu?**  
Đ: Tài liệu chi tiết có sẵn [tại đây](https://reference.aspose.com/barcode/java/).

**H: Nếu gặp vấn đề, tôi nên tìm trợ giúp ở đâu?**  
Đ: Đăng câu hỏi trên [diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13) để cộng đồng và kỹ sư Aspose hỗ trợ.

**H: Có bản tải thử miễn phí không?**  
Đ: Có – bạn có thể tải phiên bản dùng thử từ [trang phát hành Aspose](https://releases.aspose.com/).

## Kết luận

Bạn đã học cách **đọc mã vạch 1D trong Java** bằng Aspose.BarCode, một **thư viện mã vạch cho Java** mạnh mẽ giúp việc giải mã mã vạch từ các tệp hình ảnh trở nên đơn giản và đáng tin cậy. Hãy tích hợp đoạn mã này vào ứng dụng của bạn để tự động hoá việc quét tồn kho, xác thực vé, hoặc bất kỳ kịch bản nào có mã vạch tuyến tính trong hình ảnh.

---

**Cập nhật lần cuối:** 2025-11-29  
**Đã kiểm tra với:** Aspose.BarCode 24.11 for Java  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}