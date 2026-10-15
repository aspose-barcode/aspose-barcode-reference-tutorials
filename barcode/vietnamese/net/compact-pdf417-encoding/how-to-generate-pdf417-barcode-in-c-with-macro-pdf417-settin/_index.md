---
category: general
date: 2026-10-15
description: Tìm hiểu cách tạo mã vạch PDF417 trong C# bằng các tham số Macro‑PDF417,
  thiết lập kích thước mã vạch và lưu dưới dạng PNG. Bao gồm ví dụ mã đầy đủ.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to generate pdf417 barcode
- C# PDF417 barcode
- Macro PDF417 parameters
- set barcode dimensions
- barcode image format
- barcode checksum
language: vi
lastmod: 2026-10-15
og_description: Cách tạo mã vạch PDF417 trong C# với cấu hình Macro‑PDF417 đầy đủ,
  kiểm soát kích thước và xuất ra PNG. Tham khảo ví dụ hoàn chỉnh.
og_image_alt: Screenshot of a generated PDF417 barcode image created with C# code
og_title: Cách tạo mã vạch PDF417 trong C# – hướng dẫn chi tiết từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-15'
  description: Learn how to generate PDF417 barcode in C# using Macro‑PDF417 parameters,
    set barcode dimensions, and save as PNG. Complete code example included.
  headline: How to generate PDF417 barcode in C# with Macro‑PDF417 settings
  type: TechArticle
tags:
- barcode
- PDF417
- C#
- Aspose.Barcode
title: Cách tạo mã vạch PDF417 trong C# với cài đặt Macro‑PDF417
url: /vi/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-macro-pdf417-settin/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# với cài đặt Macro‑PDF417

Nếu bạn cần **cách tạo mã vạch PDF417** cho quy trình tài liệu, hướng dẫn này sẽ chỉ cho bạn các bước chính xác. Bạn sẽ thấy cách cấu hình các tham số Macro‑PDF417, thiết lập kích thước mã vạch, và xuất kết quả dưới dạng ảnh PNG—tất cả trong một chương trình C# có thể chạy được.

Việc tạo mã vạch PDF417 không đòi hỏi nhiều thư viện hay xử lý hậu kỳ phức tạp. Bằng cách sử dụng Aspose.Barcode cho .NET, bạn có thể kiểm soát mọi khía cạnh của mã vạch, từ độ rộng mô-đun đến checksum, và tạo ra hình ảnh chất lượng cao, sẵn sàng cho việc in ấn hoặc quét.

## Yêu cầu trước

* .NET 6.0 (hoặc mới hơn) SDK đã được cài đặt  
* Visual Studio 2022 hoặc bất kỳ IDE C# nào bạn thích  
* Gói NuGet Aspose.Barcode cho .NET (`Install-Package Aspose.Barcode`)  

Những yêu cầu này đảm bảo mã nguồn biên dịch mà không cần cấu hình bổ sung.

## Bước 1: Tạo trình tạo mã vạch cho mã Macro‑PDF417

Hoạt động đầu tiên tạo một thể hiện `BarcodeGenerator` nhắm tới định dạng `EncodeTypes.MacroPdf417`. Hàm khởi tạo nhận dữ liệu bạn muốn mã hoá—trong trường hợp này là chuỗi `"Sample text"`.

```csharp
using Aspose.Barcode;
using Aspose.Barcode.Generation;

// Step 1: Initialize the generator with Macro‑PDF417 and data to encode
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps configure the barcode
```

Việc tạo trình tạo thiết lập đối tượng `Parameters` nội bộ, mà bạn sẽ dùng để điều chỉnh các thuộc tính **C# PDF417 barcode**.

## Bước 2: Đặt giao diện cơ bản của mã vạch – thiết lập kích thước mã vạch

Kiểm soát kích thước hiển thị của mã vạch giúp cải thiện độ tin cậy khi quét. Thuộc tính `XDimension.Pixels` xác định độ rộng của mô-đun (điểm), trong khi `Pdf417.Columns` quyết định số cột mà mã vạch sẽ chứa.

```csharp
    // Step 2: Define module width and column count
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width in pixels
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns
```

Việc thiết lập các kích thước này đảm bảo mã vạch vừa vặn trong các kích thước nhãn tiêu chuẩn và đáp ứng các thông số kỹ thuật của máy quét.

## Bước 3: Cung cấp thông tin nhận dạng tệp Macro‑PDF417

Macro‑PDF417 mở rộng mã vạch PDF417 tiêu chuẩn bằng siêu dữ liệu ở mức tệp. Bạn phải gán một ID tệp duy nhất, ID đoạn, tổng số đoạn, và một tên tệp có thể đọc được bởi con người.

```csharp
    // Step 3: Assign macro file identification
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";
```

Các **tham số Macro PDF417** này cho phép các hệ thống hạ nguồn tái tạo lại tệp gốc từ nhiều đoạn mã vạch.

## Bước 4: Thêm siêu dữ liệu macro bổ sung – bao gồm checksum của mã vạch

Ngoài việc nhận dạng, Macro‑PDF417 có thể lưu checksum, kích thước tệp, dấu thời gian, người nhận, người gửi và cờ kết thúc. Cung cấp checksum giúp cải thiện việc kiểm tra tính toàn vẹn dữ liệu trong quá trình giải mã.

```csharp
    // Step 4: Populate extra macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // UTC timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

Việc bao gồm **checksum của mã vạch** và các siêu dữ liệu khác làm cho mã vạch tự mô tả, điều này có giá trị cho các quy trình xử lý tài liệu tự động.

## Bước 5: Lưu mã vạch đã tạo dưới dạng ảnh PNG – chọn định dạng ảnh mã vạch

Bước cuối cùng ghi mã vạch vào tệp. Phương thức `Save` nhận một đường dẫn tệp và một enum `BarCodeImageFormat`. PNG cung cấp nén không mất dữ liệu, giữ các cạnh sắc nét để quét đáng tin cậy.

```csharp
    // Step 5: Export the barcode to PNG
    generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Sau khi thực thi, tệp `MacroPdf417.png` chứa một mã vạch PDF417 sắc nét, sẵn sàng để nhúng vào PDF, in lên nhãn hoặc hiển thị trên màn hình.

## Kết quả mong đợi

Mở `C:/Barcodes/MacroPdf417.png` sẽ hiển thị một mã vạch hình chữ nhật với văn bản đã mã hoá “Sample text”. Mã vạch bao gồm các siêu dữ liệu macro mà bạn đã thiết lập, bạn có thể xác minh bằng bất kỳ máy quét PDF417 nào hỗ trợ Macro‑PDF417. Kích thước ảnh phản ánh độ rộng mô-đun (2 px) và số cột (5), tạo ra một mã vạch gọn gàng nhưng vẫn dễ đọc.

## Các biến thể phổ biến và trường hợp đặc biệt

| Tình huống | Điều chỉnh |
|-----------|------------|
| **Độ dài dữ liệu khác** | Thay `"Sample text"` bằng bất kỳ chuỗi UTF‑8 nào; trình tạo sẽ tự động điều chỉnh kích thước mã vạch. |
| **Độ phân giải cao hơn** | Tăng `XDimension.Pixels` lên 3 hoặc 4 để có mô-đun lớn hơn, hữu ích cho máy in độ phân giải thấp. |
| **Nhiều đoạn hơn** | Thay đổi `MacroPdf417SegmentsCount` để phù hợp với tổng số phần mã vạch bạn dự định tạo. |
| **Định dạng ảnh thay thế** | Sử dụng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp` nếu hệ thống hạ nguồn của bạn ưu tiên các định dạng đó. |
| **Sửa lỗi tùy chỉnh** | Sửa `generator.Parameters.Barcode.Pdf417.ErrorLevel` (phạm vi 0‑8) để cân bằng mật độ dữ liệu và khả năng chịu lỗi. |

**Mẹo:** Luôn xác thực mã vạch đã tạo bằng một máy quét thực tế trước khi triển khai vào môi trường sản xuất. Máy quét có thể có giới hạn riêng về độ rộng mô-đun hoặc số cột tùy thuộc vào firmware.

## Mã nguồn đầy đủ

```csharp
using System;
using Aspose.Barcode;
using Aspose.Barcode.Generation;

namespace Pdf417MacroDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for Macro‑PDF417 with sample data
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Set visual dimensions
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // column count

                // Provide macro file identification
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 1;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 10;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "myFile.pdf";

                // Add macro metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 0x1A2B;               // CCITT‑16 checksum
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 850_000;             // file size in bytes
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = DateTime.UtcNow;   // timestamp
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "Acme Corp";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "John Doe";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export as PNG
                generator.Save("C:/Barcodes/MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("PDF417 barcode generated successfully.");
        }
    }
}
```

Chạy chương trình này sẽ tạo `MacroPdf417.png` trong thư mục `C:/Barcodes`. Console sẽ xác nhận việc tạo thành công.

## Kết luận

Bây giờ bạn đã biết **cách tạo mã vạch PDF417** trong C# với khả năng kiểm soát Macro‑PDF417 đầy đủ, cách **đặt kích thước mã vạch**, cách nhúng **checksum của mã vạch** và các siêu dữ liệu macro khác, và cách xuất kết quả bằng **định dạng ảnh mã vạch** đã chọn. Ví dụ hoàn chỉnh này có thể sao chép vào bất kỳ dự án .NET nào, chỉnh sửa cho các tải dữ liệu khác nhau, và tích hợp vào các pipeline tự động hoá tài liệu lớn hơn.

### Các bước tiếp theo

* Khám phá các mức **C# PDF417 barcode** error‑correction để cải thiện độ tin cậy khi quét.  
* Kết hợp nhiều đoạn Macro‑PDF417 để mã hoá các tệp lớn như PDF hoặc hình ảnh.  
* Chuyển **định dạng ảnh mã vạch** sang SVG để có đồ họa vector có thể mở rộng trong các ứng dụng web.  

Bạn có thể tự do thử nghiệm các tham số, và chia sẻ kết quả của mình trong phần bình luận hoặc trên các diễn đàn cộng đồng. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao phủ các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoạt động đầy đủ với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Tạo mã vạch C# với Macro PDF417 – ví dụ đầy đủ](/barcode/english/net/compact-pdf417-encoding/generate-barcode-c-with-macro-pdf417-full-example/)
- [Cách tạo mã vạch PDF417 – Hướng dẫn lập trình đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-complete-programming-guide/)
- [Cách tạo mã vạch PDF417 trong C# với kích thước tùy chỉnh](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-custom-dimensions/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}