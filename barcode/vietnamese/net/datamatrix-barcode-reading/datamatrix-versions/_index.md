---
title: Tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET
linktitle: Phiên bản DataMatrix
second_title: API Aspose.BarCode .NET
description: Tìm hiểu cách tạo mã vạch DataMatrix trong .NET bằng Aspose.BarCode cho .NET. Thứ nguyên tùy chỉnh, hỗ trợ ECC, v.v.
weight: 12
url: /vi/net/datamatrix-barcode-reading/datamatrix-versions/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET

Nếu bạn đang tìm kiếm một giải pháp đáng tin cậy để tạo mã vạch DataMatrix trong các ứng dụng .NET của mình thì Aspose.BarCode cho .NET là lựa chọn phù hợp. Trong hướng dẫn từng bước này, chúng tôi sẽ hướng dẫn bạn quy trình sử dụng Aspose.BarCode cho .NET để tạo mã vạch DataMatrix. Chúng tôi sẽ chia mỗi ví dụ thành nhiều bước để đảm bảo rằng bạn có thể làm theo một cách dễ dàng.

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào mã, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:
- Một môi trường phát triển có hỗ trợ .NET.
-  Một bản sao của Aspose.BarCode cho .NET mà bạn có thể tải xuống từ[liên kết này](https://releases.aspose.com/barcode/net/).
- Kiến thức cơ bản về C# và .NET framework.

Bây giờ, hãy khám phá các phiên bản DataMatrix và cách tạo chúng bằng Aspose.BarCode cho .NET.

## Nhập không gian tên

Trong bất kỳ dự án C# nào, việc nhập các không gian tên cần thiết là điều cần thiết. Trong trường hợp Aspose.BarCode, bạn sẽ cần bao gồm những thông tin sau:

```csharp
using Aspose.BarCode.Generation;
```

 Không gian tên này cung cấp quyền truy cập vào`BarcodeGenerator` lớp, điều này rất quan trọng để tạo mã vạch.

Bây giờ, hãy chia ví dụ thành nhiều bước.

## Bước 1: Thiết lập đường dẫn thư mục của bạn

Bắt đầu bằng cách xác định đường dẫn thư mục nơi bạn muốn lưu mã vạch DataMatrix đã tạo.

```csharp
string path = "Your Directory Path";
```

 Thay thế`"Your Directory Path"` với đường dẫn thực tế nơi bạn muốn lưu hình ảnh mã vạch.

## Bước 2: Khởi tạo Trình tạo mã vạch

 Tạo một thể hiện của`BarcodeGenerator` lớp và chỉ định loại mã vạch là`DataMatrix`. Bạn cũng có thể cung cấp dữ liệu mà bạn muốn mã hóa trong mã vạch.

```csharp
using (BarcodeGenerator generator = new BarcodeGenerator(EncodeTypes.DataMatrix, "Åspóse.Barcóde©"))
{
    // Mã để tạo mã vạch ở đây
}
```

## Bước 3: Định cấu hình thuộc tính mã vạch

Bạn có thể tùy chỉnh các thuộc tính khác nhau của mã vạch DataMatrix, chẳng hạn như kích thước và loại ECC (Mã sửa lỗi). Dưới đây là ví dụ về đặt kích thước X thành 4 pixel và chọn ECC200:

```csharp
generator.Parameters.Barcode.XDimension.Pixels = 4;
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc200;
```

## Bước 4: Đặt phiên bản DataMatrix và lưu

Bạn có thể chỉ định phiên bản DataMatrix bằng cách đặt số hàng và cột. Sau khi cấu hình phiên bản, hãy lưu hình ảnh mã vạch.

Ví dụ: để tạo mã vạch DataMatrix có 22 hàng và 22 cột bằng ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC200_22x22;
generator.Save($"{path}DataMatrixRows22Columns22Ecc200.png", BarCodeImageFormat.Png);
```

Tương tự, bạn có thể tạo mã vạch với các thông số khác nhau bằng cách thay đổi phiên bản và loại ECC nếu cần.

## Bước 5: Lặp lại cho các phiên bản khác

Bạn có thể lặp lại Bước 4 cho các phiên bản DataMatrix khác. Ví dụ: để tạo mã vạch có 12 hàng và 64 cột bằng ECC200:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.DMRE_12x64;
generator.Save($"{path}DataMatrixRows12Columns64Ecc200.png", BarCodeImageFormat.Png);
```

## Bước 6: Chuyển đổi loại ECC

Nếu bạn muốn thay đổi loại ECC thành Ecc140, bạn có thể làm như vậy bằng cách cập nhật thuộc tính ECC:

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixEcc = DataMatrixEccType.Ecc140;
```

## Bước 7: Tạo mã vạch với các phiên bản và ECC khác nhau

Lặp lại Bước 4 cho các phiên bản DataMatrix và loại ECC khác, lưu từng mã vạch bằng một tên tệp duy nhất.

```csharp
generator.Parameters.Barcode.DataMatrix.DataMatrixVersion = DataMatrixVersion.ECC000_140_29x29;
generator.Save($"{path}DataMatrixRows29Columns29Ecc140.png", BarCodeImageFormat.Png);
```

Bây giờ bạn đã học cách tạo mã vạch DataMatrix bằng Aspose.BarCode cho .NET, bạn có thể dễ dàng tích hợp chức năng này vào các ứng dụng .NET của mình.

## Phần kết luận

Aspose.BarCode for .NET đơn giản hóa quá trình tạo mã vạch DataMatrix trong các ứng dụng .NET của bạn. Với hướng dẫn từng bước này, bạn có thể tạo mã vạch với các phiên bản và loại ECC khác nhau, mang lại sự linh hoạt và tùy chỉnh để đáp ứng nhu cầu cụ thể của bạn.

 Nếu bạn có thắc mắc hoặc cần hỗ trợ, đừng ngần ngại truy cập[Aspose.BarCode cho tài liệu .NET](https://reference.aspose.com/barcode/net/) hoặc kiểm tra[Diễn đàn Aspose.BarCode](https://forum.aspose.com/c/barcode/13) để hỗ trợ.

## Câu hỏi thường gặp

### Câu hỏi 1: ECC trong mã vạch DataMatrix là gì?

Câu trả lời 1: ECC (Mã sửa lỗi) là thành phần quan trọng của mã vạch DataMatrix giúp đảm bảo tính toàn vẹn dữ liệu. Các mức ECC khác nhau cung cấp mức độ sửa lỗi khác nhau.

### Câu hỏi 2: Tôi có thể tạo mã vạch DataMatrix với kích thước tùy chỉnh bằng Aspose.BarCode cho .NET không?

Câu trả lời 2: Có, bạn có thể tùy chỉnh kích thước của mã vạch DataMatrix bằng cách đặt số hàng và cột như được minh họa trong hướng dẫn.

### Câu hỏi 3: Tôi có thể tải xuống Aspose.BarCode cho .NET ở đâu?

 Câu trả lời 3: Bạn có thể tải xuống Aspose.BarCode cho .NET từ[liên kết này](https://releases.aspose.com/barcode/net/).

### Câu hỏi 4: Có bản dùng thử miễn phí dành cho Aspose.BarCode cho .NET không?

 Câu trả lời 4: Có, bạn có thể truy cập bản dùng thử miễn phí Aspose.BarCode cho .NET[đây](https://releases.aspose.com/).

### Câu hỏi 5: Làm cách nào tôi có thể nhận được giấy phép tạm thời cho Aspose.BarCode cho .NET?

 Câu trả lời 5: Để nhận giấy phép tạm thời cho Aspose.BarCode cho .NET, hãy truy cập[liên kết này](https://purchase.aspose.com/temporary-license/).
{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
