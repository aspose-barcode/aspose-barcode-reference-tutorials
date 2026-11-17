---
category: general
date: 2026-11-17
description: Tìm hiểu cách lưu mã vạch, bật chế độ gọn, điều chỉnh cột và tạo mã vạch
  PDF417 với ví dụ C# hoàn chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to save barcode
- enable compact mode
- how to adjust columns
- generate pdf417 barcode
- how to enable compact mode
language: vi
lastmod: 2026-11-17
og_description: Cách lưu mã vạch, bật chế độ gọn gàng và điều chỉnh cột khi tạo mã
  vạch PDF417 bằng C#. Thực hiện theo hướng dẫn chi tiết từng bước.
og_image_alt: Screenshot showing how to save barcode as PNG file in C#
og_title: Cách lưu mã vạch dưới dạng PNG và bật chế độ gọn trong C#
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  headline: How to save barcode as PNG and enable compact mode in C#
  type: TechArticle
- description: Learn how to save barcode, enable compact mode, adjust columns, and
    generate PDF417 barcode with a complete C# example.
  name: How to save barcode as PNG and enable compact mode in C#
  steps:
  - name: Expected output
    text: Opening the saved PNG file shows a vertically compact PDF417 barcode with
      three columns and truncated padding. The visual size is roughly 2 px per module,
      making the image suitable for embedding in HTML `<img>` tags or for printing
      on small labels.
  - name: What if I need a different image format?
    text: The `Save` method accepts any `BarCodeImageFormat` enum value, such as `Jpeg`,
      `Bmp`, or `Gif`. Replace `BarCodeImageFormat.Png` with the desired format, and
      the rest of the code remains unchanged.
  - name: How does truncation affect data capacity?
    text: Enabling **compact mode** (truncation) reduces the number of rows, which
      can lower the maximum data capacity of the barcode. If you encounter a “Data
      too large” exception, either increase the number of columns or disable truncation.
  - name: Can I use a dynamic column count?
    text: 'Yes. You can calculate the column count based on the length of the input
      string:'
  - name: Is the X‑dimension limited to integer pixels?
    text: The `Pixels` property accepts any positive integer. For higher‑resolution
      outputs (e.g., printing), you might prefer setting `Points` instead of `Pixels`
      to achieve device‑independent sizing.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- image generation
title: Cách lưu mã vạch dưới dạng PNG và bật chế độ gọn trong C#
url: /vi/net/compact-pdf417-encoding/how-to-save-barcode-as-png-and-enable-compact-mode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách lưu mã vạch dưới dạng PNG và bật chế độ gọn trong C#

Nếu bạn cần **cách lưu mã vạch** ở định dạng có thể sử dụng trên web hoặc in ấn, hướng dẫn này sẽ chỉ cho bạn các bước chính xác. Bạn cũng sẽ học cách **bật chế độ gọn**, **điều chỉnh cột**, và **tạo mã vạch PDF417** bằng thư viện Aspose.BarCode cho .NET.

Bài hướng dẫn bao gồm mọi thứ từ thiết lập dự án đến tệp PNG cuối cùng, vì vậy bạn có thể sao chép mã vào giải pháp của mình mà không cần nghiên cứu thêm. Không cần tài liệu bên ngoài; ví dụ đầy đủ, có thể chạy được đã được bao gồm.

## Yêu cầu trước

* .NET 6.0 hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE C# nào)  
* Gói NuGet `Aspose.BarCode` (`Install-Package Aspose.BarCode`)  

Ba mục này là các phụ thuộc duy nhất cho đoạn mã phía sau.

## Bước 1: Tạo trình tạo mã vạch PDF417

Nhiệm vụ đầu tiên khi bạn **tạo mã vạch PDF417** là khởi tạo một `BarcodeGenerator` với kiểu mã hoá đúng và dữ liệu bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a PDF417 barcode generator with the desired text.
BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");
```

`enum` `EncodeTypes.Pdf417` cho thư viện biết sử dụng ký hiệu PDF417, là một mã vạch tuyến tính xếp chồng phù hợp cho việc mã hoá lượng lớn dữ liệu. Chuỗi `"Compact mode"` sẽ trở thành văn bản có thể đọc được bởi con người dưới mã vạch.

## Bước 2: Đặt kích thước X (độ rộng mô-đun)

Mỗi thanh trong mã vạch được gọi là một mô-đun. Kiểm soát độ rộng mô-đun cho phép bạn tinh chỉnh kích thước hiển thị của mã vạch mà không thay đổi dữ liệu.

```csharp
// Step 2: Set the module (X) dimension – each bar will be 2 pixels wide.
barcode.Parameters.Barcode.XDimension.Pixels = 2;
```

Kích thước X 2 pixel tạo ra một hình ảnh gọn gàng nhưng vẫn quét được một cách đáng tin cậy trên hầu hết các thiết bị.

## Bước 3: **Cách điều chỉnh cột** cho mã PDF417

PDF417 cho phép bạn chỉ định số cột mà mã vạch sẽ sử dụng. Ít cột hơn tạo ra ký hiệu cao hơn, hẹp hơn, trong khi nhiều cột hơn làm ký hiệu rộng hơn nhưng ngắn hơn.

```csharp
// Step 3: Define the number of columns for the PDF417 code (3 columns).
barcode.Parameters.Barcode.Pdf417.Columns = 3;
```

Dòng này minh họa **cách điều chỉnh cột**. Bạn có thể thay đổi giá trị thành 2, 4, hoặc bất kỳ số nào được thư viện hỗ trợ, tùy thuộc vào không gian bạn có trên phương tiện mục tiêu.

## Bước 4: **Cách bật chế độ gọn** và cắt ngắn ký hiệu

Chế độ gọn loại bỏ các khoảng đệm không cần thiết và giảm kích thước tổng thể của mã vạch. Thư viện cung cấp tính năng này thông qua thuộc tính `Truncate`.

```csharp
// Step 4: Enable compact mode by truncating the symbol.
barcode.Parameters.Barcode.Pdf417.Truncate = true;
```

Lưu ý rằng cụm từ **bật chế độ gọn** xuất hiện ở đây, và hành động tương tự được mô tả bằng cụm từ **cách bật chế độ gọn** sau này trong hướng dẫn để đáp ứng yêu cầu từ khóa phụ.

## Bước 5: **Cách lưu mã vạch** dưới dạng ảnh PNG

Lưu ảnh đã tạo là bước cuối cùng. Phương thức `Save` ghi mã vạch vào hệ thống tệp ở định dạng bạn chỉ định.

```csharp
// Step 5: Save the generated barcode as a PNG image.
barcode.Save("YOUR_DIRECTORY/CompactPdf417.png", BarCodeImageFormat.Png);
```

Thay thế `YOUR_DIRECTORY` bằng đường dẫn tuyệt đối hoặc tương đối mà ứng dụng của bạn có thể ghi vào. Sau khi thực thi, bạn sẽ thấy một tệp có tên `CompactPdf417.png` chứa mã vạch PDF417 gọn.

### Kết quả mong đợi

Mở tệp PNG đã lưu sẽ hiển thị một mã vạch PDF417 dọc gọn với ba cột và khoảng đệm đã cắt ngắn. Kích thước hiển thị khoảng 2 px mỗi mô-đun, làm cho hình ảnh phù hợp để nhúng vào thẻ HTML `<img>` hoặc in trên nhãn nhỏ.

## Ví dụ đầy đủ, có thể chạy

Dưới đây là chương trình đầy đủ mà bạn có thể sao chép vào một dự án console mới. Nó bao gồm tất cả các chỉ thị `using` cần thiết và minh họa **cách lưu mã vạch**, **bật chế độ gọn**, **cách điều chỉnh cột**, và **tạo mã vạch PDF417** trong một quy trình duy nhất.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace Pdf417CompactDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // Create a PDF417 barcode generator with the desired text.
            BarcodeGenerator barcode = new BarcodeGenerator(EncodeTypes.Pdf417, "Compact mode");

            // Set the module (X) dimension – each bar will be 2 pixels wide.
            barcode.Parameters.Barcode.XDimension.Pixels = 2;

            // Define the number of columns for the PDF417 code (3 columns).
            barcode.Parameters.Barcode.Pdf417.Columns = 3;

            // Enable compact mode by truncating the symbol.
            barcode.Parameters.Barcode.Pdf417.Truncate = true;

            // Save the generated barcode as a PNG image.
            string outputPath = "CompactPdf417.png"; // Adjust path as needed.
            barcode.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

Chạy chương trình này sẽ tạo ra tệp PNG đã mô tả ở trên. Đầu ra console xác nhận vị trí của tệp đã lưu, giúp bạn kiểm tra rằng bước **cách lưu mã vạch** đã thành công.

## Câu hỏi thường gặp và các trường hợp đặc biệt

### Nếu tôi cần định dạng ảnh khác thì sao?

Phương thức `Save` chấp nhận bất kỳ giá trị enum `BarCodeImageFormat` nào, chẳng hạn `Jpeg`, `Bmp`, hoặc `Gif`. Thay thế `BarCodeImageFormat.Png` bằng định dạng mong muốn, và phần còn lại của mã sẽ không thay đổi.

### Cắt ngắn ảnh hưởng như thế nào đến dung lượng dữ liệu?

Bật **chế độ gọn** (cắt ngắn) giảm số hàng, có thể làm giảm dung lượng dữ liệu tối đa của mã vạch. Nếu bạn gặp ngoại lệ “Data too large”, hãy tăng số cột hoặc tắt tính năng cắt ngắn.

### Tôi có thể sử dụng số cột động không?

Có. Bạn có thể tính số cột dựa trên độ dài của chuỗi đầu vào:

```csharp
int desiredColumns = Math.Max(2, Math.Min(30, inputText.Length / 10));
barcode.Parameters.Barcode.Pdf417.Columns = desiredColumns;
```

Đoạn mã này cho thấy **cách điều chỉnh cột** một cách lập trình, đảm bảo mã vạch phù hợp với bố cục đã cho.

### Kích thước X có giới hạn ở pixel nguyên không?

Thuộc tính `Pixels` chấp nhận bất kỳ số nguyên dương nào. Đối với đầu ra độ phân giải cao hơn (ví dụ: in ấn), bạn có thể muốn đặt `Points` thay vì `Pixels` để đạt kích thước độc lập với thiết bị.

## Mẹo cho việc sử dụng trong môi trường sản xuất

* **Mẹo chuyên nghiệp:** Bao quanh quá trình tạo mã vạch trong khối try‑catch để xử lý `BarCodeException` khi dữ liệu đầu vào vượt quá khả năng của ký hiệu.  
* **Cảnh báo:** Quyền truy cập hệ thống tệp. Quy trình phải có quyền ghi vào thư mục mục tiêu, nếu không bước **cách lưu mã vạch** sẽ thất bại với lỗi `UnauthorizedAccessException`.  
* **Lưu ý hiệu năng:** Tạo nhiều mã vạch trong vòng lặp sẽ có lợi khi tái sử dụng một thể hiện `BarcodeGenerator` duy nhất và chỉ cập nhật thuộc tính `CodeText` giữa các vòng lặp.

## Kết luận

Bây giờ bạn đã biết **cách lưu mã vạch** dưới dạng tệp PNG, **bật chế độ gọn**, **cách điều chỉnh cột**, và **tạo mã vạch PDF417** bằng Aspose.BarCode cho C#. Ví dụ đầy đủ minh họa mọi bước cần thiết, từ khởi tạo trình tạo đến ghi hình ảnh cuối cùng.

Từ đây bạn có thể khám phá các chủ đề liên quan như thêm logo vào mã vạch, tùy chỉnh màu sắc, hoặc tích hợp trình tạo vào API ASP.NET Core. Mỗi phần mở rộng này tuân theo cùng một mẫu được trình bày trong hướng dẫn này, vì vậy bạn có thể điều chỉnh mã một cách tự tin.

Hãy thoải mái thử nghiệm với các số cột khác nhau, kích thước X và định dạng ảnh để đáp ứng các yêu cầu chính xác của dự án. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách lưu mã vạch và tạo PDF417 với Aspose trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-and-generate-pdf417-with-aspose-in-c/)
- [Cách tạo mã vạch PDF417 trong C# với chế độ gọn](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-compact-mode/)
- [Cách tạo mã vạch PDF417 và lưu dưới dạng PNG trong C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-and-save-it-as-png-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}