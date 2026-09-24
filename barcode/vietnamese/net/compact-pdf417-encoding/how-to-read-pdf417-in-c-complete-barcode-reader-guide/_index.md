---
category: general
date: 2026-08-09
description: Cách đọc PDF417 trong C# bằng BarCodeReader. Tìm hiểu cách đọc các tệp
  PNG chứa mã vạch, xử lý nhiều mã vạch và trích xuất siêu dữ liệu mở rộng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to read pdf417
- c# barcode reader
- read multiple barcodes
- read barcode png
- read barcode extended
language: vi
lastmod: 2026-08-09
og_description: Cách đọc PDF417 trong C# với Aspose.BarCode. Hướng dẫn này cho bạn
  biết cách đọc các tệp PNG chứa mã vạch, xử lý nhiều mã vạch trong một hình ảnh và
  truy xuất siêu dữ liệu PDF417 mở rộng.
og_image_alt: Screenshot of C# BarCodeReader console output displaying PDF417 metadata
og_title: Cách đọc PDF417 trong C# – hướng dẫn đọc mã vạch
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  headline: How to read PDF417 in C# – complete barcode reader guide
  type: TechArticle
- description: How to read PDF417 in C# using the BarCodeReader. Learn to read barcode
    PNG files, handle multiple barcodes, and extract extended metadata.
  name: How to read PDF417 in C# – complete barcode reader guide
  steps:
  - name: Verify the file exists before creating the reader.
    text: Verify the file exists before creating the reader.
  - name: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
    text: Use `Image.FromFile` only when you need to pre‑process (rotate, crop). The
      `BarCodeReader` can open the file directly, which avoids extra memory allocation.
  - name: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
    text: If the PNG contains transparency, the reader still works because the barcode
      is rendered on opaque pixels.
  type: HowTo
tags:
- barcode
- C#
- PDF417
title: Cách đọc PDF417 trong C# – hướng dẫn đầy đủ về trình đọc mã vạch
url: /vi/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc PDF417 trong C# – hướng dẫn đọc mã vạch hoàn chỉnh

Nếu bạn cần **cách đọc PDF417** trong một ứng dụng .NET, hướng dẫn này cung cấp cho bạn một giải pháp sẵn sàng chạy. Bạn sẽ thấy cách đọc một mã vạch PNG, xử lý nhiều mã vạch trong cùng một hình ảnh, và lấy các trường PDF417 mở rộng mà nhiều máy quét ẩn.

Việc đọc mã vạch PDF417 là phổ biến trong logistics, bán vé và quản lý tài liệu. Đến cuối hướng dẫn này, bạn có thể giải mã một hình ảnh Macro PDF417, hiển thị mọi kết quả, và sử dụng thông tin bổ sung (ID tệp, số đoạn, dấu thời gian, v.v.) trong logic kinh doanh của mình.

## Yêu cầu trước

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.7+)
- Visual Studio 2022 hoặc bất kỳ IDE C# nào
- **Aspose.BarCode for .NET** (bản dùng thử miễn phí hoặc gói NuGet có bản quyền)
- Một hình ảnh PNG chứa mã vạch Macro PDF417 (tệp mẫu có tên `ExtPDF417Meta.png`)

> **Mẹo:** Cài đặt thư viện bằng console NuGet:  
> `dotnet add package Aspose.BarCode`

## Cách đọc PDF417 với BarCodeReader trong C#

Lõi của giải pháp là lớp `BarCodeReader`. Nó nhận một đường dẫn hình ảnh và một enum `DecodeType` cho biết engine nên tìm kiếm ký hiệu nào.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.ReadEngine;

class Pdf417Demo
{
    static void Main()
    {
        // Step 1: Create a BarCodeReader for a Macro PDF417 image
        using (BarCodeReader reader = new BarCodeReader(
            "YOUR_DIRECTORY/ExtPDF417Meta.png",
            DecodeType.MacroPdf417))
        {
            // Step 2: Read all barcodes from the image
            foreach (BarCodeResult result in reader.ReadBarCodes())
            {
                // Step 3: Output basic barcode information
                Console.WriteLine($"CodeType: {result.CodeTypeName}");
                Console.WriteLine($"CodeText: {result.CodeText}");

                // Step 4: Display Macro PDF417 extended metadata
                Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended.Pdf417.MacroPdf417FileName}");
                Console.WriteLine($"Pdf417MacroChecksum: {result.Extended.Pdf417.MacroPdf417Checksum}");
                Console.WriteLine($"Pdf417MacroFileSize: {result.Extended.Pdf417.MacroPdf417FileSize}");
                Console.WriteLine($"Pdf417MacroTimeStamp: {result.Extended.Pdf417.MacroPdf417TimeStamp}");
                Console.WriteLine($"Pdf417MacroAddressee: {result.Extended.Pdf417.MacroPdf417Addressee}");
                Console.WriteLine($"Pdf417MacroSender: {result.Extended.Pdf417.MacroPdf417Sender}");
                Console.WriteLine($"MacroPdf417Terminator: {result.Extended.Pdf417.MacroPdf417Terminator}");
                Console.WriteLine(new string('-', 40));
            }
        }
    }
}
```

### Tại sao cách này hoạt động

- **`DecodeType.MacroPdf417`** cho biết bộ đọc nên tìm kiếm biến thể Macro PDF417, vốn lưu trữ các trường bổ sung mà bạn thấy ở bước 4.
- Khối `using` sẽ tự động giải phóng bộ đọc, giải phóng các handle tệp.
- `ReadBarCodes()` trả về **tất cả** các mã vạch khớp với loại được yêu cầu, đáp ứng yêu cầu *đọc nhiều mã vạch* ngay cả khi hình ảnh chỉ chứa một mã.

Chạy chương trình sẽ in ra đầu ra tương tự như:

```
CodeType: MacroPdf417
CodeText: 1234567890
Pdf417MacroFileID: 1
Pdf417MacroSegmentID: 0
Pdf417MacroSegmentsCount: 3
Pdf417MacroFileName: invoice_2023.pdf
Pdf417MacroChecksum: 0x1A2B
Pdf417MacroFileSize: 254321
Pdf417MacroTimeStamp: 2023-03-15T10:45:00Z
Pdf417MacroAddressee: ACME Corp.
Pdf417MacroSender: Warehouse 7
MacroPdf417Terminator: True
----------------------------------------
```

## Sử dụng bộ đọc mã vạch C# để đọc nhiều mã vạch

Nếu một hình ảnh chứa nhiều ký hiệu Macro PDF417 (ví dụ, một trang quét với một loạt vé), vòng lặp `foreach` giống nhau sẽ xử lý từng ký hiệu. Không cần mã bổ sung; bộ đọc sẽ tổng hợp kết quả nội bộ.

```csharp
// Example: processing a batch image
using (BarCodeReader batchReader = new BarCodeReader(
    "batch.png", DecodeType.MacroPdf417))
{
    int index = 0;
    foreach (BarCodeResult item in batchReader.ReadBarCodes())
    {
        Console.WriteLine($"--- Barcode #{++index} ---");
        Console.WriteLine($"Text: {item.CodeText}");
        // extended fields are accessed the same way
    }
}
```

### Những cạm bẫy thường gặp

- **Định dạng ảnh:** Bộ đọc hỗ trợ PNG, JPEG, BMP và TIFF. Nếu bạn thử một định dạng mà nó không thể giải mã, bạn sẽ nhận được một bộ sưu tập rỗng. Đó là lý do tại sao hướng dẫn nhấn mạnh *đọc mã vạch PNG*.
- **Độ phân giải:** Ảnh độ phân giải thấp (< 300 dpi) có thể gây mất các đoạn. Hãy tăng độ phân giải hoặc yêu cầu quét chất lượng cao hơn khi có thể.
- **Cờ Macro:** Quên `DecodeType.MacroPdf417` sẽ giới hạn engine chỉ đọc PDF417 thông thường và loại bỏ dữ liệu mở rộng. Luôn chỉ định loại macro khi bạn cần các trường *đọc mã vạch mở rộng*.

## Đọc tệp PNG chứa mã vạch – các thực hành tốt nhất

Làm việc với tệp PNG rất đơn giản vì định dạng này giữ nguyên dữ liệu pixel không mất mát. Dưới đây là danh sách kiểm tra nhanh:

1. Xác minh tệp tồn tại trước khi tạo bộ đọc.  
   ```csharp
   if (!File.Exists(path))
       throw new FileNotFoundException($"File not found: {path}");
   ```
2. Sử dụng `Image.FromFile` chỉ khi bạn cần tiền xử lý (xoay, cắt). `BarCodeReader` có thể mở tệp trực tiếp, tránh việc cấp phát bộ nhớ thêm.
3. Nếu PNG có độ trong suốt, bộ đọc vẫn hoạt động vì mã vạch được hiển thị trên các pixel không trong suốt.

## Truy cập siêu dữ liệu PDF417 mở rộng

Đối tượng `Extended.Pdf417` cung cấp mọi trường tùy chọn được định nghĩa trong đặc tả PDF417. Bạn có thể ánh xạ các trường này vào mô hình miền, lưu chúng vào cơ sở dữ liệu, hoặc sử dụng để xác thực.

```csharp
public class Pdf417Metadata
{
    public int FileID { get; set; }
    public int SegmentID { get; set; }
    public int SegmentsCount { get; set; }
    public string FileName { get; set; }
    public string Checksum { get; set; }
    public long FileSize { get; set; }
    public DateTime TimeStamp { get; set; }
    public string Addressee { get; set; }
    public string Sender { get; set; }
    public bool Terminator { get; set; }
}
```

Điền dữ liệu vào mô hình:



## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đọc mã DataMatrix với Aspose.BarCode cho .NET](/barcode/english/net/datamatrix-barcode-reading/)
- [Cách tạo mã vạch – Compact PDF417 với Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [Đọc mã DataMatrix C# – Tạo chế độ DataMatrix (Tự động)](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}