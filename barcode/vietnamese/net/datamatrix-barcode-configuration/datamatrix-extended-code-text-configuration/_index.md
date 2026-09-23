---
date: 2026-09-23
description: Tìm hiểu cách sử dụng Aspose.BarCode để tạo mã vạch DataMatrix với văn
  bản mã mở rộng trong .NET, lý tưởng cho các ứng dụng quản lý tồn kho và logistics.
keywords:
- how to use aspose
- create barcode for inventory
- barcode generation .net core
- generate barcode image c#
lastmod: 2026-09-23
linktitle: Cấu hình Văn bản Mã mở rộng cho DataMatrix
og_description: Cách sử dụng Aspose.BarCode để tạo mã vạch DataMatrix với văn bản
  mã mở rộng trong .NET. Thực hiện theo hướng dẫn nhanh từng bước cho các giải pháp
  quản lý tồn kho và logistics.
og_image_alt: Screenshot of a DataMatrix barcode generated with Aspose.BarCode in
  a .NET console app
og_title: Cách sử dụng Aspose.BarCode để tạo văn bản mã DataMatrix trong .NET
schemas:
- author: Aspose
  dateModified: '2026-09-23'
  description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  headline: How to use Aspose.BarCode to create DataMatrix code text in .NET
  type: TechArticle
- description: Learn how to use Aspose.BarCode to generate a DataMatrix barcode with
    extended code text in .NET, ideal for inventory and logistics applications.
  name: How to use Aspose.BarCode to create DataMatrix code text in .NET
  steps:
  - name: Define the output folder
    text: Specify where the generated barcode image will be saved. Replace the placeholder
      with a valid path on your machine.
  - name: Build the extended code text
    text: '`DataMatrixExtCodetextBuilder` is a helper class that assembles the extended
      code text according to the DataMatrix specification. It automatically inserts
      the required ECI (Extended Channel Interpretation) markers. This mix demonstrates
      how you can combine Unicode characters, C40 encoding, plain tex'
  - name: Generate the final codetext string
    text: After configuring all parts, retrieve the combined string that Aspose.BarCode
      will embed into the barcode.
  - name: Create the DataMatrix barcode
    text: '`BarcodeGenerator` is the core class that produces barcode images. Instantiate
      it with `EncodeTypes.DataMatrix` and the extended codetext, then set visual
      parameters such as X‑dimension, image format, and optional human‑readable text.
      The above code **creates barcode aspose .net** with the desired e'
  - name: Verify the barcode by reading it back
    text: '`BarCodeReader` validates that the generated symbol can be decoded correctly,
      which is essential for automated test pipelines and quality assurance. If everything
      is set up properly, the console will output the exact extended code text you
      built earlier.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET
    question: What library is needed?
  - answer: DataMatrix with extended code text
    question: Which barcode type?
  - answer: Yes, the API is cross‑platform
    question: Can I use .NET Core / .NET 6?
  - answer: A free trial works for development; a license is required for production
    question: Do I need a license for testing?
  - answer: About 10‑15 minutes for a basic example
    question: How long does implementation take?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- Aspose.BarCode
- DataMatrix
- .NET barcode
- C# barcode generation
- inventory labeling
title: Cách sử dụng Aspose.BarCode để tạo văn bản mã DataMatrix trong .NET
url: /vi/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/
weight: 17
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách sử dụng Aspose.BarCode để tạo văn bản mã DataMatrix trong .NET

Việc tích hợp mã vạch vào các ứng dụng .NET hiện đại không còn là một nhiệm vụ hẹp nữa — nó là yêu cầu cốt lõi cho quản lý tồn kho, logistics và các giải pháp quét di động. Trong hướng dẫn này, bạn sẽ **học cách sử dụng Aspose.BarCode** để cấu hình mã vạch DataMatrix với văn bản mã mở rộng, tạo hình ảnh và xác minh nó bằng chương trình. Bạn sẽ thấy tại sao cách tiếp cận này lý tưởng cho việc tạo mã vạch cho tồn kho và cách nó phù hợp với .NET Core hoặc .NET 6.

## Câu trả lời nhanh
- **Thư viện cần thiết là gì?** Aspose.BarCode for .NET  
- **Loại mã vạch nào?** DataMatrix với văn bản mã mở rộng  
- **Tôi có thể sử dụng .NET Core / .NET 6 không?** Có, API hỗ trợ đa nền tảng  
- **Có cần giấy phép để thử nghiệm không?** Bản dùng thử miễn phí hoạt động cho phát triển; cần giấy phép cho môi trường sản xuất  
- **Thời gian triển khai mất bao lâu?** Khoảng 10‑15 phút cho một ví dụ cơ bản  

## Aspose.BarCode cho .NET là gì?
Aspose.BarCode cho .NET là một thư viện thương mại cho phép các nhà phát triển tạo và nhận dạng hơn 30 loại mã vạch, bao gồm DataMatrix, QR và Code 128, và tạo hình ảnh lên tới 10.000 × 10.000 pixel mà không cần phụ thuộc bên ngoài. Nó hỗ trợ .NET Framework 4.5+, .NET Core 3.1+, và .NET 5/6/7.

## Tại sao nên sử dụng văn bản mã mở rộng của DataMatrix?
Văn bản mã mở rộng của DataMatrix cho phép bạn nhúng nhiều chế độ mã hoá — UTF‑8, C40, Text, X12 — trong một ký hiệu duy nhất, cho phép lên tới **3116 codewords** (khoảng 155 KB dữ liệu) trong một ô vuông nhỏ gọn. Khả năng này hoàn hảo cho việc dán nhãn sản phẩm đa ngôn ngữ, theo dõi thiết bị y tế và bao bì thông minh, nơi bạn cần kết hợp ID chữ và số với dữ liệu nhị phân.

## Yêu cầu trước

Trước khi bắt đầu, hãy xác nhận rằng bạn có những thứ sau:

1. **Aspose.BarCode cho .NET** – tải xuống từ trang chính thức **[Aspose.BarCode .NET download page](https://releases.aspose.com/barcode/net/)**.  
2. **Môi trường phát triển .NET** – Visual Studio, Rider, hoặc VS Code với .NET SDK.  
3. **Kiến thức cơ bản về C#** – bạn nên quen thuộc với các lớp, không gian tên và chỉ thị `using`.

## Nhập không gian tên

Thêm các không gian tên cần thiết ở đầu tệp C# của bạn để trình biên dịch biết nơi tìm các lớp mã vạch.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Các không gian tên này cung cấp cho bạn quyền truy cập vào cả tính năng tạo và nhận dạng mã vạch.

## Cách cấu hình văn bản mã mở rộng của DataMatrix?

Tải builder, thêm các đoạn mong muốn, và để Aspose.BarCode tự động xử lý các dấu hiệu ECI. Đoạn văn trả lời trực tiếp này chỉ cho bạn các bước chính xác: tạo một `DataMatrixExtCodetextBuilder`, thêm các đoạn Unicode, C40, plain‑text và Text mode, sau đó lấy chuỗi đã kết hợp cho trình tạo.

### Bước 1: Xác định thư mục đầu ra

Xác định nơi hình ảnh mã vạch được tạo sẽ được lưu. Thay thế placeholder bằng đường dẫn hợp lệ trên máy của bạn.

```csharp
string path = "Your Directory Path";
```

### Bước 2: Xây dựng văn bản mã mở rộng

`DataMatrixExtCodetextBuilder` là một lớp trợ giúp lắp ráp văn bản mã mở rộng theo chuẩn DataMatrix. Nó tự động chèn các dấu hiệu ECI (Extended Channel Interpretation) cần thiết.

```csharp
DataMatrixExtCodetextBuilder codetextBuilder = new DataMatrixExtCodetextBuilder();
codetextBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
codetextBuilder.AddECICodetextWithEncodeMode(ECIEncodings.UTF8, DataMatrixEncodeMode.C40, "ABCDE");
codetextBuilder.AddPlainCodetext("test");
codetextBuilder.AddCodetextWithEncodeMode(DataMatrixEncodeMode.Text, "abcde");
```

Sự kết hợp này minh họa cách bạn có thể kết hợp ký tự Unicode, mã hoá C40, plain text và Text mode trong một ký hiệu DataMatrix duy nhất.

### Bước 3: Tạo chuỗi codetext cuối cùng

Sau khi cấu hình tất cả các phần, lấy chuỗi đã kết hợp mà Aspose.BarCode sẽ nhúng vào mã vạch.

```csharp
string codetext = codetextBuilder.GetExtendedCodetext();
```

### Bước 4: Tạo mã vạch DataMatrix

`BarcodeGenerator` là lớp cốt lõi tạo ra hình ảnh mã vạch. Khởi tạo nó với `EncodeTypes.DataMatrix` và codetext mở rộng, sau đó đặt các tham số hiển thị như X‑dimension, định dạng ảnh và văn bản có thể đọc được tùy chọn.

```csharp
using (var generator = new BarcodeGenerator(EncodeTypes.DataMatrix, codetext))
{
    generator.Parameters.Barcode.XDimension.Pixels = 4;
    generator.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Extended Codetext";
    generator.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.ExtendedCodetext;

    generator.Save($"{path}DataMatrixExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Mã trên **tạo mã vạch aspose .net** với văn bản mã mở rộng mong muốn và lưu nó dưới dạng tệp PNG.

### Bước 5: Xác minh mã vạch bằng cách đọc lại

`BarCodeReader` xác thực rằng ký hiệu đã tạo có thể giải mã đúng, điều này quan trọng cho các pipeline kiểm thử tự động và đảm bảo chất lượng.

```csharp
using (var reader = new BarCodeReader(generator.GenerateBarCodeImage(), DecodeType.DataMatrix))
{
    foreach (BarCodeResult result in reader.ReadBarCodes())
        Console.WriteLine("DataMatrixExtendedCodetext:" + result.CodeText);
}
```

Nếu mọi thứ được thiết lập đúng, console sẽ xuất ra chính xác văn bản mã mở rộng mà bạn đã xây dựng trước đó.

## Những lỗi thường gặp và cách khắc phục

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Mã vạch không đọc được | X‑dimension quá thấp | Tăng `XDimension.Pixels` (ví dụ, 4 → 6) |
| Ký tự bị lỗi | Mã hoá ECI sai | Đảm bảo `ECIEncodings.UTF8` khớp với bộ ký tự |
| Tệp không được lưu | Đường dẫn không hợp lệ | Sử dụng đường dẫn tuyệt đối hoặc đảm bảo thư mục tồn tại |
| Lỗi giấy phép | Bản dùng thử đã hết hạn | Áp dụng giấy phép tạm thời hoặc đầy đủ (xem FAQ) |

## Câu hỏi thường gặp

### Câu hỏi 1: Aspose.BarCode cho .NET là gì?
A1: Aspose.BarCode cho .NET là một thư viện mạnh mẽ cho phép các nhà phát triển tạo và nhận dạng đa dạng các loại mã vạch, bao gồm DataMatrix, QR, Code128 và nhiều hơn nữa.

### Câu hỏi 2: Tôi có thể tìm tài liệu cho Aspose.BarCode cho .NET ở đâu?
A2: Bạn có thể truy cập tài liệu API đầy đủ **[Aspose.BarCode .NET API reference](https://reference.aspose.com/barcode/net/)**.

### Câu hỏi 3: Có bản dùng thử miễn phí cho Aspose.BarCode cho .NET không?
A3: Có, phiên bản dùng thử miễn phí có thể tải xuống từ **[Aspose.BarCode free trial download](https://releases.aspose.com/)**.

### Câu hỏi 4: Làm sao để lấy giấy phép tạm thời để thử nghiệm?
A4: Giấy phép tạm thời được cung cấp cho mục đích đánh giá và có thể yêu cầu tại **[Aspose temporary license request page](https://purchase.aspose.com/temporary-license/)**.

### Câu hỏi 5: Tôi có thể nhận hỗ trợ hoặc đặt câu hỏi về Aspose.BarCode cho .NET ở đâu?
A5: Diễn đàn chính thức của Aspose.BarCode là nơi tốt nhất để tìm trợ giúp: **[Aspose.BarCode forum](https://forum.aspose.com/c/barcode/13)**.

---

**Cập nhật lần cuối:** 2026-09-23  
**Kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose

## Hướng dẫn liên quan

- [Cách tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET – Hướng dẫn từng bước](/barcode/net/datamatrix-barcode-configuration/)
- [Tạo mã vạch DataMatrix ở chế độ ASCII với Aspose.BarCode cho .NET (C#)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Tạo mã vạch Aztec với mã hoá văn bản bằng Aspose.BarCode cho .NET](/barcode/net/aztec-barcode-encoding/aztec-code-text-encoding/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}