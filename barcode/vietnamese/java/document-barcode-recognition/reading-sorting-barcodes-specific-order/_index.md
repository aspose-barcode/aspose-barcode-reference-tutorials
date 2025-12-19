---
date: 2025-12-19
description: Tìm hiểu cách đọc mã vạch với Aspose.BarCode cho Java, sắp xếp chúng
  theo một thứ tự cụ thể và xem ví dụ đầy đủ về phát hiện mã vạch bằng Java.
linktitle: Reading and Sorting Barcodes in Specific Order
second_title: Aspose.BarCode Java API
title: Cách Đọc Mã Vạch và Sắp Xếp Chúng Theo Thứ Tự Cụ Thể trong Java
url: /vi/java/document-barcode-recognition/reading-sorting-barcodes-specific-order/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách Đọc Mã Vạch và Sắp Xếp Chúng Theo Thứ Tự Cụ Thể trong Java

## Giới thiệu

Trong các ứng dụng Java hiện đại, **cách đọc mã vạch** một cách hiệu quả là một câu hỏi thường gặp. Dù bạn đang xử lý danh sách tồn kho, nhãn vận chuyển, hay vé sự kiện, một giải pháp mã vạch đáng tin cậy có thể tiết kiệm cho bạn hàng giờ làm việc thủ công. Trong hướng dẫn này, chúng tôi sẽ chỉ cho bạn cách đọc mã vạch và sắp xếp chúng theo một thứ tự cụ thể bằng **Aspose.BarCode for Java**. Bạn sẽ nhận được một ví dụ hoàn chỉnh, sẵn sàng chạy, thể hiện việc phát hiện mã vạch, trích xuất văn bản mã và logic sắp xếp tùy chỉnh.

## Câu trả lời nhanh
- **Thư viện nào nên sử dụng?** Aspose.BarCode for Java
- **Tôi có thể sắp xếp mã vạch sau khi đọc chúng không?** Có – chỉ cần lưu kết quả và áp dụng một comparator
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; cần giấy phép thương mại cho môi trường sản xuất
- **Phiên bản Java nào được hỗ trợ?** Java 8 trở lên
- **Đây có phải là ví dụ Java về phát hiện mã vạch không?** Chắc chắn – mã này đọc các mã vạch CODE_128 và sắp xếp chúng

## “Cách đọc mã vạch” trong Java là gì?
Đọc mã vạch có nghĩa là giải mã mẫu hình ảnh của một mã vạch thành giá trị văn bản cơ bản của nó. Aspose.BarCode cung cấp một **động cơ đọc mã vạch aspose** hiệu suất cao, hỗ trợ hàng chục loại symbology, bao gồm CODE_128, QR, DataMatrix và nhiều hơn nữa.

## Tại sao nên sử dụng Aspose.BarCode để đọc mã vạch?
- **Độ chính xác cao** – hoạt động ngay cả với hình ảnh độ phân giải thấp
- **API đơn giản** – chỉ vài dòng mã là bạn đã có được văn bản từ hình ảnh
- **Đa nền tảng** – hoạt động trên bất kỳ môi trường tương thích JVM nào
- **Hỗ trợ sắp xếp tích hợp** – bạn có thể dễ dàng kết hợp việc đọc với các collection của Java

## Yêu cầu trước

Trước khi bắt đầu với mã, hãy đảm bảo bạn đã chuẩn bị các yêu cầu sau:

- Java Development Kit (JDK): Aspose.BarCode for Java yêu cầu một JDK hoạt động. Bạn có thể tải phiên bản mới nhất [tại đây](https://www.oracle.com/java/technologies/javase-downloads.html).

- Thư viện Aspose.BarCode: Đảm bảo bạn đã có thư viện Aspose.BarCode. Bạn có thể tải nó từ [liên kết tải xuống](https://releases.aspose.com/barcode/java/).

## Nhập các gói

Bắt đầu bằng cách nhập các gói cần thiết vào dự án Java của bạn. Các gói này cung cấp các lớp và phương thức thiết yếu để làm việc với mã vạch.

```java
// Import Aspose.BarCode classes
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;

import java.awt.Point;
import java.util.ArrayList;
import java.util.Collections;
import java.util.Comparator;
import java.util.List;
```

Bây giờ, chúng ta sẽ phân tích mã theo hướng dẫn từng bước:

## Bước 1: Thiết lập Thư mục Tài nguyên

```java
// The path to the resource directory.
String dataDir = "Your Document Directory";
```

Thay thế `"Your Document Directory"` bằng đường dẫn thực tế tới thư mục tài liệu của bạn.

## Bước 2: Chỉ định Đường dẫn Hình ảnh Mã vạch và Khởi tạo Trình đọc

```java
String path = dataDir + "barcode.png";
List<FoundBarCodes> found = new ArrayList<FoundBarCodes>();

// Initialize BarCodeReader with the specified path and decode type
BarCodeReader reader = new BarCodeReader(path, DecodeType.CODE_128);
```

## Bước 3: Đọc Mã vạch và Lưu Kết quả

```java
// Iterate through barcodes and store results
for (BarCodeResult result : reader.readBarCodes()) {
    found.add(new FoundBarCodes(result.getCodeText(), result.getRegion()));
}
```

## Bước 4: Định nghĩa Comparator để Sắp xếp

```java
// Define a comparator for sorting barcodes based on code text
Comparator<FoundBarCodes> foundComparator = new Comparator<FoundBarCodes>() {
    @Override
    public int compare(FoundBarCodes e1, FoundBarCodes e2) {
        return e1.getCodeText().compareTo(e2.getCodeText());
    }
};
```

## Bước 5: Sắp xếp Mã vạch

```java
// Sort the list of barcodes using the defined comparator
found.sort(foundComparator);
```

## Bước 6: Hiển thị Mã vạch Đã sắp xếp

```java
// Display sorted barcodes with their coordinates
int i = 1;
for (FoundBarCodes barcode : found) {
    Point[] point = barcode.BarCodeRegion.getPoints();
    System.out.println("Codetext ( " + i + " ): " + barcode.CodeText);
    System.out.println("Top left coordinates: X = " + point[0].getX() + ", Y = " + point[0].getY());
    System.out.println("Bottom left coordinates: X = " + point[1].getX() + ", Y = " + point[1].getY());
    System.out.println("Bottom right coordinates: X = " + point[2].getX() + ", Y = " + point[2].getY());
    System.out.println("Top right coordinates: X = " + point[3].getX() + ", Y = " + point[3].getY());
    System.out.println();
    i++;
}
```

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|-------------|----------------|
| **Không phát hiện được mã vạch** | DecodeType không đúng hoặc hình ảnh chất lượng thấp | Xác minh hình ảnh chứa mã vạch CODE_128 và sử dụng DecodeType phù hợp. Bạn cũng có thể thử `DecodeType.ALL` để tự động phát hiện. |
| **Thứ tự sắp xếp không đúng** | Comparator so sánh chuỗi theo thứ tự từ điển | Nếu cần sắp xếp số, chuyển `CodeText` sang `int` trước khi so sánh. |
| **Lỗi null pointer trên `BarCodeRegion`** | Đường dẫn hình ảnh sai hoặc tệp không tồn tại | Đảm bảo `path` trỏ tới tệp PNG hợp lệ và tệp có thể đọc được bởi JVM. |

## Câu hỏi thường gặp

**Q: Tôi có thể tìm tài liệu Aspose.BarCode cho Java ở đâu?**  
A: Tài liệu có sẵn [tại đây](https://reference.aspose.com/barcode/java/).

**Q: Làm sao tôi có thể tải Aspose.BarCode cho Java?**  
A: Bạn có thể tải nó từ [liên kết tải xuống](https://releases.aspose.com/barcode/java/).

**Q: Có bản dùng thử miễn phí không?**  
A: Có, bạn có thể khám phá bản dùng thử miễn phí [tại đây](https://releases.aspose.com/).

**Q: Làm sao tôi lấy thông tin giấy phép tạm thời?**  
A: Giấy phép tạm thời có thể được lấy [tại đây](https://purchase.aspose.com/temporary-license/).

**Q: Tôi có thể tìm hỗ trợ hoặc đặt câu hỏi ở đâu?**  
A: Truy cập diễn đàn hỗ trợ [tại đây](https://forum.aspose.com/c/barcode/13).

## Câu hỏi bổ sung (tối ưu AI)

**Q: Tôi có thể dùng đoạn mã này với các loại mã vạch khác không?**  
A: Chắc chắn. Thay `DecodeType.CODE_128` bằng bất kỳ symbology nào được hỗ trợ, chẳng hạn `DecodeType.QR` hoặc `DecodeType.DATA_MATRIX`.

**Q: Aspose.BarCode có hỗ trợ xử lý hàng loạt nhiều hình ảnh không?**  
A: Có. Lặp qua một tập hợp các đường dẫn tệp và tái sử dụng cùng logic `BarCodeReader` cho mỗi hình ảnh.

**Q: Làm sao tôi cải thiện hiệu năng khi làm việc với bộ ảnh lớn?**  
A: Tái sử dụng đối tượng `BarCodeReader` khi có thể và xử lý các hình ảnh song song bằng `ExecutorService` của Java.

## Kết luận

Trong hướng dẫn này, chúng tôi đã trình bày **cách đọc mã vạch** bằng Aspose.BarCode cho Java, lưu mỗi kết quả và sắp xếp danh sách theo một thứ tự tùy chỉnh. Bằng cách làm theo hướng dẫn từng bước, bạn có thể tích hợp việc phát hiện và sắp xếp mã vạch mạnh mẽ vào bất kỳ ứng dụng Java nào—dù là quản lý tồn kho, logistics, hay bán vé sự kiện.

---

**Cập nhật lần cuối:** 2025-12-19  
**Kiểm tra với:** Aspose.BarCode for Java 24.11 (phiên bản mới nhất tại thời điểm viết)  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}