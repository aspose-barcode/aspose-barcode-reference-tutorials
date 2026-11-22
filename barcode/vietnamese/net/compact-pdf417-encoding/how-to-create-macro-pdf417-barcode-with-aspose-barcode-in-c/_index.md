---
category: general
date: 2026-11-20
description: Tìm hiểu cách tạo mã vạch macro PDF417 trong C# bằng Aspose.BarCode.
  Hướng dẫn này bao gồm siêu dữ liệu, các tham số và việc lưu hình ảnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create macro PDF417 barcode
- macro PDF417 metadata
- Aspose.BarCode C#
- PDF417 macro parameters
- barcode generator example
language: vi
lastmod: 2026-11-20
og_description: Tạo mã vạch macro PDF417 trong C# với Aspose.BarCode. Thực hiện theo
  hướng dẫn đầy đủ này để thiết lập siêu dữ liệu, cấu hình các tham số và xuất ra
  PNG.
og_image_alt: Screenshot of a generated macro PDF417 barcode image
og_title: Tạo mã vạch macro PDF417 trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-11-20'
  description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  headline: How to create macro PDF417 barcode with Aspose.BarCode in C#
  type: TechArticle
- description: Learn how to create macro PDF417 barcode in C# using Aspose.BarCode.
    This guide covers metadata, parameters, and saving the image.
  name: How to create macro PDF417 barcode with Aspose.BarCode in C#
  steps:
  - name: Expected output
    text: 'Running the program prints a confirmation line similar to:'
  - name: What if I need more than 20 segments?
    text: The `MacroPdf417SegmentsCount` property can be set up to `255`. Ensure the
      receiving system can handle the larger segment count, and consider splitting
      the data into a manageable number of symbols.
  - name: How does the checksum affect scanning?
    text: The CCITT‑16 checksum (`MacroPdf417Checksum`) provides an additional error‑checking
      layer. If a scanner detects a mismatch, it will reject the barcode. You can
      omit the checksum if your workflow does not require it.
  - name: Can I generate a PDF417 macro barcode without Aspose?
    text: Yes, other libraries (e.g., ZXing.Net, Dynamsoft) support PDF417, but macro‑specific
      fields are often missing. Aspose.BarCode offers the most complete implementation
      for macro metadata.
  - name: What image formats are supported for saving?
    text: The `Save` method accepts any format defined in `BarCodeImageFormat`, such
      as `Png`, `Jpeg`, `Gif`, `Bmp`, and `Tiff`. Choose a format that matches your
      downstream processing pipeline.
  type: HowTo
tags:
- barcode
- PDF417
- C#
- Aspose
title: Cách tạo mã vạch macro PDF417 bằng Aspose.BarCode trong C#
url: /vi/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-with-aspose-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo macro PDF417 barcode với Aspose.BarCode trong C#

Nếu bạn cần **tạo macro PDF417 barcode** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn các bước chính xác. Bạn sẽ thấy cách cấu hình siêu dữ liệu đặc thù cho macro, điều chỉnh các thiết lập hiển thị, và lưu kết quả dưới dạng tệp PNG.

Việc tạo macro PDF417 barcode hữu ích khi bạn muốn chia một tập dữ liệu lớn thành nhiều ký hiệu đồng thời giữ lại một định danh toàn tệp. Trong ví dụ dưới đây, chúng ta sử dụng thư viện Aspose.BarCode, cung cấp một API linh hoạt cho tất cả các tính năng của PDF417.

Kết thúc hướng dẫn này, bạn sẽ có một chương trình console sẵn sàng chạy, tạo ra hình ảnh mã vạch chứa đầy đủ thông tin macro.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt.
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#).
* Gói NuGet **Aspose.BarCode for .NET** (`Aspose.BarCode`).

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Khởi tạo trình tạo mã vạch cho macro PDF417

Bước đầu tiên là tạo một đối tượng `BarcodeGenerator` với giá trị enum `EncodeTypes.MacroPdf417`. Điều này thông báo cho thư viện xử lý mã vạch như một ký hiệu macro PDF417.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
           EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // The generator is now ready for further configuration.
```

*Why this matters*: Selecting `MacroPdf417` enables all macro‑related properties on the `Pdf417` parameter object.

## Bước 2: Đặt giao diện hiển thị cơ bản

Một mã vạch dễ đọc bắt đầu bằng kích thước mô-đun và số cột phù hợp. Thuộc tính `XDimension.Pixels` điều khiển độ rộng của một mô-đun, trong khi `Pdf417.Columns` xác định số cột dữ liệu mỗi hàng chứa.

```csharp
    // Set module width to 2 pixels.
    barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

    // Use 5 columns per row – a compact layout for this example.
    barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;
```

Việc điều chỉnh các giá trị này ảnh hưởng đến độ tin cậy của máy quét và kích thước hình ảnh.

## Bước 3: Định nghĩa chi tiết nhận dạng tệp macro

Macro PDF417 yêu cầu một định danh tệp, một định danh đoạn, và tổng số đoạn. Ba trường này cho phép máy quét ghép lại tập dữ liệu gốc.

```csharp
    // Unique file identifier for the whole macro file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;

    // Identifier of the current segment (starting at 0 or 1 based on your protocol).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;

    // Total number of segments that compose the complete file.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;

    // Optional human‑readable file name.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
```

Các **macro PDF417 parameters** này là cốt lõi của chức năng macro. Không có chúng, máy quét không thể liên kết các ký hiệu lại với nhau.

## Bước 4: Thêm siêu dữ liệu macro tùy chọn

Ngoài các định danh bắt buộc, định dạng macro hỗ trợ các trường bổ sung như checksum, kích thước tệp, dấu thời gian, người nhận, người gửi, và cờ kết thúc. Cung cấp dữ liệu này cải thiện việc phát hiện lỗi và cung cấp ngữ cảnh cho các hệ thống hạ nguồn.

```csharp
    // CCITT‑16 checksum example.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;

    // Approximate file size in bytes (helps the receiver allocate buffers).
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;

    // Timestamp of when the macro file was generated.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);

    // Optional address fields.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";

    // Terminator indicates that this is the final segment.
    barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

*Pro tip*: If your workflow does not need a particular field, you can leave it at its default value. The library will omit the corresponding data element from the barcode.

## Bước 5: Lưu hình ảnh mã vạch

Sau khi cấu hình tất cả các tham số, gọi `Save` để xuất mã vạch. Ví dụ lưu tệp PNG vào thư mục do người dùng chỉ định.

```csharp
    // Replace with a valid folder on your machine.
    string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";

    // Save as PNG – other formats (Jpeg, Gif, etc.) are also supported.
    barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
}
```

Khi chương trình kết thúc, `ExtPDF417Meta.png` chứa một macro PDF417 barcode mã hoá văn bản `"Åspóse.Barcóde©"` cùng với tất cả macro metadata.

## Mã nguồn đầy đủ

Dưới đây là chương trình hoàn chỉnh, độc lập. Sao chép nó vào một dự án console mới và chạy sau khi đã cài đặt gói NuGet Aspose.BarCode.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Step 1: Create a macro PDF417 barcode generator.
            using (BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
                       EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Step 2: Visual appearance.
                barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
                barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 5;

                // Step 3: Core macro identifiers.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Step 4: Optional macro metadata.
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                barcodeGenerator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Step 5: Export the image.
                string outputPath = "YOUR_DIRECTORY/ExtPDF417Meta.png";
                barcodeGenerator.Save(outputPath, BarCodeImageFormat.Png);
                Console.WriteLine($"Macro PDF417 barcode saved to {outputPath}");
            }
        }
    }
}
```

### Kết quả mong đợi

Chạy chương trình sẽ in ra một dòng xác nhận tương tự như:

```
Macro PDF417 barcode saved to YOUR_DIRECTORY/ExtPDF417Meta.png
```

Mở tệp PNG sẽ hiển thị một mã vạch dày đặc, độ tương phản cao. Quét nó bằng máy quét hỗ trợ PDF417 sẽ trả về văn bản gốc cùng với tất cả các trường macro.

## Câu hỏi thường gặp và các trường hợp đặc biệt

### Nếu tôi cần hơn 20 đoạn thì sao?

Thuộc tính `MacroPdf417SegmentsCount` có thể được đặt lên tới `255`. Đảm bảo hệ thống nhận có thể xử lý số đoạn lớn hơn, và cân nhắc chia dữ liệu thành số lượng ký hiệu có thể quản lý được.

### Kiểm tra checksum ảnh hưởng như thế nào đến việc quét?

Checksum CCITT‑16 (`MacroPdf417Checksum`) cung cấp một lớp kiểm tra lỗi bổ sung. Nếu máy quét phát hiện sự không khớp, nó sẽ từ chối mã vạch. Bạn có thể bỏ qua checksum nếu quy trình của bạn không yêu cầu.

### Tôi có thể tạo PDF417 macro barcode mà không dùng Aspose không?

Có, các thư viện khác (ví dụ: ZXing.Net, Dynamsoft) hỗ trợ PDF417, nhưng thường thiếu các trường đặc thù cho macro. Aspose.BarCode cung cấp triển khai đầy đủ nhất cho macro metadata.

### Các định dạng hình ảnh nào được hỗ trợ khi lưu?

Phương thức `Save` chấp nhận bất kỳ định dạng nào được định nghĩa trong `BarCodeImageFormat`, như `Png`, `Jpeg`, `Gif`, `Bmp`, và `Tiff`. Chọn định dạng phù hợp với quy trình xử lý hạ nguồn của bạn.

## Kết luận

Bây giờ bạn đã biết cách **tạo macro PDF417 barcode** trong C# bằng Aspose.BarCode. Hướng dẫn đã bao gồm việc khởi tạo trình tạo, các thiết lập hiển thị, định danh tệp macro, siêu dữ liệu tùy chọn và xuất hình ảnh. Với nền tảng này, bạn có thể nhúng macro PDFs trong hệ thống tồn kho, theo dõi tài liệu, hoặc bất kỳ kịch bản nào yêu cầu truyền dữ liệu phân đoạn.

Các bước tiếp theo bao gồm thử nghiệm các giá trị `XDimension` khác nhau để có độ phân giải cao hơn, thêm điều chỉnh mức độ sửa lỗi, hoặc tích hợp mã vạch vào một web API trả về luồng PNG trực tiếp. Đối với các chủ đề liên quan, xem các hướng dẫn về **barcode generator example**, **PDF417 macro parameters**, và **macro PDF417 metadata** handling.

Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to create PDF417 barcode image in C# with Macro PDF417 options](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)
- [How to Create PDF417 Barcode with Aspose – Complete Step‑by‑Step Guide](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}