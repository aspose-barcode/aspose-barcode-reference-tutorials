---
date: 2026-09-08
description: Tìm hiểu cách tạo mã vạch code 128 và tạo mã vạch GS1 trong C# với Aspose.BarCode
  cho .NET. Hướng dẫn chi tiết từng bước, các yêu cầu trước, và tùy chỉnh không cần
  viết mã.
keywords:
- create code 128 barcode
- generate gs1 barcode
- how to generate barcode
- create barcode from data
- step by step barcode
lastmod: 2026-09-08
linktitle: Ví dụ GS1 Code 128
og_description: Tìm hiểu cách tạo mã vạch code 128 và tạo mã vạch GS1 trong C# với
  Aspose.BarCode cho .NET. Thực hiện theo hướng dẫn chi tiết từng bước để nhanh chóng
  tạo và lưu hình ảnh mã vạch.
og_image_alt: 'Developer guide: create code 128 barcode with Aspose.BarCode .NET'
og_title: Cách tạo mã vạch code 128 với GS1 bằng Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-09-08'
  description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  headline: How to create code 128 barcode with GS1 using Aspose.BarCode
  type: TechArticle
- description: Learn how to create code 128 barcode and generate GS1 barcodes in C#
    with Aspose.BarCode for .NET. Step‑by‑step guide, prerequisites, and code‑free
    customization.
  name: How to create code 128 barcode with GS1 using Aspose.BarCode
  steps:
  - name: set your directory path
    text: Define the folder where the generated image will be stored. Keeping the
      path configurable makes the code reusable across environments. Replace `"Your
      Directory Path"` with an absolute or relative path that your application can
      write to, such as `@"C:\Barcodes"` or `Path.Combine(Environment.CurrentDi
  - name: create a GS1 Code 128 barcode
    text: Create the barcode generator, specify the symbology, and provide GS1‑formatted
      data. The data string must include Application Identifiers wrapped in parentheses.
      The example uses the GTIN `(01)12345678901231`, a serial number `(21)ASPOSE`,
      and an additional custom AI `(30)9876`. Aspose.BarCode autom
  - name: customize barcode parameters
    text: Adjust visual parameters such as `XDimension` (the width of the narrow bar)
      to control the barcode’s density. You can also modify height, colors, and margins.
      Setting `XDimension = 2` yields a barcode that is easily scannable by most handheld
      readers while keeping the image size modest.
  - name: save the barcode image
    text: Persist the generated barcode to disk. You may choose PNG for lossless quality,
      JPEG for smaller files, or TIFF for printing workflows. The `Save` method writes
      the image file in the format indicated by the file extension. Replace `GS1Code128Example.png`
      with any valid filename and extension that ma
  - name: verify the barcode (optional)
    text: After saving, you can load the image back into your application or use a
      barcode scanner to confirm that the encoded data matches the original string.
      This step is useful during development and automated testing.
  type: HowTo
- questions:
  - answer: Yes, Aspose.BarCode works with .NET Core and .NET 5/6, so you can expose
      a lightweight REST endpoint that returns barcode images on demand.
    question: Can I generate barcodes in a web API without installing the full .NET
      Framework?
  - answer: Absolutely. Loop through a collection of data strings, instantiate a `BarcodeGenerator`
      for each, and call `Save` inside the loop. The library is thread‑safe for parallel
      processing.
    question: Does the library support batch generation of multiple barcodes?
  - answer: Use Aspose.PDF to create a PDF document, then call `PdfPage.AddImage`
      with the barcode image stream. This avoids writing intermediate files to disk.
    question: Is there a way to embed the barcode directly into a PDF?
  - answer: Set `BarcodeGenerator.Options.Barcode.XDimension` to at least 0.33 mm
      and enable `BarHeight` according to the label size. Aspose.BarCode validates
      the AI format and throws an exception for invalid data.
    question: How can I ensure the barcode meets ISO/GS1 quality standards?
  - answer: Aspose offers perpetual, subscription, and cloud‑based licensing models.
      A trial license works for evaluation, but a paid license removes the evaluation
      watermark and unlocks all features.
    question: What licensing options are available for production use?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- create code 128 barcode
- Aspose.BarCode
- .NET barcode generation
title: Cách tạo mã vạch code 128 với GS1 bằng Aspose.BarCode
url: /vi/net/gs1-barcode-encoding/gs1-code-128-example/
weight: 10
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch code 128 với GS1 bằng Aspose.BarCode

Trong tutorial này, bạn sẽ học cách **tạo mã vạch code 128** tuân thủ tiêu chuẩn GS1 bằng thư viện Aspose.BarCode cho .NET. Cho dù bạn cần mã vạch cho quản lý tồn kho, vận chuyển, hoặc điểm bán hàng, hướng dẫn này sẽ dẫn bạn qua mọi bước — từ thiết lập môi trường phát triển đến lưu ảnh cuối cùng — để bạn có thể bắt đầu tạo mã vạch đáng tin cậy trong vài phút.

## Câu trả lời nhanh
- **Lớp chính để tạo mã vạch là gì?** `BarcodeGenerator` tạo và cấu hình hình ảnh mã vạch.  
- **Biểu tượng nào mà GS1 Code 128 sử dụng?** Nó sử dụng kiểu `EncodeTypes.Code128` với định dạng dữ liệu đặc thù cho GS1.  
- **Tôi có cần giấy phép cho việc phát triển không?** Bản dùng thử miễn phí đủ cho việc đánh giá; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể thay đổi định dạng ảnh không?** Có — lưu dưới dạng PNG, JPEG, BMP, hoặc TIFF bằng cách thay đổi phần mở rộng tập tin.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5+, và .NET 6+.

## Tạo mã vạch code 128 là gì?
`create code 128 barcode` đề cập đến việc tạo một mã vạch tuyến tính mã hoá dữ liệu alphanumeric bằng biểu tượng Code 128, được áp dụng rộng rãi trong logistics vì nó hỗ trợ toàn bộ bộ ký tự ASCII và có thể nhúng các Application Identifier của GS1. Mã vạch có thể lưu trữ các định danh sản phẩm, số sê-ri và các dữ liệu tùy chỉnh khác, phù hợp cho nhiều kịch bản kinh doanh.

## Tại sao nên sử dụng Aspose.BarCode cho GS1 Code 128?
Aspose.BarCode hỗ trợ **hơn 30 biểu tượng mã vạch** và có thể tạo ảnh lên tới **10.000 × 10.000 px** mà không mất chất lượng, phù hợp cho việc in nhãn độ phân giải cao. Thư viện cũng tự động xác thực cấu trúc dữ liệu GS1, giảm nguy cơ mã vạch sai định dạng trong dây chuyền sản xuất. Ngoài ra, nó cung cấp các tùy chọn tùy chỉnh rộng rãi cho kích thước, màu sắc và bố cục, giúp đáp ứng các tiêu chuẩn khắt khe của ngành.

## Yêu cầu trước
1. **Môi trường phát triển .NET** – Visual Studio 2022, Rider, hoặc bất kỳ IDE nào hỗ trợ .NET 6+.  
2. **Aspose.BarCode cho .NET** – tải xuống từ **trang tải Aspose.BarCode cho .NET** tại [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/) và thêm gói NuGet `Aspose.BarCode` vào dự án của bạn.  
3. **Kiến thức cơ bản về C#** – bạn nên quen thuộc với việc tạo các ứng dụng console hoặc Windows.  
4. **Hiểu biết về GS1 Code 128** – không bắt buộc nhưng hữu ích; GS1 sử dụng các Application Identifier (AI) như `(01)` cho GTIN và `(21)` cho số sê-ri.

## Cách tạo mã vạch code 128 từng bước

Tải thư viện, cấu hình loại mã vạch, thiết lập dữ liệu GS1, tùy chỉnh kích thước, và cuối cùng lưu ảnh. Câu trả lời trực tiếp cho câu hỏi “cách tạo mã vạch code 128?” là: **khởi tạo `BarcodeGenerator` với `EncodeTypes.Code128` và dữ liệu định dạng GS1, điều chỉnh `XDimension` nếu cần, sau đó gọi `Save` với tên tệp và định dạng mong muốn**. Các phần sau sẽ phân tích từng bước.

### Bước 1: đặt đường dẫn thư mục của bạn
Xác định thư mục nơi ảnh được tạo sẽ được lưu. Giữ đường dẫn có thể cấu hình giúp mã có thể tái sử dụng trong nhiều môi trường.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;
```

Thay thế `"Your Directory Path"` bằng một đường dẫn tuyệt đối hoặc tương đối mà ứng dụng của bạn có thể ghi vào, chẳng hạn `@"C:\Barcodes"` hoặc `Path.Combine(Environment.CurrentDirectory, "Output")`.

### Bước 2: tạo mã vạch GS1 Code 128
Tạo đối tượng barcode generator, chỉ định biểu tượng, và cung cấp dữ liệu định dạng GS1. Chuỗi dữ liệu phải bao gồm các Application Identifier được đặt trong dấu ngoặc đơn.

```csharp
string path = "Your Directory Path";
```

Ví dụ sử dụng GTIN `(01)12345678901231`, số sê-ri `(21)ASPOSE`, và một AI tùy chỉnh bổ sung `(30)9876`. Aspose.BarCode tự động chèn ký tự FNC1 cần thiết để tuân thủ GS1.

### Bước 3: tùy chỉnh tham số mã vạch
Điều chỉnh các tham số hiển thị như `XDimension` (độ rộng của thanh mảnh) để kiểm soát mật độ của mã vạch. Bạn cũng có thể thay đổi chiều cao, màu sắc và lề.

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.GS1Code128, "(01)12345678901231(21)ASPOSE(30)9876");
```

Đặt `XDimension = 2` tạo ra một mã vạch dễ dàng quét bởi hầu hết các máy đọc cầm tay trong khi giữ kích thước ảnh ở mức vừa phải.

### Bước 4: lưu ảnh mã vạch
Lưu mã vạch đã tạo vào đĩa. Bạn có thể chọn PNG để có chất lượng không mất dữ liệu, JPEG cho tệp nhỏ hơn, hoặc TIFF cho quy trình in ấn. Phương thức `Save` ghi tệp ảnh theo định dạng được chỉ định bởi phần mở rộng tệp.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
```

Thay thế `GS1Code128Example.png` bằng bất kỳ tên tệp hợp lệ và phần mở rộng nào phù hợp với định dạng đầu ra bạn muốn.

### Bước 5: xác minh mã vạch (tùy chọn)
Sau khi lưu, bạn có thể tải lại ảnh vào ứng dụng hoặc dùng máy quét mã vạch để xác nhận dữ liệu đã mã hoá khớp với chuỗi gốc. Bước này hữu ích trong quá trình phát triển và kiểm thử tự động.

```csharp
gen.Save($"{path}GS1Code128Example.png", BarCodeImageFormat.Png);
```

## Các vấn đề thường gặp và mẹo khắc phục
- **FNC1 không được phát hiện** – Đảm bảo chuỗi dữ liệu bắt đầu bằng dấu ngoặc mở và bao gồm các AI GS1 hợp lệ; thư viện chỉ tự động chèn FNC1 cho các mẫu được nhận dạng.  
- **Ảnh không được lưu** – Kiểm tra thư mục đích có tồn tại và ứng dụng có quyền ghi. Sử dụng `Directory.CreateDirectory(path)` để tạo thư mục ngay khi cần.  
- **Mã vạch quá dày** – Giảm `XDimension` hoặc tăng chiều cao ảnh để máy quét có không gian đọc các thanh mảnh hơn.  
- **Ký tự không được hỗ trợ** – Code 128 chỉ có thể mã hoá toàn bộ bộ ký tự ASCII; tránh các ký tự Unicode nằm ngoài phạm vi này.

## Câu hỏi thường gặp

**Q: Tôi có thể tạo mã vạch trong một web API mà không cài đặt đầy đủ .NET Framework không?**  
A: Có, Aspose.BarCode hoạt động với .NET Core và .NET 5/6, vì vậy bạn có thể cung cấp một endpoint REST nhẹ trả về hình ảnh mã vạch theo yêu cầu.

**Q: Thư viện có hỗ trợ tạo hàng loạt nhiều mã vạch không?**  
A: Hoàn toàn có. Duyệt qua một tập hợp các chuỗi dữ liệu, khởi tạo `BarcodeGenerator` cho mỗi chuỗi, và gọi `Save` trong vòng lặp. Thư viện an toàn với đa luồng cho việc xử lý song song.

**Q: Có cách nào để nhúng mã vạch trực tiếp vào PDF không?**  
A: Sử dụng Aspose.PDF để tạo tài liệu PDF, sau đó gọi `PdfPage.AddImage` với luồng ảnh mã vạch. Điều này tránh việc ghi các tệp trung gian lên đĩa.

**Q: Làm sao để đảm bảo mã vạch đáp ứng tiêu chuẩn chất lượng ISO/GS1?**  
A: Đặt `BarcodeGenerator.Options.Barcode.XDimension` ít nhất 0.33 mm và bật `BarHeight` phù hợp với kích thước nhãn. Aspose.BarCode xác thực định dạng AI và ném ngoại lệ nếu dữ liệu không hợp lệ.

**Q: Các tùy chọn cấp phép nào có sẵn cho việc sử dụng trong môi trường sản xuất?**  
A: Aspose cung cấp các mô hình cấp phép vĩnh viễn, thuê bao và dựa trên đám mây. Giấy phép dùng thử đủ cho việc đánh giá, nhưng giấy phép trả phí sẽ loại bỏ watermark đánh giá và mở khóa toàn bộ tính năng.

## Tài nguyên bổ sung

- **Tài liệu** – Truy cập tham chiếu API đầy đủ tại [https://reference.aspose.com/barcode/net/](https://reference.aspose.com/barcode/net/).  
- **Tải xuống** – Nhận phiên bản thư viện mới nhất từ [https://releases.aspose.com/barcode/net/](https://releases.aspose.com/barcode/net/).  
- **Dùng thử miễn phí** – Bắt đầu dùng thử 30 ngày tại [https://releases.aspose.com/](https://releases.aspose.com/).  
- **Mua** – Mua giấy phép thương mại tại [https://purchase.aspose.com/buy](https://purchase.aspose.com/buy).  
- **Hỗ trợ** – Tham gia diễn đàn cộng đồng tại [https://forum.aspose.com/c/barcode/13](https://forum.aspose.com/c/barcode/13) để được trợ giúp khắc phục sự cố.

---

**Cập nhật lần cuối:** 2026-09-08  
**Kiểm tra với:** Aspose.BarCode 24.11 cho .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo mã vạch ITF-14 .NET – Hướng dẫn toàn diện Aspose.BarCode Tutorials](/barcode/net/)
- [Tạo mã vạch Databar 2D một chiều bằng Aspose.BarCode .NET API](/barcode/net/one-dimensional-barcode-types/one-dimensional-databar-2d-component-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}