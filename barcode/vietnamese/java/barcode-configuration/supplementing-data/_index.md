---
date: 2026-08-28
description: Tìm hiểu cách thêm dữ liệu phụ vào mã vạch trong Java bằng Aspose.BarCode.
  Hướng dẫn này trình bày ví dụ tạo mã vạch bằng Java cho việc tạo mã vạch động và
  EAN‑13 với dữ liệu phụ.
keywords:
- how to add supplement
- barcode generator example java
- how to generate barcode java
- dynamic barcode generation java
lastmod: 2026-08-28
linktitle: Thêm Dữ liệu Phụ
og_description: Tìm hiểu cách thêm dữ liệu phụ vào mã vạch trong Java bằng Aspose.BarCode.
  Bài hướng dẫn này cung cấp ví dụ tạo mã vạch bằng Java, các bước tạo mã vạch động
  và cách tạo mã vạch EAN‑13 với dữ liệu phụ.
og_image_alt: 'Developer guide: Adding supplement to Java barcode using Aspose.BarCode'
og_title: Cách thêm dữ liệu phụ khi tạo mã vạch trong Java
schemas:
- author: Aspose
  dateModified: '2026-08-28'
  description: Learn how to add supplement to barcodes in Java using Aspose.BarCode.
    This guide shows a barcode generator example Java for dynamic barcode generation
    and EAN‑13 with supplemental data.
  headline: How to add supplement when generating barcode in Java
  type: TechArticle
- description: Learn how to add supplement to barcodes in Java using Aspose.BarCode.
    This guide shows a barcode generator example Java for dynamic barcode generation
    and EAN‑13 with supplemental data.
  name: How to add supplement when generating barcode in Java
  steps:
  - name: define your document directory
    text: Set the folder where the generated image will be stored.
  - name: create barcode generator instance
    text: '`BarcodeGenerator` is Aspose.BarCode''s core object that creates barcode
      images from supplied data. Instantiate it with the desired **codetext** and
      **symbology**. Here we **create an EAN‑13 barcode** using the numeric string
      `"123456789123"`.'
  - name: set supplement data
    text: Add a 5‑digit supplemental string. This is useful for magazines, periodicals,
      or any case where extra information follows the main barcode.
  - name: set supplement space
    text: Adjust the gap between the main barcode and its supplement. The value is
      expressed in points.
  - name: save the barcode image
    text: Finally, write the image to disk. The format is inferred from the file extension
      (JPEG in this example). > **Pro tip:** You can change the file extension to
      `.png` or `.bmp` to get a different image format without extra code.
  type: HowTo
- questions:
  - answer: Aspose.BarCode for Java.
    question: What library is best for generating barcodes in Java?
  - answer: EAN‑13.
    question: Which symbology creates a 13‑digit numeric barcode?
  - answer: Yes, using the `Supplement` API.
    question: Can I add supplemental data to an EAN‑13 barcode?
  - answer: Call `generator.save("path/filename.jpg")`.
    question: How do I save the generated barcode as an image?
  - answer: Yes, a commercial license is needed; a free trial is available.
    question: Is a license required for production use?
  type: FAQPage
second_title: Aspose.BarCode Java API
tags:
- barcode supplement
- Aspose.BarCode
- Java barcode generation
- EAN-13
title: Cách thêm dữ liệu phụ khi tạo mã vạch trong Java
url: /vi/java/barcode-configuration/supplementing-data/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thêm phần bổ sung khi tạo mã vạch trong Java

## Giới thiệu

Trong hệ sinh thái kỹ thuật số đang phát triển nhanh ngày nay, nhiều nhà phát triển Java tự hỏi **cách thêm phần bổ sung** vào mã vạch một cách hiệu quả. Aspose.BarCode for Java cung cấp một API mạnh mẽ, dễ sử dụng, hỗ trợ **tạo mã vạch động**, bao gồm việc tạo **mã vạch EAN‑13** với dữ liệu bổ sung. Dù bạn đang xây dựng hệ thống quản lý tồn kho, ứng dụng POS bán lẻ, hay theo dõi logistics, hướng dẫn này sẽ dẫn bạn qua một **ví dụ tạo mã vạch Java** lưu hình ảnh mã vạch vào đĩa và cho phép bạn tùy chỉnh phần bổ sung.

## Câu trả lời nhanh
- **Thư viện nào là tốt nhất để tạo mã vạch trong Java?** Aspose.BarCode for Java.  
- **Biểu tượng nào tạo mã vạch số 13 chữ số?** EAN‑13.  
- **Tôi có thể thêm dữ liệu bổ sung vào mã vạch EAN‑13 không?** Có, sử dụng API `Supplement`.  
- **Làm thế nào để lưu mã vạch đã tạo dưới dạng hình ảnh?** Gọi `generator.save("path/filename.jpg")`.  
- **Cần giấy phép cho việc sử dụng trong môi trường sản xuất không?** Có, cần giấy phép thương mại; một bản dùng thử miễn phí có sẵn.

## Tạo mã vạch Java là gì?

Tạo mã vạch có nghĩa là chuyển đổi dữ liệu thô—số, chữ hoặc hỗn hợp—thành một mẫu hình ảnh mà máy quét có thể đọc được. Aspose.BarCode có thể tạo **hình ảnh mã vạch độ phân giải cao** ngay lập tức, làm cho nó trở nên lý tưởng cho các kịch bản **tạo mã vạch động trong Java** như bán vé thời gian thực, thực hiện đơn hàng, hoặc tạo nhãn nhanh. Khả năng này loại bỏ nhu cầu lưu trữ các tài nguyên hình ảnh đã tạo sẵn và cho phép bạn kiểm soát hoàn toàn kích thước, định dạng và giao diện.

## Tại sao nên sử dụng Aspose.BarCode cho Java?

Aspose.BarCode hỗ trợ **hơn 30 loại mã vạch** và có thể tạo hình ảnh lên tới **10.000 × 10.000 px** mà không cần tải toàn bộ tệp vào bộ nhớ, cho phép môi trường xử lý tốc độ cao. Thư viện hoạt động trên bất kỳ môi trường Java 8+ nào, chạy trên Windows, Linux và macOS, và cung cấp một API duy nhất cho cả đầu ra raster (PNG, JPEG, BMP) và vector (SVG, PDF).

## Yêu cầu trước

- **Java Development Kit (JDK)** – bất kỳ phiên bản mới nào (8 trở lên).  
- **IDE** – IntelliJ IDEA, Eclipse, hoặc trình chỉnh sửa yêu thích của bạn.  
- **Aspose.BarCode for Java** – tải thư viện từ trang chính thức **[Aspose.BarCode for Java download](https://releases.aspose.com/barcode/java/)** và thêm JAR vào classpath của dự án.

## Nhập các gói

Sau khi thư viện đã được tham chiếu, nhập lớp cốt lõi điều khiển việc tạo mã vạch.

```java
// Import Aspose.BarCode for Java
import com.aspose.barcode.generation.BarcodeGenerator;
```

## Hướng dẫn từng bước

### Bước 1: xác định thư mục tài liệu của bạn

Đặt thư mục nơi hình ảnh được tạo sẽ được lưu.

```java
String dataDir = "Your Document Directory";
```

### Bước 2: tạo thể hiện barcode generator

`BarcodeGenerator` là đối tượng cốt lõi của Aspose.BarCode tạo hình ảnh mã vạch từ dữ liệu cung cấp. Khởi tạo nó với **codetext** và **symbology** mong muốn. Ở đây chúng ta **tạo một mã vạch EAN‑13** bằng chuỗi số `"123456789123"`.

```java
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.EAN_13, "123456789123");
```

### Bước 3: thiết lập dữ liệu bổ sung

Thêm một chuỗi bổ sung 5 chữ số. Điều này hữu ích cho tạp chí, ấn phẩm định kỳ, hoặc bất kỳ trường hợp nào thông tin bổ sung xuất hiện sau mã vạch chính.

```java
generator.getParameters().getBarcode().getSupplement().setSupplementData("12345");
```

### Bước 4: thiết lập khoảng cách bổ sung

Điều chỉnh khoảng cách giữa mã vạch chính và phần bổ sung. Giá trị được biểu thị bằng điểm.

```java
generator.getParameters().getBarcode().getSupplement().getSupplementSpace().setPoint(2.0f);
```

### Bước 5: lưu hình ảnh mã vạch

Cuối cùng, ghi hình ảnh ra đĩa. Định dạng được suy ra từ phần mở rộng tệp (JPEG trong ví dụ này).

```java
generator.save(dataDir + "supplementData.jpg");
```

> **Mẹo chuyên nghiệp:** Bạn có thể thay đổi phần mở rộng tệp thành `.png` hoặc `.bmp` để nhận được định dạng hình ảnh khác mà không cần thêm mã.

## Cách tạo mã vạch EAN‑13 với dữ liệu bổ sung?

Tải `BarcodeGenerator` với mã EAN‑13, gọi `setSupplement()` để gắn các chữ số bổ sung, tùy chọn điều chỉnh `setSupplementSpace()`, sau đó gọi `save()` để ghi hình ảnh. Quy trình bốn bước này tạo ra một mã vạch tuân thủ tiêu chuẩn mà máy quét đọc đúng, trong khi các chữ số bổ sung xuất hiện như một nhóm thanh nhỏ hơn ở phía bên phải của mã chính.

## Các trường hợp sử dụng phổ biến cho tạo mã vạch động trong Java

- **Quản lý tồn kho bán lẻ:** Tạo mã vạch sản phẩm theo yêu cầu khi có SKU mới được thêm.  
- **Xuất bản:** Gắn số phát hành làm dữ liệu bổ sung vào mã vạch các ấn phẩm định kỳ.  
- **Logistics:** Tạo nhãn vận chuyển với mã vạch nhanh bao gồm số lô hoặc batch.  

## Các vấn đề thường gặp và giải pháp

| Vấn đề | Nguyên nhân | Giải pháp |
|-------|-------------|----------|
| **Hình ảnh không được lưu** | `dataDir` trỏ tới thư mục không tồn tại | Đảm bảo thư mục tồn tại hoặc tạo nó bằng chương trình (`new File(dataDir).mkdirs();`). |
| **Độ dài bổ sung không hợp lệ** | Bổ sung EAN‑13 phải có 2 hoặc 5 chữ số | Cung cấp đúng 2 hoặc 5 ký tự; nếu không sẽ ném ngoại lệ. |
| **Ký tự không được hỗ trợ** | Có ký tự không phải số trong codetext EAN‑13 | Chỉ sử dụng các chữ số 0‑9 cho EAN‑13; chuyển sang biểu tượng khác cho dữ liệu alphanumerics. |

## Câu hỏi thường gặp

### Aspose.BarCode có tương thích với tất cả các phiên bản Java không?

Aspose.BarCode cho Java được thiết kế để hoạt động với Java 8 đến Java 21, bao gồm cả các phiên bản LTS và các bản phát hành mới nhất. **[tài liệu chính thức](https://reference.aspose.com/barcode/java/)** liệt kê các phiên bản được hỗ trợ chính xác.

### Tôi có thể tùy chỉnh giao diện của các mã vạch được tạo không?

Có, Aspose.BarCode cung cấp các tùy chọn định dạng phong phú như màu nền/màu chữ, kiểu phông chữ cho văn bản có thể đọc được, độ rộng thanh và cài đặt lề. Bạn cũng có thể nhúng mã vạch vào PDF, tài liệu Word hoặc trang HTML bằng cùng một API.

### Có phiên bản dùng thử không?

Một phiên bản dùng thử miễn phí có sẵn **[trang tải thử Aspose](https://releases.aspose.com/)**. Bản dùng thử bao gồm tất cả các tính năng nhưng sẽ thêm một watermark nhỏ vào các hình ảnh được tạo.

### Làm sao tôi có thể nhận hỗ trợ cho Aspose.BarCode?

Truy cập **[diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13)** để nhận sự trợ giúp từ cộng đồng và các chuyên gia sản phẩm. Hỗ trợ cao cấp cũng được cung cấp kèm theo giấy phép thương mại.

### Tôi có thể mua Aspose.BarCode cho Java ở đâu?

Bạn có thể mua giấy phép **[trang mua Aspose](https://purchase.aspose.com/buy)**. Giấy phép có sẵn dưới dạng vĩnh viễn hoặc thuê bao, với các tùy chọn cho nhà phát triển, nhóm và doanh nghiệp.

## Câu hỏi bổ sung (định dạng thân thiện AI)

**Q:** Cách dễ nhất để bắt đầu một **ví dụ tạo mã vạch Java** là gì?  
**A:** Thêm JAR Aspose.BarCode vào dự án của bạn, nhập `BarcodeGenerator`, và làm theo hướng dẫn từng bước ở trên để tạo và lưu một mã vạch EAN‑13 với dữ liệu bổ sung.

**Q:** Tôi có thể tạo nhiều mã vạch trong một vòng lặp để xử lý hàng loạt không?  
**A:** Chắc chắn. Khởi tạo một `BarcodeGenerator` mới trong vòng lặp, đặt `codetext` duy nhất cho mỗi lần lặp, và gọi `save()` với tên tệp khác nhau.

**Q:** API có hỗ trợ các định dạng hình ảnh khác như PNG hoặc SVG không?  
**A:** Có. Định dạng đầu ra được suy ra từ phần mở rộng tệp bạn cung cấp (ví dụ: `.png`, `.svg`). Không cần mã bổ sung.

**Q:** Làm sao tôi xử lý khối lượng lớn mà không tiêu tốn quá nhiều bộ nhớ?  
**A:** Tạo và lưu mỗi mã vạch ngay lập tức, sau đó hủy thể hiện generator trước vòng lặp tiếp theo. Điều này giữ mức sử dụng bộ nhớ thấp ngay cả khi xử lý hàng ngàn hình ảnh.

**Q:** Có cách nào để nhúng mã vạch trực tiếp vào PDF không?  
**A:** Lấy mã vạch dưới dạng `byte[]` bằng cách sử dụng `generator.generateBarCodeImage()` và chèn nó vào PDF với Aspose.PDF hoặc bất kỳ thư viện PDF nào khác.

**Cập nhật lần cuối:** 2026-08-28  
**Đã kiểm tra với:** Aspose.BarCode for Java 24.11  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo mã vạch Java – Hướng dẫn cấu hình đầy đủ](/barcode/java/barcode-configuration/)
- [Áp dụng kiểm tra checksum Java – Hướng dẫn Aspose.BarCode](/barcode/java/checksum-and-validation/applying-checksum-validation/)
- [Cách thêm chú thích vào mã vạch trong Java bằng Aspose.Barcode Java](/barcode/java/text-and-styling/adding-caption-barcode/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}