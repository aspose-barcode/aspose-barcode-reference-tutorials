---
category: general
date: 2026-09-29
description: Cách giải mã mã vạch PDF417 trong C# bằng Aspose.BarCode. Tìm hiểu ví
  dụ trình đọc mã vạch cho thấy cách đọc hình ảnh mã vạch và trích xuất dữ liệu macro.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to decode pdf417
- how to read barcode
- barcode reader example
- read pdf417 barcode
- read barcode image c#
language: vi
lastmod: 2026-09-29
og_description: Cách giải mã mã vạch PDF417 trong C# với Aspose.BarCode. Hướng dẫn
  này trình bày một ví dụ trình đọc mã vạch đã sẵn sàng chạy để đọc hình ảnh mã vạch.
og_image_alt: Screenshot of C# code decoding a PDF417 macro barcode and printing its
  fields
og_title: Cách giải mã mã vạch PDF417 trong C# – ví dụ đầy đủ về trình đọc mã vạch
schemas:
- author: Aspose
  dateModified: '2026-09-29'
  description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  headline: How to decode PDF417 barcodes in C# – step‑by‑step guide
  type: TechArticle
- description: How to decode PDF417 barcodes in C# using Aspose.BarCode. Learn a barcode
    reader example that shows how to read barcode images and extract macro data.
  name: How to decode PDF417 barcodes in C# – step‑by‑step guide
  steps:
  - name: Expected console output
    text: '``` Pdf417MacroFileID: 12345 Pdf417MacroSegmentID: 1 Pdf417MacroFileName:
      Invoice_2026_09_29.pdf ```'
  - name: No barcode detected
    text: '```csharp var results = reader.ReadBarCodes().ToList(); if (!results.Any())
      { Console.WriteLine("No PDF417 barcode found in the image."); return; } ```'
  - name: Unsupported image format
    text: Aspose.BarCode supports PNG, JPEG, BMP, TIFF, and GIF. Attempting to read
      a RAW or WebP file throws `ArgumentException`. Convert the image to a supported
      format before feeding it to the reader.
  - name: Large macro files
    text: Macro‑PDF417 can span many segments. To reconstruct the original file you
      must collect all segments (ordered by `MacroPdf417SegmentID`) and concatenate
      their payloads. The example above only prints individual segment metadata; a
      production implementation would store each segment in a dictionary, the
  - name: Performance tip
    text: If you process thousands of images, reuse a single `BarCodeReader` instance
      with the `SetImage` method instead of creating a new object for each file. This
      reduces memory allocations and speeds up decoding.
  type: HowTo
tags:
- barcode
- pdf417
- csharp
- Aspose.BarCode
title: Cách giải mã mã vạch PDF417 trong C# – hướng dẫn từng bước
url: /vi/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách giải mã PDF417 mã vạch trong C# – hướng dẫn từng bước

Nếu bạn cần **cách giải mã PDF417** mã vạch trong C#, hướng dẫn này cung cấp cho bạn một giải pháp hoàn chỉnh, có thể chạy được. Bạn sẽ thấy một **ví dụ trình đọc mã vạch** minh họa **cách đọc mã vạch** từ hình ảnh, trích xuất thông tin macro và in kết quả ra console.

Giải mã PDF417 thường gặp khi xử lý nhãn vận chuyển, vé, hoặc chứng minh thư chính phủ. Khi kết thúc hướng dẫn này, bạn sẽ có thể đọc hình ảnh mã vạch PDF417, truy cập các trường macro của nó và xử lý các trường hợp đặc biệt thường gặp. Không cần tài liệu bên ngoài – mọi thứ bạn cần đã được bao gồm.

## Những gì bạn sẽ học

- Cài đặt thư viện Aspose.BarCode cho .NET  
- Tạo một `BarCodeReader` mà **đọc dữ liệu mã vạch PDF417** từ tệp PNG hoặc JPEG  
- Duyệt qua các đối tượng `BarCodeResult` và lấy các thuộc tính macro‑PDF417  
- Xử lý các vấn đề thường gặp như định dạng hình ảnh không được hỗ trợ hoặc thiếu dữ liệu macro  

## Yêu cầu trước

| Requirement | Reason |
|-------------|--------|
| .NET 6.0 SDK hoặc mới hơn | Cung cấp môi trường chạy cho các dự án C# |
| Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET) | Cho phép tạo dự án và gỡ lỗi dễ dàng |
| Gói NuGet **Aspose.BarCode** | Cung cấp lớp `BarCodeReader` được sử dụng trong ví dụ |
| Hình ảnh macro PDF417 (ví dụ, `ExtPDF417Meta.png`) | Tệp nguồn mà trình đọc sẽ giải mã |

> **Mẹo:** Nếu bạn không có hình ảnh PDF417, bạn có thể tạo một hình ảnh bằng bản demo trực tuyến miễn phí của Aspose.BarCode hoặc quét một nhãn thực.

## Bước 1: Cài đặt Aspose.BarCode qua NuGet

Mở terminal trong thư mục giải pháp của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm phiên bản ổn định mới nhất của Aspose.BarCode vào dự án của bạn và cập nhật tệp `.csproj`. Thư viện này triển khai chức năng **đọc hình ảnh mã vạch C#** cho hàng chục loại mã vạch, bao gồm PDF417.

## Bước 2: Tạo một BarCodeReader để **cách giải mã PDF417**

Cốt lõi của quy trình **cách đọc mã vạch** là `BarCodeReader`. Bạn phải cung cấp cho trình đọc cả đường dẫn tệp và loại mã vạch mong muốn (`DecodeType.MacroPdf417`). Cung cấp `DecodeType` chính xác sẽ cải thiện tốc độ và độ chính xác của việc phát hiện.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

// Adjust the path to point at your PDF417 macro image
string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

// The reader is disposable; wrap it in a using block to release resources automatically.
using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
{
    // Step 3 is inside this block.
}
```

**Tại sao điều này quan trọng:**  
- `DecodeType.MacroPdf417` báo cho engine tìm các trường macro‑PDF417 (ID tệp, ID đoạn, v.v.).  
- Sử dụng `using` đảm bảo luồng hình ảnh nền được đóng, ngăn ngừa các vấn đề khóa tệp trên Windows.

## Bước 3: Duyệt qua các mã vạch được phát hiện

Một hình ảnh duy nhất có thể chứa nhiều mã vạch. Phương thức `ReadBarCodes()` trả về một `IEnumerable<BarCodeResult>` mà bạn có thể lặp qua.

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Inside the loop we will extract macro data.
}
```

Nếu hình ảnh không chứa bất kỳ ký hiệu PDF417 nào, phần thân vòng lặp sẽ không bao giờ thực thi, và bạn có thể xử lý trường hợp này sau vòng lặp (xem phần “Xử lý lỗi”).

## Bước 4: Truy cập các trường macro PDF417

Mỗi `BarCodeResult` cung cấp một thuộc tính `Extended` chứa một đối tượng con `Pdf417`. Các trường macro mà bạn thường cần nhất là:

| Property | Ý nghĩa |
|----------|---------|
| `MacroPdf417FileID` | Định danh của toàn bộ tệp macro PDF417 |
| `MacroPdf417SegmentID` | Số thứ tự của đoạn hiện tại |
| `MacroPdf417FileName` | Tên tệp tùy chọn được lưu trong macro |

Dưới đây là đoạn mã đầy đủ in các giá trị đó:

```csharp
foreach (BarCodeResult result in reader.ReadBarCodes())
{
    // Macro fields are nullable; use the null‑conditional operator to avoid exceptions.
    Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
    Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
    Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");

    // You can also read other macro properties, such as:
    // result.Extended.Pdf417.MacroPdf417Addressee
    // result.Extended.Pdf417.MacroPdf417Sender
}
```

### Đầu ra console dự kiến

```
Pdf417MacroFileID:    12345
Pdf417MacroSegmentID: 1
Pdf417MacroFileName:  Invoice_2026_09_29.pdf
```

Nếu các trường macro không tồn tại, đầu ra sẽ hiển thị các dòng trống vì các thuộc tính có giá trị `null`. Điều này là bình thường đối với các mã vạch PDF417 không phải macro.

## Bước 5: Xử lý các vấn đề thường gặp (xử lý lỗi & trường hợp đặc biệt)

### Không phát hiện mã vạch

```csharp
var results = reader.ReadBarCodes().ToList();
if (!results.Any())
{
    Console.WriteLine("No PDF417 barcode found in the image.");
    return;
}
```

### Định dạng hình ảnh không được hỗ trợ

Aspose.BarCode hỗ trợ PNG, JPEG, BMP, TIFF và GIF. Cố gắng đọc tệp RAW hoặc WebP sẽ gây ra `ArgumentException`. Chuyển đổi hình ảnh sang định dạng được hỗ trợ trước khi đưa vào trình đọc.

### Tệp macro lớn

Macro‑PDF417 có thể bao gồm nhiều đoạn. Để tái tạo lại tệp gốc, bạn phải thu thập tất cả các đoạn (theo thứ tự `MacroPdf417SegmentID`) và nối chúng lại. Ví dụ trên chỉ in siêu dữ liệu của từng đoạn; trong môi trường thực tế, bạn sẽ lưu mỗi đoạn vào một từ điển, sau đó ghép chúng lại khi đã đọc hết tất cả các đoạn.

### Mẹo về hiệu suất

Nếu bạn xử lý hàng nghìn hình ảnh, hãy tái sử dụng một thể hiện `BarCodeReader` duy nhất với phương thức `SetImage` thay vì tạo đối tượng mới cho mỗi tệp. Điều này giảm việc cấp phát bộ nhớ và tăng tốc độ giải mã.

```csharp
using (BarCodeReader reader = new BarCodeReader(null, DecodeType.MacroPdf417))
{
    foreach (string file in Directory.GetFiles(@"YOUR_DIRECTORY", "*.png"))
    {
        reader.SetImage(file);
        // read barcodes as shown earlier
    }
}
```

## Ví dụ hoàn chỉnh hoạt động

Sao chép chương trình dưới đây vào một dự án Console App mới (`dotnet new console`). Nó bao gồm tất cả các bước, xử lý lỗi và chú thích.

```csharp
// Program.cs
using System;
using System.IO;
using System.Linq;
using Aspose.BarCode;
using Aspose.BarCode.BarCodeRecognition;

class Program
{
    static void Main()
    {
        // Path to the PDF417 macro image – update to your actual location.
        string imagePath = @"YOUR_DIRECTORY/ExtPDF417Meta.png";

        // Verify the file exists before attempting to read.
        if (!File.Exists(imagePath))
        {
            Console.WriteLine($"File not found: {imagePath}");
            return;
        }

        // Initialize the reader for Macro PDF417.
        using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
        {
            var results = reader.ReadBarCodes().ToList();

            if (!results.Any())
            {
                Console.WriteLine("No PDF417 barcode detected in the image.");
                return;
            }

            foreach (BarCodeResult result in results)
            {
                // Print macro information safely.
                Console.WriteLine($"Pdf417MacroFileID:   {result.Extended?.Pdf417?.MacroPdf417FileID}");
                Console.WriteLine($"Pdf417MacroSegmentID:{result.Extended?.Pdf417?.MacroPdf417SegmentID}");
                Console.WriteLine($"Pdf417MacroFileName: {result.Extended?.Pdf417?.MacroPdf417FileName}");
                Console.WriteLine(); // blank line for readability
            }
        }
    }
}
```

**Chạy chương trình**

```bash
dotnet run
```

Bạn sẽ thấy các trường macro được in ra console, khớp với đầu ra dự kiến đã hiển thị ở trên.

## Kết luận

Trong hướng dẫn này, bạn đã học **cách giải mã PDF417** mã vạch trong C# với một **ví dụ trình đọc mã vạch** ngắn gọn. Bằng cách cài đặt Aspose.BarCode, tạo một `BarCodeReader` cho `MacroPdf417`, duyệt qua các kết quả và truy cập các thuộc tính macro `Extended.Pdf417`, bạn có thể một cách đáng tin cậy **đọc dữ liệu mã vạch PDF417** từ bất kỳ hình ảnh nào được hỗ trợ.  

Từ đây bạn có thể:

- Thực hiện tổng hợp các đoạn để tái tạo các tệp macro đa đoạn.  
- Khám phá các loại mã vạch khác (QR, Code128) bằng cùng mẫu `BarCodeReader`.  
- Tích hợp bộ giải mã vào một API web xử lý các hình ảnh được tải lên (`read barcode image C#` trong ngữ cảnh dịch vụ).  

Hãy tự do thử nghiệm với các nguồn hình ảnh khác nhau, các chiến lược xử lý lỗi và tối ưu hoá hiệu suất. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách đọc PDF417 trong C# – hướng dẫn trình đọc mã vạch đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-read-pdf417-in-c-complete-barcode-reader-guide/)
- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn đầy đủ](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-with-aspose-complete-guide/)
- [Cách tạo mã vạch PDF417 với Aspose – Hướng dẫn chi tiết từng bước](/barcode/english/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-with-aspose-complete-step-by-st/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}