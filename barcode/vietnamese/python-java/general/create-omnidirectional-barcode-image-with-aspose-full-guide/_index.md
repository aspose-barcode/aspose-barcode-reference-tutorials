---
category: general
date: 2026-07-27
description: Tạo hình ảnh mã vạch đa hướng bằng Aspose.BarCode. Tìm hiểu cách tạo
  mã vạch với Aspose, điều chỉnh tỷ lệ khung hình và lưu file PNG.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create omnidirectional barcode image
- generate barcode with aspose
language: vi
lastmod: 2026-07-27
og_description: Tạo hình ảnh mã vạch đa hướng bằng Aspose. Thực hiện theo hướng dẫn
  này để tạo mã vạch với Aspose, điều chỉnh tỷ lệ khung hình và xuất ra PNG.
og_image_alt: Screenshot of two omnidirectional barcode images with different aspect
  ratios
og_title: Tạo hình ảnh mã vạch đa hướng với Aspose – Từng bước
schemas:
- author: Aspose
  dateModified: '2026-07-27'
  description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  headline: Create Omnidirectional Barcode Image with Aspose – Full Guide
  type: TechArticle
- description: Create omnidirectional barcode image using Aspose.BarCode. Learn how
    to generate barcode with Aspose, adjust aspect ratio, and save PNG files.
  name: Create Omnidirectional Barcode Image with Aspose – Full Guide
  steps:
  - name: 1. Different Image Formats
    text: 'Aspose supports BMP, JPEG, TIFF, and SVG in addition to PNG. Swap the enum
      value:'
  - name: 2. Customizing Colors
    text: 'You might need a white barcode on a dark background. Set `ForeColor` and
      `BackColor`:'
  - name: 3. Handling Invalid Aspect Ratios
    text: 'Aspose validates the range (usually 5‑50). If you pass an out‑of‑range
      value, an `ArgumentException` is thrown. Wrap the save call in a try‑catch to
      give a friendly message:'
  - name: 4. Batch Generation
    text: When you have a list of GTINs, loop over them, update `CodeText`, and save
      each file with a unique name. The generator object can be reused, keeping memory
      usage low.
  type: HowTo
tags:
- barcode
- Aspose
- C#
- image-generation
title: Tạo hình ảnh mã vạch đa hướng với Aspose – Hướng dẫn đầy đủ
url: /vi/python-java/general/create-omnidirectional-barcode-image-with-aspose-full-guide/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo hình ảnh mã vạch Omnidirectional với Aspose – Hướng dẫn đầy đủ

Bạn đã bao giờ cần **tạo hình ảnh mã vạch omnidirectional** nhưng không chắc nên chọn thư viện nào? Bạn không phải là người duy nhất. Trong nhiều dự án logistics và bán lẻ, định dạng DataBar Stacked Omnidirectional là công thức bí mật cho việc mã hoá gọn gàng, mật độ cao.  

Tin tốt? Với **Aspose.BarCode** bạn có thể tạo mã vạch đó chỉ trong vài dòng code, điều chỉnh tỷ lệ khung hình, và lưu PNG trực tiếp lên đĩa. Dưới đây bạn sẽ thấy chính xác cách **generate barcode with Aspose**, lý do mỗi cài đặt quan trọng, và những lưu ý khi thay đổi tỷ lệ khung hình.

---

## Nội dung hướng dẫn này

Chúng ta sẽ đi qua toàn bộ vòng đời:

1. Thiết lập thư mục đầu ra.
2. Tạo một đối tượng generator DataBar Stacked Omnidirectional.
3. Cấu hình kích thước pixel và tỷ lệ khung hình.
4. Lưu mã vạch dưới dạng tệp PNG.
5. Mở rộng ví dụ cho các định dạng khác và các trường hợp đặc biệt.

Khi kết thúc, bạn sẽ có một ứng dụng console C# sẵn sàng chạy, tạo ra hai hình ảnh mã vạch khác nhau. Không cần công cụ bên ngoài, chỉ cần mã Aspose thuần túy.

**Yêu cầu trước**

- .NET 6.0 SDK hoặc phiên bản mới hơn (mã này cũng hoạt động trên .NET Framework 4.7.2).
- Gói NuGet Aspose.BarCode cho .NET (`Install-Package Aspose.BarCode`).
- Một thư mục trên đĩa để lưu các hình ảnh.

Nếu bạn đã có những thứ trên, hãy bắt đầu.

---

## Bước 1: Chuẩn bị thư mục đầu ra

Đầu tiên—cho chương trình biết nơi sẽ lưu các tệp PNG. Việc hard‑coding một đường dẫn hoạt động cho bản demo, nhưng trong môi trường thực tế bạn có thể đọc nó từ cấu hình.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Define the folder where the images will be saved
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);   // ensures the folder exists
```

*Tiêu đề này quan trọng:* `Directory.CreateDirectory` là idempotent; nó sẽ không ném lỗi nếu thư mục đã tồn tại, giúp bạn tránh việc dùng khối try‑catch.

---

## Bước 2: Tạo một DataBar Stacked Omnidirectional Generator

Bây giờ chúng ta khởi tạo generator với loại mã hoá cụ thể và dữ liệu mẫu. Chuỗi `"(01)12345678901231"` tuân theo cú pháp GS1 Application Identifier cho GTIN 14 chữ số.

```csharp
        // Step 2: Create a DataBar Stacked Omnidirectional barcode generator with sample data
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");
```

*Giải thích:* `EncodeTypes.DatabarStackedOmniDirectional` chỉ cho Aspose sử dụng biến thể omnidirectional, có thể đọc được từ bất kỳ hướng nào—lý tưởng cho các nhãn nhỏ có thể bị xoay.

---

## Bước 3: Đặt các tham số chung cho mã vạch

Trước khi render bất kỳ thứ gì, chúng ta định nghĩa kích thước phần tử nhỏ nhất (X‑Dimension). Giá trị **2 pixel** cho ra hình ảnh sắc nét mà không làm tăng kích thước tệp.

```csharp
        // Step 3: Set common barcode parameters (pixel size of the smallest element)
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

*Mẹo:* Nếu bạn cần độ phân giải cao hơn cho việc in, tăng lên 3 hoặc 4. Chỉ cần nhớ rằng X‑Dimension lớn hơn sẽ tăng cả chiều rộng và chiều cao một cách tỷ lệ.

---

## Bước 4: Tạo và lưu với Aspect Ratio 15

Họ họ DataBar cho phép bạn điều chỉnh **aspect ratio**, kiểm soát mối quan hệ chiều cao‑so‑với‑chiều rộng. Aspect ratio **15** là giá trị mặc định phổ biến cho mã vạch omnidirectional.

```csharp
        // Step 4: Generate a barcode with an aspect ratio of 15 and save it as PNG
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
```

*Bạn sẽ thấy:* Một mã vạch tương đối cao nhưng vẫn vừa vặn trên nhãn 2 × 1 cm. Định dạng PNG giữ nguyên chất lượng lossless, lý tưởng cho việc xử lý hoặc in tiếp.

---

## Bước 5: Thay đổi Aspect Ratio thành 30 và lưu lại

Muốn một mã vạch dẹt hơn? Chỉ cần điều chỉnh thuộc tính `AspectRatio` và gọi lại `Save`. Không cần tạo lại generator.

```csharp
        // Step 5: Change the aspect ratio to 30 and save the new image
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
    }
}
```

*Tại sao dùng lại cùng một generator?* Các đối tượng Aspose nhẹ; việc thay đổi thuộc tính và lưu lại nhanh hơn tạo một instance mới, và nó đảm bảo các cài đặt mã hoá (ví dụ X‑Dimension) vẫn nhất quán.

---

## Ví dụ hoàn chỉnh hoạt động

Kết hợp tất cả lại, đây là chương trình đầy đủ, tự chứa mà bạn có thể sao chép‑dán vào một dự án console mới.

```csharp
using System;
using System.IO;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Define output folder
        string outputFolder = Path.Combine(Environment.CurrentDirectory, "Barcodes");
        Directory.CreateDirectory(outputFolder);

        // Initialize generator with omnidirectional DataBar
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.DatabarStackedOmniDirectional,
            "(01)12345678901231");

        // Common settings
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;

        // First image – aspect ratio 15
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 15;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio15.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio15.png");

        // Second image – aspect ratio 30
        barcodeGenerator.Parameters.Barcode.DataBar.AspectRatio = 30;
        barcodeGenerator.Save(Path.Combine(outputFolder, "DatabarAspectRatio30.png"),
                              BarCodeImageFormat.Png);
        Console.WriteLine("Saved: DatabarAspectRatio30.png");
    }
}
```

**Kết quả mong đợi**

Chạy chương trình sẽ tạo một thư mục con `Barcodes` chứa:

- `DatabarAspectRatio15.png` – cao hơn, kiểu cổ điển.
- `DatabarAspectRatio30.png` – dẹt hơn, phù hợp cho nhãn rộng.

Cả hai hình ảnh đều hiển thị cùng dữ liệu GTIN; chỉ tỷ lệ hình ảnh khác nhau.

---

## Mở rộng ví dụ (Trường hợp đặc biệt & Biến thể)

### 1. Định dạng hình ảnh khác

Aspose hỗ trợ BMP, JPEG, TIFF và SVG ngoài PNG. Thay đổi giá trị enum:

```csharp
barcodeGenerator.Save(Path.Combine(outputFolder, "Databar.svg"),
                      BarCodeImageFormat.Svg);
```

SVG là dạng vector, cho phép bạn phóng to mà không mất độ sắc nét—hữu ích cho các ứng dụng web đáp ứng.

### 2. Tùy chỉnh màu sắc

Bạn có thể cần mã vạch màu trắng trên nền tối. Đặt `ForeColor` và `BackColor`:

```csharp
barcodeGenerator.Parameters.Barcode.ForeColor = System.Drawing.Color.White;
barcodeGenerator.Parameters.Barcode.BackColor = System.Drawing.Color.Black;
```

### 3. Xử lý Aspect Ratio không hợp lệ

Aspose kiểm tra phạm vi (thường 5‑50). Nếu bạn truyền giá trị ngoài phạm vi, sẽ ném `ArgumentException`. Bao quanh lệnh save bằng try‑catch để đưa ra thông báo thân thiện:

```csharp
try
{
    barcodeGenerator.Save(...);
}
catch (ArgumentException ex)
{
    Console.WriteLine($"Invalid aspect ratio: {ex.Message}");
}
```

### 4. Tạo hàng loạt

Khi có danh sách GTIN, lặp qua chúng, cập nhật `CodeText`, và lưu mỗi tệp với tên duy nhất. Đối tượng generator có thể tái sử dụng, giảm mức tiêu thụ bộ nhớ.

---

## Những lỗi thường gặp & Mẹo chuyên nghiệp

- **Không bao giờ quên đặt `XDimension`** trước khi lưu; mặc định (0.33 mm) có thể tạo ra hình ảnh mờ trên màn hình độ phân giải thấp.
- **Aspect ratio là chiều cao‑so‑với‑chiều rộng**, không phải ngược lại. Số lớn hơn làm mã vạch *ngắn* hơn theo chiều dọc.
- **Đường dẫn tệp:** Sử dụng `Path.Combine` để tránh các vấn đề về dấu phân tách đặc thù của nền tảng—đặc biệt nếu mã chạy trên container Linux.
- **Giấy phép:** Aspose.BarCode là phần mềm thương mại. Trong chế độ dùng thử sẽ có watermark trên hình ảnh. Đăng ký giấy phép sớm để tránh bất ngờ trong môi trường production.

---

## Kết luận

Bây giờ bạn đã biết cách **tạo hình ảnh mã vạch omnidirectional** bằng Aspose, điều chỉnh aspect ratio, và xuất tệp PNG—tất cả trong chưa đầy 30 dòng C#. Hướng dẫn này đã trình bày quy trình từng bước, giải thích lý do mỗi cài đặt quan trọng, và đề cập đến các mở rộng như định dạng khác, màu sắc, và tạo hàng loạt.

Sẵn sàng cho thử thách tiếp theo? Hãy thử tạo QR code, nhúng mã vạch vào PDF, hoặc tích hợp đầu ra vào API ASP.NET Core. Các nguyên tắc **generate barcode with Aspose** giống nhau áp dụng cho mọi loại mã vạch, vì vậy bạn có thể tái sử dụng những gì đã học hôm nay.

Có câu hỏi hoặc muốn chia sẻ cách tùy chỉnh của bạn? Để lại bình luận bên dưới—chúc lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các hướng dẫn sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật được trình bày trong hướng dẫn này. Mỗi tài nguyên bao gồm các ví dụ mã đầy đủ, hoạt động với giải thích từng bước, giúp bạn nắm vững các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [Cách tạo mã vạch Aztec với tỷ lệ khung hình tùy chỉnh bằng Aspose.BarCode cho .NET](/barcode/english/net/aztec-barcode-encoding/aztec-aspect-ratio-customization/)
- [Cách tạo Barcode Aspose Java - Điều chỉnh chất lượng hình ảnh](/barcode/english/java/image-manipulation/adjusting-image-quality-barcode/)
- [Cách tạo hình ảnh mã vạch trong Java với Aspose.BarCode](/barcode/english/java/barcode-rendering-techniques/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}