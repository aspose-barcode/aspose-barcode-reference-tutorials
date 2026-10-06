---
category: general
date: 2026-10-05
description: Tạo mã vạch PNG bằng C# và tìm hiểu cách đặt tỷ lệ khung hình 15 cho
  các mã vạch DataBar xếp chồng đa hướng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode png
- how to set aspect ratio
- set aspect ratio 15
language: vi
lastmod: 2026-10-05
og_description: Tạo mã vạch PNG bằng C# và khám phá cách đặt tỷ lệ khung hình 15 cho
  các mã vạch DataBar xếp chồng đa hướng trong vài bước.
og_image_alt: Screenshot showing a generated barcode PNG with aspect ratio 15
og_title: Tạo mã vạch PNG trong C# – hướng dẫn đặt tỷ lệ khung hình 15
schemas:
- author: Aspose
  dateModified: '2026-10-05'
  description: Create barcode PNG in C# and learn how to set aspect ratio 15 for stacked
    DataBar omnidirectional barcodes.
  headline: How to create barcode PNG with a custom aspect ratio in C#
  type: TechArticle
tags:
- barcode generation
- C#
- Aspose.BarCode
title: Cách tạo PNG mã vạch với tỷ lệ khung hình tùy chỉnh trong C#
url: /vi/python-java/general/how-to-create-barcode-png-with-a-custom-aspect-ratio-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo PNG mã vạch với tỷ lệ khung hình tùy chỉnh trong C#

Nếu bạn cần **tạo PNG mã vạch** trong C#, hướng dẫn này sẽ chỉ cho bạn **cách đặt tỷ lệ khung hình** 15 cho mã DataBar xếp chồng đa hướng. Chúng tôi sẽ đi qua từng lời gọi API, giải thích tại sao tỷ lệ khung hình lại quan trọng, và cung cấp cho bạn một ví dụ hoàn chỉnh, có thể chạy được mà bạn có thể chèn vào bất kỳ dự án .NET nào.

Việc tạo hình ảnh mã vạch là một yêu cầu phổ biến cho các hệ thống quản lý tồn kho, nhãn vận chuyển và các ứng dụng bán lẻ tại điểm bán. Khi kết thúc tutorial này, bạn sẽ có một tệp PNG đáp ứng đúng các thông số hình ảnh mà đối tác kinh doanh của bạn yêu cầu. Không cần công cụ bên ngoài, không cần chỉnh sửa ảnh thủ công—chỉ cần code.

## Các điều kiện tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 hoặc mới hơn (ví dụ sử dụng .NET 6 nhưng cũng hoạt động với .NET 5+)
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)
* Gói NuGet **Aspose.BarCode for .NET**  
  ```bash
  dotnet add package Aspose.BarCode
  ```
* Quyền ghi vào thư mục mà bạn muốn lưu tệp PNG

Các yêu cầu này là tối thiểu; cùng một đoạn code hoạt động trong .NET Core, .NET Framework, hoặc một ứng dụng console.

## Tạo PNG mã vạch với Aspose.BarCode

Bước đầu tiên là khởi tạo lớp `BarcodeGenerator` với loại mã vạch đúng. Trong trường hợp này, chúng ta sử dụng `EncodeTypes.DatabarStackedOmniDirectional`, loại tạo ra một DataBar xếp chồng có thể đọc được từ mọi hướng.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Initialize the generator with sample data
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarStackedOmniDirectional,
    "(01)12345678901231");
```

*Tại sao điều này quan trọng:* Constructor nhận hai đối số—**kiểu mã vạch** và **chuỗi dữ liệu**. Định dạng DataBar yêu cầu một định danh ứng dụng GS1, vì vậy dữ liệu mẫu bắt đầu bằng `(01)`.

## Cách đặt tỷ lệ khung hình cho DataBar xếp chồng

Chiều rộng trực quan của DataBar được điều khiển bởi thuộc tính **aspect ratio**. Tỷ lệ cao hơn làm các thanh rộng hơn, có thể cải thiện độ tin cậy khi quét trên các máy in độ phân giải thấp.

```csharp
// Step 2: Define the module width (X‑dimension) in pixels
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

`XDimension` xác định kích thước của một mô-đun duy nhất (thanh hoặc khoảng trống nhỏ nhất). Giữ giá trị này ở 2 px sẽ cho ra hình ảnh sắc nét, mật độ cao, phù hợp với hầu hết các máy in nhãn.

## Đặt tỷ lệ khung hình 15 – phân tích mã

Bây giờ chúng ta áp dụng yêu cầu **set aspect ratio 15**. Đây là phần cốt lõi của tutorial và minh họa lời gọi API chính xác mà bạn cần.

```csharp
// Step 3: Set the DataBar aspect ratio to 15 for a wider appearance
generator.Parameters.Barcode.DataBar.AspectRatio = 15;
```

*Tại sao lại là 15?* Tỷ lệ khung hình mặc định cho DataBar xếp chồng là 12. Tăng lên 15 sẽ mở rộng chiều rộng của mỗi thanh lên 25 %, thường phù hợp với các yêu cầu của nhà cung cấp logistic cần mã vạch rộng hơn để quét nhanh hơn.

## Lưu mã vạch dưới dạng PNG

Khi trình tạo đã được cấu hình, bước cuối cùng là ghi hình ảnh ra đĩa. Phương thức `Save` nhận đường dẫn tệp và một enum định dạng ảnh.

```csharp
// Step 4: Save the generated barcode as a PNG image
string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";
generator.Save(outputPath, BarCodeImageFormat.Png);
```

Định dạng PNG giữ nguyên chất lượng không mất dữ liệu, đảm bảo mã vạch hiển thị chính xác như thiết kế trên bất kỳ màn hình hay máy in nào.

## Ví dụ hoàn chỉnh và kết quả mong đợi

Dưới đây là chương trình đầy đủ mà bạn có thể sao chép vào phương thức `Main` của một ứng dụng console. Nó bao gồm tất cả các bước đã mô tả ở trên, cùng một thông báo xác nhận ngắn.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Initialize the generator with stacked DataBar (omnidirectional) and sample GS1 data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Define the X‑dimension (module width) in pixels
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // Set the DataBar aspect ratio to 15 – this is the key to a wider barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;

        // Choose a folder you have write access to
        string outputPath = @"C:\Barcodes\DatabarAspectRatio15.png";

        // Save the barcode as a PNG file
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode PNG created at: {outputPath}");
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo một tệp có tên `DatabarAspectRatio15.png` chứa một mã DataBar xếp chồng rộng, rõ ràng. Khi mở PNG, bạn sẽ thấy một mã vạch được kéo dài theo chiều ngang nhưng vẫn tuân thủ các tiêu chuẩn GS1 DataBar.

![Mã vạch PNG với tỷ lệ khung hình 15](barcode-aspect15.png)

*Văn bản thay thế hình ảnh:* **tạo mã vạch PNG hiển thị DataBar xếp chồng với tỷ lệ khung hình 15**

### Mẹo và những lỗi thường gặp

| Tình huống | Khuyến nghị |
|-----------|----------------|
| **Hình ảnh bị mờ** | Tăng `XDimension.Pixels` lên 3 px hoặc cao hơn, nhưng giữ tổng kích thước ảnh dưới 500 px để tránh tệp quá lớn. |
| **Máy quét không đọc được mã** | Kiểm tra chuỗi dữ liệu có tuân theo định dạng GS1 (`(01)` ở đầu) không. Đồng thời, đảm bảo độ phân giải máy in ít nhất 300 dpi. |
| **Cần định dạng tệp khác** | Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp` hoặc `Gif`—API hỗ trợ tất cả các định dạng raster chính. |
| **Chạy trong ứng dụng web** | Sử dụng `generator.Save(Stream, BarCodeImageFormat.Png)` để ghi trực tiếp vào phản hồi HTTP mà không cần lưu vào hệ thống tệp. |

### Mở rộng ví dụ

* **Nhiều mã vạch trong một ảnh:** Tạo các thể hiện `BarcodeGenerator` bổ sung và vẽ chúng lên một `Bitmap` duy nhất bằng `Graphics`.  
* **Thêm văn bản có thể đọc được:** Đặt `generator.Parameters.Caption.Visible = true` và tùy chỉnh phông chữ qua `generator.Parameters.Caption.Font`.  
* **Tỷ lệ khung hình động:** Lấy giá trị tỷ lệ từ tệp cấu hình hoặc cơ sở dữ liệu để tạo mã vạch với độ rộng khác nhau theo yêu cầu.

## Kết luận

Trong tutorial này, bạn đã học cách **tạo PNG mã vạch** trong C# và **đặt tỷ lệ khung hình** 15 một cách chính xác cho mã DataBar xếp chồng đa hướng. Mã hoàn chỉnh, có thể chạy được minh họa mọi lời gọi API cần thiết, giải thích lý do mỗi cài đặt quan trọng, và cung cấp các mẹo thực tiễn cho việc triển khai thực tế.  

Tiếp theo, bạn có thể khám phá **cách đặt tỷ lệ khung hình** cho các loại mã vạch khác (ví dụ QR Code hoặc Code 128) hoặc tích hợp trình tạo vào dịch vụ ASP .NET Core trả về hình ảnh mã vạch theo yêu cầu. Chúc bạn lập trình vui vẻ!

## Bạn Nên Học Gì Tiếp Theo?


Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ code đầy đủ, hoạt động với các giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to create databar PNG images with C# and Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-png-images-with-c-and-aspose-barcode/)
- [How to create databar stacked barcode in C# with Aspose.Barcode](/barcode/english/python-java/general/how-to-create-databar-stacked-barcode-in-c-with-aspose-barco/)
- [Customize databar stacked omnidirectional Aspect Ratio in .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}