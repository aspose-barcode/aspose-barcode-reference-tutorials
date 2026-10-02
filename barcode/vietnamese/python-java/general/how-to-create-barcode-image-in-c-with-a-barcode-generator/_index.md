---
category: general
date: 2026-10-02
description: Tạo hình ảnh mã vạch trong C# bằng trình tạo mã vạch, kiểm soát kích
  thước pixel của mã vạch và điều chỉnh chiều cao mã vạch để có kích thước tùy chỉnh.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- barcode generator c#
- barcode pixel size
- adjust barcode height
- custom barcode dimensions
language: vi
lastmod: 2026-10-02
og_description: Tạo hình ảnh mã vạch trong C# bằng trình tạo mã vạch. Học cách đặt
  kích thước pixel của mã vạch, điều chỉnh chiều cao mã vạch và định nghĩa kích thước
  tùy chỉnh cho mã vạch.
og_image_alt: Sample DataBar Omnidirectional barcode saved at 30 px height and 60 px
  height
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn tạo mã vạch và kích thước tùy
  chỉnh
schemas:
- author: Aspose
  dateModified: '2026-10-02'
  description: Create barcode image in C# using a barcode generator, control barcode
    pixel size and adjust barcode height for custom barcode dimensions.
  headline: How to create barcode image in C# with a barcode generator
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Cách tạo hình ảnh mã vạch trong C# bằng trình tạo mã vạch
url: /vi/python-java/general/how-to-create-barcode-image-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo ảnh mã vạch trong C# bằng trình tạo mã vạch

Nếu bạn cần **tạo ảnh mã vạch** một cách lập trình, hướng dẫn này sẽ cho bạn một giải pháp hoàn chỉnh, sẵn sàng chạy trong C#. Bằng cách sử dụng trình tạo mã vạch, bạn có thể kiểm soát **kích thước pixel của mã vạch**, **điều chỉnh chiều cao mã vạch**, và định nghĩa **kích thước mã vạch tùy chỉnh** mà không rời khỏi IDE của mình.

Bạn sẽ học cách tạo hai tệp PNG—một với chiều cao thanh 30 px và một nữa với 60 px—trong khi giữ độ rộng mô-đun không đổi. Các bước này hoạt động với bất kỳ loại mã vạch nào được thư viện hỗ trợ, vì vậy bạn có thể áp dụng chúng cho mã QR, Code 128, hoặc các ký hiệu khác.

## Những gì bạn cần

- .NET 6.0 hoặc mới hơn (mã cũng biên dịch được với .NET Framework 4.8)
- Tham chiếu tới thư viện mã vạch (ví dụ, Aspose.BarCode cho .NET hoặc bất kỳ lớp `BarcodeGenerator` tương thích nào)
- Kiến thức cơ bản về C#
- Quyền ghi vào thư mục nơi các tệp PNG sẽ được lưu

## Bước 1: Khởi tạo trình tạo mã vạch để **tạo ảnh mã vạch**

Đầu tiên, nhập các namespace cần thiết và tạo một thể hiện của `BarcodeGenerator`. Hàm khởi tạo nhận loại mã vạch (`EncodeTypes.DatabarOmniDirectional`) và chuỗi dữ liệu bạn muốn mã hoá.

```csharp
using Aspose.BarCode.Generation;   // or the namespace of your barcode library
using Aspose.BarCode;               // for BarCodeImageFormat
using System.IO;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator to create barcode image
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Việc tạo trình tạo là nền tảng cho bất kỳ quy trình **barcode generator c#** nào. Nó cấp phát canvas vẽ nội bộ và chuẩn bị dữ liệu để render.

## Bước 2: Định nghĩa **kích thước pixel của mã vạch** và chiều cao thanh ban đầu

Chất lượng hình ảnh cuối cùng phụ thuộc vào hai tham số:

| Tham số | Ý nghĩa |
|-----------|---------|
| `XDimension.Pixels` | Chiều rộng của một mô-đun duy nhất (phần tử đen/trắng nhỏ nhất). |
| `BarHeight.Pixels` | Chiều cao của các thanh cho hình ảnh hiện tại. |

```csharp
        // Step 2: Set common visual parameters – module size and initial bar height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size (module width)
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height in pixels
```

Giữ **kích thước pixel của mã vạch** không đổi trong khi thay đổi chiều cao cho phép bạn tạo **kích thước mã vạch tùy chỉnh** phù hợp với hướng dẫn thương hiệu hoặc yêu cầu quét.

## Bước 3: Lưu tệp PNG đầu tiên (chiều cao 30 px)

Bây giờ ghi hình ảnh ra đĩa. Phương thức `Save` nhận đường dẫn tệp và định dạng ảnh mong muốn.

```csharp
        // Step 3: Save the first barcode image (30 px height)
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder); // ensure the folder exists

        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);
```

Tệp kết quả là một **barcode image** với chiều cao thanh 30 px và độ rộng mô-đun 2 px, hoàn hảo cho nhãn dán nhỏ gọn.

## Bước 4: **Điều chỉnh chiều cao mã vạch** cho phiên bản lớn hơn

Để tạo một hình ảnh thứ hai với kích thước hiển thị khác, chỉ cần thay đổi thuộc tính `BarHeight.Pixels`. Điều này cho thấy việc **điều chỉnh chiều cao mã vạch** rất dễ dàng mà không cần tạo lại trình tạo.

```csharp
        // Step 4: Change the bar height to 60 px for a larger barcode
        barcode.Parameters.Barcode.BarHeight.Pixels = 60;
```

Thay đổi chiều cao trong khi giữ **kích thước pixel của mã vạch** đảm bảo các thanh vẫn sắc nét và tỷ lệ khung hình tổng thể vẫn đồng nhất.

## Bước 5: Lưu tệp PNG thứ hai (chiều cao 60 px)

Cuối cùng, lưu phiên bản lớn hơn.

```csharp
        // Step 5: Save the second barcode image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

Bây giờ bạn có hai **kích thước mã vạch tùy chỉnh** được lưu cạnh nhau:

- `DatabarBarHeight30Pixels.png` – chiều cao thanh 30 px
- `DatabarBarHeight60Pixels.png` – chiều cao thanh 60 px

Cả hai hình ảnh đều có **kích thước pixel của mã vạch** giống nhau là 2 px, đảm bảo tính nhất quán về hình ảnh trên các kích thước khác nhau.

## Tại sao các thiết lập này lại quan trọng

- **Kích thước pixel của mã vạch** (`XDimension`) ảnh hưởng đến khả năng đọc của máy quét. Độ rộng 2 px là giá trị mặc định phổ biến, cân bằng giữa kích thước tệp và độ tin cậy khi quét.
- **Chiều cao thanh** quyết định độ cao của mã vạch trên nhãn. Một số máy quét bán lẻ yêu cầu chiều cao tối thiểu; các máy khác cho phép thanh cao hơn vì lý do thẩm mỹ.
- Giữ thể hiện của trình tạo tồn tại trong khi chỉ điều chỉnh `BarHeight` giúp giảm việc cấp phát bộ nhớ và tăng tốc xử lý hàng loạt.

## Các trường hợp đặc biệt và mẹo thực hành tốt nhất

| Tình huống | Cách tiếp cận đề xuất |
|-----------|----------------------|
| **Các định dạng ảnh khác nhau** (JPEG, BMP) | Thay đổi `BarCodeImageFormat.Jpeg` hoặc `.Bmp` trong lời gọi `Save`. JPEG có kích thước nhỏ hơn nhưng có thể gây ra hiện tượng nén mất chất lượng. |
| **Đầu ra độ phân giải cao** (ví dụ, 300 DPI) | Tăng `XDimension.Pixels` tỷ lệ (ví dụ, 4 px) và điều chỉnh `BarHeight.Pixels` để duy trì cùng kích thước vật lý. |
| **Chuỗi dữ liệu động** | Bao bọc việc tạo trình tạo trong một phương thức nhận chuỗi dữ liệu làm tham số, sau đó tái sử dụng cùng một thể hiện `barcode` cho nhiều lần lưu. |
| **Tạo batch an toàn đa luồng** | Tạo một `BarcodeGenerator` riêng cho mỗi luồng hoặc sử dụng pool cục bộ cho luồng để tránh điều kiện tranh chấp. |
| **Lỗi quyền hệ thống tệp** | Kiểm tra `outputFolder` tồn tại và tiến trình có quyền ghi; xử lý `IOException` một cách nhẹ nhàng. |

## Danh sách mã nguồn đầy đủ

Dưới đây là chương trình hoàn chỉnh, tự chứa mà bạn có thể sao chép, dán và chạy.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
using System.IO;

class Program
{
    static void Main()
    {
        // Create a barcode generator – this is the core of the create barcode image workflow
        BarcodeGenerator barcode = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Define barcode pixel size (module width) and initial height
        barcode.Parameters.Barcode.XDimension.Pixels = 2;   // barcode pixel size
        barcode.Parameters.Barcode.BarHeight.Pixels = 30; // first image height

        // Prepare output folder
        string outputFolder = @"YOUR_DIRECTORY";
        Directory.CreateDirectory(outputFolder);

        // Save first image (30 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight30Pixels.png"),
                     BarCodeImageFormat.Png);

        // Adjust height for the second image
        barcode.Parameters.Barcode.BarHeight.Pixels = 60; // adjust barcode height

        // Save second image (60 px height)
        barcode.Save(Path.Combine(outputFolder, "DatabarBarHeight60Pixels.png"),
                     BarCodeImageFormat.Png);
    }
}
```

### Kết quả mong đợi

Sau khi chạy chương trình, thư mục `YOUR_DIRECTORY` chứa hai tệp PNG:

- **DatabarBarHeight30Pixels.png** – một mã vạch gọn gàng phù hợp cho nhãn nhỏ.
- **DatabarBarHeight60Pixels.png** – một phiên bản lớn hơn, lý tưởng cho các ứng dụng cần độ hiển thị cao.

Cả hai tệp đều có thể mở bằng bất kỳ trình xem ảnh nào, in ra, hoặc nhúng vào file PDF.

## Kết luận

Bây giờ bạn đã biết cách **tạo ảnh mã vạch** trong C# bằng **barcode generator c#**, kiểm soát **kích thước pixel của mã vạch**, **điều chỉnh chiều cao mã vạch**, và tạo ra **kích thước mã vạch tùy chỉnh** đáp ứng các yêu cầu quét hoặc thương hiệu cụ thể. Ví dụ này minh họa một mẫu sạch sẽ, có thể lặp lại và mở rộng cho xử lý hàng loạt hoặc các ký hiệu khác nhau.

### Những gì nên khám phá tiếp theo

- Thay `EncodeTypes.DatabarOmniDirectional` bằng các loại khác như `EncodeTypes.Code128` hoặc `EncodeTypes.QR`.
- Áp dụng màu nền và màu chữ thông qua `barcode.Parameters.Barcode.ForeColor` và `BackColor`.
- Tạo đầu ra SVG hoặc PDF cho việc in dựa trên vector.
- Kết hợp nhiều mã vạch thành một hình ảnh duy nhất bằng cách sử dụng `Graphics` cho các nhãn ghép.

Hãy tự do thử nghiệm các tham số, và tích hợp mẫu này vào hệ thống quản lý tồn kho, bán vé, hoặc bất kỳ hệ thống nào cần tạo mã vạch một cách lập trình. Chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây bao phủ các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh, hoạt động với các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo ảnh mã vạch trong C# với chiều cao có thể điều chỉnh](/barcode/english/python-java/general/how-to-create-barcode-image-in-c-with-adjustable-height/)
- [Cách tạo bộ mã vạch kích thước tùy chỉnh và lưu ảnh trong C#](/barcode/english/python-java/general/how-to-generate-barcode-set-custom-size-and-save-image-in-c/)
- [Tạo ảnh mã vạch C# với ví dụ trình tạo mã vạch](/barcode/english/python-java/general/create-barcode-image-c-with-barcode-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}