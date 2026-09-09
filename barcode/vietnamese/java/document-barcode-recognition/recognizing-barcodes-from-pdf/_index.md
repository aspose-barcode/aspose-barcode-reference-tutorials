---
date: 2026-04-08
description: Tìm hiểu cách đọc mã vạch từ PDF trong Java bằng Aspose.BarCode. Hướng
  dẫn này cũng chỉ cách tạo hình ảnh mã vạch trong Java và trích xuất hình ảnh từ
  PDF trong Java.
keywords:
- read barcode from pdf java
- generate barcode image java
- extract images from pdf java
linktitle: Nhận dạng mã vạch từ PDF
second_title: Aspose.BarCode Java API
title: Cách đọc mã vạch từ PDF trong Java bằng Aspose.BarCode
url: /vi/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# đọc mã vạch từ PDF Java

## Giới thiệu

Chào mừng bạn đến với hướng dẫn **cách đọc mã vạch từ PDF trong Java** bằng Aspose.BarCode. Mã vạch là yếu tố quan trọng để tự động thu thập dữ liệu, và với Aspose.BarCode bạn có thể phát hiện chúng một cách liền mạch trong tài liệu PDF. Trong tutorial này chúng tôi sẽ hướng dẫn bạn mọi thứ cần thiết — từ cài đặt giấy phép đến tạo hình ảnh mã vạch Java, thêm nó vào PDF, trích xuất hình ảnh từ PDF Java, và cuối cùng là đọc lại mã vạch.

## Câu trả lời nhanh
- **Thư viện tôi cần là gì?** Aspose.BarCode for Java (plus Aspose.PDF for PDF handling).  
- **Tôi có thể tạo hình ảnh mã vạch trong Java không?** Có – the `BarcodeGenerator` class lets you create PNG/JPEG images.  
- **Làm thế nào để trích xuất hình ảnh từ PDF?** Use `PdfExtractor` from Aspose.PDF.  
- **Loại mã vạch nào được minh họa?** CODE‑39 (standard).  
- **Tôi có cần giấy phép không?** A valid Aspose.BarCode and Aspose.PDF license is required for production use.

## Tại sao nên sử dụng Aspose.BarCode cho Java?
- **Độ chính xác cao** – supports dozens of symbologies and works on low‑resolution images.  
- **Không phụ thuộc bên ngoài** – pure Java, no native libraries.  
- **Tích hợp PDF đầy đủ** – combine with Aspose.PDF to read or embed barcodes directly in PDF files.

## Yêu cầu trước

Trước khi bắt đầu viết mã, hãy chắc chắn rằng bạn đã có:

1. **Giấy phép Aspose.BarCode cho Java** – lấy tại [Aspose Purchase](https://purchase.aspose.com/buy).  
2. **Giấy phép Aspose.PDF** – cần cho việc thao tác PDF; bạn có thể đăng ký giấy phép [tại đây](https://purchase.aspose.com/temporary-license/).  
3. **Thư viện Aspose.BarCode** – tải xuống JAR mới nhất từ [tại đây](https://releases.aspose.com/barcode/java/).  

Bây giờ bạn đã có các yêu cầu cần thiết, hãy nhập các gói cần thiết và bắt đầu viết mã.

## Nhập gói

Trong dự án Java của bạn, thêm các import của Aspose.BarCode và Aspose.PDF. Khối này không thay đổi so với hướng dẫn gốc:

```java
import com.aspose.barcode.*;
import com.aspose.barcode.License;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.BaseDecodeType;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.pdf.*;
import com.aspose.pdf.facades.PdfExtractor;
import java.awt.image.BufferedImage;
import java.io.File;
import javax.imageio.ImageIO;
```

## Bước 1: Tạo hình ảnh mã vạch Java

Đầu tiên, chúng ta tạo một hình ảnh mã vạch mà sau này sẽ chèn vào PDF. Điều này minh họa khả năng **tạo hình ảnh mã vạch java**.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

## Bước 2: Tạo PDF và thêm hình ảnh mã vạch

Tiếp theo, chúng ta tạo một tài liệu PDF mới và chèn hình ảnh mã vạch vừa tạo.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

## Bước 3: Trích xuất hình ảnh từ PDF Java

Với PDF đã sẵn sàng, chúng ta cần lấy lại hình ảnh đã nhúng để có thể đọc mã vạch. Điều này sử dụng **trích xuất hình ảnh từ pdf java**.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

## Bước 4: Nhận dạng mã vạch từ các hình ảnh đã trích xuất

Cuối cùng, chúng ta đưa mỗi hình ảnh đã trích xuất vào `BarCodeReader` để lấy văn bản đã mã hoá.

```java
String suffix = ".jpg";
int imageCount = 1;

while (extractor.hasNextImage()) {
    System.out.println("Extracting image " + imageCount);
    strBarCodeImage = "tmpbarcode" + imageCount + suffix;
    extractor.getNextImage(strBarCodeImage);

    BarCodeReader reader = new BarCodeReader(strBarCodeImage, DecodeType.CODE_39_EXTENDED);

    for (BarCodeResult result : reader.readBarCodes()) {
        System.out.println("CodeText: " + result.getCodeText());
        System.out.println("Symbology type: " + result.getCodeType());
    }

    imageCount++;
}
```

Lặp lại các bước này khi cần, điều chỉnh tên tệp và đường dẫn cho phù hợp với cấu trúc dự án của bạn.

## Vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|--------|-----|
| **Không phát hiện mã vạch** | Chất lượng hình ảnh quá thấp hoặc mã vạch quá nhỏ. | Tăng độ phân giải hình ảnh khi lưu (`builder.save(..., BarCodeImageFormat.JPEG, 300)`). |
| **`PdfExtractor` gây ra ngoại lệ** | Không tìm thấy tệp PDF hoặc đường dẫn không đúng. | Xác minh `strPdfDoc` trỏ tới tệp tồn tại và ứng dụng có quyền đọc. |
| **Giấy phép chưa được áp dụng** | Các thành phần Aspose chạy ở chế độ dùng thử, giới hạn đầu ra. | Tải các tệp giấy phép ở đầu chương trình: `new License().setLicense("Aspose.BarCode.lic");` và tương tự cho Aspose.PDF. |

## Câu hỏi thường gặp (FAQs)

### Q: Tôi có thể sử dụng Aspose.BarCode cho Java mà không có giấy phép không?
Mặc dù Aspose.BarCode có thể được sử dụng mà không có giấy phép, nhưng nên có giấy phép để có đầy đủ chức năng và tuân thủ các điều khoản giấy phép.

### Q: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.BarCode cho Java?
Bạn có thể đăng ký giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Q: Có bất kỳ hạn chế nào đối với các loại mã vạch mà Aspose.BarCode hỗ trợ không?
Aspose.BarCode hỗ trợ nhiều loại mã vạch. Tham khảo tài liệu để biết danh sách đầy đủ.

### Q: Có phiên bản dùng thử cho Aspose.BarCode cho Java không?
Có, bạn có thể tải phiên bản dùng thử từ [tại đây](https://releases.aspose.com/).

### Q: Tôi có thể tìm hỗ trợ hoặc đặt câu hỏi về Aspose.BarCode cho Java ở đâu?
Truy cập diễn đàn Aspose.BarCode [forum](https://forum.aspose.com/c/barcode/13) để được hỗ trợ và thảo luận.

## Kết luận

Chúc mừng! Bạn đã học cách **đọc mã vạch từ PDF trong Java** bằng Aspose.BarCode, cách **tạo hình ảnh mã vạch Java**, và cách **trích xuất hình ảnh từ PDF Java** để xử lý tiếp. Hãy tự do khám phá các tính năng bổ sung như xử lý hàng loạt, xử lý các loại mã vạch khác nhau, hoặc tích hợp với các sản phẩm Aspose khác. Để biết chi tiết hơn, xem [tài liệu](https://reference.aspose.com/barcode/java/).

---

**Cập nhật lần cuối:** 2026-04-08  
**Kiểm tra với:** Aspose.BarCode for Java 24.12, Aspose.PDF for Java 24.12  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}