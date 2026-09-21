---
date: 2026-06-09
description: Tìm hiểu cách tạo mã vạch DataMatrix ở chế độ ASCII bằng cách sử dụng
  Aspose.BarCode cho .NET. Hướng dẫn này cho thấy cách tạo mã vạch C# nhanh chóng.
keywords:
- create datamatrix barcode
- generate barcode c#
- how to encode barcode
- barcode generator example
linktitle: Chế độ mã hoá DataMatrix (ASCII)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  headline: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode in ASCII mode using Aspose.BarCode
    for .NET. This guide shows how to generate barcode C# quickly.
  name: Create DataMatrix barcode in ASCII mode with Aspose.BarCode for .NET
  steps:
  - name: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
    text: '**Development Environment** – Visual Studio, Rider, or any C#‑compatible
      IDE.'
  - name: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
    text: '**Aspose.BarCode for .NET** – Download the latest package from [here](https://releases.aspose.com/barcode/net/).'
  - name: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
    text: '**Basic C# knowledge** – Familiarity with .NET project structure will help
      you follow the steps quickly.'
  - name: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
    text: '**Other Aspose products** can be found [here](https://releases.aspose.com/).'
  type: HowTo
- questions:
  - answer: Yes, a valid Aspose license is required for production use; a free trial
      is available for evaluation.
    question: Can I use this in a commercial application?
  - answer: Absolutely – Aspose.BarCode fully supports .NET Core 3.1+, .NET 5, .NET
      6, and later versions.
    question: Does the library work with .NET Core?
  - answer: Up to 2,335 alphanumeric characters fit in a single DataMatrix symbol
      when using ASCII encoding.
    question: How many characters can I encode in ASCII mode?
  - answer: Yes, adjust `generator.Parameters.Image.ForeColor` and `BackColor` to
      any `System.Drawing.Color` value.
    question: Can I change the barcode’s foreground or background color?
  - answer: The official documentation contains dozens of samples covering custom
      sizes, colors, and error‑correction levels.
    question: Where can I find more advanced examples?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Tạo mã vạch DataMatrix ở chế độ ASCII với Aspose.BarCode cho .NET
url: /vi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch DataMatrix ở chế độ ASCII với Aspose.BarCode cho .NET

## Giới thiệu

Sẵn sàng **tạo mã vạch DataMatrix** dưới dạng hình ảnh sử dụng mã hóa ASCII hiệu quả? Trong hướng dẫn này, bạn sẽ học cách tạo mã vạch DataMatrix ở chế độ ASCII bằng Aspose.BarCode cho .NET. Chúng tôi sẽ hướng dẫn từng bước — từ việc thiết lập dự án đến lưu ảnh cuối cùng — để bạn có thể thêm chức năng tạo mã vạch vào các ứng dụng C# của mình trong vài phút.

## Câu trả lời nhanh
- **Thư viện nào là tốt nhất cho DataMatrix trong .NET?** Aspose.BarCode for .NET  
- **Cần bao nhiêu dòng mã?** Khoảng 5‑7 dòng cho một mã vạch ASCII cơ bản  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí đủ cho phát triển; cần giấy phép cho môi trường sản xuất  
- **Các nền tảng được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7  
- **Tôi có thể thay đổi kích thước hoặc màu sắc không?** Có, Aspose.BarCode cung cấp các thuộc tính cho kích thước và màu nền/màu chữ  

## DataMatrix là gì?
DataMatrix là một mã vạch hai chiều lưu trữ văn bản và dữ liệu nhị phân trong một mẫu hình vuông gọn gàng.  
Mã vạch DataMatrix mã hóa thông tin trong một lưới các mô-đun đen trắng, cho phép lên tới 2.335 ký tự chữ và số trong một ký hiệu duy nhất. Nó được sử dụng rộng rãi trong sản xuất, logistics và y tế vì có thể in ở kích thước rất nhỏ mà vẫn dễ quét.

## Cách tạo mã vạch DataMatrix ở chế độ ASCII?
Tải namespace Aspose.BarCode, khởi tạo một `BarcodeGenerator`, đặt `EncodeMode` thành **EncodeMode.ASCII**, gán chuỗi dữ liệu của bạn, và gọi `Save` để ghi tệp ảnh. Cách tiếp cận này tạo ra một mã vạch DataMatrix tuân thủ chuẩn với mã hóa chỉ ASCII trong chỉ vài dòng mã C#.

## Tại sao sử dụng mã hóa ASCII cho DataMatrix?
Chế độ ASCII là mặc định và là mã hóa hiệu quả nhất cho dữ liệu văn bản thuần, mang lại kích thước ký hiệu nhỏ nhất có thể cho các chuỗi chữ và số. Nó hỗ trợ tất cả 128 ký tự ASCII, xử lý dữ liệu nhanh hơn so với các chế độ mở rộng, và đảm bảo tính tương thích tối đa với các máy quét cũ chỉ nhận các ký hiệu ASCII tiêu chuẩn.

## Yêu cầu trước

1. **Môi trường phát triển** – Visual Studio, Rider, hoặc bất kỳ IDE nào hỗ trợ C#.  
2. **Aspose.BarCode cho .NET** – Tải gói mới nhất từ [đây](https://releases.aspose.com/barcode/net/).  
   - Tài liệu: [Tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/)  
   - Diễn đàn: [Diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13)  
3. **Kiến thức cơ bản về C#** – Quen thuộc với cấu trúc dự án .NET sẽ giúp bạn theo dõi các bước nhanh chóng.  
4. **Các sản phẩm Aspose khác** có thể được tìm thấy [đây](https://releases.aspose.com/).

## Nhập các namespace

Để bắt đầu, thêm các chỉ thị `using` cần thiết ở đầu tệp C# của bạn:

```csharp
using Aspose.BarCode.Generation;
using System.Drawing;
```

Các namespace này cung cấp cho bạn quyền truy cập vào lớp `BarcodeGenerator` và các kiểu liên quan đến hình ảnh cần thiết để lưu kết quả.

## Bước 1: Tạo thư mục

Chọn một thư mục để lưu các hình ảnh mã vạch được tạo. Thay thế `"Your Directory Path"` bằng đường dẫn tuyệt đối hoặc tương đối tồn tại trên máy của bạn.

```csharp
string outputDir = @"C:\Barcodes";
if (!System.IO.Directory.Exists(outputDir))
{
    System.IO.Directory.CreateDirectory(outputDir);
}
```

Mã này đảm bảo thư mục tồn tại trước khi cố gắng ghi bất kỳ tệp nào, ngăn ngừa lỗi thời gian chạy.

## Bước 2: Mã hóa dữ liệu ở chế độ ASCII

Lớp `BarcodeGenerator` tạo và cấu hình các hình ảnh mã vạch. Enum `DataMatrixEncodeMode` chọn thuật toán mã hóa cho các ký hiệu DataMatrix.

```csharp
// Initialise the generator with the data you want to encode
BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "1234567890");

// Set the encoding mode to ASCII for optimal size
generator.Parameters.Barcode.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;

// Optional: adjust image dimensions or colors here
generator.Parameters.Image.Width = 200;
generator.Parameters.Image.Height = 200;

// Save the barcode as a PNG file
string filePath = System.IO.Path.Combine(outputDir, "datamatrix_ascii.png");
generator.Save(filePath, BarCodeImageFormat.Png);
```

Sau khi chạy mã, bạn sẽ thấy `datamatrix_ascii.png` trong thư mục bạn đã chỉ định. Hình ảnh chứa một mã vạch DataMatrix mã hóa chuỗi `"1234567890"` bằng chế độ ASCII gọn gàng.

## Các vấn đề thường gặp và giải pháp

- **Lỗi truy cập tệp** – Đảm bảo ứng dụng có quyền ghi vào thư mục đích. Chạy Visual Studio với quyền Administrator có thể giải quyết vấn đề quyền trên Windows.  
- **Kích thước ký hiệu không đúng** – Nếu mã vạch quá lớn hoặc quá nhỏ, điều chỉnh `generator.Parameters.Image.Width` và `Height` hoặc để Aspose tự động tính kích thước tối ưu bằng cách bỏ qua các thuộc tính này.  
- **Ký tự không được hỗ trợ** – Chế độ ASCII chỉ chấp nhận các ký tự trong phạm vi 0‑127. Đối với dữ liệu Unicode, chuyển sang `DataMatrixEncodeMode.Base256` hoặc chế độ phù hợp khác.

## Câu hỏi thường gặp

**Q: Tôi có thể sử dụng điều này trong ứng dụng thương mại không?**  
A: Có, cần giấy phép Aspose hợp lệ cho việc sử dụng trong môi trường sản xuất; bản dùng thử miễn phí có sẵn để đánh giá.

**Q: Thư viện có hoạt động với .NET Core không?**  
A: Hoàn toàn – Aspose.BarCode hỗ trợ đầy đủ .NET Core 3.1+, .NET 5, .NET 6 và các phiên bản sau.

**Q: Tôi có thể mã hóa bao nhiêu ký tự trong chế độ ASCII?**  
A: Lên tới 2.335 ký tự chữ và số có thể chứa trong một ký hiệu DataMatrix khi sử dụng mã hóa ASCII.

**Q: Tôi có thể thay đổi màu nền hoặc màu chữ của mã vạch không?**  
A: Có, điều chỉnh `generator.Parameters.Image.ForeColor` và `BackColor` thành bất kỳ giá trị `System.Drawing.Color` nào.

**Q: Tôi có thể tìm các ví dụ nâng cao hơn ở đâu?**  
A: Tài liệu chính thức chứa hàng chục mẫu ví dụ về kích thước tùy chỉnh, màu sắc và mức độ sửa lỗi.

## Câu hỏi thường gặp

### Câu hỏi 1: Tôi có thể sử dụng Aspose.BarCode cho .NET với các ngôn ngữ lập trình khác ngoài C# không?
A1: Aspose.BarCode hỗ trợ nhiều ngôn ngữ lập trình, nhưng hướng dẫn này tập trung vào C#.

### Câu hỏi 2: Các chế độ mã hóa khác nhau có sẵn trong mã vạch DataMatrix là gì?
A2: Mã vạch DataMatrix hỗ trợ nhiều chế độ mã hóa, bao gồm ASCII, C40, Text và Base256. Mỗi chế độ phù hợp với các loại dữ liệu khác nhau.

### Câu hỏi 3: Tôi có thể tùy chỉnh giao diện của mã vạch được tạo, như kích thước và màu sắc không?
A3: Có, Aspose.BarCode cung cấp nhiều tham số để tùy chỉnh giao diện mã vạch, bao gồm kích thước, màu sắc và hơn thế nữa.

### Câu hỏi 4: Có phiên bản dùng thử miễn phí của Aspose.BarCode cho .NET không?
A4: Có, bạn có thể khám phá Aspose.BarCode cho .NET với bản dùng thử miễn phí từ [đây](https://releases.aspose.com/).

### Câu hỏi 5: Tôi có thể mua giấy phép cho Aspose.BarCode cho .NET ở đâu?
A5: Bạn có thể mua giấy phép từ trang web Aspose [đây](https://purchase.aspose.com/buy).

---

**Cập nhật lần cuối:** 2026-06-09  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Mã hóa DataMatrix bằng Bytes với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Đọc mã vạch DataMatrix C# – Tạo chế độ DataMatrix (Tự động)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}

{{< blocks/products/products-backtop-button >}}

```csharp
using Aspose.BarCode.Generation;
```

```csharp
string path = "Your Directory Path";
```

```csharp
System.Console.WriteLine("DataMatrixEncodeModeASCII:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "Aspose"))
{
    // Set the X-dimension (size) of the barcode in pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    
    // Set the encoding mode to ASCII
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ASCII;
    
    // Save the barcode as a PNG image
    gen.Save($"{path}DataMatrixEncodeModeASCII.png", BarCodeImageFormat.Png);
}
```

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}