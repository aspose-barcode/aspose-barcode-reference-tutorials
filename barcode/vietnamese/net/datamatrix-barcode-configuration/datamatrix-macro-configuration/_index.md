---
date: 2026-08-17
description: Tìm hiểu cách tạo DataMatrix barcode với macro characters bằng Aspose.BarCode
  cho .NET và khám phá cách sử dụng DataMatrix trong ứng dụng của bạn.
keywords:
- create datamatrix barcode
- datamatrix barcode error correction
- aspose barcode macro
- .net barcode generation
lastmod: 2026-08-17
linktitle: Cấu hình Macro DataMatrix
og_description: Tìm hiểu cách tạo DataMatrix barcode với macro characters bằng Aspose.BarCode
  cho .NET. Hướng dẫn này cung cấp step‑by‑step code, customization options và verification
  tips cho việc tạo barcode generation đáng tin cậy.
og_image_alt: Guide showing creation of DataMatrix barcode with macro characters in
  .NET using Aspose.BarCode
og_title: Tạo DataMatrix barcode với macro characters bằng Aspose.BarCode
schemas:
- author: Aspose
  dateModified: '2026-08-17'
  description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  headline: How to create DataMatrix barcode with macro characters in .NET
  type: TechArticle
- description: Learn how to create DataMatrix barcode with macro characters using
    Aspose.BarCode for .NET and discover how to use DataMatrix in your applications.
  name: How to create DataMatrix barcode with macro characters in .NET
  steps:
  - name: setting up your project
    text: Create a new Console Application (or any .NET project) in Visual Studio.
      Add a reference to the Aspose.BarCode DLLs that you obtained from the download.
  - name: DataMatrix macro configuration
    text: The core of the tutorial – here we actually **create DataMatrix barcode**
      with a macro character. > **Pro tip:** Replace `"ASPOSE"` with any string you
      need to encode. The macro character (`Macro05`) tells scanners that this barcode
      is part of a macro sequence.
  - name: customize barcode parameters for error correction
    text: 'Before saving, you can tweak additional settings: - **XDimension** – controls
      the size of each module (pixel). - **Margin**, **ErrorCorrection**, and **EncodingMode**
      – all accessible via `gen.Parameters.Barcode.DataMatrix`.'
  - name: save the barcode
    text: The snippet above saves the image as `DataMatrixMacro.png` in the folder
      you specified. PNG is loss‑less, making it ideal for further processing.
  - name: recognize the barcode
    text: '`BarCodeReader` is Aspose.BarCode''s class for decoding barcodes from images.
      Using `BarCodeReader` we immediately read back the generated image to confirm
      that the macro character and data are correct. This round‑trip validation is
      especially handy during automated testing.'
  type: HowTo
- questions:
  - answer: Aspose.BarCode for .NET is a powerful library that allows .NET developers
      to generate and recognize barcodes in various formats, including DataMatrix,
      QR, and more.
    question: What is Aspose.BarCode for .NET?
  - answer: DataMatrix barcodes are compact, highly reliable, and can store large
      amounts of data, making them ideal for manufacturing, logistics, and healthcare.
    question: Why should I use DataMatrix barcodes?
  - answer: You can find the documentation at [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).
    question: Where can I find the documentation for Aspose.BarCode for .NET?
  - answer: Yes, you can download a free trial from [the free trial link](https://releases.aspose.com/).
    question: Is there a free trial available for Aspose.BarCode for .NET?
  - answer: If you have any questions or need support, you can visit the Aspose.BarCode
      for .NET forum at [the support forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
tags:
- datamatrix barcode
- aspose.barcode
- c# barcode generation
- macro barcode
- barcode error correction
title: Cách tạo DataMatrix barcode với macro characters trong .NET
url: /vi/net/datamatrix-barcode-configuration/datamatrix-macro-configuration/
weight: 18
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo mã vạch DataMatrix với ký tự macro trong .NET

## Giới thiệu

Tạo một **DataMatrix barcode** có chứa ký tự macro cho phép bạn đóng gói thông tin tham chiếu bổ sung vào một biểu tượng hình vuông nhỏ. Trong hướng dẫn này, bạn sẽ học cách **tạo DataMatrix barcode** với ký tự macro bằng Aspose.BarCode cho .NET, tùy chỉnh kích thước và mức sửa lỗi, và ngay lập tức xác minh kết quả. Khi hoàn thành, bạn sẽ sẵn sàng nhúng các mã vạch hỗ trợ macro vào nhãn sản phẩm, tài liệu hoặc thiết bị y tế.

## Câu trả lời nhanh
- **Thư viện chính là gì?** Aspose.BarCode for .NET  
- **Tôi có thể tạo DataMatrix barcode với ký tự macro không?** Có – đặt thuộc tính `MacroCharacters`.  
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép Aspose hợp lệ để sử dụng trong môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6+.  
- **Có bản dùng thử miễn phí không?** Chắc chắn – tải xuống từ trang web chính thức của Aspose.  

## Yêu cầu trước

Trước khi bắt đầu cấu hình macro, hãy đảm bảo bạn có những thứ sau:

1. **Visual Studio** – bất kỳ phiên bản gần đây nào cũng hoạt động.  
2. **Aspose.BarCode for .NET** – tải xuống từ [the download link](https://releases.aspose.com/barcode/net/).  
3. **Kiến thức cơ bản về .NET** – quen thuộc với C# và hệ sinh thái .NET.  

## Nhập không gian tên

Chúng ta bắt đầu bằng cách nhập các không gian tên cần thiết cho việc tạo và nhận dạng mã vạch.

```csharp
using System;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

## “generate DataMatrix barcode” với ký tự macro là gì?

`MacroCharacters` cho phép các mã vạch DataMatrix bao gồm các ký hiệu macro tham chiếu dữ liệu bổ sung. Sử dụng các ký tự macro như Macro05 hoặc Macro06, một mã vạch duy nhất có thể chỉ tới một tập dữ liệu lớn hơn hoặc một chuỗi các mã vạch liên quan, điều này có giá trị trong logistics, sản xuất và theo dõi tài liệu nơi cần mã hoá gọn gàng thông tin liên kết.

## Tại sao sử dụng Aspose.BarCode để tạo DataMatrix barcode?

Aspose.BarCode cung cấp cho bạn khả năng kiểm soát chính xác kích thước DataMatrix, mức sửa lỗi và cài đặt macro, hỗ trợ hơn 30 loại mã vạch và xử lý các tệp lên tới 10 MB mà không cần tải toàn bộ hình ảnh vào bộ nhớ. Triển khai .NET đa nền tảng của nó hoạt động trên .NET Framework, .NET Core và .NET 5/6, và bao gồm tính năng nhận dạng tích hợp để bạn có thể xác thực mã vạch ngay lập tức.

## Hướng dẫn từng bước

### Bước 1: thiết lập dự án của bạn

Tạo một ứng dụng Console mới (hoặc bất kỳ dự án .NET nào) trong Visual Studio. Thêm tham chiếu tới các DLL của Aspose.BarCode mà bạn đã tải về.

### Bước 2: Cấu hình macro DataMatrix

Phần cốt lõi của hướng dẫn – ở đây chúng ta thực sự **tạo DataMatrix barcode** với một ký tự macro.

```csharp
string path = "Your Directory Path";
System.Console.WriteLine("DataMatrixMacro:");

using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE"))
{
    gen.Parameters.Barcode.XDimension.Pixels = 4;
    // Set the macro character to 05
    gen.Parameters.Barcode.DataMatrix.MacroCharacters = MacroCharacter.Macro05;
    gen.Save($"{path}DataMatrixMacro.png", BarCodeImageFormat.Png);

    // Try to recognize it
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixMacro:" + result.CodeText);
    }
}
```

> **Mẹo chuyên nghiệp:** Thay thế `"ASPOSE"` bằng bất kỳ chuỗi nào bạn cần mã hoá. Ký tự macro (`Macro05`) thông báo cho máy quét rằng mã vạch này là một phần của chuỗi macro.

### Bước 3: tùy chỉnh tham số mã vạch cho sửa lỗi

Trước khi lưu, bạn có thể điều chỉnh các cài đặt bổ sung:

- **XDimension** – điều khiển kích thước của mỗi mô-đun (pixel).  
- **Margin**, **ErrorCorrection**, và **EncodingMode** – tất cả có thể truy cập qua `gen.Parameters.Barcode.DataMatrix`.

### Bước 4: lưu mã vạch

Đoạn mã trên lưu hình ảnh dưới dạng `DataMatrixMacro.png` trong thư mục bạn chỉ định. PNG không mất dữ liệu, rất phù hợp cho việc xử lý tiếp theo.

### Bước 5: nhận dạng mã vạch

`BarCodeReader` là lớp của Aspose.BarCode dùng để giải mã mã vạch từ hình ảnh. Sử dụng `BarCodeReader`, chúng ta ngay lập tức đọc lại hình ảnh đã tạo để xác nhận ký tự macro và dữ liệu là chính xác. Việc xác thực vòng vòng này đặc biệt hữu ích trong kiểm thử tự động.

## Cách sử dụng DataMatrix trong các kịch bản thực tế?

Bạn có thể áp dụng mã vạch DataMatrix có ký tự macro cho việc dán nhãn sản phẩm, liên kết số sê-ri với cơ sở dữ liệu trung tâm, theo dõi tài liệu bằng cách nhúng tham chiếu tới bản ghi kỹ thuật số, và cho các thẻ thiết bị y tế lưu trữ dữ liệu bệnh nhân hoặc thiết bị trong một biểu tượng nhỏ, có thể quét được. Những trường hợp sử dụng này giảm nhập liệu thủ công và cải thiện khả năng truy xuất.

## Các vấn đề thường gặp & giải pháp

| Vấn đề | Nguyên nhân | Cách khắc phục |
|-------|------------|----------------|
| Mã vạch không được nhận dạng | `XDimension` không đúng hoặc độ phân giải hình ảnh thấp | Tăng `XDimension.Pixels` lên 4‑6 và lưu dưới dạng PNG hoặc TIFF |
| Ký tự macro bị bỏ qua | Trình đọc không hỗ trợ chế độ macro | Sử dụng máy quét/trình đọc hỗ trợ rõ ràng macro DataMatrix (ví dụ, các phiên bản ZXing mới hơn) |
| Không tìm thấy đường dẫn | Biến `path` không hợp lệ | Đảm bảo thư mục tồn tại hoặc sử dụng `Path.Combine` với `Environment.CurrentDirectory` |

## Câu hỏi thường gặp

**Q: Aspose.BarCode for .NET là gì?**  
A: Aspose.BarCode for .NET là một thư viện mạnh mẽ cho phép các nhà phát triển .NET tạo và nhận dạng mã vạch ở nhiều định dạng, bao gồm DataMatrix, QR và các loại khác.

**Q: Tại sao tôi nên sử dụng mã vạch DataMatrix?**  
A: Mã vạch DataMatrix có kích thước nhỏ gọn, độ tin cậy cao và có thể lưu trữ lượng dữ liệu lớn, làm cho chúng lý tưởng cho sản xuất, logistics và y tế.

**Q: Tôi có thể tìm tài liệu cho Aspose.BarCode for .NET ở đâu?**  
A: Bạn có thể tìm tài liệu tại [the Aspose.BarCode for .NET documentation](https://reference.aspose.com/barcode/net/).

**Q: Có bản dùng thử miễn phí cho Aspose.BarCode for .NET không?**  
A: Có, bạn có thể tải bản dùng thử miễn phí từ [the free trial link](https://releases.aspose.com/).

**Q: Tôi có thể nhận hỗ trợ cho Aspose.BarCode for .NET ở đâu?**  
A: Nếu bạn có bất kỳ câu hỏi nào hoặc cần hỗ trợ, bạn có thể truy cập diễn đàn Aspose.BarCode cho .NET tại [the support forum](https://forum.aspose.com/c/barcode/13).

---

**Cập nhật lần cuối:** 2026-08-17  
**Được kiểm tra với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose

## Các hướng dẫn liên quan

- [Tạo mã vạch aspose .net - Cấu hình Văn bản Mã DataMatrix](/barcode/net/datamatrix-barcode-configuration/datamatrix-extended-code-text-configuration/)
- [Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)
- [Cấu hình Structured Append cho DataMatrix với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-reading/datamatrix-structured-append-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}