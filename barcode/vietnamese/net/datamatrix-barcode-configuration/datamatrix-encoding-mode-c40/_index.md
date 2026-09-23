---
date: 2026-06-09
description: Tìm hiểu cách tạo mã vạch DataMatrix và lưu dưới dạng PNG bằng mã hoá
  C40 với Aspose.BarCode – hướng dẫn đầy đủ cho việc tạo mã vạch trên .NET Core.
keywords:
- how to generate datamatrix
- barcode generation .net core
- datamatrix c40 png
linktitle: Chế độ mã hoá DataMatrix (C40)
schemas:
- author: Aspose
  dateModified: '2026-06-09'
  description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  headline: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  type: TechArticle
- description: Learn how to generate DataMatrix barcodes and save PNG using C40 encoding
    with Aspose.BarCode – full guide for .NET Core barcode generation.
  name: How to Generate DataMatrix PNG with C40 using Aspose.BarCode
  steps:
  - name: Define the Directory Path
    text: Set the folder where the PNG image will be stored. Replace the placeholder
      with an actual path on your machine.
  - name: Set Up Barcode Generation
    text: Create a `BarcodeGenerator` instance, specify `EncodeTypes.DataMatrix`,
      and provide the data you want to encode.
  - name: Customize Barcode
    text: Configure the X‑dimension (pixel width of the modules) and switch the encoding
      mode to C40.
  - name: Save the Barcode Image
    text: Finally, save the generated barcode as a PNG file. This is the concrete
      answer to **how to save png** with Aspose.BarCode. When you run the program,
      you’ll find `DataMatrixEncodeModeC40.png` in the folder you specified, ready
      to be used in reports, labels, or web pages.
  type: HowTo
- questions:
  - answer: C40 is a compact alphanumeric encoding scheme for DataMatrix symbols,
      ideal for text that includes letters, numbers, and a limited set of special
      characters.
    question: What is DataMatrix Encoding Mode (C40)?
  - answer: You can find the documentation [here](https://reference.aspose.com/barcode/net/).
      It provides detailed guidance on all barcode types and encoding options.
    question: Where can I find the Aspose.BarCode for .NET documentation?
  - answer: Yes, the library supports a wide range of .NET versions, from .NET Framework
      4.5+ to .NET 6 and later.
    question: Is Aspose.BarCode for .NET compatible with all .NET versions?
  - answer: Yes, you can explore a free trial of Aspose.BarCode for .NET by visiting
      [this link](https://releases.aspose.com/). It allows you to test the library’s
      features and capabilities.
    question: Can I try Aspose.BarCode for .NET before purchasing?
  - answer: You can find a supportive community and access support for Aspose.BarCode
      for .NET on the [Aspose forum](https://forum.aspose.com/c/barcode/13).
    question: Where can I get support for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Cách tạo DataMatrix PNG với C40 bằng Aspose.BarCode
url: /vi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-c40/
weight: 16
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Chế độ Mã hoá DataMatrix (C40) chính với Aspose.BarCode cho .NET

## Giới thiệu

Trong hướng dẫn này, bạn sẽ học **cách tạo mã vạch datamatrix** và lưu chúng dưới dạng tệp PNG bằng cách sử dụng chế độ mã hoá C40 với Aspose.BarCode cho .NET. Cho dù bạn đang xây dựng một hệ thống quản lý tồn kho, một công cụ tạo nhãn vận chuyển, hoặc bất kỳ giải pháp nào yêu cầu các ký hiệu gọn nhẹ, mật độ cao, việc thành thạo C40 sẽ cho bạn các ký hiệu nhỏ hơn mà không làm giảm khả năng đọc. Chúng tôi sẽ hướng dẫn từng bước — từ việc thiết lập môi trường đến tạo ra tệp PNG cuối cùng — để bạn có thể tích hợp mã ngay lập tức vào dự án của mình.

## Câu trả lời nhanh

- **Câu hỏi “how to generate datamatrix” đề cập đến gì?** Tạo một hình ảnh mã vạch DataMatrix bằng cách lập trình.  
- **Chế độ mã hoá nào được đề cập?** DataMatrix C40, một sơ đồ alphanumeric hiệu quả.  
- **Tôi có cần giấy phép không?** Bản dùng thử miễn phí hoạt động cho việc thử nghiệm; giấy phép thương mại cần thiết cho môi trường sản xuất.  
- **Tôi có thể chạy điều này trên .NET Core không?** Có, Aspose.BarCode hoàn toàn hỗ trợ .NET Core, .NET 5, .NET 6 và các phiên bản sau.  
- **Định dạng tệp nào được tạo ra?** PNG – định dạng ảnh không mất dữ liệu, thân thiện với web.

## Cách tạo DataMatrix với mã hoá C40

Tải dữ liệu của bạn, cấu hình trình tạo, và gọi `Save` – đó là quy trình hoàn chỉnh trong ba bước ngắn gọn. Lớp `BarcodeGenerator` xử lý việc tạo ký hiệu, trong khi enum `BarCodeImageFormat.Png` chỉ cho Aspose.BarCode ghi kết quả dưới dạng tệp PNG. `Save` ghi hình ảnh mã vạch đã tạo vào đường dẫn tệp được chỉ định với định dạng đã chọn. Đoạn văn trả lời trực tiếp này cung cấp cho bạn giải pháp toàn diện trước khi chúng ta đi sâu vào từng dòng mã.

## DataMatrix Encoding Mode (C40) là gì?

`DataMatrixEncodeMode` là một enumeration xác định sơ đồ mã hoá nào mà Aspose.BarCode sẽ sử dụng cho các ký hiệu DataMatrix. Tùy chọn `DataMatrixEncodeMode.C40` chọn mã hoá alphanumeric C40, gói các chữ cái, chữ số và một tập hợp hạn chế các dấu câu vào ít mô-đun hơn, giảm kích thước tổng thể của ký hiệu trong khi vẫn duy trì khả năng đọc cho văn bản tồn kho thường gặp. Sơ đồ hiệu quả này lý tưởng khi bạn cần mã hoá dữ liệu alphanumeric ở dạng gọn nhẹ.

## Tại sao nên sử dụng Aspose.BarCode cho .NET?

Aspose.BarCode cung cấp **hơn 30 tham số có thể cấu hình** cho kích thước, mức độ sửa lỗi và các chế độ mã hoá, và nó hỗ trợ **hơn 50 định dạng ảnh và mã vạch**. Thư viện chạy trên **.NET Framework 4.5+, .NET Core 2.0+, .NET 5/6+**, cung cấp khả năng tạo mã không phụ thuộc, hoạt động trên máy chủ, máy để bàn và thiết bị di động.

## Yêu cầu trước

1. **.NET Development Environment** – Visual Studio, Rider, hoặc bất kỳ IDE nào hỗ trợ C#.  
2. **Aspose.BarCode for .NET** – được cài đặt qua NuGet hoặc trình cài đặt chính thức. Xem [documentation](https://reference.aspose.com/barcode/net/) để biết chi tiết.  
3. **Basic C# knowledge** – bạn nên quen thuộc với namespaces, classes và using statements.  
4. **Write‑access folder** – một thư mục trên máy của bạn nơi PNG sẽ được lưu.

## Nhập các namespace cần thiết

Lớp `BarcodeGenerator` là điểm vào để tạo bất kỳ mã vạch nào. Thêm namespace cần thiết vào đầu tệp nguồn C# của bạn để có thể truy cập API tạo mã:

```csharp
using Aspose.BarCode.Generation;
```

## Hướng dẫn tạo mã vạch từng bước

Dưới đây là một hướng dẫn **bước‑đầu‑bước tạo mã vạch**. Mỗi bước được giải thích bằng ngôn ngữ đơn giản, và các placeholder gốc được giữ nguyên để tiện sao chép.

### Bước 1: Xác định Đường dẫn Thư mục
Đặt thư mục nơi hình ảnh PNG sẽ được lưu. Thay thế placeholder bằng một đường dẫn thực tế trên máy của bạn.

```csharp
string path = "Your Directory Path";
```

### Bước 2: Thiết lập Tạo mã vạch
Tạo một thể hiện `BarcodeGenerator`, chỉ định `EncodeTypes.DataMatrix`, và cung cấp dữ liệu bạn muốn mã hoá.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, "ASPOSE.BARCODE"))
{
    // Additional steps go here
}
```

### Bước 3: Tùy chỉnh Mã vạch
Cấu hình X‑dimension (độ rộng pixel của các mô-đun) và chuyển chế độ mã hoá sang C40.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 6;
gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.C40;
```

### Bước 4: Lưu hình ảnh Mã vạch
Cuối cùng, lưu mã vạch đã tạo dưới dạng tệp PNG. Đây là câu trả lời cụ thể cho **how to save png** với Aspose.BarCode.

```csharp
gen.Save($"{path}DataMatrixEncodeModeC40.png", BarCodeImageFormat.Png);
```

Khi bạn chạy chương trình, bạn sẽ thấy tệp `DataMatrixEncodeModeC40.png` trong thư mục bạn đã chỉ định, sẵn sàng để sử dụng trong báo cáo, nhãn hoặc trang web.

## Các vấn đề thường gặp & Mẹo

- **Invalid Path** – Đảm bảo thư mục tồn tại và bạn có quyền ghi; nếu không, `gen.Save` sẽ ném ra một ngoại lệ.  
- **Incorrect Encoding Mode** – Nếu bạn cần mã hoá các ký tự ngoài bộ C40, chuyển sang `DataMatrixEncodeMode.Auto` hoặc chế độ phù hợp khác.  
- **Image Size** – Điều chỉnh `XDimension.Pixels` để tăng hoặc giảm kích thước tổng thể của mã vạch mà không ảnh hưởng đến khả năng đọc.

## Câu hỏi thường gặp

**Q: DataMatrix Encoding Mode (C40) là gì?**  
A: C40 là một sơ đồ mã hoá alphanumeric gọn nhẹ cho các ký hiệu DataMatrix, lý tưởng cho văn bản bao gồm chữ cái, số và một tập hợp hạn chế các ký tự đặc biệt.

**Q: Tôi có thể tìm tài liệu Aspose.BarCode cho .NET ở đâu?**  
A: Bạn có thể tìm tài liệu [tại đây](https://reference.aspose.com/barcode/net/). Nó cung cấp hướng dẫn chi tiết về tất cả các loại mã vạch và các tùy chọn mã hoá.

**Q: Aspose.BarCode cho .NET có tương thích với mọi phiên bản .NET không?**  
A: Có, thư viện hỗ trợ một loạt các phiên bản .NET, từ .NET Framework 4.5+ đến .NET 6 và các phiên bản sau.

**Q: Tôi có thể dùng thử Aspose.BarCode cho .NET trước khi mua không?**  
A: Có, bạn có thể khám phá bản dùng thử miễn phí của Aspose.BarCode cho .NET bằng cách truy cập [liên kết này](https://releases.aspose.com/). Nó cho phép bạn thử nghiệm các tính năng và khả năng của thư viện.

**Q: Tôi có thể nhận hỗ trợ cho Aspose.BarCode cho .NET ở đâu?**  
A: Bạn có thể tìm cộng đồng hỗ trợ và truy cập hỗ trợ cho Aspose.BarCode cho .NET trên [diễn đàn Aspose](https://forum.aspose.com/c/barcode/13).

## Kết luận

Bằng cách làm theo hướng dẫn **bước‑đầu‑bước tạo mã vạch** này, bạn hiện đã biết chính xác **cách tạo datamatrix** và lưu chúng dưới dạng tệp PNG bằng chế độ mã hoá C40 với Aspose.BarCode cho .NET. Cách tiếp cận này cho phép bạn kiểm soát toàn diện về giao diện, kích thước và cách biểu diễn dữ liệu của mã vạch, giúp dễ dàng nhúng các mã vạch chất lượng cao vào bất kỳ ứng dụng .NET nào.

---

**Cập nhật lần cuối:** 2026-06-09  
**Kiểm thử với:** Aspose.BarCode 24.11 for .NET  
**Tác giả:** Aspose  

{{< blocks/products/products-backtop-button >}}

## Hướng dẫn liên quan

- [Mã hoá DataMatrix bằng Bytes với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/)
- [Chế độ Mã hoá DataMatrix chính bằng ASCII với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)

{{< /blocks/products/pf/tutorial-page-section >}}
{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}