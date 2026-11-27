---
category: general
date: 2026-11-27
description: Tạo hình ảnh mã vạch trong C# và lưu dưới định dạng PNG với Aspose.BarCode
  – hướng dẫn từng bước.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- save image PNG format
- Aspose.BarCode C#
- Macro PDF417 barcode
- barcode generation .NET
language: vi
lastmod: 2026-11-27
og_description: Tạo hình ảnh mã vạch trong C# và lưu dưới định dạng PNG bằng Aspose.BarCode.
  Thực hiện theo hướng dẫn này để tạo mã vạch Macro PDF417 từng bước.
og_image_alt: Screenshot of a created barcode image saved as PNG
og_title: Tạo hình ảnh mã vạch và lưu dưới định dạng PNG trong C# – hướng dẫn đầy
  đủ
schemas:
- author: Aspose
  dateModified: '2026-11-27'
  description: Create barcode image in C# and save image PNG format with Aspose.BarCode
    – step‑by‑step guide.
  headline: Create barcode image and save PNG format in C#
  type: TechArticle
tags:
- barcode
- C#
- Aspose
title: Tạo hình ảnh mã vạch và lưu ở định dạng PNG trong C#
url: /vi/net/one-dimensional-barcode-types/create-barcode-image-and-save-png-format-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch và lưu ở định dạng PNG trong C#

Nếu bạn cần **tạo hình ảnh mã vạch** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách tạo mã vạch Macro PDF417 và **lưu hình ảnh ở định dạng PNG** bằng cách sử dụng Aspose.BarCode. Bạn sẽ nhận được một ví dụ đầy đủ, có thể chạy được và một giải thích cho mỗi thiết lập để bạn có thể điều chỉnh mã cho các yêu cầu của mình.

Việc tạo mã vạch không chỉ là gọi một phương thức duy nhất; bạn phải cấu hình kích thước mô-đun, các tham số macro và định dạng đầu ra. Khi kết thúc hướng dẫn này, bạn sẽ hiểu tại sao mỗi thuộc tính quan trọng, cách xử lý các trường hợp biên thường gặp, và cách xác minh rằng tệp PNG đã được ghi đúng.

## Những gì bạn cần

- .NET 6.0 hoặc mới hơn (mã cũng hoạt động với .NET Framework 4.6+)
- Aspose.BarCode cho .NET (có sẵn qua NuGet: `Install-Package Aspose.BarCode`)
- Một IDE như Visual Studio 2022 hoặc Visual Studio Code
- Quyền ghi vào thư mục nơi tệp PNG sẽ được lưu

## Bước 1: Khởi tạo trình tạo mã vạch

Bước đầu tiên là tạo một thể hiện `BarcodeGenerator` chỉ định ký hiệu `EncodeTypes.MacroPdf417` và văn bản bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;

// Step 1: Initialize a Macro PDF417 barcode generator with the desired text
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent steps go here
}
```

**Tại sao điều này quan trọng:**  
`EncodeTypes.MacroPdf417` cho thư viện biết sử dụng biến thể PDF417 macro, hỗ trợ phân đoạn tệp và siêu dữ liệu bổ sung. Hàm khởi tạo cũng nhận văn bản có thể đọc được bởi con người sẽ được mã hoá trong mã vạch.

## Bước 2: Định nghĩa kích thước mô-đun (X‑dimension)

X‑dimension kiểm soát độ rộng của một mô-đun mã vạch duy nhất (phần tử đen/trắng nhỏ nhất). Giá trị `2` pixel hoạt động tốt cho PNG hiển thị trên màn hình.

```csharp
    // Step 2: Define the module size (X‑dimension) in pixels
    generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Mẹo thực tế:**  
Nếu bạn dự định in mã vạch, tăng giá trị pixel (ví dụ, `4` hoặc `5`) để tránh kết quả mờ trên máy in độ phân giải thấp.

## Bước 3: Cấu hình các tham số macro PDF417

Macro PDF417 thêm một số trường tùy chọn giúp xác định tệp nguồn, thứ tự đoạn và kiểm tra tính toàn vẹn. Dưới đây là một bộ đầy đủ các tham số điển hình; bạn có thể bỏ qua bất kỳ trường nào không cần.

```csharp
    // Step 3: Set PDF417 macro parameters
    generator.Parameters.Barcode.Pdf417.Columns = 5;                     // Number of columns per row
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;    // Unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;      // Current segment number
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20; // Total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01"; // Logical file name
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;  // Approximate file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

**Tại sao các trường này hữu ích:**  

| Parameter | Purpose |
|-----------|---------|
| `Columns` | Kiểm soát độ rộng của mã vạch; ít cột hơn tạo ra mã vạch cao hơn. |
| `MacroPdf417FileID` | Mã định danh duy nhất liên kết tất cả các đoạn lại với nhau. |
| `MacroPdf417SegmentID` | Vị trí của đoạn này trong toàn bộ tệp. |
| `MacroPdf417SegmentsCount` | Tổng số đoạn; cần thiết để tái tạo. |
| `MacroPdf417FileName` | Tên có thể đọc được bởi con người, có thể hiển thị bởi các ứng dụng quét. |
| `MacroPdf417Checksum` | Giúp người nhận xác minh tính toàn vẹn dữ liệu (CCITT‑16). |
| `MacroPdf417FileSize` | Gợi ý kích thước tùy chọn cho tệp gốc. |
| `MacroPdf417TimeStamp` | Dấu thời gian của việc tạo tệp gốc. |
| `MacroPdf417Addressee` / `MacroPdf417Sender` | Siêu dữ liệu cho việc định tuyến hoặc sở hữu. |
| `MacroPdf417Terminator` | Chỉ ra liệu đây là đoạn cuối cùng (`Set`) hay một đoạn trung gian (`Unset`). |

**Trường hợp biên:** Nếu bạn tạo một mã vạch một đoạn, đặt `MacroPdf417SegmentsCount` thành `1` và `MacroPdf417Terminator` thành `Unset`. Thư viện sẽ tự động bỏ qua các trường liên quan đến đoạn không áp dụng.

## Bước 4: Lưu mã vạch đã tạo dưới dạng hình ảnh PNG

Cuối cùng, gọi `Save` với đường dẫn tệp và giá trị enum `BarCodeImageFormat.Png`. Phương thức sẽ ghi hình ảnh vào đĩa ở định dạng PNG không mất dữ liệu.

```csharp
    // Step 4: Save the generated barcode as a PNG image
    string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
    generator.Save(outputPath, BarCodeImageFormat.Png);
}
```

**Tại sao lại PNG?**  
PNG giữ nguyên giá trị pixel, điều này rất quan trọng đối với các máy quét mã vạch dựa vào độ tương phản sắc nét. Nén JPEG có thể tạo ra các artefact làm hỏng mẫu mã vạch.

### Xác minh đầu ra

Sau khi chương trình chạy, bạn sẽ thấy một tệp có tên `ExtPDF417Meta.png` trong thư mục thực thi. Mở nó bằng bất kỳ trình xem ảnh nào sẽ hiển thị một mã vạch hình chữ nhật dày đặc. Bạn có thể xác minh tính đúng đắn bằng cách quét hình ảnh bằng một ứng dụng đọc mã vạch di động hỗ trợ PDF417 macro; ứng dụng thường sẽ hiển thị siêu dữ liệu được nhúng (ID tệp, số đoạn, v.v.).

## Những lỗi thường gặp và cách tránh chúng

| Symptom | Likely cause | Fix |
|---------|--------------|-----|
| Mã vạch xuất hiện mờ | X‑dimension quá thấp so với DPI đã chọn | Tăng `XDimension.Pixels` hoặc render ở DPI cao hơn (`generator.Parameters.ImageResolution`). |
| Máy quét báo lỗi “checksum” | Giá trị `MacroPdf417Checksum` không đúng | Để Aspose tự tính checksum bằng cách bỏ qua thuộc tính này, hoặc đảm bảo giá trị khớp với thuật toán CCITT‑16. |
| Tệp PNG rỗng hoặc không được tạo | Đường dẫn đầu ra không hợp lệ hoặc thiếu quyền ghi | Sử dụng `Path.Combine` với một thư mục đã biết có thể ghi được (ví dụ, `Environment.GetFolderPath(Environment.SpecialFolder.Desktop)`). |
| Các trường macro bị bỏ qua | `EncodeTypes` được đặt thành `Pdf417` thông thường thay vì `MacroPdf417` | Xác minh rằng `EncodeTypes.MacroPdf417` được sử dụng trong hàm khởi tạo. |

## Ví dụ đầy đủ, có thể chạy

Dưới đây là chương trình hoàn chỉnh bạn có thể sao chép vào một ứng dụng console. Nó biên dịch với .NET 6.0 và tạo ra tệp PNG đã mô tả ở trên.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize a Macro PDF417 barcode generator with the desired text
        using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
        {
            // Define the module size (X-dimension) in pixels
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // Set PDF417 macro parameters
            generator.Parameters.Barcode.Pdf417.Columns = 5;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
            generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234; // CCITT‑16 checksum
            generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
            generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2019, 11, 1);
            generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
            generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

            // Save the generated barcode as a PNG image
            string outputPath = Path.Combine(Environment.CurrentDirectory, "ExtPDF417Meta.png");
            generator.Save(outputPath, BarCodeImageFormat.Png);

            Console.WriteLine($"Barcode image saved to: {outputPath}");
        }
    }
}
```

**Kết quả mong đợi (console):**

```
Barcode image saved to: C:\YourProject\bin\Debug\net6.0\ExtPDF417Meta.png
```

Mở `ExtPDF417Meta.png` sẽ hiển thị một mã vạch Macro PDF417 rõ ràng, sẵn sàng để quét.

## Các bước tiếp theo

- **Thay đổi định dạng ảnh** – thay `BarCodeImageFormat.Png` bằng `Jpeg` hoặc `Bmp` nếu bạn cần loại tệp khác. Hãy nhớ rằng JPEG tạo ra các artefact nén, có thể ảnh hưởng đến độ tin cậy khi quét.
- **Điều chỉnh độ phân giải** – sử dụng

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng dựa trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, hoạt động với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo hình ảnh mã vạch với Aspose.Barcode trong C#](/barcode/english/python-java/general/how-to-create-barcode-image-with-aspose-barcode-in-c/)
- [Cách tạo hình ảnh mã vạch PDF417 trong C# với tùy chọn Macro PDF417](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-image-in-c-with-macro-pdf417-op/)
- [Cách đọc mã vạch từ hình ảnh bằng C# với Aspose.BarCode – hướng dẫn từng bước](/barcode/english/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}