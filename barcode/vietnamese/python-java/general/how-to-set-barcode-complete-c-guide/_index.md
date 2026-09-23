---
category: general
date: 2026-08-15
description: Cách thiết lập các tham số mã vạch trong C# và tạo hình ảnh mã vạch.
  Học từng bước để tạo mã vạch Databar và lưu tệp PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- how to set barcode
- how to generate barcode
- create databar barcode
- generate barcode image c#
language: vi
lastmod: 2026-08-15
og_description: Cách thiết lập mã vạch trong C# với Aspose.Barcode, sau đó tạo hình
  ảnh mã vạch C#. Hãy làm theo hướng dẫn này để tạo mã vạch Databar và lưu dưới dạng
  tệp PNG.
og_image_alt: Screenshot of a Databar barcode saved as PNG using C# code
og_title: Cách thiết lập mã vạch trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-15'
  description: How to set barcode parameters in C# and generate barcode images. Learn
    step‑by‑step to create Databar barcode and save PNG files.
  headline: How to set barcode – complete C# guide
  type: TechArticle
tags:
- barcode
- C#
- Aspose.Barcode
title: Cách thiết lập mã vạch – hướng dẫn C# đầy đủ
url: /vi/python-java/general/how-to-set-barcode-complete-c-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách thiết lập mã vạch – hướng dẫn đầy đủ C# 

Nếu bạn đang tìm kiếm **cách thiết lập mã vạch** trong một dự án .NET, hướng dẫn này sẽ chỉ cho bạn các bước cần thiết. Bạn sẽ học **cách tạo mã vạch** dưới dạng hình ảnh, tạo mã Databar, và kiểm soát chiều cao thanh pixel‑by‑pixel — tất cả bằng mã C# sạch sẽ, sẵn sàng cho môi trường production.  

Trong hướng dẫn này bạn sẽ:

* Cài đặt gói NuGet cần thiết.  
* Tạo mã Databar Omnidirectional (phần “tạo mã Databar”).  
* Điều chỉnh X‑dimension và chiều cao thanh để minh họa **cách thiết lập mã vạch** kích thước.  
* Lưu kết quả dưới dạng tệp PNG, bao phủ kịch bản **tạo hình ảnh mã vạch C#**.  

Mã này hoạt động với Aspose.Barcode for .NET mới nhất (phiên bản 24.12 tại thời điểm viết) và chạy trên .NET 6 hoặc cao hơn.  

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6 SDK (hoặc bất kỳ phiên bản nào mới hơn).  
* Một IDE như Visual Studio 2022 hoặc VS Code.  
* Kết nối Internet để tải gói NuGet Aspose.Barcode.  

Không cần thư viện bên thứ ba nào khác.  

## Bước 1: Cài đặt Aspose.Barcode cho .NET

Cách đáng tin cậy nhất để **tạo mã vạch** dưới dạng hình ảnh trong C# là sử dụng Aspose.Barcode. Mở terminal trong thư mục dự án của bạn và chạy:

```bash
dotnet add package Aspose.BarCode
```

Lệnh này sẽ thêm phiên bản ổn định mới nhất vào tệp dự án của bạn, đảm bảo bạn có lớp `BarcodeGenerator` và enum `EncodeTypes`.  

*Mẹo:* Giữ gói luôn cập nhật (`dotnet list package --outdated`) để nhận được các bản sửa lỗi và các biểu tượng mã vạch mới.  

## Bước 2: Tạo mã Databar (tạo mã Databar)

Databar Omnidirectional rất phù hợp cho bán lẻ và logistics vì nó có thể mã hoá giá trị GTIN‑14 cùng với dữ liệu bổ sung. Đoạn mã sau tạo đối tượng mã vạch:

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

// Step 2: Initialize the generator for a Databar Omnidirectional barcode
BarcodeGenerator generator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

*Tại sao điều này quan trọng:* Enum `EncodeTypes.DatabarOmniDirectional` thông báo cho thư viện sử dụng biểu tượng Databar, trong khi chuỗi `"(01)12345678901231"` tuân theo định dạng GS1 Application Identifier cho một GTIN 14 chữ số.  

## Bước 3: Định nghĩa các tham số chung – X‑dimension và chiều cao cơ bản

Hầu hết các máy quét mã vạch yêu cầu X‑dimension tối thiểu (độ rộng của thanh mảnh nhất). Đặt nó thành 2 pixel sẽ tạo ra một hình ảnh gọn gàng nhưng vẫn dễ đọc.  

```csharp
// Step 3: Set a 2‑pixel X‑dimension (common for most scanners)
generator.Parameters.Barcode.XDimension.Pixels = 2;
```

Bạn có thể điều chỉnh chiều cao thanh sau này mà không cần tạo lại generator — đây là cốt lõi của **cách thiết lập mã vạch** các thuộc tính sau khi khởi tạo.  

## Bước 4: Đặt chiều cao thanh đầu tiên và lưu hình ảnh (tạo hình ảnh mã vạch C#)

Bây giờ chúng ta sẽ minh họa phần đầu tiên của **cách thiết lập mã vạch** chiều cao. Chiều cao thanh kiểm soát độ dài hiển thị của mỗi thanh; giá trị 30 pixel tạo ra một mã vạch ngắn, trong khi 60 pixel tạo ra phiên bản cao hơn.  

```csharp
// Step 4a: 30‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 30;

// Save the first PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

Sau khi thực thi, `DatabarBarHeight30Pixels.png` chứa một mã Databar với thanh cao 30 pixel. Mở tệp trong bất kỳ trình xem ảnh nào để xác nhận kết quả.  

## Bước 5: Thay đổi chiều cao thanh và lưu ảnh thứ hai

Để minh họa rằng **cách thiết lập mã vạch** có thể thay đổi ngay lập tức, chúng ta sẽ thay đổi chiều cao thanh thành 60 pixel và ghi một tệp thứ hai.  

```csharp
// Step 5a: 60‑pixel bar height
generator.Parameters.Barcode.BarHeight.Pixels = 60;

// Save the second PNG image
generator.Save(@"YOUR_DIRECTORY\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Bây giờ bạn có hai tệp PNG hiển thị cùng dữ liệu Databar nhưng với chiều cao hiển thị khác nhau. Điều này hữu ích khi bạn cần một mã vạch lớn hơn cho nhãn in hoặc nhỏ hơn cho hiển thị trên màn hình.  

## Bước 6: Ví dụ đầy đủ, có thể chạy

Kết hợp tất cả lại, dưới đây là một chương trình console tự chứa thực hiện tất cả các bước đã mô tả ở trên. Sao chép mã vào một tệp `Program.cs` mới, thay thế `YOUR_DIRECTORY` bằng đường dẫn thư mục thực tế, và chạy nó.  

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // Common parameters
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // 2‑pixel narrow bar

        // First image: 30‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save(@"C:\Barcodes\DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode.");

        // Second image: 60‑pixel height
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save(@"C:\Barcodes\DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode.");

        // Dispose the generator to free native resources
        generator.Dispose();
    }
}
```

**Kết quả mong đợi**

```
Saved 30-pixel barcode.
Saved 60-pixel barcode.
```

Và thư mục `C:\Barcodes` (hoặc đường dẫn bạn đã cung cấp) chứa hai tệp PNG. Cả hai hình ảnh đều hiển thị một mã Databar Omnidirectional hợp lệ có thể được máy đọc GS1 tiêu chuẩn quét.  

## Câu hỏi thường gặp

**Liệu điều này có hoạt động với các định dạng ảnh khác không?**  
Có. Thay `BarCodeImageFormat.Png` bằng `Jpeg`, `Bmp`, `Gif`, hoặc `Tiff` để tạo ra loại tệp tương ứng.  

**Tôi có thể thay đổi màu nền (foreground) không?**  
Đặt `generator.Parameters.Barcode.ForeColor` thành bất kỳ giá trị `System.Drawing.Color` nào, ví dụ `Color.Blue`.  

**Nếu tôi cần một biểu tượng (symbology) khác thì sao?**  
Truyền một giá trị `EncodeTypes` khác vào constructor, chẳng hạn `EncodeTypes.Code128` cho mã vạch tuyến tính hoặc `EncodeTypes.QR` cho mã ma trận.  

**Có cách nào để nhúng mã vạch vào PDF không?**  
Aspose.Barcode cung cấp lớp `PdfGenerator`. Sau khi tạo hình ảnh, bạn có thể thêm nó vào một trang PDF bằng Aspose.PDF.  

## Các thực tiễn tốt nhất cho việc tạo mã vạch trong C#

* **Tái sử dụng instance `BarcodeGenerator`** khi bạn chỉ cần điều chỉnh kích thước — điều này tránh việc cấp phát bộ nhớ không cần thiết.  
* **Giải phóng (Dispose) generator** (`generator.Dispose()`) sau khi hoàn thành để giải phóng tài nguyên gốc kịp thời.  
* **Xác thực dữ liệu đầu vào** (ví dụ, độ dài GTIN) trước khi tạo mã vạch để tránh ngoại lệ thời gian chạy.  
* **Kiểm tra bằng máy quét thực tế** sau khi thay đổi X‑dimension hoặc chiều cao thanh; các giá trị cực đoan có thể ảnh hưởng đến khả năng đọc.  
* **Đảm bảo thư mục đầu ra có quyền ghi** cho tài khoản thực thi; nếu không `Save` sẽ ném ra `UnauthorizedAccessException`.  

## Kết luận

Bây giờ bạn đã biết **cách thiết lập mã vạch** các thuộc tính như X‑dimension và chiều cao thanh, **cách tạo mã vạch** dưới dạng hình ảnh trong C#, và các bước chính xác để **tạo mã Databar** bằng Aspose.Barcode. Bằng cách theo dõi ví dụ đầy đủ, bạn có thể tạo nhiều tệp PNG với các đặc điểm hình ảnh khác nhau, đáp ứng yêu cầu **tạo hình ảnh mã vạch C#** cho bất kỳ ứng dụng .NET nào.  

Tiếp theo, hãy khám phá các chủ đề liên quan như **cách tạo mã vạch** hàng loạt, nhúng mã vạch vào PDF, hoặc chuyển sang các biểu tượng khác như QR hoặc Code 128. Thử nghiệm các tham số được trình bày ở đây để tinh chỉnh giao diện mã vạch cho môi trường quét cụ thể của bạn. Chúc lập trình vui vẻ!  

## Bạn Nên Học Gì Tiếp Theo?

Các hướng dẫn sau đây bao gồm các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên đều có các ví dụ mã hoạt động đầy đủ kèm theo giải thích từng bước để giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.  

- [How to Generate DataMatrix Barcodes (ECC 200) with Aspose.BarCode for .NET](/barcode/english/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)  
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)  
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)  

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}