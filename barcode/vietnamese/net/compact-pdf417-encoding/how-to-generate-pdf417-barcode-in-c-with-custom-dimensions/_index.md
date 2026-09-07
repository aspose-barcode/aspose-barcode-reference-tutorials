---
category: general
date: 2026-09-07
description: Tạo mã vạch PDF417 trong C# và học cách thiết lập kích thước mã vạch
  để kiểm soát chính xác. Thực hiện theo hướng dẫn từng bước này để tạo hình ảnh PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate pdf417 barcode
- how to generate pdf417 barcode
- how to set barcode dimensions
language: vi
lastmod: 2026-09-07
og_description: Tạo mã vạch PDF417 bằng C# và học cách thiết lập kích thước mã vạch.
  Hướng dẫn này trình bày một ví dụ đầy đủ, có thể chạy được.
og_image_alt: Generated PDF417 barcode image with custom dimensions
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ kèm kích thước
schemas:
- author: Aspose
  dateModified: '2026-09-07'
  description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  headline: How to generate PDF417 barcode in C# with custom dimensions
  type: TechArticle
- description: Generate PDF417 barcode in C# and learn how to set barcode dimensions
    for precise control. Follow this step‑by‑step guide to create a PNG image.
  name: How to generate PDF417 barcode in C# with custom dimensions
  steps:
  - name: Expected output
    text: '- **File:** `Pdf417Layout.png` (PNG, lossless) - **Dimensions:** Determined
      by `XDimension` (2 px) × (columns × rows) matrix - **Content:** A scannable
      PDF417 barcode encoding the Unicode string `Åspóse.Barcóde©`'
  - name: What if I need a larger image for printing?
    text: Increase `XDimension.Pixels` to 4 or 5. Larger values produce a higher‑resolution
      barcode but also increase file size.
  - name: Can I encode more data than the example string?
    text: Yes. PDF417 can hold up to 1,850 characters. Just replace the text argument
      in the `BarcodeGenerator` constructor. If the data exceeds the matrix capacity,
      the library automatically adds extra rows.
  - name: How does error correction work?
    text: 'PDF417 includes built‑in error correction. You can adjust its level via:'
  - name: What if the barcode appears blurry on screen?
    text: 'Make sure the output image’s DPI matches the display environment. You can
      set DPI when saving:'
  - name: Next steps
    text: '- Explore **how to generate PDF417 barcode** with different image formats
      (JPEG, BMP). - Learn **how to set barcode dimensions** dynamically based on
      user input or device DPI. - Integrate the barcode generation into an ASP.NET
      Core API to serve barcodes on demand.'
  type: HowTo
tags:
- barcode generation
- PDF417
- C#
title: Cách tạo mã vạch PDF417 trong C# với kích thước tùy chỉnh
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# với kích thước tùy chỉnh

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác. Bạn sẽ thấy một ví dụ đầy đủ, có thể chạy được, tạo ra một hình ảnh PNG đồng thời cho phép bạn kiểm soát kích thước của mã vạch.

Việc tạo mã vạch PDF417 là một yêu cầu phổ biến cho các hệ thống quản lý tồn kho, vé lên máy bay và tài liệu bảo mật. Trong bài hướng dẫn này, bạn cũng sẽ học **cách đặt kích thước mã vạch** để kết quả phù hợp với nhu cầu bố cục của bạn.

## Yêu cầu trước

- .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
- Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)  
- Gói NuGet **Aspose.BarCode for .NET** (hoặc bất kỳ thư viện tương thích nào hỗ trợ PDF417)  

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

## Bước 1: Tạo trình tạo mã vạch PDF417

Bước đầu tiên là khởi tạo một `BarcodeGenerator` với loại `EncodeTypes.Pdf417` và văn bản bạn muốn mã hoá. Đối tượng generator chứa tất cả các cài đặt cho mã vạch.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");
```

**Tại sao điều này quan trọng:** Enum `EncodeTypes.Pdf417` cho thư viện biết sử dụng ký hiệu PDF417, hỗ trợ tải dữ liệu lớn và khả năng sửa lỗi. Chuỗi văn bản có thể chứa ký tự Unicode, vì vậy bạn có thể mã hoá các ký hiệu quốc tế mà không cần công việc bổ sung.

## Bước 2: Cách đặt kích thước mã vạch

Kiểm soát kích thước của mỗi mô-đun (hình vuông đen/trắng nhỏ nhất) quyết định độ phân giải tổng thể của hình ảnh. Thuộc tính `XDimension.Pixels` đặt chiều rộng tính bằng pixel của một mô-đun.

```csharp
        // Step 2: Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Tại sao điều này quan trọng:** `XDimension` lớn hơn tạo ra hình ảnh có độ phân giải cao hơn, hữu ích cho việc in ấn hoặc quét từ khoảng cách xa. Ngược lại, giá trị nhỏ hơn giảm kích thước tệp cho việc sử dụng trên web.

## Bước 3: Xác định bố cục PDF417 (cột và hàng)

PDF417 cho phép bạn ảnh hưởng đến hình dạng ma trận bằng cách chỉ định số cột và hàng. Điều này có thể ảnh hưởng đến khả năng đọc và kích thước vật lý của mã vạch.

```csharp
        // Step 3: Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows
```

**Tại sao điều này quan trọng:** Điều chỉnh số cột và hàng giúp bạn vừa mã vạch vào không gian cụ thể hoặc đáp ứng yêu cầu tỷ lệ khung hình của máy quét. Thư viện tự động thêm đệm nếu dữ liệu không lấp đầy ma trận hoàn toàn.

## Bước 4: Lưu mã vạch dưới dạng hình ảnh PNG

Cuối cùng, ghi mã vạch đã tạo ra vào một tệp. PNG giữ nguyên chất lượng không mất dữ liệu, làm cho nó lý tưởng cho các bước xử lý tiếp theo.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

Khi bạn chạy chương trình, tệp `Pdf417Layout.png` sẽ xuất hiện trong thư mục đầu ra của dự án. Hình ảnh trông như sau:

![Hình ảnh mã vạch PDF417 được tạo với kích thước tùy chỉnh](og_image_placeholder.png)

*Văn bản thay thế hình ảnh: Hình ảnh mã vạch PDF417 được tạo với kích thước tùy chỉnh*

**Tại sao điều này quan trọng:** Lưu dưới dạng PNG đảm bảo rằng các kích thước mô-đun chính xác mà bạn đã đặt được giữ nguyên, điều này rất quan trọng cho các ứng dụng quét sau này.

## Ví dụ hoàn chỉnh trong một khối

Dưới đây là toàn bộ chương trình mà bạn có thể sao chép, dán và chạy mà không cần sửa đổi (ngoại trừ đường dẫn đầu ra nếu muốn).

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a PDF417 barcode generator with the desired text
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417,
            "Åspóse.Barcóde©");

        // Set the size of each barcode module (pixel resolution)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // Define the layout – number of columns and rows in the PDF417 matrix
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4; // 4 columns
        barcodeGenerator.Parameters.Barcode.Pdf417.Rows    = 9; // 9 rows

        // Save the generated barcode as a PNG image
        barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png);
    }
}
```

### Kết quả mong đợi

- **Tệp:** `Pdf417Layout.png` (PNG, không mất dữ liệu)  
- **Kích thước:** Được xác định bởi `XDimension` (2 px) × ma trận (cột × hàng)  
- **Nội dung:** Một mã vạch PDF417 có thể quét được, mã hoá chuỗi Unicode `Åspóse.Barcóde©`

## Các câu hỏi thường gặp và trường hợp đặc biệt

### Nếu tôi cần hình ảnh lớn hơn để in ấn thì sao?

Tăng `XDimension.Pixels` lên 4 hoặc 5. Giá trị lớn hơn tạo ra mã vạch có độ phân giải cao hơn nhưng cũng làm tăng kích thước tệp.

### Tôi có thể mã hoá dữ liệu nhiều hơn chuỗi ví dụ không?

Có. PDF417 có thể chứa tới 1.850 ký tự. Chỉ cần thay thế đối số văn bản trong hàm khởi tạo `BarcodeGenerator`. Nếu dữ liệu vượt quá khả năng của ma trận, thư viện sẽ tự động thêm các hàng bổ sung.

### Cách hoạt động của sửa lỗi là gì?

PDF417 bao gồm chức năng sửa lỗi tích hợp. Bạn có thể điều chỉnh mức độ của nó qua:

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorLevel = 5; // 0‑8, higher = more correction
```

Mức độ cao hơn tăng độ bền vững nhưng đổi lại là mã vạch lớn hơn.

### Nếu mã vạch xuất hiện mờ trên màn hình thì sao?

Đảm bảo DPI của hình ảnh đầu ra phù hợp với môi trường hiển thị. Bạn có thể đặt DPI khi lưu:

```csharp
barcodeGenerator.Save("Pdf417Layout.png", BarCodeImageFormat.Png, 300);
```

## Mẹo chuyên nghiệp

- **Mẹo chuyên nghiệp:** Luôn kiểm tra mã vạch đã tạo bằng máy quét thực tế mà bạn dự định sử dụng. Các thiết bị khác nhau có độ chịu lỗi khác nhau đối với kích thước mô-đun và vùng yên lặng.  
- **Cảnh báo:** Giá trị `XDimension` rất nhỏ (< 1 px) có thể hiển thị dưới dạng các đường vô hình trên màn hình DPI cao.  
- **Mẹo cho ứng dụng web:** Phục vụ PNG với header `Cache-Control: public, max-age=86400` để giảm tải tạo lại liên tục.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch PDF417** trong C# và chính xác **đặt kích thước mã vạch** để đáp ứng bất kỳ yêu cầu nào. Ví dụ đầy đủ, có thể chạy này minh họa cách tạo hình ảnh PNG với bố cục cột/hàng và kích thước mô-đun tùy chỉnh, sẵn sàng cho việc in ấn hoặc phân phối kỹ thuật số.

### Các bước tiếp theo

- Khám phá **cách tạo mã vạch PDF417** với các định dạng hình ảnh khác nhau (JPEG, BMP).  
- Tìm hiểu **cách đặt kích thước mã vạch** một cách động dựa trên đầu vào của người dùng hoặc DPI của thiết bị.  
- Tích hợp việc tạo mã vạch vào một API ASP.NET Core để cung cấp mã vạch theo yêu cầu.

Bạn có thể thoải mái thử nghiệm các cài đặt khác của PDF417 như sửa lỗi, lề và màu sắc. Chúc lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách Đặt Mức Sửa Lỗi trong Mã Vạch PDF417 – Hướng Dẫn Đầy Đủ](/barcode/english/net/compact-pdf417-encoding/how-to-set-error-level-in-pdf417-barcode-complete-guide/)
- [Cách Lưu Mã Vạch trong C# – Tạo Mã Vạch PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-save-barcode-in-c-generate-pdf417-barcodes/)
- [Tạo Mã Vạch PDF417 trong C# – Hướng Dẫn Đầy Đủ](/barcode/english/net/compact-pdf417-encoding/generate-pdf417-barcode-in-c-complete-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}