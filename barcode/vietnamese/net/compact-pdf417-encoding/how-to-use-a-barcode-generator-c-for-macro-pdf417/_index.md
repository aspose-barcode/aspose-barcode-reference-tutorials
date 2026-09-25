---
category: general
date: 2026-08-22
description: Hướng dẫn tạo mã vạch C# cho thấy cách tạo mã vạch Macro PDF417 có siêu
  dữ liệu và lưu dưới dạng PNG bằng Aspose.BarCode.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode generator C#
- Macro PDF417
- Aspose.BarCode
- C# barcode library
- PDF417 barcode
- barcode metadata
language: vi
lastmod: 2026-08-22
og_description: Trình tạo mã vạch C# cho phép bạn tạo mã Macro PDF417 với siêu dữ
  liệu cấp tệp đầy đủ và xuất ra định dạng PNG. Hãy làm theo hướng dẫn này để triển
  khai giải pháp.
og_image_alt: Screenshot of a Macro PDF417 barcode generated with C#
og_title: Trình tạo mã vạch C# – tạo mã vạch Macro PDF417 từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-22'
  description: barcode generator C# tutorial shows how to create a Macro PDF417 barcode
    with metadata and save it as PNG using Aspose.BarCode.
  headline: How to use a barcode generator C# for Macro PDF417
  type: TechArticle
tags:
- barcode
- C#
- PDF417
title: Cách sử dụng trình tạo mã vạch C# cho Macro PDF417
url: /vi/net/compact-pdf417-encoding/how-to-use-a-barcode-generator-c-for-macro-pdf417/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng trình tạo mã vạch C# cho Macro PDF417

Nếu bạn cần một **barcode generator C#** có thể tạo ra ký hiệu Macro PDF417 với siêu dữ liệu ở mức file, hướng dẫn này cung cấp giải pháp hoàn chỉnh, sẵn sàng chạy. Bạn sẽ thấy cách cấu hình giao diện mã vạch, nhúng thông tin macro như file ID và số đoạn, và cuối cùng lưu kết quả dưới dạng ảnh PNG.

Ví dụ sử dụng thư viện Aspose.BarCode, một **C# barcode library** được áp dụng rộng rãi và hỗ trợ đầy đủ các tính năng của PDF417. Không cần dịch vụ bên ngoài, và mã chạy được với .NET 6 hoặc phiên bản mới hơn.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6 SDK (hoặc bất kỳ phiên bản nào mới hơn) đã được cài đặt.
* Visual Studio 2022, VS Code, hoặc bất kỳ IDE C# nào khác.
* Tham chiếu NuGet tới **Aspose.BarCode** (`dotnet add package Aspose.BarCode`).

Hiểu biết cơ bản về cú pháp C# và khái niệm mã vạch PDF417 sẽ giúp bạn theo dõi các bước, nhưng tutorial sẽ giải thích chi tiết mọi tùy chọn cấu hình.

## Nội dung tutorial

* Khởi tạo một **barcode generator C#** cho định dạng Macro PDF417.  
* Điều chỉnh các tham số hiển thị như X‑dimension và số cột.  
* Cung cấp các trường mức file của Macro PDF417: file ID, segment ID, segment count, file name, checksum, file size, timestamp, addressee, sender và terminator.  
* Lưu ký hiệu đã tạo dưới dạng file PNG.  
* Mẹo xử lý các trường hợp đặc biệt như kích thước file lớn hoặc timestamp tùy chỉnh.

Sau khi đọc xong bài viết này, bạn sẽ có một chương trình tự chứa có thể tạo ra mã vạch Macro PDF417 hoàn toàn tuân chuẩn.

## Bước 1: Tạo instance trình tạo mã vạch C#

Hoạt động đầu tiên là khởi tạo `BarcodeGenerator` với giá trị enum `EncodeTypes.MacroPdf417` và chuỗi văn bản bạn muốn mã hoá. Constructor cũng cho phép truyền chuỗi payload, sẽ trở thành phần dữ liệu của mã vạch macro.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 1: Create a barcode generator for Macro PDF417
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
{
    // Subsequent configuration goes here
}
```

**Tại sao lại quan trọng** – Cờ `EncodeTypes.MacroPdf417` báo cho Aspose.BarCode biết ký hiệu là mã vạch macro, kích hoạt các trường bổ sung phía sau. Nếu không có cờ này, thư viện sẽ tạo một mã vạch PDF417 thông thường, không có siêu dữ liệu mức file.

## Bước 2: Điều chỉnh giao diện cơ bản của mã vạch (cài đặt visual PDF417)

Độ rõ nét trực quan rất quan trọng để quét chính xác. Hai tham số thường dùng là độ rộng mô-đun (`XDimension`) và số cột. Điều chỉnh các giá trị này giúp cân bằng giữa kích thước và khả năng đọc.

```csharp
    // Step 2: Adjust basic barcode appearance
    generator.Parameters.Barcode.XDimension.Pixels = 2;   // width of a single module
    generator.Parameters.Barcode.Pdf417.Columns = 5;    // number of columns in the symbol
```

* `XDimension.Pixels` kiểm soát độ rộng của mỗi thanh đen/trắng. Giá trị **2** thường phù hợp với hầu hết máy in nhãn.
* `Pdf417.Columns` xác định số cột mà mã vạch sẽ sử dụng. Năm cột tạo ra ký hiệu gọn gàng mà không làm giảm dung lượng dữ liệu.

## Bước 3: Định nghĩa thông tin mức file cho Macro PDF417

Macro PDF417 mở rộng định dạng PDF417 tiêu chuẩn bằng các trường mô tả cách một file lớn được chia thành nhiều đoạn mã vạch. Cung cấp các trường này giúp máy quét phía sau có thể tái tạo lại file gốc.

```csharp
    // Step 3: Define Macro PDF417 file‑level information
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;          // unique file identifier
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;            // current segment number (0‑indexed)
    generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;       // total number of segments
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";      // optional logical file name
```

* `MacroPdf417FileID` phải giống nhau cho mọi đoạn thuộc cùng một file logic.
* `MacroPdf417SegmentID` tăng dần từ **0** tới `SegmentsCount‑1`.
* `MacroPdf417SegmentsCount` cho decoder biết có bao nhiêu đoạn cần chờ.
* `MacroPdf417FileName` là tùy chọn nhưng hữu ích cho việc nhận dạng bằng mắt người.

## Bước 4: Thiết lập siêu dữ liệu macro bổ sung

Ngoài thông tin file cốt lõi, đặc tả cho phép các trường phụ như checksum, file size, timestamp, addressee, sender và một cờ terminator. Điền đầy đủ các trường này sẽ cải thiện tính toàn vẹn và khả năng truy vết dữ liệu.

```csharp
    // Step 4: Set additional macro metadata
    generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;                     // CCITT‑16 checksum
    generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;                  // file size in bytes
    generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
    generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
    generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;
```

* `MacroPdf417Checksum` cung cấp một checksum CCITT 16‑bit cho toàn bộ file; decoder có thể xác thực tính toàn vẹn sau khi tái tạo.
* `MacroPdf417FileSize` phải phản ánh đúng số byte của file gốc; giá trị lớn hơn `2^31‑1` yêu cầu trường 64‑bit, Aspose sẽ tự động xử lý.
* `MacroPdf417TimeStamp` ghi lại thời điểm mã vạch được tạo. Hãy dùng UTC để tránh nhầm lẫn múi giờ.
* `MacroPdf417Addressee` và `MacroPdf417Sender` là các chuỗi tự do có thể lưu thông tin định tuyến.
* `MacroPdf417Terminator` báo hiệu đây là đoạn cuối cùng; đặt thành `Set` cho phần cuối, nếu không để mặc định (`NotSet`).

**Mẹo cho trường hợp đặc biệt** – Nếu kích thước file vượt quá 4 GB, hãy chia nội dung thành nhiều segment macro và điều chỉnh `SegmentsCount` cho phù hợp. Thư viện sẽ quản lý trường kích thước lớn mà không bị tràn.

## Bước 5: Lưu mã vạch dưới dạng ảnh PNG

Bước cuối cùng ghi ký hiệu đã tạo ra đĩa. PNG giữ nguyên kích thước pixel và được hầu hết phần cứng quét hỗ trợ.

```csharp
    // Step 5: Save the generated barcode as a PNG image
    generator.Save("YOUR_DIRECTORY/MacroPdf417.png", BarCodeImageFormat.Png);
}
```

Thay `YOUR_DIRECTORY` bằng đường dẫn tuyệt đối hoặc tương đối mà tiến trình thực thi có quyền ghi. Enum `BarCodeImageFormat.Png` đảm bảo đầu ra không mất dữ liệu.

**Tại sao lại dùng PNG?** – Các định dạng raster như PNG giữ các cạnh mô-đun sắc nét, điều này rất quan trọng đối với máy quét dựa vào độ tương phản cao. Nếu bạn cần định dạng vector, Aspose cũng hỗ trợ `Pdf` và `Svg`.

## Ví dụ đầy đủ có thể chạy

Dưới đây là chương trình hoàn chỉnh bạn có thể sao chép vào một ứng dụng console. Nó bao gồm các chỉ thị `using` cần thiết và một phương thức `Main`.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace MacroPdf417Demo
{
    class Program
    {
        static void Main()
        {
            // Create a barcode generator for Macro PDF417 with sample payload
            using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.MacroPdf417, "Sample text"))
            {
                // Adjust visual appearance
                generator.Parameters.Barcode.XDimension.Pixels = 2;
                generator.Parameters.Barcode.Pdf417.Columns = 5;

                // Define macro file‑level fields
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileID = 12345678;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentID = 12;
                generator.Parameters.Barcode.Pdf417.MacroPdf417SegmentsCount = 20;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileName = "file01";

                // Add optional metadata
                generator.Parameters.Barcode.Pdf417.MacroPdf417Checksum = 1234;
                generator.Parameters.Barcode.Pdf417.MacroPdf417FileSize = 400_000;
                generator.Parameters.Barcode.Pdf417.MacroPdf417TimeStamp = new DateTime(2024, 4, 1);
                generator.Parameters.Barcode.Pdf417.MacroPdf417Addressee = "street";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Sender = "aspose";
                generator.Parameters.Barcode.Pdf417.MacroPdf417Terminator = Pdf417MacroTerminator.Set;

                // Export to PNG
                generator.Save("MacroPdf417.png", BarCodeImageFormat.Png);
            }

            Console.WriteLine("Macro PDF417 barcode generated successfully.");
        }
    }
}
```

### Kết quả mong đợi

Chạy chương trình sẽ tạo một file có tên **MacroPdf417.png** trong thư mục làm việc của dự án. Mở ảnh sẽ thấy một mã vạch PDF417 gọn gàng với các trường macro được nhúng. Quét ảnh bằng một trình đọc hỗ trợ PDF417 (ví dụ: ZXing, Aspose.BarCode decoder) sẽ trả về payload gốc `"Sample text"` cùng với siêu dữ liệu macro.

## Câu hỏi thường gặp và khắc phục sự cố

| Câu hỏi | Trả lời |
|----------|--------|
| *Nếu mã vạch quá lớn so với nhãn mục tiêu thì sao?* | Giảm `XDimension.Pixels` hoặc tăng `Pdf417.Columns`. Cả hai tham số đều ảnh hưởng đến kích thước tổng thể. |
| *Tôi có thể tạo ảnh vector thay vì PNG không?* | Có. Gọi `generator.Save("MacroPdf417.svg", BarCodeImageFormat.Svg);` để xuất ra định dạng có thể mở rộng. |
| *Làm sao kiểm tra checksum sau khi quét?* | Bộ giải mã Aspose.BarCode tự động xác thực `MacroPdf417Checksum` và báo lỗi trong đối tượng `MacroPdf417Result`. |
| *Thư viện có tương thích với .NET Core không?* | Gói NuGet hỗ trợ .NET Standard 2.0+, bao gồm .NET Core, .NET 5, .NET 6 và các phiên bản sau. |
| *Nếu tôi muốn nhúng dữ liệu nhị phân thay vì văn bản thì sao?* | Chuyển payload nhị phân sang Base64 hoặc dùng overload `EncodeTypes.MacroPdf417` chấp nhận mảng byte. |

## Mẹo chuyên nghiệp cho môi trường production

* **Cache the generator** –


## Bạn nên học gì tiếp theo?

Các tutorial sau đây liên quan chặt chẽ và mở rộng các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ và giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to Create Barcode – Compact PDF417 with Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/compact-pdf417-basic-configuration/)
- [How to read barcode from PDF in Java using Aspose.BarCode](/barcode/english/java/document-barcode-recognition/recognizing-barcodes-from-pdf/)
- [Create Codabar Barcode with Aspose.Barcode – Generator & Reader API](/barcode/english/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}