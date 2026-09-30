---
category: general
date: 2026-08-22
description: Cách đọc mã vạch PDF417 trong C# với hướng dẫn từng bước, bao gồm cách
  đọc nhiều mã vạch từ một hình ảnh và trích xuất chi tiết MacroPdf417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- read multiple barcodes
- read barcodes image c#
language: vi
lastmod: 2026-08-22
og_description: Cách đọc mã vạch PDF417 trong C# nhanh chóng. Hướng dẫn này chỉ cho
  bạn cách đọc nhiều mã vạch từ một hình ảnh và truy xuất thông tin mở rộng MacroPdf417.
og_image_alt: Developer console displaying MacroPdf417 barcode details extracted by
  C# code
og_title: Cách đọc mã vạch PDF417 trong C# – hướng dẫn lập trình chi tiết
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: How to read PDF417 barcodes in C# with a step‑by‑step guide, covering
    how to read multiple barcodes from an image and extract MacroPdf417 details.
  headline: How to read PDF417 barcodes in C# – complete guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách đọc mã vạch PDF417 trong C# – hướng dẫn đầy đủ
url: /vi/net/compact-pdf417-encoding/how-to-read-pdf417-barcodes-in-c-complete-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc mã vạch PDF417 trong C# – hướng dẫn đầy đủ

Nếu bạn cần **cách đọc PDF417** trong một ứng dụng .NET, hướng dẫn này cung cấp cho bạn một giải pháp sẵn sàng chạy. Bạn sẽ học cách đọc nhiều mã vạch từ một hình ảnh duy nhất, trích xuất toàn bộ bộ dữ liệu MacroPdf417, và hiển thị chúng trên console. Cách tiếp cận này hoạt động với thư viện Aspose.BarCode cho .NET và chỉ yêu cầu vài dòng mã.

Đọc mã vạch từ hình ảnh là một nhiệm vụ phổ biến trong hệ thống quản lý tồn kho, xác thực vé, và quản lý tài liệu. Khi kết thúc hướng dẫn này, bạn sẽ có thể giải mã bất kỳ mã vạch PDF417 hoặc MacroPdf417 nào, xử lý nhiều mã trong một hình ảnh, và hiểu các trường mở rộng mà MacroPdf417 cung cấp.

## Yêu cầu trước

- .NET 6.0 SDK hoặc phiên bản mới hơn (mã cũng biên dịch được với .NET Framework 4.7+)
- Visual Studio 2022 hoặc bất kỳ trình soạn thảo C# nào bạn thích
- Gói NuGet Aspose.BarCode cho .NET (`Install-Package Aspose.BarCode`)
- Một hình ảnh mẫu chứa mã vạch MacroPdf417 (ví dụ, `MacroPdf417.png`)

Không cần cấu hình bổ sung; thư viện tự động xử lý việc tải và giải mã hình ảnh.

## Cách đọc mã vạch PDF417 từ hình ảnh trong C#

Cốt lõi của giải pháp là lớp `BarCodeReader`. Nó mở hình ảnh, phát hiện tất cả các mã vạch của loại được chỉ định, và trả về một tập hợp các đối tượng `BarCodeResult`. Đoạn mã dưới đây hiển thị một chương trình console hoàn chỉnh.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            // Path to the image that contains one or more MacroPdf417 barcodes
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            // 1️⃣ Initialize the reader for MacroPdf417 barcodes.
            // DecodeType.MacroPdf417 tells the engine to look for the extended PDF417 format.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // 2️⃣ Iterate over every barcode found in the image.
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // 3️⃣ Print basic information.
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // 4️⃣ Access MacroPdf417 extended fields.
                    // The Extended property contains format‑specific data; for PDF417 it is .Pdf417.
                    var macro = result.Extended.Pdf417;

                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");

                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Tại sao mỗi dòng lại quan trọng

| Bước | Mục đích |
|------|----------|
| **1️⃣ Initialize** | Tạo một `BarCodeReader` liên kết với tệp hình ảnh và giới hạn việc phát hiện chỉ ở ký hiệu MacroPdf417, giúp tăng tốc xử lý. |
| **2️⃣ Iterate** | `ReadBarCodes()` trả về **tất cả** các mã vạch khớp với loại yêu cầu, cho phép bạn **đọc nhiều mã vạch** mà không cần vòng lặp bổ sung. |
| **3️⃣ Basic output** | Hiển thị `CodeTypeName` chung và `CodeText` dễ đọc cho con người. Điều này hữu ích cho việc ghi log hoặc xác thực nhanh. |
| **4️⃣ Extended data** | MacroPdf417 chứa siêu dữ liệu bổ sung (ID tệp, số lượng đoạn, dấu thời gian, v.v.). Đối tượng `Extended.Pdf417` hiển thị mỗi trường trực tiếp, cho phép bạn lưu hoặc xác minh toàn bộ gói dữ liệu. |

Chạy chương trình với một hình ảnh MacroPdf417 hợp lệ sẽ tạo ra đầu ra console tương tự như dưới đây:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12345678
Pdf417MacroSegmentID: 1
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: document.pdf
Pdf417MacroChecksum: 0x9A3F
Pdf417MacroFileSize: 245760
Pdf417MacroTimeStamp: 2024-07-15T14:32:00Z
Pdf417MacroAddressee: John Doe
Pdf417MacroSender: Acme Corp.
MacroPdf417Terminator: True
----------------------------------------
```

Đầu ra xác nhận rằng thư viện đã đọc thành công mã vạch, trích xuất văn bản, và cung cấp mọi trường của MacroPdf417.

## Đọc nhiều mã vạch từ một hình ảnh duy nhất

Nhiều trường hợp thực tế đặt nhiều ký hiệu PDF417 trên một nhãn—ví dụ như một phiếu vận chuyển chứa mã hãng, số theo dõi và tờ khai hải quan. Khối mã ở trên đã **đọc nhiều mã vạch** vì `ReadBarCodes()` trả về một enumerable của tất cả các kết quả phù hợp. Không cần cấu hình bổ sung; bạn chỉ cần lặp qua các kết quả, như đã minh họa.

Nếu bạn muốn giới hạn trình đọc chỉ ở PDF417 tiêu chuẩn (không macro) trong khi vẫn xử lý nhiều mã, hãy thay thế `DecodeType.MacroPdf417` bằng `DecodeType.Pdf417`. Phần còn lại của logic không thay đổi.

## Hiểu dữ liệu mở rộng của MacroPdf417

MacroPdf417 là một phần mở rộng của chuẩn PDF417 thông thường. Nó chia các tải trọng lớn thành nhiều đoạn và thêm một tiêu đề nhỏ mô tả toàn bộ tệp. Các trường quan trọng nhất bao gồm:

- **MacroPdf417FileID** – một định danh duy nhất được chia sẻ bởi tất cả các đoạn của cùng một tệp.
- **MacroPdf417SegmentID** – số thứ tự của đoạn hiện tại.
- **MacroPdf417SegmentsCount** – tổng số đoạn dự kiến.
- **MacroPdf417FileName** – tên tệp tùy chọn được truyền cùng mã vạch.
- **MacroPdf417Checksum** – giá trị kiểm tra lỗi cho toàn bộ tệp.
- **MacroPdf417FileSize** – kích thước của tải trọng nhị phân gốc.
- **MacroPdf417TimeStamp** – dấu thời gian ISO‑8601 khi mã vạch được tạo.
- **MacroPdf417Addressee / Sender** – các trường văn bản tùy chọn để định tuyến.
- **MacroPdf417Terminator** – chỉ ra liệu đoạn này có phải là đoạn cuối cùng hay không.

Khi bạn nhận được tất cả các đoạn, bạn có thể tái tạo lại tệp gốc bằng cách sắp xếp chúng theo `MacroPdf417SegmentID` và nối các giá trị `CodeText`. Logic này rất đơn giản để triển khai một khi bạn đã có các trường dữ liệu.

## Những lỗi thường gặp và mẹo chuyên nghiệp

- **Chất lượng hình ảnh quan trọng** – các tệp PNG/JPEG có độ phân giải thấp hoặc nén mạnh có thể gây mất phát hiện. Sử dụng DPI ít nhất 300 dpi cho các mã vạch được in.
- **Ký hiệu hỗn hợp** – nếu hình ảnh chứa cả MacroPdf417 và PDF417 thông thường, khởi tạo hai trình đọc (mỗi `DecodeType` một) hoặc sử dụng `DecodeType.AllSupported` và lọc kết quả bằng `result.CodeTypeName`.
- **Tiêu thụ bộ nhớ** – câu lệnh `using` giải phóng `BarCodeReader` ngay lập tức, ngăn các bộ đệm hình ảnh lớn tồn tại trong bộ nhớ.
- **An toàn đa luồng** – `BarCodeReader` không an toàn khi dùng đa luồng. Tạo một thể hiện riêng cho mỗi luồng nếu bạn giải mã hình ảnh song song.
- **Xử lý lỗi** – bao bọc lời gọi `ReadBarCodes()` trong khối try/catch để bắt `BarCodeException` cho các hình ảnh bị hỏng.

## Tóm tắt ví dụ hoạt động đầy đủ

Dưới đây là chương trình hoàn chỉnh mà bạn có thể sao chép vào một dự án console mới. Nó bao gồm tất cả các chỉ thị `using`, một hằng số cho đường dẫn hình ảnh, và mẫu giải phóng tài nguyên.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

namespace Pdf417ReaderDemo
{
    class Program
    {
        static void Main()
        {
            const string imagePath = @"YOUR_DIRECTORY\MacroPdf417.png";

            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    var macro = result.Extended.Pdf417;
                    Console.WriteLine($"Pdf417MacroFileID: {macro.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {macro.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {macro.MacroPdf417SegmentsCount}");
                    Console.WriteLine($"Pdf417MacroFileName: {macro.MacroPdf417FileName}");
                    Console.WriteLine($"Pdf417MacroChecksum: {macro.MacroPdf417Checksum}");
                    Console.WriteLine($"Pdf417MacroFileSize: {macro.MacroPdf417FileSize}");
                    Console.WriteLine($"Pdf417MacroTimeStamp: {macro.MacroPdf417TimeStamp}");
                    Console.WriteLine($"Pdf417MacroAddressee: {macro.MacroPdf417Addressee}");
                    Console.WriteLine($"Pdf417MacroSender: {macro.MacroPdf417Sender}");
                    Console.WriteLine($"MacroPdf417Terminator: {macro.MacroPdf417Terminator}");
                    Console.WriteLine(new string('-', 40));
                }
            }

            Console.WriteLine("Decoding completed. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

Biên dịch bằng `dotnet build` và chạy bằng `dotnet run`. Console sẽ in dữ liệu cơ bản của mỗi mã vạch và toàn bộ payload MacroPdf417.

## Các bước tiếp theo

- **Tái tạo các tệp đa phần** – thu thập tất cả các đoạn, sắp xếp theo `MacroPdf417SegmentID`, và nối `CodeText` để

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch PDF417 – Mã hóa PDF417 Compact](/barcode/english/net/compact-pdf417-encoding/)
- [Cách đọc mã vạch PDF417 với ký tự Thổ Nhĩ Kỳ trong Java](/barcode/english/java/multilingual-support/recognizing-pdf417-turkish-characters/)
- [Cách sử dụng Aspose cho mã vạch PDF417 (Tiếng Trung) trong Java](/barcode/english/java/multilingual-support/recognizing-pdf417-chinese-characters/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}