---
date: 2025-12-19
description: Tìm hiểu cách đọc mã vạch Java từ các tệp PDF bằng Aspose.BarCode. Hướng
  dẫn từng bước này cho thấy cách tạo hình ảnh mã vạch và giải mã chúng một cách hiệu
  quả.
linktitle: Recognizing Barcodes from PDF
second_title: Aspose.BarCode Java API
title: Đọc Mã Vạch Java – Nhận Dạng Mã Vạch Từ PDF
url: /vi/java/document-barcode-recognition/recognizing-barcodes-from-pdf/
weight: 11
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Read Barcode Java – Nhận Dạng Mã Vạch Từ PDF

## Giới thiệu

Chào mừng bạn đến với hướng dẫn từng bước của chúng tôi về **cách đọc barcode java** từ các tệp PDF bằng Aspose.BarCode for Java. Mã vạch đóng vai trò quan trọng trong quản lý và tổ chức dữ liệu, và với Aspose.BarCode quá trình này trở nên liền mạch. Trong tutorial này, chúng tôi sẽ hướng dẫn bạn mọi thứ cần thiết — từ việc thiết lập các yêu cầu trước đến tạo hình ảnh mã vạch, thêm nó vào PDF, chuyển PDF thành hình ảnh, và cuối cùng giải mã hình ảnh mã vạch.

## Câu trả lời nhanh
- **Nội dung của tutorial này là gì?** Tạo hình ảnh mã vạch, nhúng nó vào PDF, trích xuất hình ảnh và đọc lại mã vạch.  
- **Thư viện nào được yêu cầu?** Aspose.BarCode for Java (với Aspose.PDF để xử lý PDF).  
- **Tôi có cần giấy phép không?** Có – cần giấy phép Aspose.BarCode và giấy phép Aspose.PDF cho việc sử dụng trong môi trường sản xuất.  
- **Tôi có thể sử dụng các loại mã vạch khác không?** Chắc chắn – API hỗ trợ nhiều loại symbology; ví dụ này sử dụng CODE‑39.  
- **Thời gian triển khai mất bao lâu?** Khoảng 10‑15 phút cho một quy trình cơ bản từ đầu đến cuối.

## **read barcode java** là gì?

Đọc mã vạch trong Java có nghĩa là trích xuất dữ liệu được mã hoá từ một hình ảnh hoặc tài liệu bằng thư viện nhận dạng mã vạch. Aspose.BarCode cung cấp một API đơn giản giúp giải mã mà không cần công cụ bên ngoài.

## Tại sao nên sử dụng Aspose.BarCode for Java?

- **All‑in‑one solution** – tạo, nhúng và giải mã mã vạch với một duy nhất.  
- **High accuracy** – hỗ trợ các symbology 1D, 2D và bưu chính.  
- **No external dependencies** – hoạt động với các dự án Java thuần.  
- **Robust PDF support** – tích hợp chặt chẽ với Aspose.PDF để thao tác PDF liền mạch.

## Yêu cầu trước

1. **Aspose.BarCode for Java License** – Nhận và thiết lập giấy phép hợp lệ cho Aspose.BarCode for Java. Bạn có thể mua giấy phép tại [Aspose Purchase](https://purchase.aspose.com/buy).

2. **Aspose.PDF License** – Ngoài ra, thiết lập giấy phép cho Aspose.PDF, cần thiết để làm việc với các tệp PDF. Bạn có thể đăng ký giấy phép [tại đây](https://purchase.aspose.com/temporary-license/).

3. **Download Aspose.BarCode for Java** – Tải thư viện Aspose.BarCode từ [here](https://releases.aspose.com/barcode/java/).

Bây giờ bạn đã có các yêu cầu cần thiết, hãy tiến hành nhập các gói cần thiết và bắt đầu tutorial.

## Nhập các gói

Trong dự án Java của bạn, bao gồm các gói Aspose.BarCode và Aspose.PDF. Dưới đây là một đoạn mã mẫu để bạn bắt đầu:

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

## Cách đọc barcode java từ PDF

Dưới đây là quy trình hoàn chỉnh từ đầu đến cuối. Mỗi bước được giải thích bằng ngôn ngữ đơn giản, và mã nguồn kèm theo không thay đổi so với tutorial gốc.

### Bước 1: Tạo mã vạch và thêm vào PDF

Đầu tiên, chúng ta **tạo một hình ảnh mã vạch** bằng `BarcodeGenerator`. Hình ảnh này sẽ được nhúng vào tài liệu PDF sau.

```java
BarcodeGenerator builder = new BarcodeGenerator(com.aspose.barcode.EncodeTypes.CODE_39_STANDARD);
builder.setCodeText("test123");
String strBarCodeImageSave = dataDir + "input_image1.jpg";
builder.save(strBarCodeImageSave);
```

### Bước 2: Tạo PDF và Thêm Hình Ảnh Mã Vạch

Tiếp theo, chúng ta **thêm hình ảnh mã vạch đã tạo vào một PDF mới** (tức là *add barcode pdf*). Điều này minh họa cách nhúng hình ảnh trực tiếp vào một trang PDF.

```java
Document pdf1 = new Document();
Page page = pdf1.getPages().add();
BufferedImage originalImage = ImageIO.read(new File(strBarCodeImageSave));
page.getResources().getImages().add(originalImage);
pdf1.save(strPdfDoc);
```

### Bước 3: Trích xuất hình ảnh từ PDF

Để **chuyển PDF thành hình ảnh**, chúng ta sử dụng `PdfExtractor`. Bước này lấy hình ảnh mã vạch đã nhúng ra khỏi PDF để có thể giải mã.

```java
PdfExtractor extractor = new PdfExtractor();
extractor.bindPdf(strPdfDoc);
extractor.extractImage();
```

### Bước 4: Nhận dạng mã vạch từ các hình ảnh đã trích xuất

Cuối cùng, chúng ta **giải mã hình ảnh mã vạch** (tức là *decode barcode image*) bằng `BarCodeReader`. Vòng lặp xử lý mỗi hình ảnh đã trích xuất và in ra văn bản và symbology đã giải mã.

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

Lặp lại các bước này khi cần, điều chỉnh tên tệp và đường dẫn cho phù hợp.

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Giải pháp |
|-------|----------|
| **Không tìm thấy giấy phép** | Đảm bảo cả giấy phép Aspose.BarCode và Aspose.PDF đều được tải đúng cách trước khi gọi bất kỳ API nào. |
| **Không có hình ảnh nào được trích xuất** | Xác minh rằng PDF thực sự chứa hình ảnh và `extractImage()` được gọi sau khi liên kết PDF. |
| **Loại mã vạch không đúng** | Sử dụng `DecodeType` phù hợp với symbology bạn đã tạo (ví dụ, `CODE_39_EXTENDED`). |
| **Vấn đề về đường dẫn tệp** | Sử dụng đường dẫn tuyệt đối hoặc đảm bảo thư mục làm việc được đặt tới thư mục chứa tài nguyên của bạn. |

## Câu hỏi thường gặp (FAQs)

### Q: Tôi có thể sử dụng Aspose.BarCode for Java mà không có giấy phép không?
Mặc dù Aspose.BarCode có thể được sử dụng mà không có giấy phép, nhưng nên mua giấy phép để có đầy đủ chức năng và tuân thủ điều khoản giấy phép.

### Q: Làm thế nào tôi có thể nhận giấy phép tạm thời cho Aspose.BarCode for Java?
Bạn có thể nhận giấy phép tạm thời [tại đây](https://purchase.aspose.com/temporary-license/).

### Q: Có bất kỳ hạn chế nào về các loại mã vạch được Aspose.BarCode hỗ trợ không?
Aspose.BarCode hỗ trợ nhiều loại mã vạch. Tham khảo tài liệu để biết danh sách đầy đủ.

### Q: Có phiên bản dùng thử cho Aspose.BarCode for Java không?
Có, bạn có thể tải phiên bản dùng thử [tại đây](https://releases.aspose.com/).

### Q: Tôi có thể tìm hỗ trợ hoặc đặt câu hỏi về Aspose.BarCode cho Java ở đâu?
Truy cập diễn đàn Aspose.BarCode [tại đây](https://forum.aspose.com/c/barcode/13) để được hỗ trợ và thảo luận.

**Câu hỏi nhanh bổ sung**

**Q: Tôi có thể đọc mã vạch từ PDF được bảo mật bằng mật khẩu không?**  
A: Có – tải PDF với mật khẩu phù hợp bằng Aspose.PDF trước khi trích xuất.

**Q: Phương pháp này có hoạt động với các symbology mã vạch khác không?**  
A: Chắc chắn. Thay đổi `EncodeTypes` và `DecodeType` để phù hợp với symbology mong muốn.

## Kết luận

Chúc mừng! Bạn đã học cách **đọc barcode java** từ các tệp PDF bằng Aspose.BarCode for Java. Tutorial này đã bao gồm việc tạo hình ảnh mã vạch, nhúng nó vào PDF, chuyển PDF thành hình ảnh và giải mã hình ảnh mã vạch — tất cả đều được trình bày bằng mã rõ ràng, từng bước. Hãy khám phá thêm các tính năng và chức năng khác mà Aspose.BarCode cung cấp trong [tài liệu](https://reference.aspose.com/barcode/java/).

**Cập nhật lần cuối:** 2025-12-19  
**Kiểm thử với:** Aspose.BarCode for Java 24.11, Aspose.PDF for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}