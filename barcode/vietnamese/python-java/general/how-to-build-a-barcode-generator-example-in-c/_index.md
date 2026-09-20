---
category: general
date: 2026-09-19
description: Ví dụ trình tạo mã vạch cho thấy cách thay đổi chiều cao, tạo DataBar
  Omni‑Directional và điều chỉnh kích thước mã vạch cho đầu ra hình ảnh C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator example
- how to change height
- how to create databar
- adjust barcode dimensions
- create barcode image c#
language: vi
lastmod: 2026-09-19
og_description: Ví dụ trình tạo mã vạch dạy cách thay đổi chiều cao, tạo DataBar Omni‑Directional
  và điều chỉnh kích thước mã vạch cho hình ảnh PNG trong C#.
og_image_alt: Screenshot of a DataBar Omni‑Directional barcode generated in C#
og_title: Ví dụ trình tạo mã vạch bằng C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-09-19'
  description: barcode generator example showing how to change height, create DataBar
    Omni‑Directional, and adjust barcode dimensions for C# image output
  headline: How to build a barcode generator example in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách xây dựng ví dụ trình tạo mã vạch bằng C#
url: /vi/python-java/general/how-to-build-a-barcode-generator-example-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Ví dụ tạo mã vạch bằng C# – hướng dẫn lập trình đầy đủ

Nếu bạn cần một **ví dụ tạo mã vạch** cho dự án .NET, hướng dẫn này sẽ chỉ cho bạn cách tạo, cấu hình và lưu mã vạch DataBar Omni‑Directional bằng C#. Bạn sẽ học cách thay đổi chiều cao, điều chỉnh kích thước mã vạch và xuất ảnh PNG chất lượng cao — tất cả trong một ứng dụng console có thể chạy ngay.

Các bước dưới đây bao gồm mọi thứ từ cài đặt SDK cần thiết đến việc tinh chỉnh kích thước X và chiều cao thanh. Khi kết thúc tutorial, bạn sẽ có một trình tạo mã vạch sẵn sàng để tích hợp vào hệ thống hoá đơn, quản lý tồn kho hoặc bất kỳ quy trình quét nào.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)  
* Giấy phép hoạt động cho **Aspose.BarCode for .NET** (bản dùng thử miễn phí đủ cho việc thử nghiệm)  

Nếu bạn muốn dùng thư viện khác, các khái niệm về điều chỉnh kích thước và lưu ảnh vẫn giữ nguyên; chỉ cần thay thế các lời gọi API tương ứng.

## Bước 1: Thiết lập dự án và thêm gói Aspose.BarCode

Tạo một dự án console mới và tham chiếu thư viện mã vạch.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Lệnh `dotnet add package` sẽ tải về phiên bản ổn định mới nhất của Aspose.BarCode, bao gồm hỗ trợ đầy đủ cho các ký hiệu DataBar Omni‑Directional.

## Bước 2: Viết ví dụ tạo mã vạch hoàn chỉnh

Mở **Program.cs** và thay thế nội dung bằng đoạn mã sau. Khối này chứa **ví dụ tạo mã vạch** đầy đủ — không thiếu bất kỳ phần nào.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a barcode generator for a DataBar Omni‑Directional symbol
            // The GTIN‑14 value "(01)12345678901231" is encoded as a numeric string.
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // 2️⃣ Adjust barcode dimensions
            // Set the X‑dimension (module width) to 2 pixels – this controls the thin bar width.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // 3️⃣ How to change height
            // Set the bar height to 30 pixels. Height influences readability on larger scanners.
            generator.Parameters.Barcode.BarHeight.Pixels = 30;

            // 4️⃣ Optional: fine‑tune additional properties (quiet zone, color, etc.)
            generator.Parameters.Barcode.QrCodeErrorLevel = QRErrorLevel.LevelM; // example property
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // 5️⃣ Create barcode image C#
            // Save the generated barcode as a PNG file in the output folder.
            string outputPath = "DatabarOmniDirectional.png";
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode saved to {outputPath}");
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

* **Create a barcode generator** – Hàm khởi tạo `BarcodeGenerator` liên kết kiểu mã (`EncodeTypes.DatabarOmniDirectional`) với dữ liệu bạn muốn nhúng. Đây là phần cốt lõi của bước **how to create databar**.  
* **Adjust barcode dimensions** – Thuộc tính `XDimension.Pixels` xác định độ rộng của thanh mảnh nhất. Thay đổi giá trị này ảnh hưởng đến kích thước tổng thể và độ tin cậy khi quét.  
* **How to change height** – Thuộc tính `BarHeight.Pixels` điều khiển kích thước theo chiều dọc. Tăng chiều cao cải thiện khả năng đọc cho máy quét cầm tay, trong khi giảm chiều cao giúp tiết kiệm không gian trên nhãn nhỏ.  
* **Optional tweaks** – Đặt màu nền/màu chữ hoặc mức sửa lỗi là tùy chọn nhưng cho thấy cách mở rộng khái niệm **adjust barcode dimensions**.  
* **Create barcode image C#** – Phương thức `Save` ghi mã vạch ra đĩa. Sử dụng `BarCodeImageFormat.Png` đảm bảo nén không mất dữ liệu, lý tưởng cho hầu hết các ứng dụng.

## Bước 3: Biên dịch và chạy ví dụ

Biên dịch và thực thi chương trình:

```bash
dotnet run
```

Bạn sẽ thấy đầu ra trên console:

```
Barcode saved to DatabarOmniDirectional.png
```

Một tệp có tên **DatabarOmniDirectional.png** sẽ xuất hiện trong thư mục dự án. Mở ảnh sẽ thấy một mã vạch DataBar Omni‑Directional sắc nét, sẵn sàng để quét.

## Cách thay đổi chiều cao sau khi tạo

Nếu bạn cần tạo mã vạch với các chiều cao khác nhau, hãy bọc việc gán chiều cao trong một phương thức:

```csharp
static void SetBarHeight(BarcodeGenerator gen, int heightPixels)
{
    gen.Parameters.Barcode.BarHeight.Pixels = heightPixels;
}
```

Gọi `SetBarHeight(generator, 45);` trước `Save`. Cách này cho phép bạn **how to change height** một cách động dựa trên đầu vào người dùng hoặc tệp cấu hình.

## Cách tạo mã vạch DataBar Omni‑Directional với dữ liệu khác nhau

Ký hiệu DataBar Omni‑Directional hỗ trợ GTIN‑14, GTIN‑13 và các định danh số khác. Để mã hoá một giá trị khác, chỉ cần thay thế chuỗi trong hàm khởi tạo:

```csharp
new BarcodeGenerator(EncodeTypes.DatabarOmniDirectional, "(01)98765432109876");
```

Hãy nhớ giữ dữ liệu ở dạng số và định dạng đúng; nếu không trình tạo sẽ ném ra `BarcodeException`.

## Điều chỉnh kích thước mã vạch cho các kịch bản in khác nhau

Các máy in và kích thước nhãn khác nhau yêu cầu các X‑dimension và chiều cao khác nhau. Sử dụng bảng dưới đây làm tham khảo nhanh:

| Kịch bản                     | X‑Dimension (pixels) | Bar Height (pixels) |
|------------------------------|----------------------|---------------------|
| Nhãn nhỏ (25 mm × 15 mm)     | 1                    | 20                  |
| Nhãn trung (50 mm × 30 mm)   | 2                    | 30                  |
| Nhãn lớn (100 mm × 50 mm)    | 3                    | 45                  |

Áp dụng các giá trị này bằng cách đặt `generator.Parameters.Barcode.XDimension.Pixels` và `BarHeight.Pixels` tương ứng.

## Mẹo chuyên nghiệp: xác thực mã vạch đã tạo

Trước khi phát hành nhãn, bạn có thể kiểm tra khả năng đọc của nó một cách lập trình:

```csharp
using Aspose.BarCode.BarCodeRecognition;

// ...

BarCodeReader reader = new BarCodeReader(outputPath, DecodeType.DatabarOmniDirectional);
if (reader.Read())
{
    Console.WriteLine("Validation succeeded: " + reader.GetCodeText());
}
else
{
    Console.WriteLine("Validation failed – barcode may be unreadable.");
}
```

Đoạn mã này minh họa một kiểm tra nhanh **adjust barcode dimensions** để đảm bảo mã vạch đáp ứng yêu cầu quét.

## Những lỗi thường gặp và cách tránh

| Lỗi                                   | Nguyên nhân                                 | Cách khắc phục                                                            |
|---------------------------------------|---------------------------------------------|---------------------------------------------------------------------------|
| Sử dụng dữ liệu không phải số cho DataBar | DataBar yêu cầu định dạng GTIN số           | Đảm bảo chuỗi khớp mẫu `(01)XXXXXXXXXXXXX`.                               |
| Đặt X‑dimension bằng 0 hoặc âm        | Thư viện ném `ArgumentOutOfRangeException` | Sử dụng ít nhất 1 pixel; kiểm tra trên máy in mục tiêu trước.            |
| Lưu vào thư mục chỉ đọc                | `UnauthorizedAccessException` khi `Save`   | Chọn thư mục có quyền ghi hoặc chạy ứng dụng với quyền thích hợp.        |
| Quên giải phóng `BarCodeReader`       | Rò rỉ bộ nhớ trong dịch vụ chạy lâu dài    | Đặt reader trong khối `using` hoặc gọi `Dispose()` thủ công.             |

Giải quyết những vấn đề này từ sớm sẽ tiết kiệm thời gian gỡ lỗi và nâng cao độ ổn định trong môi trường sản xuất.

## Tóm tắt mã nguồn đầy đủ

Dưới đây là chương trình hoàn chỉnh, sẵn sàng sao chép, thực hiện **ví dụ tạo mã vạch** từ đầu đến cuối.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create generator – how to create databar
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

            // Adjust barcode dimensions
            generator.Parameters.Barcode.XDimension.Pixels = 2;   // thin bar width
            generator.Parameters.Barcode.BarHeight.Pixels = 30; // how to change height

            // Optional visual tweaks
            generator.Parameters.ImageOptions.ForeColor = System.Drawing.Color.Black;
            generator.Parameters.ImageOptions.BackColor = System.Drawing.Color.White;

            // Save image – create barcode image c#
            string filePath = "DatabarOmniDirectional.png";
            generator.Save(filePath, BarCodeImageFormat.Png);
            Console.WriteLine($"Barcode saved to {filePath}");

            // Validate barcode (optional)
            using (BarCodeReader reader = new BarCodeReader(filePath, DecodeType.DatabarOmniDirectional))
            {
                if (reader.Read())
                    Console.WriteLine($"Validation succeeded: {reader.GetCodeText()}");
                else
                    Console.WriteLine("Validation failed – barcode may be unreadable.");
            }
        }
    }
}
```

Chạy chương trình này sẽ tạo ra một tệp PNG trông như sau (minh hoạ):

![Mã vạch DataBar Omni‑Directional được tạo bằng C#](https://example.com/og-image.png "Mã vạch DataBar Omni‑Directional được tạo bằng C#")

*Văn bản alt hình ảnh*: **Mã vạch DataBar Omni‑Directional được tạo bằng C#** (matches `og_image_alt`).

## Kết luận

Bạn đã có một **ví dụ tạo mã vạch** thể hiện cách thay đổi chiều cao, cách tạo ký hiệu DataBar Omni‑Directional, và cách **adjust barcode dimensions** để quét tối ưu. Mã C# hoàn chỉnh lưu ảnh PNG, xác thực nó, và có thể mở rộng để tạo hàng loạt hoặc tích hợp vào dịch vụ web.

Tiếp theo, khám phá các chủ đề liên quan như **tạo mã QR với Aspose.BarCode**, **xử lý hàng loạt nhiều giá trị mã vạch**, hoặc **nhúng mã vạch vào tài liệu PDF**. Mỗi chủ đề đều dựa trên những nền tảng đã được trình bày trong hướng dẫn này.

Chúc lập trình vui vẻ, và mã vạch của bạn luôn có thể quét được!

## Bạn nên học gì tiếp theo?

Các tutorial dưới đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ cùng giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Barcode Generator Example – Build DataBar Image in C#](/barcode/english/python-java/general/barcode-generator-example-build-databar-image-in-c/)
- [How to Generate and Adjust Barcode Height for One-Dimensional Databar using Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Barcode generator example in C# – set width and height](/barcode/english/python-java/general/barcode-generator-example-in-c-set-width-and-height/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}