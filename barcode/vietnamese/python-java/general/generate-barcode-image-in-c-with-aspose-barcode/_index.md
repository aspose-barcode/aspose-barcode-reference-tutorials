---
category: general
date: 2026-08-06
description: Tạo hình ảnh mã vạch trong C# bằng Aspose.BarCode. Tìm hiểu cách tạo
  Databar, điều chỉnh kích thước mã vạch tùy chỉnh và thay đổi chiều cao mã vạch bằng
  mã đơn giản.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- generate barcode image
- how to generate databar
- custom barcode size
- create databar barcode
- change barcode height
language: vi
lastmod: 2026-08-06
og_description: Tạo hình ảnh mã vạch trong C# với Aspose.BarCode. Hướng dẫn này cho
  bạn cách tạo mã vạch Databar Omnidirectional, tùy chỉnh kích thước và thay đổi chiều
  cao mã vạch một cách hiệu quả.
og_image_alt: Screenshot of a Databar barcode generated with custom height in C#
og_title: Tạo hình ảnh mã vạch trong C# – hướng dẫn đầy đủ Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-06'
  description: Generate barcode image in C# using Aspose.BarCode. Learn how to generate
    Databar, adjust custom barcode size, and change barcode height with simple code.
  headline: Generate barcode image in C# with Aspose.BarCode
  type: TechArticle
- questions:
  - answer: The evaluation version of Aspose.BarCode works without a license but adds
      a small watermark. For production use, apply a purchased license using `License
      license = new License(); license.SetLicense("Aspose.BarCode.lic");`.
    question: Can I generate a barcode without installing a license?
  - answer: Yes. Very small X‑dimensions can make the barcode unreadable on low‑resolution
      printers. A minimum of 1 px for screen rendering is recommended; for print,
      use at least 0.25 mm.
    question: Does changing the X‑dimension affect readability?
  - answer: 'Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`. You
      may also set `generator.Parameters.ImageQuality` to control compression. ##
      Conclusion You now know how to **generate barcode image** in C# using Aspose.BarCode,
      how to **create Databar barcode**, adjust a **custom barcode size**, '
    question: What if I need to generate a barcode in JPEG format?
  type: FAQPage
tags:
- barcode
- C#
- Aspose.BarCode
title: Tạo hình ảnh mã vạch trong C# với Aspose.BarCode
url: /vi/python-java/general/generate-barcode-image-in-c-with-aspose-barcode/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch trong C# với Aspose.BarCode

Nếu bạn cần **tạo hình ảnh mã vạch** một cách lập trình, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Dù bạn đang xây dựng hệ thống quản lý hàng tồn kho bán lẻ hay cổng thông tin theo dõi logistics, bạn sẽ thấy quy trình đầy đủ để tạo mã Databar Omnidirectional, điều chỉnh kích thước và lưu kết quả dưới dạng tệp PNG.

Việc tạo hình ảnh mã vạch là một yêu cầu phổ biến, nhưng các nhà phát triển thường thắc mắc **cách tạo Databar** với kích thước chính xác mà họ cần. Trong tutorial này, bạn sẽ học cách tạo mã Databar, tùy chỉnh chiều rộng và chiều cao, và thay đổi chiều cao mã vạch mà không phải viết lại toàn bộ trình tạo.

## Các yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc mới hơn (mã hoạt động với .NET Core và .NET Framework)
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)
* Giấy phép Aspose.BarCode for .NET hợp lệ (phiên bản dùng thử miễn phí đủ cho việc thử nghiệm)
* Kiến thức cơ bản về cú pháp C#

## Bước 1: Cài đặt Aspose.BarCode

Thêm gói NuGet Aspose.BarCode vào dự án của bạn:

```bash
dotnet add package Aspose.BarCode
```

Gói này chứa lớp `BarcodeGenerator` được sử dụng xuyên suốt tutorial. Sau khi cài đặt, hãy khôi phục dự án để tải các phụ thuộc.

## Bước 2: Tạo một trình tạo mã vạch cơ bản

Dòng mã đầu tiên tạo một **trình tạo mã vạch** sẽ sinh ra biểu tượng Databar Omnidirectional. Enum `EncodeTypes.DatabarOmniDirectional` cho thư viện biết sẽ sử dụng loại symbology nào, và chuỗi dữ liệu tuân theo cú pháp GS1 Application Identifier.

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // Step 2: Initialize the generator for a Databar Omnidirectional barcode
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional,
            "(01)12345678901231"); // GS1-14 data (example GTIN)
```

**Tại sao điều này quan trọng:** Đối tượng `BarcodeGenerator` là điểm vào cho mọi thao tác với mã vạch. Bằng cách chọn `DatabarOmniDirectional` bạn đảm bảo đầu ra tuân thủ tiêu chuẩn GS1 cho việc quét bán lẻ.

## Bước 3: Đặt X‑dimension tùy chỉnh (độ rộng module)

X‑dimension kiểm soát độ rộng của thanh mỏng nhất. Đặt giá trị pixel nhỏ sẽ cho bạn một mã vạch gọn, trong khi giá trị lớn hơn sẽ làm tăng tổng chiều rộng.

```csharp
        // Step 3: Define a custom X‑dimension (module width) of 2 px
        generator.Parameters.Barcode.XDimension.Pixels = 2;
```

**Giải thích:** X‑dimension 2 pixel là lựa chọn phổ biến cho màn hình độ phân giải cao. Điều chỉnh giá trị này nếu bạn cần mật độ hình ảnh chặt hơn hoặc lỏng hơn.

## Bước 4: Tạo hình ảnh mã vạch đầu tiên với chiều cao cụ thể

Chiều cao mã vạch độc lập với X‑dimension. Ở đây chúng ta đặt chiều cao thanh là **30 px**, sau đó lưu hình ảnh dưới dạng PNG.

```csharp
        // Step 4: Set bar height to 30 px and save the image
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

**Kết quả:** Bạn sẽ có một tệp tên `DatabarBarHeight30Pixels.png` hiển thị mã Databar cao 30 px. Điều này minh họa khả năng **điều chỉnh kích thước mã vạch** cho trường hợp sử dụng cụ thể như nhãn nhỏ.

## Bước 5: Thay đổi chiều cao mã vạch cho phiên bản lớn hơn

Nếu cùng một mã vạch phải xuất hiện trên nhãn lớn hơn, bạn chỉ cần sửa thuộc tính chiều cao và tái sử dụng cùng một instance của trình tạo.

```csharp
        // Step 5: Increase the bar height to 60 px for a larger barcode
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
    }
}
```

**Tại sao bạn có thể tái sử dụng trình tạo:** Thay đổi `BarHeight.Pixels` cập nhật bố cục nội bộ mà không cần tạo lại đối tượng, giúp tiết kiệm bộ nhớ và giữ nguyên chuỗi dữ liệu. Đây là cách được khuyến nghị để **thay đổi chiều cao mã vạch** một cách linh hoạt.

## Bước 6: Kiểm tra kết quả

Mở hai tệp PNG trong bất kỳ trình xem ảnh nào. Bạn sẽ thấy hai mã Databar Omnidirectional mã hoá cùng một GTIN nhưng khác nhau về kích thước dọc:

* `DatabarBarHeight30Pixels.png` – cao 30 px, phù hợp cho biên lai gọn.
* `DatabarBarHeight60Pixels.png` – cao 60 px, lý tưởng cho nhãn kệ hàng lớn hơn.

Cả hai hình ảnh đều giữ cùng một X‑dimension, vì vậy tỷ lệ thanh‑khoảng trống vẫn đồng nhất trong khi tổng chiều cao được mở rộng.

## Các biến thể phổ biến và trường hợp góc cạnh

| Tình huống | Cách xử lý |
|-----------|------------|
| **Symbology mã vạch khác** | Thay `EncodeTypes.DatabarOmniDirectional` bằng giá trị enum khác (ví dụ: `EncodeTypes.Code128`). Phần còn lại của mã không thay đổi. |
| **Kích thước không phải pixel** | Sử dụng `generator.Parameters.Barcode.XDimension.Millimeters` hoặc `BarHeight.Millimeters` nếu bạn cần đo lường thực tế cho đầu ra sẵn sàng in. |
| **Nền trong suốt** | Đặt `generator.Parameters.ImageBackgroundColor = Color.Transparent;` trước khi gọi `Save`. |
| **Đầu ra độ phân giải cao** | Tăng cả `XDimension.Pixels` và `BarHeight.Pixels` một cách tỷ lệ, hoặc lưu dưới dạng `BarCodeImageFormat.Tiff` để có chất lượng không mất dữ liệu. |
| **Nhiều mã vạch trong một hình ảnh** | Tạo các instance `BarcodeGenerator` riêng biệt, render mỗi cái vào một `Bitmap`, sau đó ghép chúng bằng `Graphics.DrawImage`. |

**Mẹo chuyên nghiệp:** Luôn kiểm tra mã vạch đã tạo bằng một máy quét thực tế trước khi đưa vào sản xuất. Máy quét có thể diễn giải các thanh quá mỏng khác nhau tùy vào ánh sáng và chất lượng cảm biến.

## Toàn bộ mã nguồn để tham khảo

```csharp
using System;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

namespace BarcodeDemo
{
    class Program
    {
        static void Main()
        {
            // Initialize the generator for a Databar Omnidirectional barcode
            BarcodeGenerator generator = new BarcodeGenerator(
                EncodeTypes.DatabarOmniDirectional,
                "(01)12345678901231"); // Example GTIN

            // Custom X‑dimension (module width) – 2 px
            generator.Parameters.Barcode.XDimension.Pixels = 2;

            // First image: 30 px height
            generator.Parameters.Barcode.BarHeight.Pixels = 30;
            generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);

            // Second image: 60 px height (larger barcode)
            generator.Parameters.Barcode.BarHeight.Pixels = 60;
            generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);

            Console.WriteLine("Barcode images generated successfully.");
        }
    }
}
```

Sao chép đoạn mã vào một dự án console mới, chạy nó, và bạn sẽ thấy hai tệp PNG xuất hiện trong thư mục output.

## Câu hỏi thường gặp

**H: Có thể tạo mã vạch mà không cài đặt giấy phép không?**  
Đ: Phiên bản dùng thử của Aspose.BarCode hoạt động mà không cần giấy phép nhưng sẽ thêm một watermark nhỏ. Đối với môi trường sản xuất, hãy áp dụng giấy phép đã mua bằng cách sử dụng `License license = new License(); license.SetLicense("Aspose.BarCode.lic");`.

**H: Thay đổi X‑dimension có ảnh hưởng đến khả năng đọc không?**  
Đ: Có. X‑dimension quá nhỏ có thể khiến mã vạch không đọc được trên máy in độ phân giải thấp. Đối với hiển thị trên màn hình, tối thiểu 1 px được khuyến nghị; đối với in, ít nhất 0.25 mm.

**H: Nếu muốn tạo mã vạch ở định dạng JPEG thì sao?**  
Đ: Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`. Bạn cũng có thể đặt `generator.Parameters.ImageQuality` để điều chỉnh mức nén.

## Kết luận

Bạn đã biết cách **tạo hình ảnh mã vạch** trong C# bằng Aspose.BarCode, cách **tạo mã Databar**, điều chỉnh **kích thước mã vạch tùy chỉnh**, và **thay đổi chiều cao mã vạch** khi cần. Ví dụ hoàn chỉnh minh họa quy trình phổ biến nhất, và bảng các biến thể giúp bạn xử lý các trường hợp thực tế.

Tiếp theo, hãy khám phá các chủ đề liên quan như **nhúng mã vạch vào tài liệu PDF**, **tạo hàng loạt nhiều mã vạch**, và **sử dụng QR code cho thanh toán di động**. Mỗi kịch bản này dựa trên các nguyên tắc đã được trình bày ở đây, vì vậy bạn có thể mở rộng kiến thức một cách tự tin.

Chúc lập trình vui vẻ, và mã vạch của bạn luôn quét được một cách hoàn hảo!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Generate barcode image – GS1 Coupon UPC-A Databar](/barcode/english/net/gs1-barcode-encoding/gs1-coupon-upc-a-databar-configuration/)
- [How to generate Aztec barcode with custom aspect ratio using Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [How to Generate Barcode – Code 39 Configuration with Aspose.BarCode](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-code-39-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}