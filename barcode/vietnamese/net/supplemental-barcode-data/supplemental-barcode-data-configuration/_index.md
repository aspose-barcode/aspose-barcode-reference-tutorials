---
title: Tạo dữ liệu mã vạch bổ sung với Aspose.BarCode cho .NET
linktitle: Cấu hình dữ liệu mã vạch bổ sung
second_title: API Aspose.BarCode .NET
description: Tạo dữ liệu mã vạch bổ sung với Aspose.BarCode cho .NET. Tùy chỉnh mã vạch EAN-2 và EAN-5 một cách dễ dàng. Hướng dẫn từng bước dành cho nhà phát triển .NET.
weight: 10
url: /vi/net/supplemental-barcode-data/supplemental-barcode-data-configuration/
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Tạo dữ liệu mã vạch bổ sung với Aspose.BarCode cho .NET


Trong thế giới tạo và tùy chỉnh mã vạch, Aspose.BarCode for .NET nổi bật như một công cụ mạnh mẽ và linh hoạt. Cho dù bạn là nhà phát triển có kinh nghiệm hay mới bắt đầu, hướng dẫn từng bước này sẽ hướng dẫn bạn quy trình định cấu hình dữ liệu mã vạch bổ sung bằng Aspose.BarCode cho .NET. 

## Điều kiện tiên quyết

Trước khi chúng ta đi sâu vào thế giới dữ liệu mã vạch bổ sung, hãy đảm bảo bạn có sẵn các điều kiện tiên quyết sau:

- Môi trường phát triển được thiết lập với Visual Studio hoặc bất kỳ công cụ phát triển .NET nào khác.
-  Một bản sao của Aspose.BarCode cho .NET. Nếu chưa có, bạn có thể tải xuống[đây](https://releases.aspose.com/barcode/net/).
- Kiến thức cơ bản về lập trình C#.
- Một thư mục nơi bạn có thể lưu hình ảnh mã vạch được tạo.

## Nhập không gian tên

Trước tiên, hãy đảm bảo rằng bạn có các vùng tên cần thiết có trong mã C# để hoạt động với Aspose.BarCode cho .NET. Nhập các không gian tên được yêu cầu ở đầu tệp C# của bạn:

```csharp
using Aspose.BarCode.Generation;
```

Bây giờ, hãy chia nhỏ quá trình định cấu hình dữ liệu mã vạch bổ sung thành nhiều bước.

## Bước 1: Thiết lập đường dẫn thư mục

 Trong mã C# của bạn, hãy xác định đường dẫn đến thư mục mà bạn muốn lưu hình ảnh mã vạch đã tạo. Thay thế`"Your Directory Path"` với đường dẫn thư mục thực tế của bạn.

```csharp
string path = "Your Directory Path";
```

## Bước 2: Tạo Trình tạo mã vạch

 Tạo một thể hiện của`BarcodeGenerator` bằng cách chỉ định loại mã vạch và dữ liệu bạn muốn mã hóa. Trong ví dụ này, chúng tôi đang sử dụng mã vạch EAN-13 với dữ liệu "1234567890128".

```csharp
BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.EAN13, "1234567890128");
```

## Bước 3: Tùy chỉnh kích thước mã vạch

Đặt kích thước của mã vạch, chẳng hạn như kích thước X (chiều rộng của phần tử nhỏ nhất trong mã vạch) và khoảng trống bổ sung. Trong ví dụ này, chúng tôi đặt kích thước X thành 2 pixel và không gian bổ sung thành 20 pixel.

```csharp
gen.Parameters.Barcode.XDimension.Pixels = 2;
gen.Parameters.Barcode.Supplement.SupplementSpace.Pixels = 20;
```

## Bước 4: Cấu hình bổ sung EAN-2

Để định cấu hình mã vạch bổ sung EAN-2, hãy đặt dữ liệu bổ sung thành giá trị mong muốn. Trong trường hợp này, chúng tôi đặt nó thành "12". 

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12";
```

## Bước 5: Lưu hình ảnh mã vạch

Lưu hình ảnh mã vạch được tạo vào thư mục được chỉ định của bạn với một tên có ý nghĩa. Trong ví dụ này, chúng tôi lưu mã vạch bổ sung EAN-2 dưới dạng "SupplementEAN2.png".

```csharp
gen.Save($"{path}SupplementEAN2.png", BarCodeImageFormat.Png);
```

## Bước 6: Cấu hình bổ sung EAN-5

 Để định cấu hình mã vạch bổ sung EAN-5, chỉ cần thay đổi`SupplementData` đến giá trị mong muốn của bạn. Ở đây, chúng tôi đặt nó thành "12345".

```csharp
gen.Parameters.Barcode.Supplement.SupplementData = "12345";
```

## Bước 7: Lưu hình ảnh mã vạch (EAN-5)

Cuối cùng, lưu hình ảnh mã vạch bổ sung EAN-5 vào thư mục đã chỉ định của bạn. Trong trường hợp này, chúng tôi lưu nó dưới dạng "SupplementEAN5.png".

```csharp
gen.Save($"{path}SupplementEAN5.png", BarCodeImageFormat.Png);
```

Bây giờ, bạn đã định cấu hình và tạo thành công dữ liệu mã vạch bổ sung bằng Aspose.BarCode cho .NET. Bạn có thể sử dụng phương pháp này để tạo ra nhiều loại mã vạch với dữ liệu bổ sung khác nhau.

## Phần kết luận

Aspose.BarCode for .NET là một công cụ mạnh mẽ để tạo và tùy chỉnh mã vạch. Trong hướng dẫn này, chúng tôi đã hướng dẫn từng bước quy trình định cấu hình và tạo dữ liệu mã vạch bổ sung. Với các điều kiện tiên quyết phù hợp và một chút mã hóa, bạn có thể làm việc hiệu quả với dữ liệu mã vạch và đáp ứng các nhu cầu cụ thể của mình.

 Để biết thêm thông tin và cách sử dụng nâng cao, hãy tham khảo[Aspose.BarCode cho tài liệu .NET](https://reference.aspose.com/barcode/net/).

## Các câu hỏi thường gặp

### Tôi có thể sử dụng Aspose.BarCode cho .NET trong dự án .NET Core của mình không?
Có, Aspose.BarCode for .NET tương thích với .NET Core.

### Có bản dùng thử miễn phí dành cho Aspose.BarCode cho .NET không?
 Có, bạn có thể dùng thử miễn phí bằng cách truy cập[liên kết này](https://releases.aspose.com/).

### Tôi có thể lấy giấy phép tạm thời cho Aspose.BarCode cho .NET ở đâu?
 Bạn có thể xin giấy phép tạm thời từ[liên kết này](https://purchase.aspose.com/temporary-license/).

### Aspose.BarCode có hỗ trợ nhiều loại mã vạch không?
Có, nó hỗ trợ nhiều loại mã vạch khác nhau, bao gồm EAN-13, Mã QR, Mã 128, v.v.

### Tôi có thể tùy chỉnh giao diện của mã vạch được tạo không?
Hoàn toàn có thể, bạn có thể tùy chỉnh kích thước, màu sắc và các khía cạnh khác của mã vạch để đáp ứng yêu cầu của bạn.

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}
