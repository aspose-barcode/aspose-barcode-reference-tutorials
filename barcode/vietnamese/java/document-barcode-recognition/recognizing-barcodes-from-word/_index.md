---
date: 2025-12-19
description: Học cách đọc mã vạch Java từ tài liệu Word bằng Aspose.BarCode. Hướng
  dẫn này bao gồm việc tạo hình ảnh mã vạch, chèn chúng vào Word và trích xuất hình
  ảnh để đọc mã vạch.
linktitle: read barcode java from Word Documents
second_title: Aspose.BarCode Java API
title: Cách đọc mã vạch Java từ tài liệu Word
url: /vi/java/document-barcode-recognition/recognizing-barcodes-from-word/
weight: 12
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc barcode java từ tài liệu Word

## Giới thiệu

Làm việc với mã vạch trong các ứng dụng Java là một nhu cầu phổ biến, đặc biệt khi các mã vạch đó được nhúng trong các tệp Microsoft Word. Trong hướng dẫn này, bạn sẽ học **cách đọc barcode java** từ một tài liệu Word bằng cách sử dụng Aspose.BarCode for Java. Chúng tôi sẽ hướng dẫn cách tạo hình ảnh mã vạch, chèn mã vạch vào tệp Word, trích xuất hình ảnh từ tài liệu Word, và cuối cùng giải mã mã vạch bằng một ví dụ trình đọc mã vạch Java.

## Câu trả lời nhanh
- **Thư viện nào được sử dụng?** Aspose.BarCode for Java (với Aspose.Words để xử lý hình ảnh)  
- **Tôi có thể thêm mã vạch vào Word không?** Có – tạo hình ảnh rồi chèn nó bằng Aspose.Words  
- **Làm thế nào để trích xuất hình ảnh từ Word?** Sử dụng `Document.getChildNodes(NodeType.SHAPE, true)`  
- **Có ví dụ trình đọc mã vạch Java không?** Mã trong Bước 3 cho thấy một ví dụ đầy đủ  
- **Các yêu cầu trước là gì?** JDK, Aspose.BarCode for Java, một IDE (Eclipse/IntelliJ)

## Nhận dạng mã vạch trong Java là gì?
Nhận dạng mã vạch trong Java đề cập đến quá trình phát hiện và giải mã các ký hiệu mã vạch từ hình ảnh hoặc tài liệu bằng một thư viện như Aspose.BarCode. Nó cho phép các ứng dụng tự động đọc mã sản phẩm, ID tồn kho, hoặc bất kỳ dữ liệu được mã hoá nào mà không cần nhập thủ công.

## Tại sao cần đọc barcode java từ tài liệu Word?
Việc nhúng mã vạch trực tiếp vào tệp Word hữu ích cho hợp đồng, nhãn vận chuyển, hoặc báo cáo nơi cần hiển thị hình ảnh của mã. Khả năng **trích xuất hình ảnh từ Word** và giải mã chúng một cách lập trình loại bỏ nhu cầu quét thủ công và giảm lỗi.

## Prerequisites

- **Java Development Kit (JDK)** – một JDK mới được cài đặt trên máy của bạn.  
- **Aspose.BarCode for Java** – tải thư viện từ trang chính thức [here](https://releases.aspose.com/barcode/java/).  
- **Integrated Development Environment (IDE)** – như Eclipse hoặc IntelliJ IDEA để viết và chạy mã.

## Nhập các gói

Trong dự án Java của bạn, nhập các gói Aspose.BarCode và Aspose.Words cần thiết:

```java
import java.text.MessageFormat;

import com.aspose.barcode.EncodeTypes;
import com.aspose.barcode.barcoderecognition.BarCodeReader;
import com.aspose.barcode.barcoderecognition.BarCodeResult;
import com.aspose.barcode.barcoderecognition.DecodeType;
import com.aspose.barcode.generation.BarcodeGenerator;
import com.aspose.words.ImageType;
import com.aspose.words.NodeCollection;
import com.aspose.words.NodeType;
```

## Bước 1: Tạo hình ảnh mã vạch (generate barcode image java)

Đầu tiên, tạo một hình ảnh mã vạch bằng Aspose.BarCode. Hình ảnh này sau này sẽ được **added barcode to word**:

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.CODE_39_STANDARD);
generator.setCodeText("test-123");
String strBarCodeImageSave = dataDir + "img.jpg";
generator.save(strBarCodeImageSave);
```

## Bước 2: Chèn hình ảnh mã vạch vào tài liệu Word (insert image into word)

Bây giờ chúng ta sẽ sử dụng Aspose.Words để **insert image into word** và lưu tài liệu:

```java
Document doc = new Document();
DocumentBuilder docBuilder = new DocumentBuilder(doc);
docBuilder.insertImage(strBarCodeImageSave);
String strWordFile = "docout.doc";
doc.save(dataDir + strWordFile);
```

## Bước 3: Nhận dạng mã vạch từ tài liệu Word (java barcode reader example)

Cuối cùng, trích xuất mỗi hình ảnh từ tệp Word và chạy **java barcode reader example** để giải mã mã vạch:

```java
NodeCollection<Shape> shapes = doc.getChildNodes(NodeType.SHAPE, true);
int imageIndex = 0;

for (Shape shape : shapes) {
    if (shape.hasImage()) {
        // Extract image to file
        String extension = ImageTypeToExtension(shape.getImageData().getImageType());
        String imageFileName = MessageFormat.format("Image.ExportImages.{0} Out.{1}", imageIndex, extension);
        String strBarCodeImageExtracted = "" + imageFileName;
        shape.getImageData().save(strBarCodeImageExtracted);

        // Recognize barcode from this image
        BarCodeReader reader = new BarCodeReader(strBarCodeImageSave, DecodeType.CODE_39_STANDARD);
        for (BarCodeResult result : reader.readBarCodes()) {
            System.out.println("CodeText: " + result.getCodeText());
            System.out.println("Symbology type: " + result.getCodeType());
        }
        imageIndex++;
    }
}
```

> **Lưu ý:** Vòng lặp trên minh họa **trích xuất hình ảnh từ word**, lưu mỗi hình ảnh, và sau đó giải mã mã vạch bằng cùng một đường dẫn tệp hình ảnh. Điều chỉnh các đường dẫn tệp (`dataDir`) cho phù hợp với môi trường của bạn.

## Các vấn đề thường gặp & Mẹo

- **Không khớp đường dẫn tệp** – Đảm bảo `dataDir` trỏ tới một thư mục hợp lệ; nếu không, trình đọc sẽ ném `FileNotFoundException`.  
- **Loại mã vạch không được hỗ trợ** – Ví dụ sử dụng `CODE_39_STANDARD`. Nếu bạn cần QR, DataMatrix, v.v., hãy thay đổi cả `EncodeTypes` và `DecodeType` cho phù hợp.  
- **Hiệu năng** – Đối với tài liệu lớn, cân nhắc xử lý hình ảnh trong các luồng song song để tăng tốc độ nhận dạng.

## Câu hỏi thường gặp (FAQs)

### Q: Can I use Aspose.BarCode for Java in commercial projects?
Có, Aspose.BarCode for Java có sẵn cho việc sử dụng thương mại. Bạn có thể tìm chi tiết giấy phép [here](https://purchase.aspose.com/buy).

### Q: Is there a free trial available for Aspose.BarCode for Java?
Có, bạn có thể khám phá các tính năng của Aspose.BarCode for Java bằng cách tải bản dùng thử miễn phí [here](https://releases.aspose.com/).

### Q: How do I get support for Aspose.BarCode for Java?
Đối với bất kỳ hỗ trợ hoặc câu hỏi nào, hãy truy cập diễn đàn Aspose.BarCode [here](https://forum.aspose.com/c/barcode/13).

### Q: Are temporary licenses available for Aspose.BarCode for Java?
Có, bạn có thể nhận giấy phép tạm thời [here](https://purchase.aspose.com/temporary-license/).

### Q: Where can I find the documentation for Aspose.BarCode for Java?
Tham khảo tài liệu đầy đủ [here](https://reference.aspose.com/barcode/java/).

## Additional FAQs

**Q: Can I read other barcode symbologies besides Code 39?**  
A: Chắc chắn. Chỉ cần thay đổi `EncodeTypes` khi tạo và `DecodeType` khi đọc để phù hợp với ký hiệu mong muốn (ví dụ, `EncodeTypes.QR`, `DecodeType.QR`).

**Q: Does this approach work with .docx files as well?**  
A: Có. Aspose.Words xử lý cả định dạng `.doc` và `.docx` một cách trong suốt; cùng một đoạn mã hoạt động cho cả hai.

**Q: How can I improve recognition accuracy for low‑resolution images?**  
A: Tăng DPI khi lưu hình ảnh mã vạch (`generator.save(strBarCodeImageSave, BarCodeImageFormat.JPEG, 300)`) hoặc sử dụng định dạng hình ảnh chất lượng cao hơn như PNG.

---

**Last Updated:** 2025-12-19  
**Được kiểm tra với:** Aspose.BarCode for Java 24.11 và Aspose.Words for Java 24.11  
**Tác giả:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}