---
category: general
date: 2026-10-28
description: Tạo mã vạch bưu chính trong C# bằng định dạng Planet. Ví dụ mã vạch Planet
  này cho thấy cách thiết lập độ rộng mã vạch và lưu cả các thanh đầy và thanh trống.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate postal barcode
- set barcode width
- planet barcode example
language: vi
lastmod: 2026-10-28
og_description: Tạo mã vạch bưu chính bằng C# với ví dụ mã vạch Planet đầy đủ. Học
  cách đặt độ rộng mã vạch, tạo các thanh đầy và tạo hình ảnh thanh trống.
og_image_alt: Screenshot of a generated Planet postal barcode saved as PNG
og_title: Tạo mã vạch bưu điện trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-10-28'
  description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  headline: How to generate postal barcode in C# – planet example
  type: TechArticle
- description: Generate postal barcode in C# using the Planet format. This planet
    barcode example shows how to set barcode width and save both filled and empty
    bars.
  name: How to generate postal barcode in C# – planet example
  steps:
  - name: Build the project (`dotnet build`).
    text: Build the project (`dotnet build`).
  - name: Run the executable (`dotnet run`).
    text: Run the executable (`dotnet run`).
  - name: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
    text: Locate `PostalPlanetFilledBars.png` and `PostalPlanetEmptyBars.png` in the
      `bin/Debug/net6.0` folder.
  - name: Open each image; you should see a series of vertical bars representing the
      numeric string
    text: Open each image; you should see a series of vertical bars representing the
      numeric string
  type: HowTo
tags:
- barcode
- C#
- Aspose.BarCode
title: Cách tạo mã vạch bưu chính trong C# – ví dụ planet
url: /vi/python-java/general/how-to-generate-postal-barcode-in-c-planet-example/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch bưu chính trong C# – ví dụ Planet

Nếu bạn cần tạo mã vạch bưu chính trong C#, hướng dẫn này sẽ đưa bạn qua một giải pháp hoàn chỉnh. Bạn sẽ thấy một ví dụ thực tế về mã vạch Planet mã hoá một chuỗi số, cho phép bạn đặt độ rộng của mã vạch và lưu cả hình ảnh các thanh đầy và trống.

Việc tạo mã vạch bưu chính không đòi hỏi một quy trình xây dựng phức tạp. Khi kết thúc tutorial này, bạn có thể tích hợp việc tạo mã vạch vào bất kỳ ứng dụng .NET nào, tùy chỉnh X‑dimension và chọn thanh hiển thị đầy hay trống.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc phiên bản mới hơn đã được cài đặt  
* Môi trường phát triển C# (Visual Studio, VS Code, hoặc Rider)  
* Gói NuGet **Aspose.BarCode for .NET** (phiên bản 23.10 hoặc mới hơn)  

Bạn có thể thêm gói bằng lệnh sau:

```bash
dotnet add package Aspose.BarCode
```

Các đoạn mã dưới đây giả định rằng bạn đã thêm `using Aspose.BarCode.Generation;` ở đầu file của mình.

## Tạo mã vạch bưu chính với biểu tượng Planet

Bước đầu tiên là tạo một thể hiện `BarcodeGenerator` sử dụng biểu tượng Planet. Planet là định dạng mã vạch bưu chính được một số dịch vụ bưu chính quốc gia sử dụng.

```csharp
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Create a Planet barcode generator with the data to encode
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

        // Additional configuration will be applied here (see next steps)

        // Save the filled‑bars image
        barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

        // Switch to empty bars and save the second image
        barcodeGenerator.Parameters.Barcode.FilledBars = false;
        barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
    }
}
```

**Tại sao điều này quan trọng:**  
`EncodeTypes.Planet` báo cho thư viện sử dụng tiêu chuẩn mã vạch Planet, mã hoá dữ liệu số dưới dạng các thanh và khoảng trống. Hàm khởi tạo nhận chuỗi dữ liệu (`"123456"` trong trường hợp này) mà bạn muốn mã hoá.

Chạy chương trình sẽ tạo ra hai file PNG trong thư mục làm việc của tệp thực thi:

* **PostalPlanetFilledBars.png** – các thanh được vẽ dưới dạng hình chữ nhật đen đặc.  
* **PostalPlanetEmptyBars.png** – các thanh được vẽ dưới dạng hình chữ nhật trắng với viền đen, hữu ích khi in trên nền tối.

## Đặt độ rộng mã vạch (X‑dimension) tính bằng pixel

Kích thước hiển thị của mã vạch được kiểm soát bởi X‑dimension, định nghĩa độ rộng của một thanh duy nhất. Điều chỉnh giá trị này giúp mã vạch được quét đúng ở độ phân giải in mong muốn.

```csharp
// Define the width of each bar (X‑dimension) in pixels
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 4;
```

**Tại sao bạn nên đặt nó:**  
X‑dimension lớn hơn giúp mã vạch dễ quét hơn với máy quét độ phân giải thấp, trong khi giá trị nhỏ hơn giảm tổng kích thước ảnh cho việc in mật độ cao. Độ rộng mặc định là 2 pixel; 4 pixel là mức cân bằng phổ biến cho hầu hết máy in để bàn.

Bạn có thể thử các giá trị khác:

| Pixel | Trường hợp sử dụng điển hình |
|-------|------------------------------|
| 2     | Nhãn dày mật độ cao |
| 4     | In văn phòng tiêu chuẩn |
| 6‑8   | Biển hiệu kích thước lớn |

**Mẹo:** Luôn kiểm tra mã vạch đã tạo với máy quét mục tiêu sau khi thay đổi X‑dimension.

## Ví dụ mã vạch Planet – thanh đầy vs thanh trống

Mã vạch Planet có thể được vẽ dưới dạng thanh đặc (filled) hoặc thanh viền (empty). Thuộc tính `FilledBars` chuyển đổi hành vi này.

```csharp
// Save the barcode with the default filled bars
barcodeGenerator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);

// Configure the generator to produce empty (unfilled) bars
barcodeGenerator.Parameters.Barcode.FilledBars = false;

// Save the barcode with empty bars
barcodeGenerator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
```

**Tại sao bạn có thể chọn thanh trống:**  
Thanh trống cải thiện độ tương phản trên bao bì màu tối, vì phần bên trong màu trắng của mỗi thanh nổi bật trên nền tối. Thanh đầy là mặc định và hoạt động tốt trên vật liệu màu sáng.

**Kết quả mong đợi:**  

*Cả hai hình ảnh đều hiển thị cùng một dữ liệu đã mã hoá (`123456`).* Sự khác biệt duy nhất là kiểu thanh. Dưới đây là mô tả bằng văn bản về những gì bạn sẽ thấy:

* **Hình ảnh thanh đầy:** Các thanh dọc màu đen đặc trên nền trắng.  
* **Hình ảnh thanh trống:** Các viền đen tạo thành cùng một mẫu, với phần bên trong màu trắng.

Bạn có thể mở các file PNG bằng bất kỳ trình xem ảnh nào để xác nhận mẫu khớp với đặc tả Planet.

## Tùy chỉnh các thuộc tính mã vạch bổ sung (tùy chọn)

Mặc dù các bước cốt lõi ở trên đã bao phủ hầu hết các kịch bản, bạn có thể muốn tinh chỉnh các cài đặt khác:

| Thuộc tính | Mô tả | Giá trị điển hình |
|------------|------|-------------------|
| `Barcode.Color` | Màu nền của các thanh | `System.Drawing.Color.Black` |
| `Barcode.BackgroundColor` | Màu nền phía sau | `System.Drawing.Color.White` |
| `Barcode.CodeText` | Văn bản có thể đọc được hiển thị dưới mã vạch | Giống dữ liệu đã mã hoá hoặc nhãn tùy chỉnh |
| `Barcode.ImageFormat` | Định dạng đầu ra (PNG, JPEG, BMP, v.v.) | `BarCodeImageFormat.Png` |

Ví dụ thiết lập màu nền tùy chỉnh:

```csharp
barcodeGenerator.Parameters.Barcode.Color = System.Drawing.Color.DarkBlue;
```

Những điều chỉnh tùy chọn này giúp bạn phù hợp với bộ nhận diện thương hiệu hoặc đáp ứng các yêu cầu in ấn cụ thể.

## Những lỗi thường gặp và cách tránh

| Vấn đề | Nguyên nhân | Cách khắc phục |
|--------|-------------|----------------|
| Mã vạch không đọc được | X‑dimension quá nhỏ so với DPI của máy in | Tăng `XDimension.Pixels` lên 4 hoặc cao hơn |
| File ảnh bị hỏng | Thiếu quyền ghi trong thư mục đích | Sử dụng đường dẫn tuyệt đối hoặc đảm bảo thư mục tồn tại |
| Định dạng biểu tượng sai | Truyền `EncodeTypes.Code128` thay vì `EncodeTypes.Planet` | Xác minh đối số `EncodeTypes` khớp với định dạng bưu chính |

**Mẹo chuyên nghiệp:** Luôn tạo một mã vạch thử và quét nó bằng phần cứng dự định trước khi triển khai vào môi trường thực tế.

## Ví dụ đầy đủ, có thể chạy được

Dưới đây là một ứng dụng console tự chứa, tích hợp tất cả các bước đã thảo luận. Sao chép mã vào một dự án console .NET mới và chạy để thấy hai file PNG xuất hiện trong thư mục đầu ra.

```csharp
using System;
using Aspose.BarCode.Generation;

namespace PostalBarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // 1️⃣ Create a Planet barcode generator with the data to encode
            BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Planet, "123456");

            // 2️⃣ Set the width of each bar (X‑dimension) to 4 pixels
            generator.Parameters.Barcode.XDimension.Pixels = 4;

            // 3️⃣ Save the barcode with the default filled bars
            generator.Save("PostalPlanetFilledBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved filled‑bars barcode as PostalPlanetFilledBars.png");

            // 4️⃣ Configure the generator to produce empty (unfilled) bars
            generator.Parameters.Barcode.FilledBars = false;

            // 5️⃣ Save the barcode with empty bars
            generator.Save("PostalPlanetEmptyBars.png", BarCodeImageFormat.Png);
            Console.WriteLine("Saved empty‑bars barcode as PostalPlanetEmptyBars.png");
        }
    }
}
```

**Các bước xác minh:**  

1. Xây dựng dự án (`dotnet build`).  
2. Chạy tệp thực thi (`dotnet run`).  
3. Tìm `PostalPlanetFilledBars.png` và `PostalPlanetEmptyBars.png` trong thư mục `bin/Debug/net6.0`.  
4. Mở mỗi hình ảnh; bạn sẽ thấy một dãy các thanh dọc đại diện cho chuỗi số

## Bạn nên học gì tiếp theo?

Các tutorial sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch planet với các thanh đầy và trống](/barcode/english/python-java/general/how-to-create-planet-barcode-with-filled-and-empty-bars/)
- [Cách đặt độ rộng và tạo mã vạch Planet trong C#](/barcode/english/python-java/general/how-to-set-width-and-generate-a-planet-barcode-in-c/)
- [Tạo mã vạch bưu chính trong C# – Ví dụ đầy đủ về trình tạo](/barcode/english/python-java/general/create-postal-barcode-in-c-full-generator-example/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}