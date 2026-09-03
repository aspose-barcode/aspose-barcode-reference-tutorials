---
date: 2026-05-30
description: Học cách tạo mã vạch DataMatrix ở chế độ Bytes và đọc mã vạch DataMatrix
  bằng Aspose.BarCode cho .NET – hướng dẫn mã vạch chi tiết từng bước.
keywords:
- generate datamatrix barcode
- read datamatrix barcode
- barcode generator settings
- step by step barcode
- create barcode asp.net
linktitle: Chế độ mã hoá DataMatrix (Bytes)
schemas:
- author: Aspose
  dateModified: '2026-05-30'
  description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  headline: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  type: TechArticle
- description: Learn how to generate DataMatrix barcode in Bytes mode and read DataMatrix
    barcode using Aspose.BarCode for .NET – a step‑by‑step barcode guide.
  name: Generate DataMatrix Barcode in Bytes Mode with Aspose.BarCode for .NET
  steps:
  - name: Initialize the BarcodeGenerator
    text: '`BarcodeGenerator` is the main class used to generate barcode images for
      a given symbology and data.'
  - name: Set DataMatrix Encode Mode to Bytes
    text: '`DataMatrixEncodeMode.Bytes` tells the generator to treat the input as
      raw binary bytes rather than text.'
  - name: Set Display Text
    text: '`CodeText` property sets the human‑readable text displayed below the barcode
      symbol.'
  - name: Save the Barcode Image
    text: '`Save` method writes the generated barcode to an image file in the specified
      format.'
  - name: Try to Recognize
    text: '`BarCodeReader` reads barcode images and extracts the encoded data.'
  - name: Iterate and Display Results
    text: Iterate over `reader.ReadBarCodes()` to access each detected barcode and
      its `CodeText`. With these steps, you have successfully **generated a DataMatrix
      barcode** in Bytes mode and verified it using Aspose.BarCode for .NET. The library
      abstracts the low‑level encoding details, so you can focus on b
  type: HowTo
- questions:
  - answer: DataMatrix encoding mode defines how input data is transformed into the
      two‑dimensional pattern; Bytes mode stores raw binary bytes directly.
    question: What is DataMatrix encoding mode?
  - answer: You can obtain a free trial of Aspose.BarCode for .NET from [here](https://releases.aspose.com/).
    question: How can I get a free trial of Aspose.BarCode for .NET?
  - answer: The documentation for Aspose.BarCode for .NET is available [here](https://reference.aspose.com/barcode/net/).
    question: Where can I find documentation for Aspose.BarCode for .NET?
  - answer: Yes, Aspose.BarCode for .NET is suitable for commercial use. You can purchase
      a license from [here](https://purchase.aspose.com/buy).
    question: Is Aspose.BarCode for .NET suitable for commercial use?
  - answer: Yes, you can obtain a temporary license for Aspose.BarCode for .NET from
      [here](https://purchase.aspose.com/temporary-license/).
    question: Can I use a temporary license for Aspose.BarCode for .NET?
  type: FAQPage
second_title: Aspose.BarCode .NET API
title: Tạo mã vạch DataMatrix ở chế độ Bytes với Aspose.BarCode cho .NET
url: /vi/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-bytes/
weight: 15
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo Mã Vạch DataMatrix ở Chế Độ Bytes với Aspose.BarCode cho .NET

Trong hướng dẫn này, bạn sẽ học cách **tạo mã vạch DataMatrix** bằng chế độ mã hoá Bytes và sau đó **đọc lại mã vạch DataMatrix** bằng Aspose.BarCode cho .NET. Dù bạn đang xây dựng hệ thống quản lý kho hay ứng dụng bán vé di động, hướng dẫn mã vạch chi tiết dưới đây sẽ cho bạn thấy cách cấu hình các thiết lập của trình tạo mã vạch, tạo ra hình ảnh chất lượng cao và giải mã lại—tất cả chỉ trong vài dòng C#.

## Câu trả lời nhanh
- **Tôi có thể tạo mã vạch DataMatrix trong .NET không?** Có, sử dụng `BarcodeGenerator` với `EncodeTypes.DataMatrix` và đặt `DataMatrixEncodeMode.Bytes`.
- **Phương thức nào đọc mã vạch?** `BarCodeReader` đọc hình ảnh và trả về văn bản đã mã hoá.
- **Tôi có cần giấy phép cho môi trường sản xuất không?** Cần một giấy phép thương mại; bản dùng thử miễn phí có sẵn.
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7.
- **Tôi có thể mã hoá bao nhiêu byte?** Lên tới 1.555 byte trong một ký hiệu DataMatrix duy nhất.

## Tạo mã vạch DataMatrix là gì?
**Generate DataMatrix barcode** có nghĩa là tạo một mã vạch hai chiều, hình vuông, có thể lưu trữ dữ liệu nhị phân. Aspose.BarCode tạo ra ký hiệu dưới dạng hình ảnh PNG, JPG hoặc SVG mà bất kỳ máy quét nào cũng có thể giải mã. Nó được sử dụng rộng rãi cho việc theo dõi tồn kho, quản lý tài liệu và xác thực vì cung cấp mật độ dữ liệu cao và khả năng sửa lỗi, làm cho nó đáng tin cậy ngay cả trên các bản in chất lượng thấp.

## Tại sao nên sử dụng chế độ mã hoá Bytes?
Chế độ Bytes cho phép bạn nhúng dữ liệu nhị phân thô (tối đa 1.555 byte) mà không cần chuyển đổi thành văn bản, rất phù hợp cho số sê-ri, GUID hoặc dữ liệu đã mã hoá. Aspose.BarCode hỗ trợ **hơn 30 loại mã vạch** và có thể xử lý **tài liệu hàng trăm trang** mà không cần tải toàn bộ tệp vào bộ nhớ, đảm bảo hiệu năng nhanh ngay cả trong các kịch bản tải cao.

## Yêu cầu trước

Trước khi chúng ta bắt đầu quá trình mã hoá, bạn cần chuẩn bị các yêu cầu sau:

1. Aspose.BarCode cho .NET: Để bắt đầu, bạn phải cài đặt thư viện Aspose.BarCode cho .NET. Bạn có thể tải xuống từ [here](https://releases.aspose.com/barcode/net/). Bạn cũng có thể tìm các sản phẩm Aspose khác tại [here](https://releases.aspose.com/).
2. Môi trường phát triển của bạn: Đảm bảo bạn đã thiết lập môi trường phát triển, bao gồm Visual Studio hoặc bất kỳ IDE nào bạn chọn.
3. Kiến thức cơ bản về C#: Hướng dẫn này giả định bạn có hiểu biết cơ bản về lập trình C#.

Để được hỗ trợ, truy cập [Aspose.BarCode Support](https://forum.aspose.com/c/barcode/13).

Với các yêu cầu trên đã sẵn sàng, bạn có thể bắt đầu mã hoá dữ liệu ở định dạng DataMatrix bằng chế độ Bytes.

## Nhập không gian tên

Để sử dụng Aspose.BarCode cho .NET, nhập các không gian tên cần thiết ở đầu tệp C# của bạn:

```csharp
using System;
using System.Text;
using Aspose.BarCode.Generation;
using Aspose.BarCode.BarCodeRecognition;
```

Bây giờ môi trường đã sẵn sàng, chúng ta sẽ đi qua các bước chính xác để **tạo mã vạch DataMatrix** và sau đó đọc lại.

## Cách tạo mã vạch DataMatrix ở chế độ Bytes?

Tải `BarcodeGenerator`, đặt chế độ mã hoá thành Bytes, cấu hình văn bản hiển thị tùy chọn, lưu hình ảnh, và cuối cùng sử dụng `BarCodeReader` để xác minh kết quả—tất cả trong sáu bước ngắn gọn. Cách tiếp cận này đảm bảo một mã vạch đáng tin cậy tuân theo tiêu chuẩn ISO/IEC 16022.

### Bước 1: Khởi tạo BarcodeGenerator

`BarcodeGenerator` là lớp chính được sử dụng để tạo hình ảnh mã vạch cho một loại ký hiệu và dữ liệu nhất định.

```csharp
string path = "Your Directory Path";
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DataMatrix, strBld.ToString()))
{
    // Set the XDimension in Pixels
    gen.Parameters.Barcode.XDimension.Pixels = 4;
```

### Bước 2: Đặt chế độ mã hoá DataMatrix thành Bytes

`DataMatrixEncodeMode.Bytes` cho trình tạo biết rằng đầu vào là các byte nhị phân thô thay vì văn bản.

```csharp
    gen.Parameters.Barcode.DataMatrix.DataMatrixEncodeMode = DataMatrixEncodeMode.Bytes;
```

### Bước 3: Đặt văn bản hiển thị

Thuộc tính `CodeText` đặt văn bản có thể đọc được bởi con người hiển thị dưới ký hiệu mã vạch.

```csharp
    gen.Parameters.Barcode.CodeTextParameters.TwoDDisplayText = "Bytes mode";
```

### Bước 4: Lưu hình ảnh mã vạch

Phương thức `Save` ghi mã vạch đã tạo vào một tệp hình ảnh ở định dạng đã chỉ định.

```csharp
    gen.Save($"{path}DataMatrixEncodeModeBytes.png", BarCodeImageFormat.Png);
```

### Bước 5: Thử nhận dạng

`BarCodeReader` đọc hình ảnh mã vạch và trích xuất dữ liệu đã mã hoá.

```csharp
    using (BarCodeReader read = new BarCodeReader(gen.GenerateBarCodeImage(), DecodeType.DataMatrix))
    {
```

### Bước 6: Lặp và hiển thị kết quả

Lặp qua `reader.ReadBarCodes()` để truy cập mỗi mã vạch được phát hiện và `CodeText` của nó.

```csharp
        foreach (BarCodeResult result in read.ReadBarCodes())
            Console.WriteLine("DataMatrixEncodeModeBytes:" + BitConverter.ToString(result.CodeBytes));
    }
}
```

Với các bước này, bạn đã thành công **tạo một mã vạch DataMatrix** ở chế độ Bytes và xác minh nó bằng Aspose.BarCode cho .NET. Thư viện trừu tượng hoá các chi tiết mã hoá cấp thấp, vì vậy bạn có thể tập trung vào logic nghiệp vụ thay vì toán học mã vạch.

## Các vấn đề thường gặp và giải pháp

- **Dữ liệu đã mã hoá bị cắt ngắn** – Đảm bảo mảng byte không vượt quá 1.555 byte; nếu không, thư viện sẽ tự động chuyển sang kích thước ký hiệu lớn hơn hoặc ném ngoại lệ.
- **Hình ảnh bị mờ** – Lưu hình ảnh ở độ phân giải cao hơn (ví dụ, 300 dpi) bằng cách đặt `generator.Parameters.ImageResolution` trước khi gọi `Save`.
- **Trình đọc trả về null** – Kiểm tra đường dẫn hình ảnh có đúng không và tệp không bị hỏng; cũng xác nhận rằng `BarCodeReader` được khởi tạo với `DecodeType.DataMatrix`.

## Câu hỏi thường gặp

**Q: Chế độ mã hoá DataMatrix là gì?**  
A: Chế độ mã hoá DataMatrix xác định cách dữ liệu đầu vào được chuyển đổi thành mẫu hai chiều; chế độ Bytes lưu trữ các byte nhị phân thô trực tiếp.

**Q: Làm sao tôi có thể nhận bản dùng thử miễn phí của Aspose.BarCode cho .NET?**  
A: Bạn có thể nhận bản dùng thử miễn phí của Aspose.BarCode cho .NET từ [here](https://releases.aspose.com/).

**Q: Tôi có thể tìm tài liệu cho Aspose.BarCode cho .NET ở đâu?**  
A: Tài liệu cho Aspose.BarCode cho .NET có sẵn tại [here](https://reference.aspose.com/barcode/net/).

**Q: Aspose.BarCode cho .NET có phù hợp cho việc sử dụng thương mại không?**  
A: Có, Aspose.BarCode cho .NET phù hợp cho việc sử dụng thương mại. Bạn có thể mua giấy phép từ [here](https://purchase.aspose.com/buy).

**Q: Tôi có thể sử dụng giấy phép tạm thời cho Aspose.BarCode cho .NET không?**  
A: Có, bạn có thể nhận giấy phép tạm thời cho Aspose.BarCode cho .NET từ [here](https://purchase.aspose.com/temporary-license/).

---

**Last Updated:** 2026-05-30  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose

## Hướng dẫn liên quan

- [Thành thạo mã hoá DataMatrix ở chế độ ASCII với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-ascii/)
- [Đọc mã vạch DataMatrix C# – Tạo chế độ DataMatrix (Tự động)](/barcode/net/datamatrix-barcode-configuration/datamatrix-encoding-mode-auto/)
- [Cách tạo mã vạch DataMatrix (ECC 200) với Aspose.BarCode cho .NET](/barcode/net/datamatrix-barcode-configuration/datamatrix-ecc-200-configuration/)


{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}