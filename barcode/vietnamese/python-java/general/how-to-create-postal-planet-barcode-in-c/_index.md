---
category: general
date: 2026-11-23
description: Tạo mã vạch Planet bưu chính bằng C# với Aspose.BarCode. Tìm hiểu cách
  tạo mã vạch Planet, thiết lập kích thước X và lưu các thanh đã điền hoặc trống.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create postal planet barcode
- how to generate planet barcode
- Aspose.BarCode C#
- postal barcode example
- Planet barcode settings
language: vi
lastmod: 2026-11-23
og_description: Tạo mã vạch planet bưu chính bằng C# và học cách tạo mã vạch planet
  với Aspose.BarCode. Tham khảo ví dụ đầy đủ để tạo các thanh đầy và trống.
og_image_alt: Example of a created postal planet barcode with filled bars
og_title: Cách tạo mã vạch Postal Planet bằng C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-11-23'
  description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  headline: How to create postal planet barcode in C#
  type: TechArticle
- description: Create postal planet barcode in C# with Aspose.BarCode. Learn how to
    generate planet barcode, set X‑dimension, and save filled or empty bars.
  name: How to create postal planet barcode in C#
  steps:
  - name: Changing the image format
    text: If your downstream system prefers JPEG, replace `BarCodeImageFormat.Png`
      with `BarCodeImageFormat.Jpeg`. JPEG introduces compression artifacts, so use
      it only when file size is a critical constraint.
  - name: Scaling the barcode
    text: 'You can enlarge the barcode while preserving the module width by adjusting
      the `Resolution` property:'
  - name: Using a custom background color
    text: 'The background can be set with:'
  type: HowTo
tags:
- barcode
- C#
- Aspose
title: Cách tạo mã vạch Postal Planet bằng C#
url: /vi/python-java/general/how-to-create-postal-planet-barcode-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch planet bưu chính trong C#

Nếu bạn cần **tạo mã vạch planet bưu chính** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn **cách tạo mã vạch planet** bằng thư viện Aspose.BarCode. Bạn sẽ thấy cách cấu hình kích thước X, chuyển đổi giữa các thanh đầy và trống, và lưu ảnh ở định dạng PNG.

Việc tạo mã vạch Planet thường được sử dụng cho các dịch vụ bưu chính yêu cầu ký hiệu mật độ cao, có thể đọc bằng máy. Khi kết thúc tutorial này, bạn sẽ có hai tệp PNG — một với các thanh đặc và một với các thanh rỗng — sẵn sàng tích hợp vào bất kỳ quy trình gửi thư nào.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 SDK hoặc phiên bản mới hơn.
* Visual Studio 2022 (hoặc bất kỳ trình soạn thảo C# nào) được cấu hình cho phát triển .NET.
* Giấy phép NuGet hoạt động cho **Aspose.BarCode for .NET**. Cài đặt gói bằng lệnh:

```bash
dotnet add package Aspose.BarCode
```

Không cần bất kỳ dịch vụ bên ngoài nào khác; thư viện thực hiện toàn bộ quá trình mã hoá trên máy cục bộ.

## Bước 1 – tạo mã vạch planet bưu chính

Hoạt động đầu tiên là khởi tạo một `BarcodeGenerator` cho ký hiệu **Planet** và cung cấp dữ liệu cần mã hoá. Chuỗi dữ liệu phải là số và không quá 12 chữ số theo quy chuẩn bưu chính.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

// Step 1: Create a Planet barcode generator with the data to encode
BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Việc tạo generator sẽ cấp phát tất cả các cấu trúc nội bộ cần thiết cho việc render. Giá trị enum `EncodeTypes.Planet` chọn thuật toán mã hoá phù hợp cho định dạng bưu chính.

## Bước 2 – đặt kích thước X để tăng khả năng hiển thị

Kích thước X định nghĩa chiều rộng của một mô-đun duy nhất (phần thanh nhỏ nhất). Giá trị 4 pixel cung cấp hình ảnh rõ ràng mà không làm tăng kích thước tổng thể của ảnh.

```csharp
// Step 2: Set the X‑dimension (module width) to 4 pixels
planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
```

Điều chỉnh kích thước X là cần thiết khi mã vạch sẽ được in trên phương tiện độ phân giải thấp. Cài đặt này sẽ được tái sử dụng cho phiên bản thanh rỗng để giữ cho cả hai ảnh nhất quán.

## Bước 3 – lưu mã vạch với các thanh đầy

Mặc định, generator sẽ render **các thanh đầy** (mô-đun đen đặc). Lưu ảnh chỉ cần một lời gọi phương thức duy nhất, ghi tệp PNG ra đĩa.

```csharp
// Step 3: Save the barcode with the default setting (filled bars)
planetFilled.Save("YOUR_DIRECTORY/PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
```

Thay `YOUR_DIRECTORY` bằng đường dẫn thực tế nơi bạn muốn lưu các tệp đầu ra. Enum `BarCodeImageFormat.Png` đảm bảo nén không mất dữ liệu, lý tưởng cho các quy trình xử lý tiếp theo.

## Bước 4 – tạo một generator Planet khác cho các thanh rỗng

Để tạo phiên bản sử dụng **các thanh rỗng** (mô-đun trắng trên nền đen), bạn cần một đối tượng `BarcodeGenerator` thứ hai. Việc tái sử dụng cùng một chuỗi dữ liệu đảm bảo cả hai ảnh đại diện cho cùng một mã bưu chính.

```csharp
// Step 4: Create another Planet barcode generator for the same data
BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
```

Việc tạo một generator riêng biệt tách biệt thuộc tính `FilledBars`, cho phép bạn chuyển đổi kiểu hiển thị mà không ảnh hưởng đến ảnh đầu tiên.

## Bước 5 – cấu hình generator để render các thanh rỗng

Cờ `FilledBars` đảo ngược chế độ render. Đặt nó thành `false` sẽ khiến thư viện vẽ các thanh dưới dạng rỗng (transparent) trong khi nền vẫn giữ màu đặc.

```csharp
// Step 5: Apply the same X‑dimension and configure empty bars
planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
planetEmpty.Parameters.Barcode.FilledBars = false;
```

Giữ kích thước X giống hệt phiên bản đầy đảm bảo rằng cả hai tệp PNG có cùng kích thước, giúp đơn giản hoá việc tính toán bố cục trong các mẫu in.

## Bước 6 – lưu mã vạch với các thanh rỗng

Cuối cùng, ghi ảnh thanh rỗng ra đĩa. Định dạng PNG vẫn được sử dụng, nhưng bạn có thể chuyển sang JPEG hoặc BMP bằng cách thay đổi giá trị `BarCodeImageFormat`.

```csharp
// Step 6: Save the barcode that renders empty bars
planetEmpty.Save("YOUR_DIRECTORY/PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

Tại thời điểm này bạn đã có hai tệp:

* `PostalPlanetFilledBars.png` – các thanh đen đặc.
* `PostalPlanetEmptyBars.png` – các thanh rỗng trên nền đen.

Cả hai đều đáp ứng quy chuẩn bưu chính cho ký hiệu Planet.

## Mã nguồn hoàn chỉnh

Kết hợp tất cả các bước lại sẽ tạo ra một ứng dụng console gọn gàng mà bạn có thể chạy ngay.

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace PlanetBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Create a Planet barcode with filled bars
            BarcodeGenerator planetFilled = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetFilled.Parameters.Barcode.XDimension.Pixels = 4;
            planetFilled.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

            // Create a Planet barcode with empty bars
            BarcodeGenerator planetEmpty = new BarcodeGenerator(EncodeTypes.Planet, "123456");
            planetEmpty.Parameters.Barcode.XDimension.Pixels = 4;
            planetEmpty.Parameters.Barcode.FilledBars = false;
            planetEmpty.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcodes generated successfully.");
        }
    }
}
```

Biên dịch và chạy chương trình:

```bash
dotnet run
```

Console sẽ in *Barcodes generated successfully.* và hai tệp PNG sẽ xuất hiện trong thư mục dự án.

## Kết quả mong đợi

Dưới đây là hình ảnh đại diện cho ảnh các thanh đầy. Phiên bản các thanh rỗng trông giống hệt, chỉ khác ở chỗ các thanh trong suốt.

![Ví dụ về mã vạch planet bưu chính đã tạo với các thanh đầy](postal-planet-filled.png)

*Văn bản thay thế ảnh:* **Ví dụ về mã vạch planet bưu chính đã tạo với các thanh đầy** (chứa từ khóa chính).

Cả hai ảnh đều có kích thước mặc định 150 × 150 pixel, nhưng bạn có thể điều chỉnh kích thước tổng thể bằng các tham số `ImageWidth` và `ImageHeight` nếu cần độ phân giải khác.

## Các biến thể tùy chọn

### Thay đổi định dạng ảnh

Nếu hệ thống downstream của bạn ưu tiên JPEG, thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`. JPEG sẽ tạo ra các artefact nén, vì vậy chỉ dùng khi kích thước tệp là yếu tố quan trọng.

### Phóng to mã vạch

Bạn có thể phóng to mã vạch trong khi giữ nguyên độ rộng mô-đun bằng cách điều chỉnh thuộc tính `Resolution`:

```csharp
planetFilled.Parameters.ImageResolution = 300; // DPI
```

Giá trị DPI cao hơn cải thiện chất lượng in trên máy in laser.

### Sử dụng màu nền tùy chỉnh

Nền có thể được đặt bằng:

```csharp
planetEmpty.Parameters.Barcode.BackColor = System.Drawing.Color.LightGray;
```

Điều này hữu ích cho việc kiểm tra trực quan nhưng nên tránh trong nhãn bưu chính sản xuất, vì chúng yêu cầu nền trắng.

## Câu hỏi thường gặp

**Điều này có hoạt động với .NET Core không?**  
Có. Thư viện Aspose.BarCode nhắm tới .NET Standard 2.0, tương thích với .NET 5, .NET 6 và .NET Core 3.1.

**Nếu chuỗi dữ liệu chứa ký tự không phải số thì sao?**  
Mã vạch Planet chỉ chấp nhận đầu vào số. Việc cung cấp chữ cái hoặc ký hiệu sẽ gây ra `BarcodeException`. Hãy xác thực đầu vào trước khi tạo generator.

**Tôi có thể tạo mã vạch trong bộ nhớ mà không ghi ra đĩa không?**  
Sử dụng phương thức `GenerateBarCodeImage` để nhận một đối tượng `System.Drawing.Image`, sau đó stream trực tiếp tới phản hồi hoặc cơ sở dữ liệu.

## Kết luận

Bây giờ bạn đã biết cách **tạo mã vạch planet bưu chính** trong C# và hiểu **cách tạo mã vạch planet** với cả hai kiểu thanh đầy và thanh rỗng. Tutorial đã bao phủ toàn bộ quy trình — từ khởi tạo generator, cấu hình kích thước X, bật/tắt cờ `FilledBars`, đến lưu tệp PNG. Hãy thử nghiệm các định dạng ảnh, cài đặt DPI và màu nền để điều chỉnh mã vạch phù hợp với hệ thống gửi thư của bạn.

Trong bước tiếp theo, hãy khám phá các ký hiệu bưu chính khác như **POSTNET** hoặc **Intelligent Mail** bằng cùng API Aspose.BarCode. Điều chỉnh các tham số như `EncodeTypes.Postnet` theo cùng mẫu đã trình bày ở đây, giúp bạn xây dựng một bộ công cụ tạo mã vạch toàn diện trong một codebase duy nhất.

## Bạn Nên Học Gì Tiếp Theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm mã mẫu đầy đủ với các giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Create empty planet barcode, generate postal barcode in C#](/barcode/english/python-java/general/create-empty-planet-barcode-generate-postal-barcode-in-c/)
- [How to set width and generate a Planet barcode in C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Generate Postal Barcode in C# – Complete Guide with Planet Barcode](/barcode/english/python-java/general/generate-postal-barcode-in-c-complete-guide-with-planet-barc/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}