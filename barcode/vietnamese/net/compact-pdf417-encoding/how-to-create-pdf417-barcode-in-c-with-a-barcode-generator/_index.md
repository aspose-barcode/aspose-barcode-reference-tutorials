---
category: general
date: 2026-11-17
description: Học cách tạo mã vạch PDF417 trong C# – hướng dẫn đầy đủ về cách tạo mã
  vạch từ chuỗi bằng trình tạo mã vạch C#.
draft: false
images:
- PLACEHOLDER_URL/og-image.png
keywords:
- create PDF417 barcode
- how to generate barcode
- c# barcode generator
- generate barcode from string
- create gs1 barcode
language: vi
lastmod: 2026-11-17
og_description: Tạo mã vạch PDF417 trong C# nhanh chóng. Hướng dẫn này cho thấy cách
  tạo mã vạch từ chuỗi bằng bộ tạo mã vạch C# và bao gồm toàn bộ mã nguồn.
og_image_alt: Screenshot of a generated PDF417 barcode created with a C# barcode generator
og_title: Tạo mã vạch PDF417 trong C# – hướng dẫn từng bước
schemas:
- author: Aspose
  dateModified: '2026-11-17'
  description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  headline: How to create PDF417 barcode in C# with a barcode generator
  type: TechArticle
- description: Learn how to create PDF417 barcode in C# – a complete guide on how
    to generate barcode from string using a C# barcode generator.
  name: How to create PDF417 barcode in C# with a barcode generator
  steps:
  - name: Expected output
    text: '![Generated PDF417 barcode showing the GTIN (01)12345678901234](/images/pdf417-sample.png){:
      .center-image alt="Generated PDF417 barcode created with a C# barcode generator"}'
  - name: Changing the image format
    text: If you prefer JPEG or BMP, just replace `BarCodeImageFormat.Png` with `BarCodeImageFormat.Jpeg`
      or `BarCodeImageFormat.Bmp`. The rest of the code stays identical.
  - name: Adjusting error correction level
    text: PDF417 supports error correction levels 0‑8. Higher levels increase redundancy
      but also enlarge the barcode.
  - name: Generating other GS1 barcodes
    text: 'The same `BarcodeGenerator` can produce **create GS1 barcode** for other
      symbologies, such as `EncodeTypes.Gs1DataMatrix` or `EncodeTypes.Gs1Qr`. Just
      swap the enum value:'
  - name: Handling empty or null data
    text: 'When you **generate barcode from string**, always validate the input:'
  type: HowTo
- questions:
  - answer: Yes. The Aspose.BarCode library targets .NET Standard 2.0, which is compatible
      with .NET Framework 4.6 and later.
    question: Can I use this code on .NET Framework 4.6?
  - answer: 'Set the `Resolution` property before saving: ```csharp generator.Parameters.ImageResolution.DpiX
      = 300; generator.Parameters.ImageResolution.DpiY = 300; ```'
    question: What if I need a higher‑resolution image?
  - answer: 'It will be a standard PDF417 barcode, but it won’t be recognized as a
      GS1‑compliant symbol. Include the `(01)` prefix when you need **create GS1 barcode**
      compliance. ## Conclusion You now know how to **create PDF417 barcode** in C#
      using a robust **c# barcode generator**. The tutorial covered: * In'
    question: Is the barcode still valid without the GS1 Application Identifier?
  type: FAQPage
tags:
- barcode
- C#
- PDF417
- GS1
- code generation
title: Cách tạo mã vạch PDF417 trong C# bằng trình tạo mã vạch
url: /vi/net/compact-pdf417-encoding/how-to-create-pdf417-barcode-in-c-with-a-barcode-generator/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch PDF417 trong C# bằng trình tạo mã vạch

Nếu bạn cần **tạo mã vạch PDF417** trong một ứng dụng .NET, hướng dẫn này sẽ chỉ cho bạn cách thực hiện. Bạn sẽ học **cách tạo mã vạch** từ một chuỗi đơn giản, cấu hình kích thước ký hiệu, và lưu kết quả dưới dạng tệp PNG—tất cả đều sử dụng một trình tạo mã vạch C# đáng tin cậy.

Việc tạo mã vạch bằng chương trình loại bỏ các bước thủ công và đảm bảo chất lượng nhất quán. Trong tutorial này, chúng ta sẽ bao quát mọi thứ từ thiết lập dự án đến hình ảnh cuối cùng, để bạn có thể tích hợp việc tạo mã vạch vào bất kỳ giải pháp C# nào ngay hôm nay.

## Yêu cầu trước

Trước khi bắt đầu, hãy chắc chắn rằng bạn có:

* .NET 6.0 SDK hoặc mới hơn (mã hoạt động với .NET Core và .NET Framework)
* Visual Studio 2022 (hoặc bất kỳ IDE nào hỗ trợ C#)
* Giấy phép hoặc bản dùng thử miễn phí của **Aspose.BarCode for .NET** – thư viện được dùng trong các ví dụ
* Kiến thức cơ bản về cú pháp C#

Không cần thêm bất kỳ gói nào; gói NuGet `Aspose.BarCode` đã chứa tất cả các lớp bạn cần.

## Bước 1 – Thiết lập trình tạo mã vạch C#

Điều đầu tiên bạn làm khi **tạo mã vạch PDF417** là khởi tạo một đối tượng `BarcodeGenerator`. Đối tượng này đại diện cho **c# barcode generator** sẽ xử lý việc mã hoá, render và lưu.

```csharp
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Step 1: Create a barcode generator for PDF417 with the data to encode
        // The data string follows the GS1 Application Identifier (01) for a GTIN
        BarcodeGenerator barcodeGenerator = new BarcodeGenerator(
            EncodeTypes.Pdf417, "(01)12345678901234");
```

*Lý do quan trọng*: Enum `EncodeTypes.Pdf417` thông báo cho thư viện sử dụng ký hiệu PDF417, tiêu chuẩn được dùng cho thẻ nhận dạng và nhãn vận chuyển. Chuỗi `"(01)12345678901234"` là một ví dụ **generate barcode from string** đồng thời minh họa cách **create GS1 barcode** dữ liệu.

## Bước 2 – Cấu hình X‑dimension (độ rộng mô-đun)

X‑dimension kiểm soát độ rộng của thanh nhỏ nhất (mô-đun). Giá trị thường dùng cho việc render trên màn hình là 2 pixel.

```csharp
        // Step 2: Set the X‑dimension (module width) to 2 pixels
        barcodeGenerator.Parameters.Barcode.XDimension.Pixels = 2;
```

Việc đặt X‑dimension một cách rõ ràng ngăn trình tạo sử dụng giá trị mặc định, có thể tạo ra mã vạch quá nhỏ đối với một số máy quét.

## Bước 3 – Xác định số cột

PDF417 cho phép bạn điều chỉnh số cột, ảnh hưởng đến hình dạng và khả năng chứa dữ liệu của mã vạch. Đối với nhãn gọn, bốn cột là lựa chọn tốt.

```csharp
        // Step 3: Define the number of columns (e.g., 4) for a compact barcode
        barcodeGenerator.Parameters.Barcode.Pdf417.Columns = 4;
```

Nếu bạn cần mã vạch cao hơn, tăng số cột; thư viện sẽ tự động tính toán số hàng cần thiết.

## Bước 4 – Lưu mã vạch dưới dạng ảnh

Cuối cùng, xuất mã vạch ra tệp PNG. PNG giữ được các cạnh sắc nét và hỗ trợ trong suốt.

```csharp
        // Step 4: Save the generated barcode as a PNG image
        barcodeGenerator.Save("output/Gs1Pdf417.png", BarCodeImageFormat.Png);
    }
}
```

Chạy chương trình sẽ tạo ra `output/Gs1Pdf417.png`. Mở tệp trong bất kỳ trình xem ảnh nào—bạn sẽ thấy một **PDF417 barcode** sạch sẽ, mã hoá dữ liệu GS1 mà bạn đã cung cấp.

### Kết quả mong đợi

![Mã vạch PDF417 được tạo hiển thị GTIN (01)12345678901234](/images/pdf417-sample.png){: .center-image alt="Mã vạch PDF417 được tạo bằng trình tạo mã vạch C#"}

*Hình ảnh trên minh họa kết quả của đoạn mã hoàn chỉnh. Mã vạch có thể được quét bằng bất kỳ trình đọc PDF417 nào.*

## Các tùy chọn bổ sung và biến thể thường gặp

### Thay đổi định dạng ảnh

Nếu bạn muốn JPEG hoặc BMP, chỉ cần thay `BarCodeImageFormat.Png` bằng `BarCodeImageFormat.Jpeg` hoặc `BarCodeImageFormat.Bmp`. Phần còn lại của mã vẫn giữ nguyên.

### Điều chỉnh mức độ sửa lỗi

PDF417 hỗ trợ các mức sửa lỗi từ 0‑8. Mức cao hơn tăng độ dư thừa nhưng cũng làm mã vạch lớn hơn.

```csharp
barcodeGenerator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // medium redundancy
```

### Tạo các mã vạch GS1 khác

Cùng một `BarcodeGenerator` có thể tạo **create GS1 barcode** cho các ký hiệu khác, chẳng hạn `EncodeTypes.Gs1DataMatrix` hoặc `EncodeTypes.Gs1Qr`. Chỉ cần đổi giá trị enum:

```csharp
BarcodeGenerator gs1Generator = new BarcodeGenerator(
    EncodeTypes.Gs1DataMatrix, "(01)12345678901234");
```

### Xử lý dữ liệu rỗng hoặc null

Khi bạn **generate barcode from string**, luôn kiểm tra đầu vào:

```csharp
string data = GetUserInput();
if (string.IsNullOrWhiteSpace(data))
{
    throw new ArgumentException("Data to encode cannot be null or empty.");
}
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.Pdf417, data);
```

Điều này ngăn ngừa ngoại lệ thời chạy và đảm bảo mã vạch tuân thủ các quy tắc định dạng GS1.

## Ví dụ đầy đủ, có thể chạy ngay

Dưới đây là chương trình hoàn chỉnh bạn có thể sao chép‑dán vào một dự án console mới. Nó bao gồm tất cả các chỉ thị `using` cần thiết, tạo thư mục, và xử lý lỗi.

```csharp
using System;
using System.IO;
using Aspose.BarCode;
using Aspose.BarCode.Generation;

class Program
{
    static void Main()
    {
        // Input data – GS1 GTIN with Application Identifier (01)
        const string gs1Data = "(01)12345678901234";

        // Validate input
        if (string.IsNullOrWhiteSpace(gs1Data))
        {
            Console.WriteLine("Error: Barcode data cannot be empty.");
            return;
        }

        // Ensure output directory exists
        string outputDir = Path.Combine(Directory.GetCurrentDirectory(), "output");
        Directory.CreateDirectory(outputDir);

        // Create the generator for PDF417 (GS1 optional)
        BarcodeGenerator generator = new BarcodeGenerator(
            EncodeTypes.Pdf417, gs1Data);

        // Configure appearance
        generator.Parameters.Barcode.XDimension.Pixels = 2;   // module width
        generator.Parameters.Barcode.Pdf417.Columns = 4;    // compact layout
        generator.Parameters.Barcode.Pdf417.ErrorCorrectionLevel = 5; // optional

        // Save as PNG
        string outputPath = Path.Combine(outputDir, "Gs1Pdf417.png");
        generator.Save(outputPath, BarCodeImageFormat.Png);

        Console.WriteLine($"Barcode saved to: {outputPath}");
    }
}
```

**Chạy chương trình** (`dotnet run`) và bạn sẽ tìm thấy `Gs1Pdf417.png` trong thư mục *output*. Quét nó bằng bất kỳ trình đọc PDF417 nào để xác nhận GTIN `(01)12345678901234` đã được mã hoá đúng.

## Câu hỏi thường gặp

**H: Tôi có thể dùng đoạn mã này trên .NET Framework 4.6 không?**  
Đ: Có. Thư viện Aspose.BarCode nhắm tới .NET Standard 2.0, tương thích với .NET Framework 4.6 và các phiên bản sau.

**H: Nếu tôi cần ảnh có độ phân giải cao hơn thì sao?**  
Đ: Đặt thuộc tính `Resolution` trước khi lưu:

```csharp
generator.Parameters.ImageResolution.DpiX = 300;
generator.Parameters.ImageResolution.DpiY = 300;
```

**H: Mã vạch có còn hợp lệ nếu không có GS1 Application Identifier không?**  
Đ: Nó sẽ là một mã vạch PDF417 tiêu chuẩn, nhưng sẽ không được công nhận là ký hiệu tuân thủ GS1. Hãy bao gồm tiền tố `(01)` khi bạn cần **create GS1 barcode** tuân thủ.

## Kết luận

Bạn đã biết cách **tạo mã vạch PDF417** trong C# bằng một **c# barcode generator** mạnh mẽ. Tutorial đã đề cập:

* Khởi tạo `BarcodeGenerator` với dữ liệu GS1  
* Cấu hình X‑dimension và số cột  
* Lưu kết quả dưới dạng ảnh PNG  
* Mở rộng giải pháp với sửa lỗi, định dạng khác, và kiểm tra đầu vào  

Với nền tảng này, bạn có thể tạo bất kỳ mã vạch PDF417 hoặc GS1 nào trực tiếp từ chuỗi, nhúng vào báo cáo, hoặc gửi tới máy in. Khám phá API Aspose.BarCode để thêm màu sắc, lề, hoặc kết hợp nhiều mã vạch trong một ảnh duy nhất.

**Bước tiếp theo**: thử **create GS1 barcode** cho DataMatrix, thử nghiệm tính toán cột động, hoặc tích hợp trình tạo vào dịch vụ web ASP.NET Core trả về ảnh mã vạch theo yêu cầu.

Chúc bạn lập trình vui vẻ!

## Bạn nên học gì tiếp theo?

Các tutorial sau đây đề cập đến các chủ đề liên quan chặt chẽ, xây dựng trên các kỹ thuật đã trình bày trong hướng dẫn này. Mỗi tài nguyên đều bao gồm mã mẫu đầy đủ và giải thích chi tiết từng bước để giúp bạn làm chủ các tính năng API bổ sung và khám phá các cách triển khai thay thế trong dự án của mình.

- [How to generate PDF417 barcode in C# – complete guide](/barcode/english/net/compact-pdf417-encoding/how-to-generate-pdf417-barcode-in-c-complete-guide/)
- [How to create micro pdf417 barcode and generate PNG in C#](/barcode/english/net/compact-pdf417-encoding/how-to-create-micro-pdf417-barcode-and-generate-png-in-c/)
- [How to create macro PDF417 barcode in C# using Aspose.BarCode](/barcode/english/net/compact-pdf417-encoding/how-to-create-macro-pdf417-barcode-in-c-using-aspose-barcode/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}
{{< blocks/products/products-backtop-button >}}