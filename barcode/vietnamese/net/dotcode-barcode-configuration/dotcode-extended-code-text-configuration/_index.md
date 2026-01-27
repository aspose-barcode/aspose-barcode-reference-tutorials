---
date: 2026-01-27
description: Tìm hiểu cách tạo mã văn bản mở rộng DotCode bằng Aspose.BarCode cho
  .NET – hướng dẫn từng bước để tạo mã vạch DotCode với mã văn bản mở rộng.
linktitle: DotCode Extended Code Text Configuration
second_title: Aspose.BarCode .NET API
title: Cách tạo mã dotcode mở rộng codetext bằng Aspose.BarCode cho .NET
url: /vi/net/dotcode-barcode-configuration/dotcode-extended-code-text-configuration/
weight: 13
---

{{< blocks/products/pf/main-wrap-class >}}
{{< blocks/products/pf/main-container >}}
{{< blocks/products/pf/tutorial-page-section >}}

# Cách tạo dotcode extended codetext với Aspose.BarCode cho .NET

## Giới thiệu

Trong lĩnh vực tạo và quản lý mã vạch, Aspose.BarCode cho .NET nổi bật như một giải pháp đa năng và hiệu quả. Dù bạn cần tạo mã vạch cho sản phẩm, tồn kho, hay bất kỳ ứng dụng nào khác, Aspose.BarCode cho .NET sẽ đáp ứng nhu cầu của bạn. Trong hướng dẫn chi tiết này, chúng ta sẽ **create dotcode extended codetext** và khám phá lý do tại sao khả năng này quan trọng trong môi trường dữ liệu phong phú hiện đại. DotCode là một mã vạch ma trận hai chiều có thể mã hoá cả dữ liệu văn bản và nhị phân, làm cho nó trở thành công cụ giá trị trong nhiều ngành công nghiệp.

## Câu trả lời nhanh
- **“create dotcode extended codetext” có nghĩa là gì?** Nó có nghĩa là tạo một mã vạch DotCode bao gồm FNC1, ECICodetext, văn bản thường và các ký tự phân tách biểu tượng trong một payload mở rộng duy nhất.  
- **Thư viện nào được yêu cầu?** Aspose.BarCode cho .NET.  
- **Tôi có cần giấy phép không?** Giấy phép tạm thời hoạt động cho việc đánh giá; giấy phép đầy đủ cần thiết cho môi trường sản xuất.  
- **Các phiên bản .NET nào được hỗ trợ?** .NET Framework 4.5+, .NET Core 3.1+, .NET 5/6/7+.  
- **Thời gian thực hiện khoảng bao lâu?** Khoảng 10‑15 phút cho một ví dụ cơ bản.

## Cách tạo dotcode extended codetext

Dưới đây là một hướng dẫn ngắn gọn, từng bước, cho thấy cách xây dựng đoạn mã mở rộng và tạo hình ảnh mã vạch.

## Yêu cầu trước

Trước khi chúng ta đi vào hướng dẫn chi tiết, bạn cần chuẩn bị một số điều kiện sau để có thể theo dõi một cách hiệu quả:

1. Aspose.BarCode cho .NET: Đảm bảo bạn đã cài đặt và sẵn sàng thư viện Aspose.BarCode cho .NET. Nếu chưa, bạn có thể tải xuống từ [tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/).

2. Môi trường phát triển: Bạn nên có một môi trường phát triển .NET hoạt động, ưu tiên là Visual Studio, được cài đặt trên hệ thống của mình.

Với các yêu cầu này đã sẵn sàng, chúng ta có thể tiếp tục tạo DotCode Extended Code Text.

## Nhập không gian tên

Đầu tiên, bạn cần nhập các không gian tên cần thiết vào dự án .NET của mình để truy cập các chức năng từ thư viện Aspose.BarCode. Đây là cách thực hiện:

```csharp
using Aspose.BarCode.Generation;
```

Bây giờ chúng ta đã hoàn tất các yêu cầu, hãy chia nhỏ quá trình tạo DotCode Extended Code Text thành các bước cụ thể.

## Bước 1: Xác định Đường dẫn Thư mục

Trong bước này, bạn cần chỉ định đường dẫn thư mục nơi sẽ lưu hình ảnh DotCode Extended Code Text được tạo.

```csharp
string path = "Your Directory Path";
```

Thay thế `"Your Directory Path"` bằng đường dẫn thực tế trên hệ thống của bạn.

## Bước 2: Tạo DotCode Extended Code Text

Để tạo DotCode Extended Code Text, thực hiện các bước phụ sau:

### 2.1 Thêm Định danh Định dạng FNC1

Định danh Định dạng FNC1 được sử dụng để chỉ ra sự bắt đầu của một trường dữ liệu mới. Đây là phần quan trọng của DotCode Extended Code Text.

```csharp
DotCodeExtCodetextBuilder textBuilder = new DotCodeExtCodetextBuilder();
textBuilder.AddFNC1FormatIdentifier();
```

### 2.2 Thêm ECICodetext

ECICodetext cho phép bạn mã hoá các ký tự đặc biệt và văn bản quốc tế. Trong ví dụ này, chúng ta đã mã hoá `"犬Right狗"` bằng mã hoá UTF‑8.

```csharp
textBuilder.AddECICodetext(ECIEncodings.UTF8, "犬Right狗");
```

### 2.3 Thêm Plain Codetext

Bạn cũng có thể thêm văn bản thường vào DotCode Extended Code Text. Ở đây, chúng ta đã thêm `"Plain text"`.

```csharp
textBuilder.AddPlainCodetext("Plain text");
```

### 2.4 Thêm Bộ tách Ký hiệu FNC3

Bộ tách Ký hiệu FNC3 được sử dụng để phân tách các phần khác nhau của đoạn mã.

```csharp
textBuilder.AddFNC3SymbolSeparator();
```

### 2.5 Thêm Khởi tạo Đọc giả FNC3

Bước này thêm thông tin Khởi tạo Đọc giả FNC3.

```csharp
textBuilder.AddFNC3ReaderInitialization();
```

### 2.6 Tạo Codetext

Bây giờ, tạo DotCode Extended Codetext bằng cách gọi phương thức `GetExtendedCodetext` trên đối tượng `textBuilder`.

```csharp
string codetext = textBuilder.GetExtendedCodetext();
```

## Bước 3: Tạo Hình ảnh DotCode

Để tạo DotCode Extended Code Text dưới dạng hình ảnh, thực hiện các bước phụ sau:

#### 4.1 Khởi tạo Trình tạo Mã vạch

Khởi tạo `BarcodeGenerator` với các tham số phù hợp. Trong trường hợp này, chúng ta sử dụng `EncodeTypes.DotCode` và đoạn mã đã tạo.

```csharp
using (BarcodeGenerator gen = new BarcodeGenerator(EncodeTypes.DotCode, codetext))
{
    // Set the X-dimension for the barcode (adjust as needed).
    gen.Parameters.Barcode.XDimension.Pixels = 10;

    // Set the DotCode encoding mode to ExtendedCodetext.
    gen.Parameters.Barcode.DotCode.DotCodeEncodeMode = DotCodeEncodeMode.ExtendedCodetext;

    // Save the generated barcode image.
    gen.Save($"{path}DotCodeExtendedCodetext.png", BarCodeImageFormat.Png);
}
```

Và thế là xong! Bạn đã tạo thành công DotCode Extended Code Text bằng Aspose.BarCode cho .NET.

## Kết luận

Aspose.BarCode cho .NET là một công cụ mạnh mẽ giúp đơn giản hoá việc tạo mã vạch. Trong hướng dẫn này, chúng ta tập trung vào cách **create dotcode extended codetext**, một yếu tố quan trọng trong nhiều ngành công nghiệp, đặc biệt khi cần mã hoá ký tự đa ngôn ngữ và đặc biệt. Bằng cách làm theo các bước ở trên, bạn có thể dễ dàng tạo DotCode Extended Code Text cho nhu cầu cụ thể của mình.

Nếu bạn cần thêm hướng dẫn hoặc có câu hỏi, đừng ngần ngại truy cập [tài liệu Aspose.BarCode cho .NET](https://reference.aspose.com/barcode/net/) hoặc tham gia cộng đồng tại [diễn đàn hỗ trợ Aspose.BarCode](https://forum.aspose.com/c/barcode/13).

## Câu hỏi thường gặp

### Hỏi 1: DotCode được dùng để làm gì?

**A1:** DotCode được dùng để mã hoá cả dữ liệu văn bản và nhị phân và thường được áp dụng trong các ngành như y tế và logistics để theo dõi và mã hoá dữ liệu.

### Hỏi 2: Tôi có thể tùy chỉnh giao diện của mã vạch DotCode không?

**A2:** Có, Aspose.BarCode cho .NET cung cấp các tùy chọn để tùy chỉnh giao diện của mã vạch DotCode, bao gồm kích thước và chế độ mã hoá.

### Hỏi 3: Aspose.BarCode cho .NET có tương thích với các framework .NET khác nhau không?

**A3:** Có, Aspose.BarCode cho .NET tương thích với một loạt các framework .NET, đảm bảo tính linh hoạt và dễ dàng tích hợp.

### Hỏi 4: Làm thế nào để tôi có được giấy phép tạm thời cho Aspose.BarCode cho .NET?

**A4:** Bạn có thể lấy giấy phép tạm thời từ [trang web của Aspose](https://purchase.aspose.com/temporary-license/) để đánh giá và thử nghiệm.

### Hỏi 5: Aspose.BarCode cho .NET có phù hợp cho việc tạo mã vạch cấp doanh nghiệp không?

**A5:** Chắc chắn, Aspose.BarCode cho .NET được thiết kế để đáp ứng nhu cầu tạo mã vạch cả ở quy mô nhỏ và doanh nghiệp, cung cấp khả năng mở rộng và độ tin cậy cao.

## Các Câu hỏi Thường gặp

**Q: Tôi có thể sử dụng mã vạch đã tạo trong ứng dụng di động không?**  
A: Có. Hình ảnh PNG do trình tạo tạo ra có thể được nhúng vào iOS, Android hoặc bất kỳ ứng dụng di động đa nền tảng nào.

**Q: Nếu tôi cần mã hoá dữ liệu nhị phân thay vì văn bản thì sao?**  
A: Sử dụng phương thức `AddECICodetext` với `ECIEncodings` phù hợp (ví dụ: `ECIEncodings.Base64`) để nhúng payload nhị phân.

**Q: Làm sao thay đổi kích thước mã vạch mà không ảnh hưởng tới khả năng đọc?**  
A: Điều chỉnh thuộc tính `XDimension.Pixels`; giá trị cao hơn làm tăng kích thước mô-đun, giá trị thấp hơn làm mã vạch gọn hơn.

**Q: Có cách nào để thêm vùng yên lặng (quiet zone) quanh mã vạch không?**  
A: Có. Đặt `gen.Parameters.Barcode.Margin` để xác định vùng yên lặng mong muốn tính bằng pixel.

**Q: Thư viện có hỗ trợ .NET 8 không?**  
A: Các phiên bản mới nhất của Aspose.BarCode tương thích với .NET 8; chỉ cần tham chiếu tới phiên bản NuGet phù hợp.

---

**Last Updated:** 2026-01-27  
**Tested With:** Aspose.BarCode 24.12 for .NET  
**Author:** Aspose  

{{< /blocks/products/pf/tutorial-page-section >}}

{{< /blocks/products/pf/main-container >}}
{{< /blocks/products/pf/main-wrap-class >}}

{{< blocks/products/products-backtop-button >}}