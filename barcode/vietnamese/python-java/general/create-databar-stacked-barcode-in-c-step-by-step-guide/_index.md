---
category: general
date: 2026-08-06
description: Tạo mã vạch databar xếp chồng nhanh chóng trong C#. Học cách đặt kích
  thước X, điều chỉnh tỷ lệ khung hình và xuất tệp PNG bằng trình tạo DataBar Stacked
  Omnidirectional.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create databar stacked barcode
- DataBar Stacked Omnidirectional
- barcode aspect ratio
- BarcodeGenerator C#
- BarCodeImageFormat PNG
language: vi
lastmod: 2026-08-06
og_description: Tạo mã vạch databar xếp chồng trong C# với Aspose.BarCode. Hướng dẫn
  này chỉ cách cấu hình kích thước X, thay đổi tỷ lệ khung hình và lưu ảnh PNG.
og_image_alt: Screenshot of two PNG files generated from a DataBar Stacked Omnidirectional
  barcode with different aspect ratios
og_title: Tạo mã vạch databar xếp chồng trong C# – hướng dẫn lập trình đầy đủ
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Create databar stacked barcode in C# quickly. Learn to set X dimension,
    adjust aspect ratio, and export PNG files using the DataBar Stacked Omnidirectional
    generator.
  headline: Create databar stacked barcode in C# – step‑by‑step guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.BarCode
title: Tạo mã vạch Databar xếp chồng trong C# – hướng dẫn từng bước
url: /vi/python-java/general/create-databar-stacked-barcode-in-c-step-by-step-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch databar stacked trong C# – hướng dẫn từng bước

Nếu bạn cần **tạo mã vạch databar stacked** dưới dạng hình ảnh trong C#, hướng dẫn này sẽ chỉ cho bạn cách thực hiện chính xác bằng cách sử dụng thư viện Aspose.BarCode. Bạn sẽ học cách đặt kích thước X, thay đổi tỷ lệ khung hình của mã vạch và lưu kết quả dưới dạng tệp PNG—tất cả trong một vài bước ngắn gọn.

Việc tạo mã vạch DataBar Stacked thường gặp khi bạn phải mã hoá dữ liệu GS1‑128 cho việc quét bán lẻ hoặc theo dõi logistics. Trong các phần sau, chúng tôi sẽ bao quát mọi thứ từ thiết lập dự án đến kiểm tra đầu ra, để bạn có thể tích hợp giải pháp này vào bất kỳ ứng dụng .NET nào mà không bỏ sót chi tiết nào.

## Prerequisites

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* **.NET 6.0** (hoặc mới hơn) đã được cài đặt – mã nguồn nhắm tới SDK hiện đại.
* Một bản **có giấy phép** của **Aspose.BarCode for .NET**. Bản dùng thử miễn phí chỉ dành cho kiểm tra nhưng sẽ có watermark.
* Một IDE như **Visual Studio 2022** hoặc **VS Code** với phần mở rộng C#.
* Kiến thức cơ bản về cú pháp **C#** và khái niệm GS1 Application Identifiers.

> **Pro tip:** Nếu bạn sử dụng trình quản lý gói NuGet, lệnh `dotnet add package Aspose.BarCode` sẽ tự động giải quyết tất cả các phụ thuộc.

## Step 1: Create a new console project

Mở terminal hoặc Package Manager Console và chạy:

```bash
dotnet new console -n DatabarStackedDemo
cd DatabarStackedDemo
dotnet add package Aspose.BarCode
```

Lệnh `dotnet new console` sẽ tạo một tệp **Program.cs** tối thiểu. Thêm gói **Aspose.BarCode** sẽ làm cho lớp `BarcodeGenerator` khả dụng.

## Step 2: Initialize the DataBar Stacked Omnidirectional generator

Mở **Program.cs** và thay thế nội dung mặc định bằng đoạn mã sau. Dòng đầu tiên tạo một **BarcodeGenerator** được cấu hình cho ký hiệu **DataBar Stacked Omnidirectional** và cung cấp payload GS1‑128.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a DataBar Stacked Omnidirectional barcode
        // "(01)12345678901231" encodes a GTIN‑14 with Application Identifier (01)
        var generator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Continue with configuration...
```

**Why this matters:** Giá trị enum `EncodeTypes.DatabarStackedOmniDirectional` thông báo cho thư viện tạo ra một **databar stacked barcode**, là biến thể xếp chồng của họ DataBar omnidirectional. Ký hiệu này có thể chứa tới 14 ký tự số, rất thích hợp cho mã GTIN‑14.

## Step 3: Set the X dimension (module width)

Kích thước X điều khiển độ rộng của thanh nhỏ nhất (module). Giá trị quá nhỏ có thể hiển thị kém trên máy in độ phân giải thấp, trong khi giá trị quá lớn có thể vượt quá không gian nhãn.

```csharp
        // Step 3: Define the module width – 2 pixels gives a crisp, printable barcode
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

> **Tip:** Thuộc tính `Pixels` tiện lợi cho việc thử nghiệm trên màn hình. Đối với các kịch bản tập trung vào in ấn, hãy sử dụng `generator.Parameters.Barcode.XDimension.Millimeters` thay thế.

## Step 4: Adjust the aspect ratio and save the first image

**Aspect ratio** ảnh hưởng đến mối quan hệ chiều cao‑so‑với‑chiều rộng của mã vạch xếp chồng. Kiểu DataBar Stacked Omnidirectional hỗ trợ tỷ lệ từ 10 đến 30. Chúng ta sẽ tạo hai hình ảnh để minh họa ảnh hưởng trực quan.

```csharp
        // Step 4a: Set aspect ratio to 15 (default is 15) and save as PNG
        generator.Parameters.Barcode.DataBar.AspectRatio = 15;
        generator.Save("DatabarAspectRatio15.png", BarCodeImageFormat.Png);
```

Lệnh `generator.Save` ghi một tệp **PNG** vào thư mục làm việc hiện tại. Enum `BarCodeImageFormat.Png` đảm bảo nén không mất dữ liệu, lý tưởng cho việc xử lý tiếp theo hoặc nhúng vào PDF.

## Step 5: Change the aspect ratio to 30 and save the second image

Bây giờ chúng ta tăng chiều cao của các thanh xếp chồng bằng cách thay đổi aspect ratio thành **30**. Điều này làm cho mã vạch cao hơn mà không thay đổi kích thước X.

```csharp
        // Step 5a: Increase aspect ratio to 30 for a taller barcode
        generator.Parameters.Barcode.DataBar.AspectRatio = 30;
        generator.Save("DatabarAspectRatio30.png", BarCodeImageFormat.Png);

        Console.WriteLine("Two barcode images have been generated:");
        Console.WriteLine(" • DatabarAspectRatio15.png");
        Console.WriteLine(" • DatabarAspectRatio30.png");
    }
}
```

Chạy chương trình hiện sẽ tạo ra hai tệp PNG:

* **DatabarAspectRatio15.png** – mã vạch gọn gàng, phù hợp cho nhãn nhỏ.
* **DatabarAspectRatio30.png** – mã vạch cao hơn, cải thiện độ tin cậy khi quét trên bề mặt có độ tương phản thấp.

Bạn có thể mở các hình ảnh bằng bất kỳ trình xem nào để xác nhận các thanh đã được xếp chồng đúng và dữ liệu đã mã hoá khớp với chuỗi GS1 gốc.

## Step 6: Verify the encoded value (optional)

Nếu bạn cần xác nhận rằng mã vạch thực sự đại diện cho chuỗi đầu vào, có thể giải mã nó bằng cùng một thư viện:

```csharp
        // Optional: Decode the generated PNG to ensure correctness
        var decoder = new BarCodeReader("DatabarAspectRatio15.png", DecodeType.DatabarStackedOmniDirectional);
        foreach (BarCodeResult result in decoder.ReadBarCodes())
        {
            Console.WriteLine($"Decoded text: {result.CodeText}");
        }
```

Trình giải mã nên xuất ra `(01)12345678901231`, chứng minh rằng quá trình **create databar stacked barcode** đã giữ nguyên dữ liệu.

## Common pitfalls and how to avoid them

| Issue | Why it happens | Fix |
|-------|----------------|-----|
| Mã vạch bị mờ | Kích thước X được đặt quá thấp so với độ phân giải đầu ra | Tăng `XDimension.Pixels` hoặc dùng `Millimeters` cho in ấn |
| Máy quét báo “symbol not found” | Aspect ratio nằm ngoài khoảng hỗ trợ 10‑30 | Giữ tỷ lệ trong khoảng 10‑30; 15 và 30 là giá trị mặc định an toàn |
| PNG có watermark | Sử dụng giấy phép dùng thử miễn phí của Aspose.BarCode | Mua giấy phép đầy đủ hoặc chỉ dùng bản trial để thử nghiệm |
| Giải mã thất bại trên hình ảnh thứ hai | Trình giải mã được cấu hình cho ký hiệu sai | Sử dụng `DecodeType.DatabarStackedOmniDirectional` khi đọc mã vạch xếp chồng |

## Next steps

Bây giờ bạn đã có thể **tạo mã vạch databar stacked** dưới dạng hình ảnh, có thể muốn:

* **Nhúng PNG vào hóa đơn PDF** bằng một thư viện PDF như **Aspose.PDF**.
* **Tạo mã vạch động trong một Web API** – trả về byte PNG trực tiếp từ controller ASP.NET Core.
* **Thử nghiệm các biến thể DataBar khác** (ví dụ: `DatabarExpanded`, `DatabarLimited`) bằng cách thay đổi enum `EncodeTypes`.
* **Điều chỉnh màu sắc** bằng cách đặt `generator.Parameters.Barcode.ForeColor` và `BackColor` cho thiết kế thương hiệu.

Mỗi chủ đề trên dựa trên các khái niệm cốt lõi đã được trình bày ở đây: khởi tạo `BarcodeGenerator`, cấu hình các tham số hiển thị, và lưu kết quả bằng `BarCodeImageFormat`.

---

### Conclusion

Bài hướng dẫn này đã minh họa cách **tạo mã vạch databar stacked** trong C# bằng Aspose.BarCode. Bạn đã học cách đặt **kích thước X**, thay đổi **aspect ratio** của mã vạch, và xuất kết quả dưới dạng tệp **PNG** bằng `BarcodeGenerator`. Với bước giải mã tùy chọn, bạn cũng có thể xác nhận dữ liệu GS1 đã được mã hoá một cách chính xác. Áp dụng các mẫu này vào hệ thống quản lý tồn kho, vận chuyển hoặc điểm bán lẻ của bạn, và khám phá nhiều tùy chỉnh khác mà thư viện cung cấp. Chúc lập trình vui vẻ!

## What Should You Learn Next?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, dựa trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ với giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [One-Dimensional Databar Barcode Height Adjustment](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}