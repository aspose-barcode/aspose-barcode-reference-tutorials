---
category: general
date: 2026-08-09
description: Tạo hình ảnh mã vạch bằng trình tạo mã vạch C# và học cách tạo nhiều
  mã vạch với tỷ lệ khung tùy chỉnh trong vài phút.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create barcode image
- c# barcode generator
- generate multiple barcodes
- barcode aspect ratio
- barcode image format
language: vi
lastmod: 2026-08-09
og_description: Tạo hình ảnh mã vạch bằng trình tạo mã vạch C#. Hướng dẫn này cho
  thấy cách tạo nhiều mã vạch, điều chỉnh tỷ lệ khung hình và lưu tệp PNG một cách
  hiệu quả.
og_image_alt: Example of create barcode image output with aspect ratios 15 and 30
  using C# barcode generator
og_title: Tạo hình ảnh mã vạch bằng trình tạo mã vạch C# – hướng dẫn nhanh
schemas:
- author: Aspose
  dateModified: '2026-08-09'
  description: Create barcode image with a C# barcode generator and learn to generate
    multiple barcodes with custom aspect ratios in minutes.
  headline: Create barcode image with C# barcode generator – guide
  type: TechArticle
tags:
- barcode
- C#
- image generation
title: Tạo hình ảnh mã vạch bằng trình tạo mã vạch C# – hướng dẫn
url: /vi/python-java/general/create-barcode-image-with-c-barcode-generator-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch với trình tạo mã vạch C# – hướng dẫn

Nếu bạn cần **tạo hình ảnh mã vạch** nhanh chóng, hướng dẫn này sẽ chỉ cho bạn cách thực hiện bằng một trình tạo mã vạch C#. Bạn sẽ học cách tạo nhiều mã vạch, thay đổi tỷ lệ khung hình và lưu mỗi hình ảnh dưới dạng tệp PNG.

Việc tạo hình ảnh mã vạch là một nhiệm vụ phổ biến khi xây dựng hệ thống quản lý tồn kho, thiết bị điểm bán hàng, hoặc nhãn vận chuyển. Khi kết thúc tutorial này, bạn sẽ có hai tệp PNG sẵn sàng sử dụng, thể hiện các tỷ lệ khung hình khác nhau, và bạn sẽ hiểu cách mở rộng phương pháp này cho bất kỳ số lượng mã vạch nào.

## Yêu cầu trước

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)  
* Tham chiếu tới một thư viện mã vạch hỗ trợ DataBar Stacked Omnidirectional (ví dụ, **Aspose.BarCode for .NET**). Các đoạn mã mẫu sử dụng API của Aspose, nhưng các khái niệm áp dụng cho bất kỳ thư viện nào có các thuộc tính tương tự.

Bạn không cần một cơ sở dữ liệu hoặc máy chủ web riêng—đây là một ứng dụng console đơn giản.

## Bước 1: Thiết lập dự án console

Tạo một dự án console mới và thêm thư viện mã vạch qua NuGet.

```bash
dotnet new console -n BarcodeDemo
cd BarcodeDemo
dotnet add package Aspose.BarCode
```

Lệnh `dotnet add package` sẽ tải phiên bản ổn định mới nhất của **Aspose.BarCode**, cung cấp lớp `BarcodeGenerator` được sử dụng sau này.

## Bước 2: Viết chương trình đầy đủ

Mở *Program.cs* và thay thế nội dung của nó bằng ví dụ hoàn chỉnh dưới đây. Chương trình tạo một **hình ảnh mã vạch**, thay đổi tỷ lệ khung hình và lưu hai tệp PNG.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // -----------------------------------------------------------------
            // 1️⃣ Create a DataBar Stacked Omnidirectional generator with sample data
            // -----------------------------------------------------------------
            // The EncodeTypes enum tells the generator which barcode symbology to use.
            // Here we use DataBar Stacked Omnidirectional (GS1 DataBar) and encode
            // a sample GTIN (01) followed by a 14‑digit numeric string.
            var generator = new BarcodeGenerator(
                EncodeTypes.DatabarStackedOmniDirectional,
                "(01)12345678901231");

            // -----------------------------------------------------------------
            // 2️⃣ Configure common parameters (pixel size and X‑dimension)
            // -----------------------------------------------------------------
            // XDimension.Pixels controls the width of the smallest bar in the image.
            // A value of 2 gives a clear, high‑resolution output without increasing file size.
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // -----------------------------------------------------------------
            // 3️⃣ Set the first aspect ratio (15) and save the image
            // -----------------------------------------------------------------
            // AspectRatio influences the height of the barcode relative to its width.
            // An aspect ratio of 15 is typical for compact labels.
            generator.Parameters.Barcode.DataBar.AspectRatio = 15;

            string outputFolder = "BarcodeOutputs/";
            System.IO.Directory.CreateDirectory(outputFolder); // Ensure folder exists

            string file15 = $"{outputFolder}DatabarAspectRatio15.png";
            generator.Save(file15, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 15 → {file15}");

            // -----------------------------------------------------------------
            // 4️⃣ Change the aspect ratio to 30 and save a second image
            // -----------------------------------------------------------------
            // A larger aspect ratio (e.g., 30) produces a taller barcode, useful for
            // scanning devices that expect more vertical space.
            generator.Parameters.Barcode.DataBar.AspectRatio = 30;

            string file30 = $"{outputFolder}DatabarAspectRatio30.png";
            generator.Save(file30, BarCodeImageFormat.Png);
            Console.WriteLine($"Saved barcode with aspect ratio 30 → {file30}");

            // -----------------------------------------------------------------
            // 5️⃣ Verify that both files exist
            // -----------------------------------------------------------------
            Console.WriteLine("\nVerification:");
            Console.WriteLine($"File 15 exists: {System.IO.File.Exists(file15)}");
            Console.WriteLine($"File 30 exists: {System.IO.File.Exists(file30)}");
        }
    }
}
```

### Tại sao mỗi phần lại quan trọng

* **Create barcode image** – Hàm khởi tạo `BarcodeGenerator` khởi tạo đối tượng với ký hiệu và dữ liệu mong muốn.  
* **c# barcode generator** – Thuộc tính `Parameters` cho phép bạn kiểm soát toàn bộ các tùy chọn render; việc đặt `XDimension.Pixels` đảm bảo mỗi vạch hiển thị sắc nét trên màn hình.  
* **generate multiple barcodes** – Bằng cách thay đổi `DataBar.AspectRatio` giữa các lần lưu, cùng một instance của generator tạo ra hai hình ảnh khác nhau mà không cần tạo lại đối tượng, giúp hiệu quả hơn.

## Bước 3: Chạy chương trình và xem kết quả

Thực thi ứng dụng:

```bash
dotnet run
```

Bạn sẽ thấy đầu ra console tương tự như:

```
Saved barcode with aspect ratio 15 → BarcodeOutputs/DatabarAspectRatio15.png
Saved barcode with aspect ratio 30 → BarcodeOutputs/DatabarAspectRatio30.png

Verification:
File 15 exists: True
File 30 exists: True
```

Mở thư mục `BarcodeOutputs`. Bạn sẽ thấy hai tệp PNG:

* **DatabarAspectRatio15.png** – một mã vạch gọn gàng phù hợp cho nhãn có chiều cao hạn chế.  
* **DatabarAspectRatio30.png** – một mã vạch cao hơn mà nhiều máy quét có thể đọc một cách đáng tin cậy hơn từ khoảng cách xa.

Cả hai hình ảnh đều sẵn sàng để nhúng vào PDF, in trên biên lai, hoặc gửi tới ứng dụng di động.

## Bước 4: Mở rộng giải pháp để tạo bất kỳ số lượng mã vạch nào

Mẫu đã trình bày ở trên có thể mở rộng dễ dàng:

```csharp
int[] ratios = { 10, 15, 20, 30, 40 };
foreach (int ratio in ratios)
{
    generator.Parameters.Barcode.DataBar.AspectRatio = ratio;
    string path = $"{outputFolder}DatabarAspectRatio{ratio}.png";
    generator.Save(path, BarCodeImageFormat.Png);
    Console.WriteLine($"Saved aspect ratio {ratio} → {path}");
}
```

* **generate multiple barcodes** – Vòng lặp lặp qua một mảng các tỷ lệ khung hình, tạo một **hình ảnh mã vạch** riêng biệt cho mỗi giá trị.  
* Điều chỉnh `EncodeTypes` hoặc chuỗi được mã hoá để tạo QR code, Code 128, hoặc các ký hiệu khác mà không cần thay đổi logic xung quanh.

## Mẹo thực tế và những lỗi thường gặp

| Mẹo | Giải thích |
|-----|------------|
| **Tái sử dụng cùng một generator** | Khởi tạo lại `BarcodeGenerator` cho mỗi hình ảnh sẽ tạo ra chi phí không cần thiết. Thay đổi các tham số giữa các lần `Save` nhanh hơn và tiêu tốn ít bộ nhớ hơn. |
| **Xác thực thư mục đầu ra** | Luôn gọi `Directory.CreateDirectory` trước khi lưu; nếu không, `Save` sẽ ném ra ngoại lệ `DirectoryNotFoundException`. |
| **Chọn X‑dimension phù hợp** | Giá trị pixel quá thấp (ví dụ, 1) có thể làm cho mã vạch không đọc được trên màn hình độ phân giải thấp. Giá trị 2–3 hoạt động tốt cho hầu hết máy in. |
| **Chú ý tới việc mã hoá** | GS1 DataBar yêu cầu có tiền tố `(01)` cho GTIN. Nếu bạn bỏ qua dấu ngoặc, thư viện có thể tạo ra mã vạch không hợp lệ. |
| **Kiểm tra với máy quét thực tế** | Kiểm tra bằng mắt thường không đủ. Hãy thử các tệp PNG với phần cứng máy quét thực tế mà bạn dự định sử dụng. |

## Kết quả mong đợi (mô tả hình ảnh)

*Cả hai tệp PNG đều hiển thị một mã vạch DataBar Stacked Omnidirectional màu tối trên nền sáng. Phiên bản có tỷ lệ khung hình 15 ngắn hơn, trong khi phiên bản có tỷ lệ khung hình 30 cao gấp khoảng đôi.*

Nếu bạn nhúng các hình ảnh vào tài liệu, chúng sẽ hiển thị sắc nét vì chúng tôi đã đặt `XDimension.Pixels = 2`.

## Kết luận

Bây giờ bạn đã biết cách **tạo hình ảnh mã vạch** bằng **trình tạo mã vạch C#**, và bạn có thể **tạo nhiều mã vạch** bằng cách điều chỉnh tỷ lệ khung hình hoặc bất kỳ tham số nào khác. Ví dụ hoàn chỉnh, có thể chạy được này minh họa các thực hành tốt như tái sử dụng instance của generator, xử lý thư mục đầu ra, và xác minh việc tạo tệp.

Tiếp theo, bạn có thể khám phá:

* Thêm màu tùy chỉnh bằng `generator.Parameters.Barcode.Color` (từ khóa phụ: **c# barcode generator**)  
* Xuất sang các định dạng khác như JPEG hoặc SVG (`BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Svg`)  
* Tích hợp logic tạo mã vạch vào một Web API để phục vụ hình ảnh theo yêu cầu (từ khóa phụ

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã đầy đủ, hoạt động kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Create Barcode PNG – DataMatrix Aspect Ratio – Aspose.BarCode](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-aspect-ratio-customization/)
- [barcode generator tutorial c# – Customize Code 16K Barcode Aspect Ratios with Aspose.BarCode for .NET](/barcode/english/net/code-16k-encoding/code-16k-aspect-ratio-customization/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}