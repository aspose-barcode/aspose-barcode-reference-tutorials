---
category: general
date: 2026-11-14
description: Tìm hiểu cách đọc mã vạch từ hình ảnh trong C# với hướng dẫn toàn diện
  về trình đọc mã vạch C#. Bao gồm cài đặt, mã nguồn đầy đủ và xử lý các trường Macro
  PDF417.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- read barcodes from image
- barcode reader tutorial c#
language: vi
lastmod: 2026-11-14
og_description: Đọc mã vạch từ hình ảnh trong C# với hướng dẫn đọc mã vạch này. Nhận
  một ví dụ hoạt động đầy đủ và học cách trích xuất dữ liệu Macro PDF417.
og_image_alt: C# code screenshot that reads barcodes from image using BarCodeReader
og_title: Đọc mã vạch từ hình ảnh trong C# – hướng dẫn đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-11-14'
  description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  headline: How to read barcodes from image using C# – step‑by‑step guide
  type: TechArticle
- description: Learn how to read barcodes from image in C# with a complete barcode
    reader tutorial c#. Includes setup, full code, and handling Macro PDF417 fields.
  name: How to read barcodes from image using C# – step‑by‑step guide
  steps:
  - name: Prerequisites
    text: '- .NET 8 SDK (or .NET 6+ if you prefer) installed. - Basic familiarity
      with C# console applications. - An image file that contains a Macro PDF417 barcode
      (e.g., `MacroPdf417.png`).'
  - name: Explanation of each step
    text: '| Step | Why it matters | |------|----------------| | **1️⃣ Define image
      path** | The reader works with a file path or stream. Using a relative path
      makes the example easy to copy‑paste. | | **2️⃣ Create BarCodeReader** | Passing
      `DecodeType.MacroPdf417` restricts the scan to that symbology, which i'
  - name: Reading other symbologies
    text: 'If you need to **read barcodes from image** that are not Macro PDF417,
      replace `DecodeType.MacroPdf417` with a comma‑separated list, e.g.:'
  - name: Handling large images
    text: 'Large PNG or JPEG files can increase memory usage. To keep the process
      lightweight, you can downscale the image before passing it to `BarCodeReader`:'
  - name: Working with streams instead of file paths
    text: 'When the image comes from a database or a web request, pass a `Stream`:'
  type: HowTo
tags:
- C#
- barcode
- image processing
title: Cách đọc mã vạch từ hình ảnh bằng C# – hướng dẫn từng bước
url: /vi/net/one-dimensional-barcode-types/how-to-read-barcodes-from-image-using-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách đọc mã vạch từ hình ảnh bằng C# – hướng dẫn từng bước

Nếu bạn cần **đọc mã vạch từ hình ảnh** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Khi kết thúc bài học, bạn sẽ có một chương trình hoàn chỉnh, có thể chạy được, trích xuất cả dữ liệu mã vạch cơ bản và các trường riêng của Macro PDF417.

Trong **barcode reader tutorial c#** này, chúng ta sẽ đề cập đến việc thiết lập dự án, gói NuGet cần thiết, và một mẫu mã đầy đủ hoạt động với .NET 8 SDK mới nhất. Không cần dịch vụ bên ngoài—tất cả đều chạy cục bộ.

## Những gì bạn sẽ học

- Cách thêm thư viện Aspose.BarCode (hoặc tương tự) vào dự án C#.  
- Cách tạo một `BarCodeReader` để đọc một tệp hình ảnh cụ thể.  
- Cách lặp qua tất cả các mã vạch được phát hiện và xuất ra loại, nội dung, và siêu dữ liệu Macro PDF417.  
- Mẹo xử lý hình ảnh có nhiều mã vạch hoặc các kiểu giải mã khác nhau.

### Yêu cầu trước

- .NET 8 SDK (hoặc .NET 6+ nếu bạn muốn) đã được cài đặt.  
- Kiến thức cơ bản về ứng dụng console C#.  
- Một tệp hình ảnh chứa mã vạch Macro PDF417 (ví dụ: `MacroPdf417.png`).  

---

## Bước 1: Thiết lập dự án console mới

Mở terminal và chạy:

```bash
dotnet new console -n BarcodeReaderDemo
cd BarcodeReaderDemo
```

Lệnh này sẽ tạo một ứng dụng console tối thiểu có tên **BarcodeReaderDemo**. Tệp dự án (`BarcodeReaderDemo.csproj`) sẽ được sử dụng ở bước tiếp theo.

## Bước 2: Cài đặt thư viện đọc mã vạch

Trong hướng dẫn này chúng ta sử dụng thư viện **Aspose.BarCode for .NET** vì nó hỗ trợ Macro PDF417 ngay từ đầu. Cài đặt qua NuGet:

```bash
dotnet add package Aspose.BarCode --version 23.12
```

> **Tại sao chọn thư viện này?** Nó cung cấp một lớp `BarCodeReader` duy nhất, hỗ trợ hàng chục loại mã vạch, và có thuộc tính `Extended` chứa các trường Macro PDF417.

## Bước 3: Viết mã đọc mã vạch (barcode reader tutorial c#)

Thay thế nội dung của `Program.cs` bằng ví dụ hoàn chỉnh dưới đây. Nó minh họa **cách đọc mã vạch từ hình ảnh** và in ra cả thông tin chung và thông tin đặc thù của Macro PDF417.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Recognition;

namespace BarcodeReaderDemo
{
    class Program
    {
        static void Main(string[] args)
        {
            // -------------------------------------------------------------
            // 1️⃣  Define the path to the image that contains the barcode.
            // -------------------------------------------------------------
            string imagePath = "YOUR_DIRECTORY/MacroPdf417.png";

            // -------------------------------------------------------------
            // 2️⃣  Create a BarCodeReader for the Macro PDF417 symbology.
            // -------------------------------------------------------------
            // DecodeType.MacroPdf417 tells the reader to look for the
            // Macro PDF417 variant and to populate the Extended.Pdf417
            // fields when they are present.
            using (BarCodeReader reader = new BarCodeReader(imagePath, DecodeType.MacroPdf417))
            {
                // ---------------------------------------------------------
                // 3️⃣  Iterate through every barcode found in the image.
                // ---------------------------------------------------------
                foreach (BarCodeResult result in reader.ReadBarCodes())
                {
                    // -----------------------------------------------------
                    // 4️⃣  Output generic barcode information.
                    // -----------------------------------------------------
                    Console.WriteLine($"CodeType: {result.CodeTypeName}");
                    Console.WriteLine($"CodeText: {result.CodeText}");

                    // -----------------------------------------------------
                    // 5️⃣  Output Macro PDF417 specific fields (if any).
                    // -----------------------------------------------------
                    // The Extended property is only populated for
                    // symbologies that expose extra data, such as Macro PDF417.
                    Console.WriteLine($"Pdf417MacroFileID: {result.Extended.Pdf417.MacroPdf417FileID}");
                    Console.WriteLine($"Pdf417MacroSegmentID: {result.Extended.Pdf417.MacroPdf417SegmentID}");
                    Console.WriteLine($"Pdf417MacroSegmentsCount: {result.Extended.Pdf417.MacroPdf417SegmentsCount}");

                    // -----------------------------------------------------
                    // 6️⃣  (Optional) Add more macro fields here as needed.
                    // -----------------------------------------------------
                    Console.WriteLine(new string('-', 40));
                }
            }

            // -------------------------------------------------------------
            // 7️⃣  Keep the console window open when debugging.
            // -------------------------------------------------------------
            Console.WriteLine("Finished reading barcodes. Press any key to exit.");
            Console.ReadKey();
        }
    }
}
```

### Giải thích từng bước

| Bước | Tại sao quan trọng |
|------|--------------------|
| **1️⃣ Xác định đường dẫn hình ảnh** | Trình đọc làm việc với đường dẫn tệp hoặc stream. Sử dụng đường dẫn tương đối giúp ví dụ dễ sao chép‑dán. |
| **2️⃣ Tạo BarCodeReader** | Truyền `DecodeType.MacroPdf417` sẽ giới hạn việc quét chỉ ở loại mã này, giúp tăng tốc và đảm bảo các trường `Extended` được điền. |
| **3️⃣ Lặp qua kết quả** | Một hình ảnh có thể chứa nhiều mã vạch; vòng `foreach` đảm bảo chúng ta bắt được tất cả. |
| **4️⃣ Xuất thông tin chung** | `CodeTypeName` và `CodeText` là hai thông tin phổ biến nhất mà nhà phát triển cần. |
| **5️⃣ Các trường Macro PDF417** | Macro PDF417 nhúng dữ liệu bổ sung (ID tệp, ID đoạn, số đoạn). Truy cập `result.Extended.Pdf417` sẽ cho bạn các giá trị này mà không cần phân tích thêm. |
| **6️⃣ Các trường phụ tùy chọn** | Thư viện còn cung cấp các trường macro khác (ví dụ `MacroPdf417FileName`). Bạn có thể mở rộng đầu ra tùy theo nhu cầu. |
| **7️⃣ Giữ console mở** | Hữu ích khi chạy từ Visual Studio hoặc `dotnet run` để xem kết quả trước khi cửa sổ đóng lại. |

## Bước 4: Chạy chương trình và kiểm tra kết quả

Đặt tệp `MacroPdf417.png` của bạn vào thư mục được tham chiếu bởi `imagePath`. Sau đó thực thi:

```bash
dotnet run
```

Kết quả console thường trông như sau:

```
CodeType: MacroPdf417
CodeText: https://example.com/document.pdf
Pdf417MacroFileID: 12
Pdf417MacroSegmentID: 3
Pdf417MacroSegmentsCount: 5
----------------------------------------
Finished reading barcodes. Press any key to exit.
```

Nếu hình ảnh chứa nhiều ký hiệu Macro PDF417, chương trình sẽ liệt kê từng bộ giá trị một cách tuần tự.

## Các biến thể phổ biến và trường hợp đặc biệt

### Đọc các loại mã vạch khác

Nếu bạn cần **đọc mã vạch từ hình ảnh** không phải là Macro PDF417, hãy thay `DecodeType.MacroPdf417` bằng danh sách các loại, ngăn cách bằng dấu phẩy, ví dụ:

```csharp
using (BarCodeReader reader = new BarCodeReader(imagePath,
    DecodeType.QR | DecodeType.Code128 | DecodeType.DataMatrix))
```

Thuộc tính `Extended` sẽ có giá trị `null` đối với các loại mã không cung cấp dữ liệu phụ, vì vậy luôn kiểm tra `null` trước khi truy cập.

### Xử lý hình ảnh lớn

Các tệp PNG hoặc JPEG lớn có thể làm tăng mức tiêu thụ bộ nhớ. Để giữ quá trình nhẹ, bạn có thể giảm kích thước ảnh trước khi truyền cho `BarCodeReader`:

```csharp
using (System.Drawing.Bitmap bmp = new System.Drawing.Bitmap(imagePath))
{
    var resized = new System.Drawing.Bitmap(bmp, new System.Drawing.Size(bmp.Width / 2, bmp.Height / 2));
    using (BarCodeReader reader = new BarCodeReader(resized, DecodeType.MacroPdf417))
    {
        // read as before...
    }
}
```

### Làm việc với stream thay vì đường dẫn tệp

Khi ảnh đến từ cơ sở dữ liệu hoặc yêu cầu web, hãy truyền một `Stream`:

```csharp
using (FileStream fs = File.OpenRead(imagePath))
using (BarCodeReader reader = new BarCodeReader(fs, DecodeType.MacroPdf417))
{
    // read as before...
}
```

## Mẹo chuyên nghiệp để có trải nghiệm đọc mã vạch mượt mà

- **Mẹo:** Luôn đặt `DecodeType` thành tập hợp hẹp nhất các loại mã bạn mong đợi. Điều này giảm các kết quả dương tính giả và tăng tốc xử lý.  
- **Cảnh báo:** Hình ảnh có độ tương phản thấp hoặc nén mạnh có thể gây mất đọc. Tiền xử lý ảnh (điều chỉnh độ sáng/độ tương phản) nếu bạn nhận thấy tỷ lệ phát hiện thấp.  
- **Tip:** Lớp `BarCodeReader` triển khai `IDisposable`; sử dụng khối `using` sẽ đảm bảo các tài nguyên gốc được giải phóng kịp thời.  

---

## Kết luận

Bây giờ bạn đã biết cách **đọc mã vạch từ hình ảnh** bằng C# và trích xuất cả thông tin tiêu chuẩn và các trường đặc thù của Macro PDF417. **barcode reader tutorial c#** này cung cấp một giải pháp hoàn chỉnh, tự chứa, mà bạn có thể đưa vào bất kỳ dự án .NET nào.

Từ đây bạn có thể:

- Khám phá các loại giải mã khác (QR, DataMatrix, Code128).  
- Tích hợp trình đọc vào API ASP.NET Core để xử lý tải lên ngay lập tức.  
- Lưu các trường macro đã trích xuất vào cơ sở dữ liệu để tổng hợp sau này.

Chúc lập trình vui vẻ, và hãy thoải mái thử nghiệm với các nguồn ảnh và định dạng mã vạch khác nhau!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong bài viết này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ và giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to decode PDF417 barcodes in C# and read barcode image C#](/barcode/english/net/compact-pdf417-encoding/how-to-decode-pdf417-barcodes-in-c-and-read-barcode-image-c/)
- [How to read barcode from image c# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-read-barcode-from-image-c-using-aspose-barcode/)
- [Read barcode from image C# – complete guide with Macro PDF417](/barcode/english/net/compact-pdf417-encoding/read-barcode-from-image-c-complete-guide-with-macro-pdf417/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}