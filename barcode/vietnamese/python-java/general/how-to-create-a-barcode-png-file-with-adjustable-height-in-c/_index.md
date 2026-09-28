---
category: general
date: 2026-08-19
description: Học cách tạo tệp PNG mã vạch trong C# và điều chỉnh chiều cao của nó,
  bao gồm cách tạo hình ảnh mã vạch và thay đổi chiều cao mã vạch một cách dễ dàng.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- barcode png file
- how to generate barcode
- adjust barcode height
- change barcode height
language: vi
lastmod: 2026-08-19
og_description: Tạo tệp PNG mã vạch bằng C# và học cách tạo hình ảnh mã vạch, điều
  chỉnh chiều cao mã vạch, và thay đổi chiều cao mã vạch để quét tối ưu.
og_image_alt: barcode PNG file showing Databar OmniDirectional barcode at two heights
og_title: Tạo tệp PNG mã vạch trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-08-19'
  description: Learn how to generate a barcode PNG file in C# and adjust its height,
    covering how to generate barcode images and change barcode height easily.
  headline: How to create a barcode PNG file with adjustable height in C#
  type: TechArticle
- questions:
  - answer: Yes. Replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`,
      `BarCodeImageFormat.Bmp`, etc.
    question: Can I generate other image formats (JPEG, BMP)?
  - answer: Serve the generated PNG via an HTTP endpoint or convert it to a Base64
      string and place it in an `<img>` tag’s `src` attribute.
    question: How do I embed the PNG in a web page?
  - answer: 'Use `generator.Parameters.Image.BackgroundColor = Color.White;` (or any
      `System.Drawing.Color`). ## Conclusion You now know how to **generate a barcode
      PNG file** in C# and precisely **adjust barcode height** to meet scanning or
      design requirements. By changing the `BarHeight.Pixels` property you ca'
    question: Is there a way to set the background color?
  type: FAQPage
tags:
- barcode
- C#
- image generation
title: Cách tạo tệp PNG mã vạch với chiều cao có thể điều chỉnh trong C#
url: /vi/python-java/general/how-to-create-a-barcode-png-file-with-adjustable-height-in-c/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo file PNG barcode với chiều cao có thể điều chỉnh trong C#

Nếu bạn cần tạo một **file PNG barcode** trong C#, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ thấy một ví dụ hoàn chỉnh, có thể chạy được, minh họa **cách tạo ảnh barcode** và **cách điều chỉnh chiều cao barcode** cho các trường hợp sử dụng khác nhau.

Việc tạo file PNG barcode là yêu cầu phổ biến cho các hệ thống quản lý tồn kho, máy POS và bất kỳ ứng dụng nào phải in hoặc hiển thị dữ liệu có thể máy đọc được. Khi kết thúc tutorial này, bạn sẽ có thể thay đổi chiều cao barcode, lưu nhiều file PNG, và hiểu được ảnh hưởng của chiều cao đến độ tin cậy khi quét.

## Các điều kiện tiên quyết

Trước khi bắt đầu, hãy chắc chắn rằng bạn đã có:

* .NET 6.0 SDK hoặc phiên bản mới hơn được cài đặt  
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ .NET)  
* Gói NuGet **Aspose.BarCode for .NET** (mẫu code sử dụng thư viện này)  

Bạn có thể thêm gói này từ dòng lệnh:

```bash
dotnet add package Aspose.BarCode
```

> **Mẹo chuyên nghiệp:** Phiên bản dùng thử miễn phí của Aspose.BarCode hoạt động cho việc phát triển và thử nghiệm. Đối với môi trường sản xuất, hãy mua key bản quyền.

## Cài đặt thư viện barcode

Bước đầu tiên là tham chiếu thư viện vào dự án của bạn. Thêm các chỉ thị `using` sau vào đầu file C#:

```csharp
using Aspose.BarCode.Generation;
using Aspose.BarCode;
```

Các namespace này cung cấp quyền truy cập tới `BarcodeGenerator`, `EncodeTypes`, và `BarCodeImageFormat`.

## Tạo file PNG barcode

Bây giờ chúng ta sẽ tạo một thể hiện `BarcodeGenerator` sẽ xuất ra một **file PNG barcode**. Ví dụ sử dụng symbology Databar OmniDirectional, nhưng bạn có thể thay `EncodeTypes.DatabarOmniDirectional` bằng bất kỳ loại nào được hỗ trợ.

```csharp
// Step 1: Create a DataBar Omnidirectional generator with the desired data
BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
    EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");
```

Chuỗi `"(01)12345678901231"` tuân theo định dạng GS1 Application Identifier cho GTIN 14 chữ số. Hãy điều chỉnh dữ liệu sao cho phù hợp với mã sản phẩm của bạn.

## Đặt X‑dimension (tùy chọn)

X‑dimension xác định độ rộng của một mô-đun barcode. Giá trị dựa trên pixel cho phép bạn kiểm soát kích thước ảnh một cách chính xác.

```csharp
// Optional: Set the pixel size of the X‑dimension (module width)
barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Giá trị `2` pixel thường phù hợp cho hầu hết các màn hình. Tăng lên nếu bạn cần barcode lớn hơn khi in.

## Điều chỉnh chiều cao barcode và lưu file PNG barcode

Thuộc tính **BarHeight** điều khiển kích thước chiều dọc của các thanh. Thay đổi giá trị này cho phép bạn **điều chỉnh chiều cao barcode** mà không ảnh hưởng tới dữ liệu đã mã hoá.

```csharp
// Step 2: Generate a 30‑pixel‑high barcode and save it as PNG
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 30;
barcodeGenerator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
```

File `DatabarBarHeight30Pixels.png` hiện là một **file PNG barcode** có chiều cao 30 pixel.  

Để **thay đổi chiều cao barcode** và tạo ảnh thứ hai, chỉ cần gán giá trị mới và gọi lại `Save`:

```csharp
// Step 3: Change the height to 60 pixels and save the new image
barcodeGenerator.Parameters.Barcode.BarHeight.Pixels = 60;
barcodeGenerator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
```

Bây giờ bạn có hai file PNG — một có chiều cao 30 px và một còn 60 px — thể hiện cách **điều chỉnh chiều cao barcode** một cách linh hoạt.

### Vì sao chiều cao thanh lại quan trọng

* **Độ đọc:** Máy quét yêu cầu chiều cao tối thiểu để phát hiện chính xác. Barcode quá ngắn có thể bị bỏ lỡ, đặc biệt trên camera độ phân giải thấp.  
* **Thẩm mỹ:** Điều chỉnh chiều cao barcode sao cho phù hợp với các yếu tố thiết kế xung quanh tạo ra giao diện sạch sẽ hơn.  
* **Ràng buộc in:** Một số máy in nhãn có khe cố định; việc điều chỉnh chiều cao barcode giúp nó vừa vặn.

**Thực hành tốt:** Giữ chiều cao là bội số của X‑dimension (ví dụ, 30 px khi X‑dimension là 2 px) để duy trì tỉ lệ và tránh biến dạng.

## Ví dụ hoàn chỉnh

Dưới đây là chương trình đầy đủ, tự chứa, bạn có thể dán vào một ứng dụng console và chạy ngay.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode;

class Program
{
    static void Main()
    {
        // 1️⃣ Create the generator with Databar OmniDirectional data
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.DatabarOmniDirectional, "(01)12345678901231");

        // 2️⃣ Set a reasonable X‑dimension (module width)
        generator.Parameters.Barcode.XDimension.Pixels = 2;

        // 3️⃣ First height: 30 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 30;
        generator.Save("DatabarBarHeight30Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 30‑pixel barcode as DatabarBarHeight30Pixels.png");

        // 4️⃣ Second height: 60 pixels → save as PNG
        generator.Parameters.Barcode.BarHeight.Pixels = 60;
        generator.Save("DatabarBarHeight60Pixels.png", BarCodeImageFormat.Png);
        Console.WriteLine("Saved 60‑pixel barcode as DatabarBarHeight60Pixels.png");
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo hai file trong thư mục làm việc của executable:

* `DatabarBarHeight30Pixels.png` – file PNG barcode cao 30 pixel  
* `DatabarBarHeight60Pixels.png` – file PNG barcode cao 60 pixel  

Mở bất kỳ file PNG nào bằng trình xem ảnh; bạn sẽ thấy một barcode Databar OmniDirectional rõ ràng, sẵn sàng để quét.

## Các trường hợp đặc biệt và khắc phục sự cố

| Tình huống | Kiểm tra | Giải pháp đề xuất |
|-----------|----------|-------------------|
| Barcode bị mờ | X‑dimension quá thấp so với chiều cao đã chọn | Tăng `XDimension.Pixels` (ví dụ, từ 2 lên 3) |
| Máy quét không nhận barcode thấp | Chiều cao dưới mức tối thiểu của máy quét | Đặt `BarHeight.Pixels` ít nhất 30 px (hoặc theo thông số máy quét) |
| File PNG rỗng hoặc hỏng | Đường dẫn xuất không hợp lệ hoặc không có quyền ghi | Dùng đường dẫn tuyệt đối hoặc đảm bảo ứng dụng có quyền ghi |
| Cần symbology khác | `EncodeTypes` hiện tại không phù hợp | Thay `EncodeTypes.DatabarOmniDirectional` bằng giá trị enum khác (ví dụ, `EncodeTypes.Code128`) |

## Câu hỏi thường gặp

**H: Tôi có thể tạo các định dạng ảnh khác (JPEG, BMP) không?**  
Đ: Có. Thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg`, `BarCodeImageFormat.Bmp`, v.v.

**H: Làm sao để nhúng PNG vào trang web?**  
Đ: Phục vụ PNG đã tạo qua một endpoint HTTP hoặc chuyển nó thành chuỗi Base64 và đặt vào thuộc tính `src` của thẻ `<img>`.

**H: Có cách nào đặt màu nền không?**  
Đ: Dùng `generator.Parameters.Image.BackgroundColor = Color.White;` (hoặc bất kỳ `System.Drawing.Color` nào).

## Kết luận

Bây giờ bạn đã biết cách **tạo file PNG barcode** trong C# và **điều chỉnh chiều cao barcode** một cách chính xác để đáp ứng yêu cầu quét hoặc thiết kế. Bằng cách thay đổi thuộc tính `BarHeight.Pixels` bạn có thể **thay đổi chiều cao barcode** ngay lập tức và tạo ra nhiều tài sản PNG từ cùng một mã nguồn.

Tiếp theo, khám phá các tùy chỉnh khác như màu foreground, lề, và thêm văn bản có thể đọc được bằng người. Bạn cũng có thể thử các symbology khác (`EncodeTypes.Code128`, `EncodeTypes.QR`) để mở rộng phạm vi dữ liệu có thể mã hoá.

Chúc lập trình vui vẻ, và hy vọng barcode của bạn luôn được quét thành công ngay lần đầu!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ code hoàn chỉnh với giải thích từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo và điều chỉnh chiều cao Barcode cho Databar một chiều bằng Aspose.BarCode for .NET](/barcode/english/net/one-dimensional-barcode-types/one-dimensional-databar-barcode-height-adjustment/)
- [Cách tạo Barcode - Các loại Barcode một chiều](/barcode/english/net/one-dimensional-barcode-types/)
- [Cách tạo barcode Aztec với tỷ lệ khung tùy chỉnh bằng Aspose.BarCode for .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}