---
category: general
date: 2026-10-05
description: Aspose Barcode Generator C# cho phép bạn thêm dữ liệu macro và tạo mã
  vạch PDF417 một cách dễ dàng. Học từng bước cách thêm siêu dữ liệu macro và tạo
  hình ảnh PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- aspose barcode generator c#
- how to add macro
- how to generate pdf417
language: vi
lastmod: 2026-10-05
og_description: Aspose Barcode Generator C# cho bạn thấy cách thêm siêu dữ liệu macro
  và tạo mã vạch PDF417 chỉ trong vài dòng mã.
og_image_alt: Screenshot of a MacroPdf417 barcode created with Aspose Barcode Generator
  C#
og_title: Trình tạo mã vạch Aspose Barcode C# – thêm macro và tạo mã vạch PDF417
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Aspose Barcode Generator C# lets you add macro data and generate PDF417
    barcodes effortlessly. Learn step‑by‑step how to add macro metadata and create
    a PDF417 image.
  headline: How to use Aspose Barcode Generator C# for a MacroPdf417 barcode
  type: TechArticle
tags:
- barcode
- csharp
- aspose
title: Cách sử dụng Aspose Barcode Generator C# cho mã vạch MacroPdf417
url: /vi/net/compact-pdf417-encoding/how-to-use-aspose-barcode-generator-c-for-a-macropdf417-barc/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng Aspose Barcode Generator C# để tạo mã vạch MacroPdf417

Nếu bạn cần tạo một mã vạch MacroPdf417 trong C#, **Aspose Barcode Generator C#** cung cấp một API ngắn gọn, xử lý cả hình ảnh mã vạch và siêu dữ liệu macro cần thiết. Hướng dẫn này sẽ chỉ cho bạn cách thêm thông tin macro và tạo hình ảnh PDF417 chỉ trong vài bước.

Bạn sẽ học cách cấu hình các tham số hiển thị, nhúng các trường macro như file ID và timestamp, và lưu kết quả dưới dạng PNG. Không cần công cụ bên ngoài—chỉ cần thư viện Aspose.BarCode và môi trường phát triển .NET.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 hoặc phiên bản mới hơn được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE C# nào)  
* Bản quyền hoặc bản dùng thử của **Aspose.BarCode for .NET**  

Mã nguồn hoạt động trên Windows, Linux và macOS vì thư viện không phụ thuộc nền tảng.

## Bước 1: Cài đặt gói NuGet Aspose.BarCode

Mở dự án của bạn trong Visual Studio, sau đó chạy lệnh sau trong **Package Manager Console**:

```powershell
Install-Package Aspose.BarCode
```

Lệnh này sẽ thêm assembly `Aspose.BarCode` và các phụ thuộc của nó vào dự án.

## Bước 2: Tạo đối tượng barcode generator

Dòng đầu tiên tạo một đối tượng `BarcodeGenerator` cho ký hiệu **MacroPdf417** và cung cấp văn bản bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

// Step 2: Initialise the generator with MacroPdf417 and the payload text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
{
    // subsequent configuration goes here
}
```

*Lý do quan trọng*: Giá trị `EncodeTypes.MacroPdf417` thông báo cho thư viện biết sẽ có các trường liên quan đến macro, những trường này sẽ được thiết lập ở bước tiếp theo.

## Bước 3: Định nghĩa giao diện hiển thị

Bạn có thể điều chỉnh kích thước của mỗi module (ô đen hoặc trắng nhỏ nhất) và số cột trong ma trận PDF417. Việc thay đổi `XDimension` ảnh hưởng đến độ phân giải tổng thể của hình ảnh.

```csharp
    // Step 3: Visual settings
    generator.Parameters.Barcode.XDimension.Pixels = 2;          // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns in the symbol
```

Tăng `Columns` sẽ giảm chiều cao của mã vạch, trong khi `XDimension` lớn hơn sẽ làm hình ảnh rõ nét hơn trên màn hình DPI cao.

## Bước 4: Thêm siêu dữ liệu macro (cách thêm macro)

MacroPdf417 yêu cầu một số trường bổ sung mô tả file nguồn và cách phân đoạn. Các thuộc tính sau ánh xạ trực tiếp tới các thông số macro của PDF417:

```csharp
    // Step 4: Macro fields – how to add macro data
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;               // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;                  // current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;              // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";             // optional file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                // CCITT‑16 placeholder
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;              // size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = 
        new DateTime(2019, 11, 1);                                                   // creation timestamp
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";            // recipient identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";               // sender identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = 
        Pdf417MacroTerminator.Set;                                                   // marks the last segment
```

*Tại sao cần các trường này*:  
* `MacroPdf417FileID` liên kết tất cả các đoạn lại với nhau, đảm bảo máy quét có thể ghép lại tài liệu gốc.  
* `MacroPdf417SegmentID` và `MacroPdf417SegmentsCount` cho bộ giải mã biết thứ tự và tổng số phần.  
* `MacroPdf417FileSize` và `MacroPdf417Checksum` cung cấp kiểm tra toàn vẹn, rất hữu ích cho việc truyền dữ liệu lớn.

## Bước 5: Lưu hình ảnh mã vạch (cách tạo pdf417)

Cuối cùng, ghi mã vạch ra đĩa. Phương thức `Save` nhận đường dẫn file và định dạng ảnh. PNG giữ được các cạnh sắc nét của mã vạch mà không bị nén gây mất chất lượng.

```csharp
    // Step 5: Save the generated barcode – how to generate pdf417 image
    generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
}
```

Khi chương trình chạy, bạn sẽ thấy **ExtPDF417Meta.png** trong thư mục output. Mở ảnh sẽ hiển thị một mã vạch MacroPdf417 sạch sẽ, sẵn sàng để in hoặc nhúng vào PDF.

### Kết quả mong đợi

| Tên file            | Định dạng | Kích thước (xấp xỉ) |
|---------------------|-----------|----------------------|
| ExtPDF417Meta.png   | PNG       | 300 × 150 px (phụ thuộc vào `XDimension`) |

Quét ảnh bằng trình đọc hỗ trợ PDF417 (ví dụ: ZXing, Aspose.BarCode for .NET) sẽ trả về văn bản gốc **“Åspóse.Barcóde©”** cùng với tất cả các trường macro.

## Các lỗi thường gặp và cách khắc phục

| Vấn đề | Nguyên nhân | Giải pháp |
|--------|-------------|-----------|
| **EncodeTypes không đúng** | Sử dụng `EncodeTypes.Pdf417` thay vì `EncodeTypes.MacroPdf417` sẽ tắt các trường macro. | Luôn khởi tạo generator với `EncodeTypes.MacroPdf417`. |
| **Thiếu trường macro** | Một số máy quét sẽ bỏ qua mã vạch nếu các trường macro bắt buộc bị thiếu. | Điền ít nhất `FileID`, `SegmentID`, `SegmentsCount` và `Terminator`. |
| **XDimension quá nhỏ** | Giá trị dưới 1 pixel có thể tạo ra mã vạch không đọc được trên màn hình độ phân giải thấp. | Giữ `XDimension` ≥ 2 pixel cho hầu hết các trường hợp màn hình và in. |
| **Lỗi đường dẫn file** | Cung cấp đường dẫn tương đối không tồn tại sẽ gây ngoại lệ. | Dùng `Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png")` hoặc đường dẫn tuyệt đối. |

## Toàn bộ mã nguồn

Dưới đây là ví dụ hoàn chỉnh, có thể chạy được, bạn có thể sao chép vào một dự án console mới.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeImageFormat;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Initialise the generator with MacroPdf417 and the payload text
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Åspóse.Barcóde©"))
            {
                // Visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;          // module width
                generator.Parameters.Barcode.Pdf417.Columns = 5;           // number of columns

                // Macro fields – how to add macro
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Save the barcode – how to generate pdf417
                generator.Save("ExtPDF417Meta.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("MacroPdf417 barcode generated successfully.");
        }
    }
}
```

Chạy chương trình (`dotnet run`). Sau khi thực thi, console sẽ in thông báo thành công và file PNG sẽ xuất hiện trong thư mục output của dự án.

## Các bước tiếp theo

* **Mã hoá dữ liệu lớn** – Tăng `Columns` hoặc điều chỉnh `Rows` (qua `Pdf417.Rows`) để chứa nhiều ký tự hơn.  
* **Nhúng vào PDF** – Sử dụng Aspose.PDF để chèn PNG đã tạo vào tài liệu.  
* **Xác minh bằng quét** – Tận dụng `Aspose.BarCode.Reader` để giải mã mã vạch và xác nhận các trường macro một cách lập trình.  

Khám phá các chủ đề này sẽ giúp bạn hiểu sâu hơn **cách tạo mã vạch PDF417** có thông tin macro phong phú và chuẩn bị cho các trường hợp thực tế như xử lý tài liệu hàng loạt hoặc trao đổi dữ liệu an toàn.

---

*Chúc lập trình vui vẻ! Nếu bạn thấy hướng dẫn này hữu ích, hãy chia sẻ với đồng nghiệp hoặc đánh dấu sao cho kho lưu trữ Aspose.BarCode trên GitHub.*

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây liên quan chặt chẽ và mở rộng các kỹ thuật đã trình bày trong bài này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ và giải thích từng bước để giúp bạn làm chủ các tính năng API khác và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)
- [How to generate PDF417 barcode in C# with Barcode Generator](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-with-barcode-generator/)
- [Aspose barcode example: generate Macro PDF417 in C#](/barcode/english/net/compact-pdf417-encoding/aspose-barcode-example-generate-macro-pdf417-in-c/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}